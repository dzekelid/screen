---
swagger: "2.0"
x-collection-name: Dezrez
x-complete: 0
info:
  title: Dezrez Gets the config back for a screen with a guid that was registered
    against a branch
  version: 1.0.0
  description: Gets the config back for a screen with a guid that was registered against
    a branch.
host: api.dezrez.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /api/screenz/config/{screenid}:
    get:
      summary: Gets the config back for a screen with a guid that was registered against
        a branch
      description: Gets the config back for a screen with a guid that was registered
        against a branch.
      operationId: Screenz_ConfigByscreenid
      x-api-path-slug: apiscreenzconfigscreenid-get
      parameters:
      - in: header
        name: Rezi-Api-Version
        description: Specifies which version of the API to call
      - in: path
        name: screenid
      responses:
        200:
          description: OK
      tags:
      - S
      - Config
      - Backa
      - Screen
      - Guid
      - That
      - Was
      - Registered
      - Against
      - Branch
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