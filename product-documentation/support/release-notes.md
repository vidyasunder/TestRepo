---
description: A GitBook Updates model for product news.
icon: clock-rotate-left
layout:
  width: wide
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
---

# Release notes model

This page demonstrates how Nearmap product news and release notes could move from article lists into GitBook's Updates block.

{% updates format="full" %}
{% update date="2026-07-07" tags="mapbrowser,docs" %}
## MapBrowser documentation refresh

Restructured quick starts, measurement guidance, collaboration topics, and export notes into a single MapBrowser path.
{% endupdate %}

{% update date="2026-07-07" tags="api,ai" %}
## AI Feature API reference generated from OpenAPI

Added a generated API reference for AI features, metadata, and rollups so endpoint pages stay aligned with the spec.
{% endupdate %}
{% endupdates %}
