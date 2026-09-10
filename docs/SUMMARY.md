# Table of contents

* [Getting Started with Nearmap APIs](README.md)
* ```yaml
  type: builtin:openapi
  props:
    models: true
    downloadLink: true
    grouping: by-tag
  dependencies:
    spec:
      ref:
        kind: openapi
        spec: poc-tiles-api-v3
  ```
* [Internal - Test Page 1](internal-test-page-1.md)
* ```yaml
  type: builtin:openapi
  props:
    models: true
    downloadLink: true
    grouping: by-operation
  dependencies:
    spec:
      ref:
        kind: openapi
        spec: ai-feature-api
  ```
* ```yaml
  type: builtin:openapi
  props:
    models: true
    downloadLink: true
    grouping: by-operation
  dependencies:
    spec:
      ref:
        kind: openapi
        spec: transactionalcontent
  ```
* [nearmap sales playbook](nearmap-sales-playbook.md)
