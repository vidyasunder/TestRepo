# nearmap sales playbook

**Notice:** This playbook has not been fully fact-checked and is a static snapshot; it will not update automatically. Verify details with product, billing, and GTM owners before using in a deal. Last updated: June 18, 2026.

## API Products

### Coverage API

[Documentation](https://developer.nearmap.com/docs/coverage-api)

**Proof of where we capture, and how often**

Docs: Good · Deprecation: Unplanned · US · CA · NZ · AU

### CPQ → Packaging & Pricing → Consumption

| CPQ                           | Packaging & Pricing | Consumption                |
| ----------------------------- | ------------------- | -------------------------- |
| Conga · Location Intelligence | Available           | No billing (metadata only) |
| Conga · Property Intelligence | Available           | No billing (metadata only) |
| Zuora · Legacy pricing        | Available           | No billing (metadata only) |

### Sales pitch

Answers the first question in most deals: do you cover my area, and how current is it. Capture dates and available content become a queryable fact rather than a claim.

### What it does for the customer

Lets a customer (or their app) check exactly what Nearmap has captured at any location: every capture date, what content exists there (imagery, 3D, AI), and at what resolution. Powers the “imagery timeline” experience customers love in demos.

In insurance: confirm coverage at a geocoded address before analyzing a property, check which assets fall within a survey, check ImpactResponse availability, and discover vertical & 3D (REM) coverage — without sharing the full PIF.

### What the customer gets

A list of capture dates and available content for any location, the customer's proof of coverage and currency.

### Who buys it

Not sold and not deprecated. A critical complement to the Tile API, and the API that drives the date dropdown in MapBrowser. Anyone with an API key has access.

<details>

<summary>Options and limitations</summary>

### Options

* Point, polygon, or bounding-box queries
* Filter by content type (`resources=`) and date range (`since`/`until`)
* Returns survey IDs usable across Tile, DSM, and Transactional calls

### Limitations

* Metadata only; returns no imagery or AI content
* Results are filtered to the API key's permissions
* Coordinate/AOI based — geocode addresses before querying

</details>

<details>

<summary>Technical details</summary>

### Typical workflow

{% stepper %}
{% step %}
## Query coverage

Query `/coverage/v2/point` or `/poly` for the customer's location or AOI.
{% endstep %}

{% step %}
## Read surveys

Read the surveys list, every capture date, content type, and survey ID available there.
{% endstep %}

{% step %}
## Retrieve imagery

Pass a `surveyId` to the Tile API (or other content APIs) to retrieve imagery for that exact date.
{% endstep %}
{% endstepper %}

### Sample request

```http
GET https://api.nearmap.com/coverage/v2/point/-95.4538,29.8131 ?resources=tiles:Vert &since=2025-01-01 &apikey=YOUR_API_KEY
```

### Sample response

```json
{
  "surveys": [
    {
      "id": "10001a2b-3c4d-...",
      "captureDate": "2026-03-14",
      "resources": {
        "tiles": [
          {
            "type": "Vert"
          }
        ]
      },
      "pixelSize": 0.055
    }
  ]
}
```

### Live sample

No API key saved. Click “API key” in the header to add one, then run the sample.

Free metadata call, lists recent surveys over a residential Houston location.

```
https://api.nearmap.com/coverage/v2/point/-95.4538,29.8131?resources=tiles:Vert&limit=3&apikey=<saved key>
```

</details>

<details>

<summary>Internal: product and deal status</summary>

### Where it can be sold

|                        | Availability |
| ---------------------- | ------------ |
| Conga (billing)        | Available    |
| Zuora (legacy billing) | Available    |
| New customers          | Available    |
| Existing customers     | Available    |

### Documentation health

Good

### Market availability

| Market             | Availability |
| ------------------ | ------------ |
| United States (US) | Available    |
| Canada (CA)        | Available    |
| New Zealand (NZ)   | Available    |
| Australia (AU)     | Available    |

Coverage metadata is available wherever Nearmap captures: US, CA, NZ, AU.

### Deprecation plan

Unplanned

Draft: TBD

### Migration to Conga

Draft: Carries forward as-is on Conga; bundled with imagery entitlements. Confirm with product/billing owner.

</details>
