---
swagger: "2.0"
x-collection-name: Datadog
x-complete: 1
info:
  title: DataDog Merged API
  version: 1.0.0
basePath: api/v1/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /screen:
    post:
      summary: Add Screen
      description: POST screen
      operationId: postScreen
      x-api-path-slug: screen-post
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
    get:
      summary: Get Screen
      description: Fetch all of your screenboards' definitions.
      operationId: getScreen
      x-api-path-slug: screen-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
  /screen/:board_id:
    put:
      summary: Put Screen Board
      description: PUT screen board
      operationId: putScreenBoard
      x-api-path-slug: screenboard-id-put
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
      - Board
    delete:
      summary: Delete Screen Board
      description: Delete an existing screenboard.
      operationId: deleteScreenBoard
      x-api-path-slug: screenboard-id-delete
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
      - Board
    get:
      summary: Get Screen Board
      description: Fetch an existing screenboard's definition.
      operationId: getScreenBoard
      x-api-path-slug: screenboard-id-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
      - Board
  /screen/share/:board_id:
    get:
      summary: Get Screen Share Board
      description: Share an existing screenboard's with a public URL.
      operationId: getScreenShareBoard
      x-api-path-slug: screenshareboard-id-get
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
      - Share
      - Board
    delete:
      summary: Delete Screen Share Board
      description: Revoke a currently shared screenboard's.
      operationId: deleteScreenShareBoard
      x-api-path-slug: screenshareboard-id-delete
      responses:
        200:
          description: OK
      tags:
      - Monitoring
      - Screen
      - Share
      - Board
---