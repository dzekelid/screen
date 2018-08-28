---
swagger: "2.0"
x-collection-name: LogMeIn
x-complete: 0
info:
  title: GoToAssist Remote Support Start Screen Sharing Session
  description: "This method creates a new screen sharing support session (either attended
    or unattended) by generating a URL that automatically launches technicians into
    a new session when clicked. If a machineUuid request parameter is specified, an
    unattended support session will be created; if it is not specified, then an attended
    session will be created. See \"Request Parameters\" for more information. Note:
    The locale of the session start dialog will be based upon the technician\u2019s
    locale setting within GoToAssist.\n\nNote: This method was formerly named \"Create
    Attended Session,\" but has been renamed to address the fact that it now includes
    unattended support sessions as well.\n\n  Request Parameters                    \n
    \                     \n    field        data type      description    \n    sessionStatusCallbackUrl*
    \       string      The URL that will receive a POST when the session status changes.
    A POST will also be made to the sessionStatusCallbackUrl when a customer joins
    the session and when the session ends (whether or not a customer joined). The
    contents of the POST will be similar as the GET /v1/sessions/ API. Note: The ID
    of the session is not known until the session is actually started on the endpoint.
    If the URL is not specified or the session is never started (e.g., if the customer
    cancels the installation of the GoToAssist Customer desktop application), then
    the callback will not be made.    \n    sessionType        string      The type
    of session to create (only \"SCREEN_SHARING\" can be used at this time).    \n
    \   partnerObject*        string      The ID of object in the partner system that
    this session will be associated with.    \n    partnerObjectUrl*        string
    \     The URL that may be used in the GoToAssist Expert desktop application if
    the technician wants to view the partner object. Note: The URL can be used in
    a popup window or iframe that is 600 pixels wide and 500 pixels wide. For example,
    a popup window could be created with HTML code as follows: \"Start Remote Support
    \"    \n    customerName*        string      The name of the customer that the
    session is being started for.    \n    customerEmail*        string      The email
    address of the customer that the session is being started for (if available)    \n
    \   machineUuid*        string      The machineUuid is only necessary for unattended
    support sessions. If the machineUuid is present when a screen sharing session
    is started, then the endpoint will connect to the specified unattended machine
    and an unattended support session will be started. If no machineUuid is specified,
    then an attended support session will be created. A list of machineUuid parameters
    associated with the user and company will be available through a /machines API
    in future.    \n                      \n* Optional parameters\n\nStatus Codes
    \             \n              \n    Staus Code      description    \n    200 OK
    \     The response contains the URL to start the session    \n    400 Bad Request
    \     An error occurred due to missing required parameters or portal not being
    created    \n    401 Unauthorized      An authentication parameter was passed,
    but either it was invalid or the technician is not entitled with a Remote Support
    seat    \n    403 Forbidden      Access denied. User doesn\u2019t have required
    roles    \n    404 Not Found      A machineUuid was specified, but the specified
    machine was not found in an account the user has access to    \n    405 Method
    Not Allowed      The method was entered incorrectly (i.e., the technician tried
    to use POST, PUT etc. instead of GET)    \n    500 Internal Server Error      An
    unhandled error occurred"
  version: 1.0.0
host: api.getgo.com
basePath: /G2A/rest/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /sessions:
    post:
      summary: Start Screen Sharing Session
      description: "This method creates a new screen sharing support session (either
        attended or unattended) by generating a URL that automatically launches technicians
        into a new session when clicked. If a machineUuid request parameter is specified,
        an unattended support session will be created; if it is not specified, then
        an attended session will be created. See \"Request Parameters\" for more information.
        Note: The locale of the session start dialog will be based upon the technician\u2019s
        locale setting within GoToAssist.\n\nNote: This method was formerly named
        \"Create Attended Session,\" but has been renamed to address the fact that
        it now includes unattended support sessions as well.\n\n  Request Parameters
        \                   \n                      \n    field        data type      description
        \   \n    sessionStatusCallbackUrl*        string      The URL that will receive
        a POST when the session status changes. A POST will also be made to the sessionStatusCallbackUrl
        when a customer joins the session and when the session ends (whether or not
        a customer joined). The contents of the POST will be similar as the GET /v1/sessions/
        API. Note: The ID of the session is not known until the session is actually
        started on the endpoint. If the URL is not specified or the session is never
        started (e.g., if the customer cancels the installation of the GoToAssist
        Customer desktop application), then the callback will not be made.    \n    sessionType
        \       string      The type of session to create (only \"SCREEN_SHARING\"
        can be used at this time).    \n    partnerObject*        string      The
        ID of object in the partner system that this session will be associated with.
        \   \n    partnerObjectUrl*        string      The URL that may be used in
        the GoToAssist Expert desktop application if the technician wants to view
        the partner object. Note: The URL can be used in a popup window or iframe
        that is 600 pixels wide and 500 pixels wide. For example, a popup window could
        be created with HTML code as follows: \"Start Remote Support \"    \n    customerName*
        \       string      The name of the customer that the session is being started
        for.    \n    customerEmail*        string      The email address of the customer
        that the session is being started for (if available)    \n    machineUuid*
        \       string      The machineUuid is only necessary for unattended support
        sessions. If the machineUuid is present when a screen sharing session is started,
        then the endpoint will connect to the specified unattended machine and an
        unattended support session will be started. If no machineUuid is specified,
        then an attended support session will be created. A list of machineUuid parameters
        associated with the user and company will be available through a /machines
        API in future.    \n                      \n* Optional parameters\n\nStatus
        Codes              \n              \n    Staus Code      description    \n
        \   200 OK      The response contains the URL to start the session    \n    400
        Bad Request      An error occurred due to missing required parameters or portal
        not being created    \n    401 Unauthorized      An authentication parameter
        was passed, but either it was invalid or the technician is not entitled with
        a Remote Support seat    \n    403 Forbidden      Access denied. User doesn\u2019t
        have required roles    \n    404 Not Found      A machineUuid was specified,
        but the specified machine was not found in an account the user has access
        to    \n    405 Method Not Allowed      The method was entered incorrectly
        (i.e., the technician tried to use POST, PUT etc. instead of GET)    \n    500
        Internal Server Error      An unhandled error occurred"
      operationId: SessionsPost2
      x-api-path-slug: sessions-post
      parameters:
      - in: header
        name: Accept
      - in: body
        name: Body
        schema:
          $ref: '#/definitions/holder'
      - in: header
        name: Content-Type
      responses:
        200:
          description: OK
      tags:
      - Start
      - Screen
      - Sharing
      - Session
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