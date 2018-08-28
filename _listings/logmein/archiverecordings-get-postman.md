{
  "info": {
    "name": "GoToAssist Remote Support Available Recordings",
    "_postman_id": "91a0942e-0be5-4e7f-a2a1-6d6599d88ff5",
    "description": "This method retrieves a list of all available recordings on the account. Only recordings which are available for transcoding or downloading will be returned. The recording IDs are always returned in the order in which the recordings were started (i.e., startTime order). The request must contain one or more of the following: accountKey, userKey or companyId. The list of recordings can be filtered by the request parameters listed below.\n\nNote: Session recording must be enabled on the account in order to use this API method. To enable session recording, log in at https://app.gotoassist.com (link is external) and go to Configure > GoToAssist Settings > Enable Session Recording check box.\n\n  Request Parameters                  \n  Each request must contain one or more of the following: accountKey, userKey or companyId.                  \n                    \n    field      data type      description    \n    accountKey      number      The account key associated with the recording ( available in the Get Screen Sharing Session Info (link is external) method response )    \n    userKey      number      The user key of the technician who started the recorded session (available in the Authentication (link is external) API method response)    \n    companyId      number      The companyId associated with the recording for unattended support sessions only ( available in the Get Companies (link is external) API method response )    \n    sessionType *      number      The type of session: attended (0) or unattended (1)    \n    fromTime *      ISO 8601 format **      The oldest sessions that should be retrieved (startTime must be greater than or equal to fromTime)    \n    toTime *      ISO 8601 format **      The most recent sessions that should be retrieved (startTime must be greater than or equal to fromTime)    \n    timePeriod *      number      The recordings within a Time Period, starting from currentDate (ex: ”timePeriod=30” would retrieve the last 30 days’ recordings)    \n    archived *      number      The option to include only archived recordings, as follows: include only archived recordings (1) or include only non-archived recordings (0 or omit)    \n                    \n* Optional                    \n** ISO 8601 format reference                    \n                    \n  Response Parameters                  \n  No more than 500 recordings at a time will be returned for readyForTranscode or readyForDownload.                  \n                    \n    field      data type      description    \n    readyForTranscode      array      A list of recordingIds for recordings that are ready to be transcoded    \n    readyForDownload      array      A list of recordingIds for recordings that are ready to be downloaded    \n                    \n                    \nStatus Codes                    \n                    \n    Staus Code      description          \n    200 OK      Recordings retrieved successfully          \n    400 Bad Request      Request may be malformed or property may be missing or invalid          \n    403 Forbidden      Invalid authorization header or invalid userKey, accountKey or companyId          \n    500 Internal Server Error      Unexpected server error",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Available",
      "item": [
        {
          "id": "b98816c8-dfcc-40c6-8cd4-f6f1c6656250",
          "name": "ArchiveRecordingsGet",
          "request": {
            "url": "http://api.getgo.com/G2A/rest/v1/archive/recordings?userKey=%7B%7D",
            "method": "GET",
            "header": [
              {
                "key": "Accept",
                "value": "{}",
                "description": "",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "This method retrieves a list of all available recordings on the account. Only recordings which are available for transcoding or downloading will be returned. The recording IDs are always returned in the order in which the recordings were started (i.e., startTime order). The request must contain one or more of the following: accountKey, userKey or companyId. The list of recordings can be filtered by the request parameters listed below.\n\nNote: Session recording must be enabled on the account in order to use this API method. To enable session recording, log in at https://app.gotoassist.com (link is external) and go to Configure > GoToAssist Settings > Enable Session Recording check box.\n\n  Request Parameters                  \n  Each request must contain one or more of the following: accountKey, userKey or companyId.                  \n                    \n    field      data type      description    \n    accountKey      number      The account key associated with the recording ( available in the Get Screen Sharing Session Info (link is external) method response )    \n    userKey      number      The user key of the technician who started the recorded session (available in the Authentication (link is external) API method response)    \n    companyId      number      The companyId associated with the recording for unattended support sessions only ( available in the Get Companies (link is external) API method response )    \n    sessionType *      number      The type of session: attended (0) or unattended (1)    \n    fromTime *      ISO 8601 format **      The oldest sessions that should be retrieved (startTime must be greater than or equal to fromTime)    \n    toTime *      ISO 8601 format **      The most recent sessions that should be retrieved (startTime must be greater than or equal to fromTime)    \n    timePeriod *      number      The recordings within a Time Period, starting from currentDate (ex: ”timePeriod=30” would retrieve the last 30 days’ recordings)    \n    archived *      number      The option to include only archived recordings, as follows: include only archived recordings (1) or include only non-archived recordings (0 or omit)    \n                    \n* Optional                    \n** ISO 8601 format reference                    \n                    \n  Response Parameters                  \n  No more than 500 recordings at a time will be returned for readyForTranscode or readyForDownload.                  \n                    \n    field      data type      description    \n    readyForTranscode      array      A list of recordingIds for recordings that are ready to be transcoded    \n    readyForDownload      array      A list of recordingIds for recordings that are ready to be downloaded    \n                    \n                    \nStatus Codes                    \n                    \n    Staus Code      description          \n    200 OK      Recordings retrieved successfully          \n    400 Bad Request      Request may be malformed or property may be missing or invalid          \n    403 Forbidden      Invalid authorization header or invalid userKey, accountKey or companyId          \n    500 Internal Server Error      Unexpected server error"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "541c410c-c51b-4561-b75f-448efa9b94a9"
            }
          ]
        }
      ]
    }
  ]
}