---
name: LogMeIn
x-slug: logmein
description: LogMeIn, Inc. is a provider of software as a service and cloud-based
  remote connectivity services for collaboration, IT management and customer engagement,
  founded in 2003 and based in Boston, Massachusetts.
image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28873-www-logmeininc-com.jpg
x-kinRank: "7"
x-alexaRank: "7271"
tags: Screen
created: "2018-08-26"
modified: "2018-08-26"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/screen/master/_listings/logmein/apis.md
specificationVersion: "0.14"
apis:
- name: GoToAssist Remote Support - Get Screen Sharing Session Info
  x-api-slug: sessionssessionid-get
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
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28873-www-logmeininc-com.jpg
  humanURL: http://www.LogMeInInc.com
  baseURL: https://api.getgo.com//G2A/rest/v1
  tags: SaaS, Technology, Enterprise, Voice, Videoconferencing, Audio, Webinars, Relative
    Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/screen/master/_listings/logmein/sessionssessionid-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/screen/master/_listings/logmein/sessionssessionid-get-openapi.md
- name: GoToAssist Remote Support - Available Recordings
  x-api-slug: archiverecordings-get
  description: "This method retrieves a list of all available recordings on the account.
    Only recordings which are available for transcoding or downloading will be returned.
    The recording IDs are always returned in the order in which the recordings were
    started (i.e., startTime order). The request must contain one or more of the following:
    accountKey, userKey or companyId. The list of recordings can be filtered by the
    request parameters listed below.\n\nNote: Session recording must be enabled on
    the account in order to use this API method. To enable session recording, log
    in at https://app.gotoassist.com (link is external) and go to Configure > GoToAssist
    Settings > Enable Session Recording check box.\n\n  Request Parameters                  \n
    \ Each request must contain one or more of the following: accountKey, userKey
    or companyId.                  \n                    \n    field      data type
    \     description    \n    accountKey      number      The account key associated
    with the recording ( available in the Get Screen Sharing Session Info (link is
    external) method response )    \n    userKey      number      The user key of
    the technician who started the recorded session (available in the Authentication
    (link is external) API method response)    \n    companyId      number      The
    companyId associated with the recording for unattended support sessions only (
    available in the Get Companies (link is external) API method response )    \n
    \   sessionType *      number      The type of session: attended (0) or unattended
    (1)    \n    fromTime *      ISO 8601 format **      The oldest sessions that
    should be retrieved (startTime must be greater than or equal to fromTime)    \n
    \   toTime *      ISO 8601 format **      The most recent sessions that should
    be retrieved (startTime must be greater than or equal to fromTime)    \n    timePeriod
    *      number      The recordings within a Time Period, starting from currentDate
    (ex: \u201DtimePeriod=30\u201D would retrieve the last 30 days\u2019 recordings)
    \   \n    archived *      number      The option to include only archived recordings,
    as follows: include only archived recordings (1) or include only non-archived
    recordings (0 or omit)    \n                    \n* Optional                    \n**
    ISO 8601 format reference                    \n                    \n  Response
    Parameters                  \n  No more than 500 recordings at a time will be
    returned for readyForTranscode or readyForDownload.                  \n                    \n
    \   field      data type      description    \n    readyForTranscode      array
    \     A list of recordingIds for recordings that are ready to be transcoded    \n
    \   readyForDownload      array      A list of recordingIds for recordings that
    are ready to be downloaded    \n                    \n                    \nStatus
    Codes                    \n                    \n    Staus Code      description
    \         \n    200 OK      Recordings retrieved successfully          \n    400
    Bad Request      Request may be malformed or property may be missing or invalid
    \         \n    403 Forbidden      Invalid authorization header or invalid userKey,
    accountKey or companyId          \n    500 Internal Server Error      Unexpected
    server error"
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28873-www-logmeininc-com.jpg
  humanURL: http://www.LogMeInInc.com
  baseURL: https://api.getgo.com//G2A/rest/v1
  tags: SaaS, Technology, Enterprise, Voice, Videoconferencing, Audio, Webinars, Relative
    Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/screen/master/_listings/logmein/archiverecordings-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/screen/master/_listings/logmein/archiverecordings-get-openapi.md
x-common:
- type: x-github
  url: https://github.com/logmein
- type: x-openapi
  url: https://www.getpostman.com/collections/94ad52bdc3d954bad52a
- type: x-postman-collection
  url: https://www.getpostman.com/collections/00bf4391e993c3afa7b7
- type: x-postman-collection
  url: https://www.getpostman.com/collections/c35d614484f21e581775
- type: x-postman-collection
  url: https://www.getpostman.com/collections/9c6e067461f45f7faa6b
- type: x-postman-collection
  url: https://drive.google.com/open?id=16WZlBkS1i8cWSfZ3mMKOwlNP-qsE7AWy
- type: x-postman-collection
  url: https://drive.google.com/file/d/1vI11FNCKpv6WJ_70hoqPNMmPAkASiOU_/view?usp=sharing
- type: x-website
  url: http://www.LogMeInInc.com
- type: x-api-gallery
  url: http://loginradius.api.gallery.streamdata.io
- type: x-api-stack
  url: http://logmein.stack.network
- type: x-crunchbase
  url: https://crunchbase.com/organization/logmein
- type: x-developer
  url: https://goto-developer.logmeininc.com/
- type: x-documentation
  url: https://goto-developer.logmeininc.com/apis/apis-overview
- type: x-faq
  url: https://goto-developer.logmeininc.com/faq-page
- type: x-support
  url: https://goto-developer.logmeininc.com/api-support-request-template
- type: x-twitter
  url: https://twitter.com/LogMeIn
- type: x-website
  url: https://www.logmeininc.com
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---