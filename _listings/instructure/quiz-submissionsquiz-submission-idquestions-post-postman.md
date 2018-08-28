{
  "info": {
    "name": "Instructure Canvas Quiz Submissions API Answering questions",
    "_postman_id": "46402b3d-8520-4512-af6d-5ceda29cbc0f",
    "description": "Answering questions.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Quiz",
      "item": [
        {
          "id": "d2f2fa4a-46f3-4fd2-b63e-5c801d829ed7",
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
              "id": "cfd174e9-d07d-4f80-8a8d-38b75fa0e2c4"
            }
          ]
        },
        {
          "id": "3ff4fdde-6b38-4968-898b-15ad7c7ba000",
          "name": "answering-questions",
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
                  "key": "access_code",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "attempt",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "quiz_questions",
                  "value": "%5B%7B%7D%5D",
                  "disabled": false
                },
                {
                  "key": "validation_token",
                  "value": "%7B%7D",
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
            "method": "POST",
            "body": {
              "mode": "raw"
            },
            "description": "Answering questions."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "6e1ee9ae-b582-453b-ad1c-7e9ebd7c3ff1"
            }
          ]
        }
      ]
    }
  ]
}