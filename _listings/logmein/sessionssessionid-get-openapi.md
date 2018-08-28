---
swagger: "2.0"
x-collection-name: LogMeIn
x-complete: 0
info:
  title: GoToAssist Remote Support Get Screen Sharing Session Info
  description: "This method retrieves detailed information about a current or previous
    support session (either attended or unattended) based on the sessionID or sessionToken.
    \u201CsessionToken\u201D is returned in response of create screen-sharing session
    API. Information about sessions that are complete may only be available for a
    limited period of time after the end of the session (currently, the information
    is available for at least 30 days). The session must have been hosted from an
    account or company that the authenticated user has access to.\r\n\r\nNote: This
    method was formerly named \"Get Attended Session Info,\" but has been renamed
    to address the fact that it now includes unattended support sessions as well.\r\n\r\n
    \ Response Parameters                    \r\n                      \r\n    field
    \       data type      description    \r\n    sessionId        string      The
    unique ID of this session.    \r\n    sessionType        string      The type
    of the session; this determines what other attributes the response may contain.
    \   \r\n    status        string      \"The current state of the session; it can
    be: \r\nwaiting = Waiting for the customer to join the session.\r\nactive = Customer
    has joined and session is currently active.\r\ncomplete = Session has ended after
    the customer joined.\r\nabandoned = Session has ended without any customer joining.\r\nnotStarted
    = Session was created but never started by the expert.\"    \r\n    accountKey
    \       number      The unique GoToAssist system ID of the account the support
    session was hosted from.    \r\n    expertName        string      The human-readable
    name of the first technician in the support session.    \r\n    expertEmail        string
    \     Email id of the first expert in the session.    \r\n    expertUserKey        string
    \     Unique ID of the first expert in the session in the G2A system.    \r\n
    \   partnerObject        number      The ID of the object in the partner system
    that is associated with this session.    \r\n    partnerObjectUrl        string
    \     The URL for the expert to view the associated partnerObject.    \r\n    startedAt*
    \       ISO 8061 format*      The time that the session started.    \r\n    customerJoinedAt*
    \       ISO 8061 format*      The time that the customer joined the session.    \r\n
    \   endedAt*        ISO 8061 format*      The time that the session ended.    \r\n
    \   unattendedMachineName*        string      Name of the unattended machine the
    session is with if this is an unattended session.    \r\n    unattendedMachineUuid*
    \       string      ID of the unattended machine the session is with if this is
    an unattended session.    \r\n    accountName*        string      The human-readable
    name of the account the support session was hosted from (unattended sessions only)
    \   \r\n    customerName*        string      The human-readable name of the customer
    in the support session.    \r\n    customerEmail*        string      The email
    address of the customer in the support session.    \r\n    customerJoinUrl        string
    \     A URL that can be sent to a customer to join the session.    \r\n    notes*
    \       string      All notes that were entered by the technician in the Viewer
    during the support session    \r\n    sessionRecordingUrl*        string      The
    URL where the technician can view a recording of the session within the GoToAssist
    web application (only available if the technician has opted to record support
    sessions (link is external))    \r\n    collaborators*        array      A list
    of other users who collaborated on the support session (i.e., other technicians
    who joined the session)    \r\n                      \r\n* Parameters only listed
    if available/applicable\r\n\r\nStatus Codes              \r\n              \r\n
    \   Staus Code      description    \r\n    200 OK      The information was successfully
    retrieved    \r\n    401 Unauthorized      An authentication parameter was passed,
    but either it was invalid or the technician is not entitled with a Remote Support
    seat    \r\n    404 Not Found      The sessionID is not valid for the authorized
    user and the session could not be found    \r\n    405 Method Not Allowed      The
    method was entered incorrectly (i.e., the technician tried to use POST, PUT etc.
    instead of GET)    \r\n    500 Internal Server Error      An unhandled error occurred"
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
  /sessions/{sessionId}:
    get:
      summary: Get Screen Sharing Session Info
      description: "This method retrieves detailed information about a current or
        previous support session (either attended or unattended) based on the sessionID
        or sessionToken. \u201CsessionToken\u201D is returned in response of create
        screen-sharing session API. Information about sessions that are complete may
        only be available for a limited period of time after the end of the session
        (currently, the information is available for at least 30 days). The session
        must have been hosted from an account or company that the authenticated user
        has access to.\r\n\r\nNote: This method was formerly named \"Get Attended
        Session Info,\" but has been renamed to address the fact that it now includes
        unattended support sessions as well.\r\n\r\n  Response Parameters                    \r\n
        \                     \r\n    field        data type      description    \r\n
        \   sessionId        string      The unique ID of this session.    \r\n    sessionType
        \       string      The type of the session; this determines what other attributes
        the response may contain.    \r\n    status        string      \"The current
        state of the session; it can be: \r\nwaiting = Waiting for the customer to
        join the session.\r\nactive = Customer has joined and session is currently
        active.\r\ncomplete = Session has ended after the customer joined.\r\nabandoned
        = Session has ended without any customer joining.\r\nnotStarted = Session
        was created but never started by the expert.\"    \r\n    accountKey        number
        \     The unique GoToAssist system ID of the account the support session was
        hosted from.    \r\n    expertName        string      The human-readable name
        of the first technician in the support session.    \r\n    expertEmail        string
        \     Email id of the first expert in the session.    \r\n    expertUserKey
        \       string      Unique ID of the first expert in the session in the G2A
        system.    \r\n    partnerObject        number      The ID of the object in
        the partner system that is associated with this session.    \r\n    partnerObjectUrl
        \       string      The URL for the expert to view the associated partnerObject.
        \   \r\n    startedAt*        ISO 8061 format*      The time that the session
        started.    \r\n    customerJoinedAt*        ISO 8061 format*      The time
        that the customer joined the session.    \r\n    endedAt*        ISO 8061
        format*      The time that the session ended.    \r\n    unattendedMachineName*
        \       string      Name of the unattended machine the session is with if
        this is an unattended session.    \r\n    unattendedMachineUuid*        string
        \     ID of the unattended machine the session is with if this is an unattended
        session.    \r\n    accountName*        string      The human-readable name
        of the account the support session was hosted from (unattended sessions only)
        \   \r\n    customerName*        string      The human-readable name of the
        customer in the support session.    \r\n    customerEmail*        string      The
        email address of the customer in the support session.    \r\n    customerJoinUrl
        \       string      A URL that can be sent to a customer to join the session.
        \   \r\n    notes*        string      All notes that were entered by the technician
        in the Viewer during the support session    \r\n    sessionRecordingUrl*        string
        \     The URL where the technician can view a recording of the session within
        the GoToAssist web application (only available if the technician has opted
        to record support sessions (link is external))    \r\n    collaborators*        array
        \     A list of other users who collaborated on the support session (i.e.,
        other technicians who joined the session)    \r\n                      \r\n*
        Parameters only listed if available/applicable\r\n\r\nStatus Codes              \r\n
        \             \r\n    Staus Code      description    \r\n    200 OK      The
        information was successfully retrieved    \r\n    401 Unauthorized      An
        authentication parameter was passed, but either it was invalid or the technician
        is not entitled with a Remote Support seat    \r\n    404 Not Found      The
        sessionID is not valid for the authorized user and the session could not be
        found    \r\n    405 Method Not Allowed      The method was entered incorrectly
        (i.e., the technician tried to use POST, PUT etc. instead of GET)    \r\n
        \   500 Internal Server Error      An unhandled error occurred"
      operationId: SessionsBySessionIdGet2
      x-api-path-slug: sessionssessionid-get
      parameters:
      - in: header
        name: Accept
      - in: header
        name: Content-Type
      - in: path
        name: sessionId
      responses:
        200:
          description: OK
      tags:
      - Screen
      - Sharing
      - Session
      - Info
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