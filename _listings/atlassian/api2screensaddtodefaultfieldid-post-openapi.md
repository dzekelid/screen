---
swagger: "2.0"
x-collection-name: Atlassian
x-complete: 0
info:
  title: Jira Cloud API Add field to default screen
  description: Adds field or custom field to the default tab
  termsOfService: http://atlassian.com/terms/
  version: 1.0.0
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /api/2/screens/addToDefault/{fieldId}:
    post:
      summary: Add field to default screen
      description: Adds field or custom field to the default tab
      operationId: com.atlassian.jira.rest.v2.issue.ScreensResource.addFieldToDefaultScreen_post
      x-api-path-slug: api2screensaddtodefaultfieldid-post
      parameters:
      - in: path
        name: fieldId
        description: id of field / custom field
      responses:
        200:
          description: OK
      tags:
      - Field
      - To
      - Default
      - Screen
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