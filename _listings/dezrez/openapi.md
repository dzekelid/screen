---
swagger: "2.0"
x-collection-name: Dezrez
x-complete: 1
info:
  title: Dezrez.Rezi.Client.Api
  version: 1.0.0
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
  /api/screenz/registered:
    get:
      summary: Gets the config back for a screen with a guid that was registered against
        a branch
      description: Gets the config back for a screen with a guid that was registered
        against a branch.
      operationId: Screenz_Registered
      x-api-path-slug: apiscreenzregistered-get
      parameters:
      - in: header
        name: Rezi-Api-Version
        description: Specifies which version of the API to call
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
  /api/twitter/directmessage:
    post:
      summary: Sends a direct message to a screen name
      description: Sends a direct message to a screen name.
      operationId: Twitter_TwitterDirectMessageBydirectMessage
      x-api-path-slug: apitwitterdirectmessage-post
      parameters:
      - in: body
        name: directMessage
        schema:
          $ref: '#/definitions/holder'
      - in: header
        name: Rezi-Api-Version
        description: Specifies which version of the API to call
      responses:
        200:
          description: OK
      tags:
      - Sends
      - Direct
      - Message
      - To
      - Screen
      - Name
  /api/twitter/tweet:
    post:
      summary: Sends a direct message to a screen name
      description: Sends a direct message to a screen name.
      operationId: Twitter_TwitterDirectMessageBytweet
      x-api-path-slug: apitwittertweet-post
      parameters:
      - in: header
        name: Rezi-Api-Version
        description: Specifies which version of the API to call
      - in: body
        name: tweet
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Sends
      - Direct
      - Message
      - To
      - Screen
      - Name
---