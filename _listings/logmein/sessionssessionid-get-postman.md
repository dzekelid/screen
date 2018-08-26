{
  "info": {
    "name": "GoToAssist Remote Support Get Screen Sharing Session Info",
    "_postman_id": "0e6871ef-26f5-48e4-992b-beb2cdc4bfb5",
    "description": "This method retrieves detailed information about a current or previous support session (either attended or unattended) based on the sessionID or sessionToken. “sessionToken” is returned in response of create screen-sharing session API. Information about sessions that are complete may only be available for a limited period of time after the end of the session (currently, the information is available for at least 30 days). The session must have been hosted from an account or company that the authenticated user has access to.\r\n\r\nNote: This method was formerly named \"Get Attended Session Info,\" but has been renamed to address the fact that it now includes unattended support sessions as well.\r\n\r\n  Response Parameters                    \r\n                      \r\n    field        data type      description    \r\n    sessionId        string      The unique ID of this session.    \r\n    sessionType        string      The type of the session; this determines what other attributes the response may contain.    \r\n    status        string      \"The current state of the session; it can be: \r\nwaiting = Waiting for the customer to join the session.\r\nactive = Customer has joined and session is currently active.\r\ncomplete = Session has ended after the customer joined.\r\nabandoned = Session has ended without any customer joining.\r\nnotStarted = Session was created but never started by the expert.\"    \r\n    accountKey        number      The unique GoToAssist system ID of the account the support session was hosted from.    \r\n    expertName        string      The human-readable name of the first technician in the support session.    \r\n    expertEmail        string      Email id of the first expert in the session.    \r\n    expertUserKey        string      Unique ID of the first expert in the session in the G2A system.    \r\n    partnerObject        number      The ID of the object in the partner system that is associated with this session.    \r\n    partnerObjectUrl        string      The URL for the expert to view the associated partnerObject.    \r\n    startedAt*        ISO 8061 format*      The time that the session started.    \r\n    customerJoinedAt*        ISO 8061 format*      The time that the customer joined the session.    \r\n    endedAt*        ISO 8061 format*      The time that the session ended.    \r\n    unattendedMachineName*        string      Name of the unattended machine the session is with if this is an unattended session.    \r\n    unattendedMachineUuid*        string      ID of the unattended machine the session is with if this is an unattended session.    \r\n    accountName*        string      The human-readable name of the account the support session was hosted from (unattended sessions only)    \r\n    customerName*        string      The human-readable name of the customer in the support session.    \r\n    customerEmail*        string      The email address of the customer in the support session.    \r\n    customerJoinUrl        string      A URL that can be sent to a customer to join the session.    \r\n    notes*        string      All notes that were entered by the technician in the Viewer during the support session    \r\n    sessionRecordingUrl*        string      The URL where the technician can view a recording of the session within the GoToAssist web application (only available if the technician has opted to record support sessions (link is external))    \r\n    collaborators*        array      A list of other users who collaborated on the support session (i.e., other technicians who joined the session)    \r\n                      \r\n* Parameters only listed if available/applicable\r\n\r\nStatus Codes              \r\n              \r\n    Staus Code      description    \r\n    200 OK      The information was successfully retrieved    \r\n    401 Unauthorized      An authentication parameter was passed, but either it was invalid or the technician is not entitled with a Remote Support seat    \r\n    404 Not Found      The sessionID is not valid for the authorized user and the session could not be found    \r\n    405 Method Not Allowed      The method was entered incorrectly (i.e., the technician tried to use POST, PUT etc. instead of GET)    \r\n    500 Internal Server Error      An unhandled error occurred",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Partner-System",
      "item": [
        {
          "id": "c65c8aab-16f3-4048-b324-05b0470bd7c6",
          "name": "SystemLinksGet",
          "request": {
            "url": "http://api.getgo.com/G2A/rest/v1/systemLinks?systemDomain=%7B%7D",
            "method": "GET",
            "header": [
              {
                "key": "Accept",
                "value": "{}",
                "description": "",
                "disabled": false
              },
              {
                "key": "Content-Type",
                "value": "{}",
                "description": "",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "This method retrieves all partner-system links that are registered for a given domain. These links are used by GoToAssist to make calls back to the partner system to enable the creation of tickets during support sessions.\n\n  Request Parameters                    \n                      \n    field        data type      description    \n    systemDomain        string      The domain name of the partner system.    \n                      \n\n\n  Response Parameters: (* Optional)                  \n                    \n    field      data type      description    \n    systemName      string      The human-readable name of the partner system (may be displayed to the user in the GoToAssist web application); it is used to uniquely identify partner systems, along with the systemDomain for a particular user    \n    systemDomain      string      The domain name of the partner system; it is used to uniquely identify partner systems, along with the systemName for a particular user    \n    userEmail      string      The email address of the user these links are for    \n    userToken      string      A unique identifier generated by the partner system that will be used to authenticate requests made by GoToAssist on behalf of this user    \n    callbackURL      string      The callback URL into the partner system    \n                    \n\nStatus Codes              \n              \n    Staus Code      description    \n    200 OK      The information was successfully retrieved    \n    400 Bad Request      An error occurred due to a missing systemDomain parameter    \n    401 Unauthorized      An authentication parameter was passed, but either it was invalid or the technician is not entitled with a Remote Support seat    \n    500 Internal Server Error      An unhandled error occurred"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "6aebab7d-6d7d-4329-a18c-5fdb9971e10f"
            }
          ]
        }
      ]
    },
    {
      "name": "Screen",
      "item": [
        {
          "id": "a427df40-e035-4429-b5e5-66bbe9099656",
          "name": "SessionsBySessionIdGet2",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.getgo.com",
              "path": [
                "G2A",
                "rest",
                "v1",
                "sessions/:sessionId"
              ],
              "variable": [
                {
                  "id": "sessionId",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "header": [
              {
                "key": "Accept",
                "value": "{}",
                "description": "",
                "disabled": false
              },
              {
                "key": "Content-Type",
                "value": "{}",
                "description": "",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "This method retrieves detailed information about a current or previous support session (either attended or unattended) based on the sessionID or sessionToken. “sessionToken” is returned in response of create screen-sharing session API. Information about sessions that are complete may only be available for a limited period of time after the end of the session (currently, the information is available for at least 30 days). The session must have been hosted from an account or company that the authenticated user has access to.\r\n\r\nNote: This method was formerly named \"Get Attended Session Info,\" but has been renamed to address the fact that it now includes unattended support sessions as well.\r\n\r\n  Response Parameters                    \r\n                      \r\n    field        data type      description    \r\n    sessionId        string      The unique ID of this session.    \r\n    sessionType        string      The type of the session; this determines what other attributes the response may contain.    \r\n    status        string      \"The current state of the session; it can be: \r\nwaiting = Waiting for the customer to join the session.\r\nactive = Customer has joined and session is currently active.\r\ncomplete = Session has ended after the customer joined.\r\nabandoned = Session has ended without any customer joining.\r\nnotStarted = Session was created but never started by the expert.\"    \r\n    accountKey        number      The unique GoToAssist system ID of the account the support session was hosted from.    \r\n    expertName        string      The human-readable name of the first technician in the support session.    \r\n    expertEmail        string      Email id of the first expert in the session.    \r\n    expertUserKey        string      Unique ID of the first expert in the session in the G2A system.    \r\n    partnerObject        number      The ID of the object in the partner system that is associated with this session.    \r\n    partnerObjectUrl        string      The URL for the expert to view the associated partnerObject.    \r\n    startedAt*        ISO 8061 format*      The time that the session started.    \r\n    customerJoinedAt*        ISO 8061 format*      The time that the customer joined the session.    \r\n    endedAt*        ISO 8061 format*      The time that the session ended.    \r\n    unattendedMachineName*        string      Name of the unattended machine the session is with if this is an unattended session.    \r\n    unattendedMachineUuid*        string      ID of the unattended machine the session is with if this is an unattended session.    \r\n    accountName*        string      The human-readable name of the account the support session was hosted from (unattended sessions only)    \r\n    customerName*        string      The human-readable name of the customer in the support session.    \r\n    customerEmail*        string      The email address of the customer in the support session.    \r\n    customerJoinUrl        string      A URL that can be sent to a customer to join the session.    \r\n    notes*        string      All notes that were entered by the technician in the Viewer during the support session    \r\n    sessionRecordingUrl*        string      The URL where the technician can view a recording of the session within the GoToAssist web application (only available if the technician has opted to record support sessions (link is external))    \r\n    collaborators*        array      A list of other users who collaborated on the support session (i.e., other technicians who joined the session)    \r\n                      \r\n* Parameters only listed if available/applicable\r\n\r\nStatus Codes              \r\n              \r\n    Staus Code      description    \r\n    200 OK      The information was successfully retrieved    \r\n    401 Unauthorized      An authentication parameter was passed, but either it was invalid or the technician is not entitled with a Remote Support seat    \r\n    404 Not Found      The sessionID is not valid for the authorized user and the session could not be found    \r\n    405 Method Not Allowed      The method was entered incorrectly (i.e., the technician tried to use POST, PUT etc. instead of GET)    \r\n    500 Internal Server Error      An unhandled error occurred"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "c5533957-c315-45c3-a14f-efb5698f0373"
            }
          ]
        }
      ]
    }
  ]
}