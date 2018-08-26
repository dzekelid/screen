---
swagger: "2.0"
x-collection-name: IBM Financial Crimes Insight for Insurance
x-complete: 0
info:
  title: IBM Financial Crimes Insight for Insurance API Screen a specific attribute
    against a dynamic list
  description: This method is used to screen data against a specific list of values,
    resulting in a JSON object containing a list of matching objects
  version: 1.0.0
host: fcihost.ibm.com:9443
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /ibm/fci/platform/fact/screen:
    get:
      summary: Screen a specific attribute against a dynamic list
      description: This method is used to screen data against a specific list of values,
        resulting in a JSON object containing a list of matching objects
      operationId: screen
      x-api-path-slug: ibmfciplatformfactscreen-get
      parameters:
      - in: query
        name: context
        description: Registered context to which to filter / restrict this screen
      - in: query
        name: fieldName
        description: Field of the logical object to be searched
      - in: header
        name: IBM-FCI-Role
        description: Userid / password for user with appropriate role
      - in: header
        name: IBM-FCI-Token
        description: Security token obtained for execution
      - in: query
        name: objectType
        description: Business object name of the objects to search
      - in: query
        name: offset
        description: Used when more then max set of objects meet the criteria; when
          paging is required, this represents the paging offset
      - in: query
        name: style
        description: Searching style, defaults to SMART_MATCH
      - in: query
        name: values
        description: Comma separated list of values to search for in the local database
      responses:
        200:
          description: OK
      tags:
      - Screen
      - Specific
      - Attribute
      - Against
      - Dynamic
      - List
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