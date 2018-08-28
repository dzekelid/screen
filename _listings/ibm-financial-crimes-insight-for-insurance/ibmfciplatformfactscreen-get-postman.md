{
  "info": {
    "name": "IBM Financial Crimes Insight for Insurance API Screen a specific attribute against a dynamic list",
    "_postman_id": "4d9537d1-bb8d-4c21-bf08-b329e58b651d",
    "description": "This method is used to screen data against a specific list of values, resulting in a JSON object containing a list of matching objects",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Screen",
      "item": [
        {
          "id": "89eb6d09-10cc-42cf-847c-109ca7dec6b3",
          "name": "screen",
          "request": {
            "url": "http://fcihost.ibm.com:9443/ibm/fci/platform/fact/screen?context=%7B%7D&fieldName=%7B%7D&objectType=%7B%7D&offset=%7B%7D&style=%7B%7D&values=%7B%7D",
            "method": "GET",
            "header": [
              {
                "key": "IBM-FCI-Role",
                "value": "{}",
                "description": "Userid / password for user with appropriate role",
                "disabled": false
              },
              {
                "key": "IBM-FCI-Token",
                "value": "{}",
                "description": "Security token obtained for execution",
                "disabled": false
              },
              {
                "key": "Accept",
                "value": "*/*",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "This method is used to screen data against a specific list of values, resulting in a JSON object containing a list of matching objects"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "165cbf62-7c96-4fc0-bf1f-958dd8e03b95"
            }
          ]
        }
      ]
    }
  ]
}