{
  "info": {
    "name": "Instructure Canvas Quiz Submissions API Flagging a question.",
    "_postman_id": "9d870217-b727-4484-8045-aed52629af9a",
    "description": "Flagging a question..",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Quiz",
      "item": [
        {
          "id": "e940a685-b93a-4ae3-947f-eb729f2578f6",
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
              "id": "2294eabd-e2be-4033-89f5-55f4bb73022a"
            }
          ]
        },
        {
          "id": "cee85e00-8daf-432a-b97d-325897811748",
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
              "id": "48079b5c-2889-4892-a0c4-63ea5716297f"
            }
          ]
        },
        {
          "id": "a71e0caf-e9e6-43ae-b6bc-590ba12971a1",
          "name": "flagging-a-question",
          "request": {
            "url": {
              "protocol": "http",
              "host": "canvas.instructure.com",
              "path": [
                "api",
                "v1",
                "quiz_submissions/:quiz_submission_id/questions/id/flag"
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
            "method": "PUT",
            "body": {
              "mode": "raw"
            },
            "description": "Flagging a question.."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "6073b7fb-4592-4c68-bee4-45a2932ddb85"
            }
          ]
        }
      ]
    }
  ]
}