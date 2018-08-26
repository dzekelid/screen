---
swagger: "2.0"
x-collection-name: Atlassian
x-complete: 0
info:
  title: Jira Cloud API Move screen tab field
  description: Moves field on the given tab
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
  /api/2/screens/{screenId}/availableFields:
    get:
      summary: Get available screen fields
      description: Gets available fields for screen. i.e ones that haven't already
        been added.
      operationId: com.atlassian.jira.rest.v2.issue.ScreensResource.getAvailableScreenFields_get
      x-api-path-slug: api2screensscreenidavailablefields-get
      parameters:
      - in: path
        name: screenId
        description: id of screen
      responses:
        200:
          description: OK
      tags:
      - Available
      - Screen
      - Fields
  /api/2/screens/{screenId}/tabs:
    get:
      summary: Get all screen tabs
      description: Returns a list of all tabs for the given screen
      operationId: com.atlassian.jira.rest.v2.issue.ScreensResource.getAllScreenTabs_get
      x-api-path-slug: api2screensscreenidtabs-get
      parameters:
      - in: query
        name: projectKey
        description: the key of the project; this parameter is optional
      - in: path
        name: screenId
        description: id of screen
      responses:
        200:
          description: OK
      tags:
      - Screen
      - Tabs
    post:
      summary: Add screen tab
      description: Creates tab for given screen
      operationId: com.atlassian.jira.rest.v2.issue.ScreensResource.addScreenTab_post
      x-api-path-slug: api2screensscreenidtabs-post
      parameters:
      - in: path
        name: screenId
        description: id of screen
      responses:
        200:
          description: OK
      tags:
      - Screen
      - Tab
  /api/2/screens/{screenId}/tabs/{tabId}:
    put:
      summary: Rename screen tab
      description: Renames tab on given screen
      operationId: com.atlassian.jira.rest.v2.issue.ScreensResource.renameScreenTab_put
      x-api-path-slug: api2screensscreenidtabstabid-put
      parameters:
      - in: path
        name: screenId
        description: id of screen
      - in: path
        name: tabId
      responses:
        200:
          description: OK
      tags:
      - Rename
      - Screen
      - Tab
    delete:
      summary: Delete screen tab
      description: Deletes tab to give screen
      operationId: com.atlassian.jira.rest.v2.issue.ScreensResource.deleteScreenTab_delete
      x-api-path-slug: api2screensscreenidtabstabid-delete
      parameters:
      - in: path
        name: screenId
        description: id of screen
      - in: path
        name: tabId
        description: id of tab
      responses:
        200:
          description: OK
      tags:
      - Screen
      - Tab
  /api/2/screens/{screenId}/tabs/{tabId}/fields:
    get:
      summary: Get all screen tab fields
      description: Gets all fields for a given tab
      operationId: com.atlassian.jira.rest.v2.issue.ScreensResource.getAllScreenTabFields_get
      x-api-path-slug: api2screensscreenidtabstabidfields-get
      parameters:
      - in: query
        name: projectKey
        description: the key of the project; this parameter is optional
      - in: path
        name: screenId
        description: id of screen
      - in: path
        name: tabId
        description: id of tab
      responses:
        200:
          description: OK
      tags:
      - Screen
      - Tab
      - Fields
    post:
      summary: Add screen tab field
      description: Adds field to the given tab.
      operationId: com.atlassian.jira.rest.v2.issue.ScreensResource.addScreenTabField_post
      x-api-path-slug: api2screensscreenidtabstabidfields-post
      parameters:
      - in: path
        name: screenId
        description: id of screen
      - in: path
        name: tabId
        description: id of tab
      responses:
        200:
          description: OK
      tags:
      - Screen
      - Tab
      - Field
  /api/2/screens/{screenId}/tabs/{tabId}/fields/{id}:
    delete:
      summary: Remove screen tab field
      description: Removes field from given tab
      operationId: com.atlassian.jira.rest.v2.issue.ScreensResource.removeScreenTabField_delete
      x-api-path-slug: api2screensscreenidtabstabidfieldsid-delete
      parameters:
      - in: path
        name: id
      - in: path
        name: screenId
        description: id of screen
      - in: path
        name: tabId
        description: id of tab
      responses:
        200:
          description: OK
      tags:
      - Remove
      - Screen
      - Tab
      - Field
  /api/2/screens/{screenId}/tabs/{tabId}/fields/{id}/move:
    post:
      summary: Move screen tab field
      description: Moves field on the given tab
      operationId: com.atlassian.jira.rest.v2.issue.ScreensResource.moveScreenTabField_post
      x-api-path-slug: api2screensscreenidtabstabidfieldsidmove-post
      parameters:
      - in: path
        name: id
      - in: path
        name: screenId
        description: id of screen
      - in: path
        name: tabId
        description: id of tab
      responses:
        200:
          description: OK
      tags:
      - Move
      - Screen
      - Tab
      - Field
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