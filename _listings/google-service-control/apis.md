---
name: Google Service Control
x-slug: google-service-control
description: Google Service Control is a Google Cloud Platform infrastructure service.
  It provides control plane functionality to managed services, such as logging, monitoring,
  and status checks. It is widely used by Google APIs and Google Cloud Endpoints.
  This page provides an overview of what it does and how it works.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Screen
  Shot 2017-03-17 at 3.49.30 PM.png
x-kinRank: "9"
x-alexaRank: "0"
tags: Google Service Control
created: "2018-06-20"
modified: "2018-06-20"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-service-control/master/_listings/google-service-control/apis.md
specificationVersion: "0.14"
apis:
- name: Google Service Control API Allocate Quota
  x-api-slug: google-service-control-api
  description: |-
    Attempts to allocate quota for the specified consumer. It should be called
    before the operation is executed.

    This method requires the `servicemanagement.services.quota`
    permission on the specified service. For more information, see
    [Google Cloud IAM](https://cloud.google.com/iam).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Screen
    Shot 2017-03-17 at 3.49.30 PM.png
  humanURL: https://cloud.google.com/service-control/overview
  baseURL: ://servicecontrol.googleapis.com////v1/services/{serviceName}:allocateQuota
  tags: Service Quota
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-service-control/master/_listings/google-service-control/v1servicesservicenameallocatequota-post-openapi.md
- name: Google Service Control API Check Operation
  x-api-slug: google-service-control-api
  description: |-
    Checks an operation with Google Service Control to decide whether
    the given operation should proceed. It should be called before the
    operation is executed.

    If feasible, the client should cache the check results and reuse them for
    60 seconds. In case of server errors, the client can rely on the cached
    results for longer time.

    NOTE: the `CheckRequest` has the size limit of 64KB.

    This method requires the `servicemanagement.services.check` permission
    on the specified service. For more information, see
    [Google Cloud IAM](https://cloud.google.com/iam).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Screen
    Shot 2017-03-17 at 3.49.30 PM.png
  humanURL: https://cloud.google.com/service-control/overview
  baseURL: ://servicecontrol.googleapis.com////v1/services/{serviceName}:check
  tags: Service Operation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-service-control/master/_listings/google-service-control/v1servicesservicenamecheck-post-openapi.md
- name: Google Service Control API End Reconciliation
  x-api-slug: google-service-control-api
  description: |-
    Signals the quota controller that service ends the ongoing usage
    reconciliation.

    This method requires the `servicemanagement.services.quota`
    permission on the specified service. For more information, see
    [Google Cloud IAM](https://cloud.google.com/iam).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Screen
    Shot 2017-03-17 at 3.49.30 PM.png
  humanURL: https://cloud.google.com/service-control/overview
  baseURL: ://servicecontrol.googleapis.com////v1/services/{serviceName}:endReconciliation
  tags: Service Reconcilliation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-service-control/master/_listings/google-service-control/v1servicesservicenameendreconciliation-post-openapi.md
- name: Google Service Control API Release Quota
  x-api-slug: google-service-control-api
  description: |-
    Releases previously allocated quota done through AllocateQuota method.

    This method requires the `servicemanagement.services.quota`
    permission on the specified service. For more information, see
    [Google Cloud IAM](https://cloud.google.com/iam).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Screen
    Shot 2017-03-17 at 3.49.30 PM.png
  humanURL: https://cloud.google.com/service-control/overview
  baseURL: ://servicecontrol.googleapis.com////v1/services/{serviceName}:releaseQuota
  tags: Service Quota
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-service-control/master/_listings/google-service-control/v1servicesservicenamereleasequota-post-openapi.md
- name: Google Service Control API Report
  x-api-slug: google-service-control-api
  description: |-
    Reports operation results to Google Service Control, such as logs and
    metrics. It should be called after an operation is completed.

    If feasible, the client should aggregate reporting data for up to 5
    seconds to reduce API traffic. Limiting aggregation to 5 seconds is to
    reduce data loss during client crashes. Clients should carefully choose
    the aggregation time window to avoid data loss risk more than 0.01%
    for business and compliance reasons.

    NOTE: the `ReportRequest` has the size limit of 1MB.

    This method requires the `servicemanagement.services.report` permission
    on the specified service. For more information, see
    [Google Cloud IAM](https://cloud.google.com/iam).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Screen
    Shot 2017-03-17 at 3.49.30 PM.png
  humanURL: https://cloud.google.com/service-control/overview
  baseURL: ://servicecontrol.googleapis.com////v1/services/{serviceName}:report
  tags: Report
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-service-control/master/_listings/google-service-control/v1servicesservicenamereport-post-openapi.md
- name: Google Service Control API Start Reconciliation
  x-api-slug: google-service-control-api
  description: |-
    Unlike rate quota, allocation quota does not get refilled periodically.
    So, it is possible that the quota usage as seen by the service differs from
    what the One Platform considers the usage is. This is expected to happen
    only rarely, but over time this can accumulate. Services can invoke
    StartReconciliation and EndReconciliation to correct this usage drift, as
    described below:
    1. Service sends StartReconciliation with a timestamp in future for each
       metric that needs to be reconciled. The timestamp being in future allows
       to account for in-flight AllocateQuota and ReleaseQuota requests for the
       same metric.
    2. One Platform records this timestamp and starts tracking subsequent
       AllocateQuota and ReleaseQuota requests until EndReconciliation is
       called.
    3. At or after the time specified in the StartReconciliation, service
       sends EndReconciliation with the usage that needs to be reconciled to.
    4. One Platform adjusts its own record of usage for that metric to the
       value specified in EndReconciliation by taking in to account any
       allocation or release between StartReconciliation and EndReconciliation.

    Signals the quota controller that the service wants to perform a usage
    reconciliation as specified in the request.

    This method requires the `servicemanagement.services.quota`
    permission on the specified service. For more information, see
    [Google Cloud IAM](https://cloud.google.com/iam).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Screen
    Shot 2017-03-17 at 3.49.30 PM.png
  humanURL: https://cloud.google.com/service-control/overview
  baseURL: ://servicecontrol.googleapis.com////v1/services/{serviceName}:startReconciliation
  tags: Service Reconcilliation
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-service-control/master/_listings/google-service-control/v1servicesservicenamestartreconciliation-post-openapi.md
- name: Google Service Control API
  x-api-slug: google-service-control-api
  description: Google Service Control is a Google Cloud Platform infrastructure service.
    It provides control plane functionality to managed services, such as logging,
    monitoring, and status checks. It is widely used by Google APIs and Google Cloud
    Endpoints. This page provides an overview of what it does and how it works.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/Screen
    Shot 2017-03-17 at 3.49.30 PM.png
  humanURL: https://cloud.google.com/service-control/overview
  baseURL: ://servicecontrol.googleapis.com//
  tags: Google Service Control
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/google-service-control/master/_listings/google-service-control/openapi.md
x-common:
- type: x-change-log
  url: https://cloud.google.com/service-control/release-notes
- type: x-code
  url: https://cloud.google.com/service-control/libraries
- type: x-documentation
  url: https://cloud.google.com/service-control/docs/
- type: x-guides
  url: https://cloud.google.com/service-control/how-to
- type: x-pricing
  url: https://cloud.google.com/service-control/pricing-and-quotas
- type: x-support
  url: https://cloud.google.com/service-control/support
- type: x-website
  url: https://cloud.google.com/service-control/overview
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---