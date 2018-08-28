swagger: "2.0"
x-collection-name: Xibo
x-complete: 1
info:
  title: Xibo API
  description: xibo-cms-api
  termsOfService: http://xibo.org.uk/legal
  version: 1.0.0
basePath: /api
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /display/requestscreenshot/{displayId}:
    put:
      summary: Request Screen Shot
      description: Notify the display that the CMS would like a screen shot to be
        sent.
      operationId: displayRequestScreenshot
      x-api-path-slug: displayrequestscreenshotdisplayid-put
      parameters:
      - in: path
        name: displayId
        description: The Display ID
      responses:
        200:
          description: OK
      tags:
      - Request
      - Screen
      - Shot