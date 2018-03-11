---
swagger: "2.0"
info:
  title: Google Service Control
  description: Google Service Control provides control plane functionality to managed
    services, such as logging, monitoring, and status checks.
  contact:
    name: Google
    url: https://google.com
  version: v1
host: servicecontrol.googleapis.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /v1/services/{serviceName}:report:
    post:
      summary: Report
      description: |-
        Reports operation results to Google Service Control, such as logs and
        metrics
      operationId: servicecontrol.services.report
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: serviceName
        description: The service name as specified in its service configuration
      responses:
        200:
          description: OK
      tags:
      - report
definitions:
  AllocateQuotaRequest:
    properties:
      allocationMode:
        description: This is a default description.
        type: post
      serviceConfigId:
        description: This is a default description.
        type: post
  AllocateQuotaResponse:
    properties:
      allocateErrors:
        description: This is a default description.
        type: post
      operationId:
        description: This is a default description.
        type: post
      quotaMetrics:
        description: This is a default description.
        type: post
      serviceConfigId:
        description: This is a default description.
        type: post
  AuditLog:
    properties:
      authorizationInfo:
        description: This is a default description.
        type: post
      methodName:
        description: This is a default description.
        type: post
      numResponseItems:
        description: This is a default description.
        type: post
      request:
        description: This is a default description.
        type: post
      resourceName:
        description: This is a default description.
        type: post
      response:
        description: This is a default description.
        type: post
      serviceData:
        description: This is a default description.
        type: post
      serviceName:
        description: This is a default description.
        type: post
  AuthenticationInfo:
    properties:
      authoritySelector:
        description: This is a default description.
        type: post
      principalEmail:
        description: This is a default description.
        type: post
  AuthorizationInfo:
    properties:
      granted:
        description: This is a default description.
        type: post
      permission:
        description: This is a default description.
        type: post
      resource:
        description: This is a default description.
        type: post
  CheckError:
    properties:
      code:
        description: This is a default description.
        type: post
      detail:
        description: This is a default description.
        type: post
  CheckInfo:
    properties:
      unusedArguments:
        description: This is a default description.
        type: post
  CheckRequest:
    properties:
      requestProjectSettings:
        description: This is a default description.
        type: post
      serviceConfigId:
        description: This is a default description.
        type: post
      skipActivationCheck:
        description: This is a default description.
        type: post
  CheckResponse:
    properties:
      checkErrors:
        description: This is a default description.
        type: post
      operationId:
        description: This is a default description.
        type: post
      serviceConfigId:
        description: This is a default description.
        type: post
  Distribution:
    properties:
      bucketCounts:
        description: This is a default description.
        type: post
      count:
        description: This is a default description.
        type: post
      maximum:
        description: This is a default description.
        type: post
      mean:
        description: This is a default description.
        type: post
      minimum:
        description: This is a default description.
        type: post
      sumOfSquaredDeviation:
        description: This is a default description.
        type: post
  EndReconciliationRequest:
    properties:
      serviceConfigId:
        description: This is a default description.
        type: post
  EndReconciliationResponse:
    properties:
      operationId:
        description: This is a default description.
        type: post
      quotaMetrics:
        description: This is a default description.
        type: post
      reconciliationErrors:
        description: This is a default description.
        type: post
      serviceConfigId:
        description: This is a default description.
        type: post
  ExplicitBuckets:
    properties:
      bounds:
        description: This is a default description.
        type: post
  ExponentialBuckets:
    properties:
      growthFactor:
        description: This is a default description.
        type: post
      numFiniteBuckets:
        description: This is a default description.
        type: post
      scale:
        description: This is a default description.
        type: post
  LinearBuckets:
    properties:
      numFiniteBuckets:
        description: This is a default description.
        type: post
      offset:
        description: This is a default description.
        type: post
      width:
        description: This is a default description.
        type: post
  LogEntry:
    properties:
      insertId:
        description: This is a default description.
        type: post
      labels:
        description: This is a default description.
        type: post
      name:
        description: This is a default description.
        type: post
      protoPayload:
        description: This is a default description.
        type: post
      severity:
        description: This is a default description.
        type: post
      structPayload:
        description: This is a default description.
        type: post
      textPayload:
        description: This is a default description.
        type: post
      timestamp:
        description: This is a default description.
        type: post
  MetricValue:
    properties:
      boolValue:
        description: This is a default description.
        type: post
      doubleValue:
        description: This is a default description.
        type: post
      endTime:
        description: This is a default description.
        type: post
      int64Value:
        description: This is a default description.
        type: post
      labels:
        description: This is a default description.
        type: post
      startTime:
        description: This is a default description.
        type: post
      stringValue:
        description: This is a default description.
        type: post
  MetricValueSet:
    properties:
      metricName:
        description: This is a default description.
        type: post
      metricValues:
        description: This is a default description.
        type: post
  Money:
    properties:
      currencyCode:
        description: This is a default description.
        type: post
      nanos:
        description: This is a default description.
        type: post
      units:
        description: This is a default description.
        type: post
  Operation:
    properties:
      consumerId:
        description: This is a default description.
        type: post
      endTime:
        description: This is a default description.
        type: post
      importance:
        description: This is a default description.
        type: post
      labels:
        description: This is a default description.
        type: post
      logEntries:
        description: This is a default description.
        type: post
      metricValueSets:
        description: This is a default description.
        type: post
      operationId:
        description: This is a default description.
        type: post
      operationName:
        description: This is a default description.
        type: post
      resourceContainer:
        description: This is a default description.
        type: post
      startTime:
        description: This is a default description.
        type: post
  QuotaError:
    properties:
      code:
        description: This is a default description.
        type: post
      description:
        description: This is a default description.
        type: post
      subject:
        description: This is a default description.
        type: post
  QuotaInfo:
    properties:
      limitExceeded:
        description: This is a default description.
        type: post
      quotaConsumed:
        description: This is a default description.
        type: post
      quotaMetrics:
        description: This is a default description.
        type: post
  QuotaOperation:
    properties:
      consumerId:
        description: This is a default description.
        type: post
      labels:
        description: This is a default description.
        type: post
      methodName:
        description: This is a default description.
        type: post
      operationId:
        description: This is a default description.
        type: post
      quotaMetrics:
        description: This is a default description.
        type: post
      quotaMode:
        description: This is a default description.
        type: post
  QuotaProperties:
    properties:
      limitByIds:
        description: This is a default description.
        type: post
      quotaMode:
        description: This is a default description.
        type: post
  ReleaseQuotaRequest:
    properties:
      serviceConfigId:
        description: This is a default description.
        type: post
  ReleaseQuotaResponse:
    properties:
      operationId:
        description: This is a default description.
        type: post
      quotaMetrics:
        description: This is a default description.
        type: post
      releaseErrors:
        description: This is a default description.
        type: post
      serviceConfigId:
        description: This is a default description.
        type: post
  ReportError:
    properties:
      operationId:
        description: This is a default description.
        type: post
  ReportInfo:
    properties:
      operationId:
        description: This is a default description.
        type: post
  ReportRequest:
    properties:
      operations:
        description: This is a default description.
        type: post
      serviceConfigId:
        description: This is a default description.
        type: post
  ReportResponse:
    properties:
      reportErrors:
        description: This is a default description.
        type: post
      reportInfos:
        description: This is a default description.
        type: post
      serviceConfigId:
        description: This is a default description.
        type: post
  RequestMetadata:
    properties:
      callerIp:
        description: This is a default description.
        type: post
      callerSuppliedUserAgent:
        description: This is a default description.
        type: post
  StartReconciliationRequest:
    properties:
      serviceConfigId:
        description: This is a default description.
        type: post
  StartReconciliationResponse:
    properties:
      operationId:
        description: This is a default description.
        type: post
      quotaMetrics:
        description: This is a default description.
        type: post
      reconciliationErrors:
        description: This is a default description.
        type: post
      serviceConfigId:
        description: This is a default description.
        type: post
  Status:
    properties:
      code:
        description: This is a default description.
        type: post
      details:
        description: This is a default description.
        type: post
      message:
        description: This is a default description.
        type: post
x-collection-name: Google Service Control
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---