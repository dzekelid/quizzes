{
  "info": {
    "name": "Instructure Canvas Quiz Submissions API Get all quiz submission questions.",
    "_postman_id": "1355cb48-22ab-4465-8db5-ebf82d93ca65",
    "description": "Get all quiz submission questions..",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Quiz",
      "item": [
        {
          "id": "7a045eb5-fa6f-41a9-9c1c-78e9d7ade9e7",
          "name": "get-all-quiz-submission-questions",
          "request": {
            "url": {
              "protocol": "http",
              "host": "canvas.instructure.com",
              "path": [
                "api",
                "v1",
                "quiz_submissions/:quiz_submission_id/questions"
              ],
              "query": [
                {
                  "key": "include",
                  "value": "%5B%7B%7D%5D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "quiz_submission_id",
                  "value": "quiz_submission_id",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get all quiz submission questions.."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "1dbadaa3-6bfd-48a8-b0cd-54785a878e40"
            }
          ]
        }
      ]
    }
  ]
}