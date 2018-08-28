---
swagger: "2.0"
x-collection-name: Instructure
x-complete: 0
info:
  title: Instructure Canvas Courses API Delete a quiz
  description: Delete a quiz.
  termsOfService: https://www.canvaslms.com/policies/api-policy
  version: v1
host: canvas.instructure.com
basePath: /api/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /courses/{course_id}/quizzes:
    get:
      summary: List quizzes in a course
      description: List quizzes in a course.
      operationId: list-quizzes-in-a-course
      x-api-path-slug: coursescourse-idquizzes-get
      parameters:
      - in: query
        name: search_term
        description: The partial title of the quizzes to match and return
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
    post:
      summary: Create a quiz
      description: Create a quiz.
      operationId: create-a-quiz
      x-api-path-slug: coursescourse-idquizzes-post
      parameters:
      - in: query
        name: quiz[access_code]
        description: Restricts access to the quiz with a password
      - in: query
        name: quiz[allowed_attempts]
        description: Number of times a student is allowed to take a quiz
      - in: query
        name: quiz[assignment_group_id]
        description: The assignment group id to put the assignment in
      - in: query
        name: quiz[cant_go_back]
        description: Only valid if one_question_at_a_time=true If true, questions
          are lockednafter answering
      - in: query
        name: quiz[description]
        description: A description of the quiz
      - in: query
        name: quiz[due_at]
        description: The day/time the quiz is due
      - in: query
        name: quiz[hide_correct_answers_at]
        description: Only valid if show_correct_answers=true If set, the correct answers
          willnstop being visible once this date has passed
      - in: query
        name: quiz[hide_results]
        description: Dictates whether or not quiz results are hidden from students
      - in: query
        name: quiz[ip_filter]
        description: Restricts access to the quiz to computers in a specified IP range
      - in: query
        name: quiz[lock_at]
        description: The day/time the quiz is locked for students
      - in: query
        name: quiz[one_question_at_a_time]
        description: If true, shows quiz to student one question at a time
      - in: query
        name: quiz[one_time_results]
        description: Whether students should be prevented from viewing their quiz
          results pastnthe first time (right after they turn the quiz in
      - in: query
        name: quiz[published]
        description: Whether the quiz should have a draft state of published or unpublished
      - in: query
        name: quiz[quiz_type]
        description: The type of quiz
      - in: query
        name: quiz[scoring_policy]
        description: Required and only valid if allowed_attempts &gt; 1
      - in: query
        name: quiz[show_correct_answers]
        description: Only valid if hide_results=null If false, hides correct answers
          fromnstudents when quiz results are viewed
      - in: query
        name: quiz[show_correct_answers_at]
        description: Only valid if show_correct_answers=true If set, the correct answers
          will benvisible by students only after this date, otherwise the correct
          answers arenvisible once the student hands in their quiz submission
      - in: query
        name: quiz[show_correct_answers_last_attempt]
        description: Only valid if show_correct_answers=true and allowed_attempts
          &gt; 1 Ifntrue, hides correct answers from students when quiz results are
          viewednuntil they submit the last attempt for the quiz
      - in: query
        name: quiz[shuffle_answers]
        description: If true, quiz answers for multiple choice questions will be randomized
          forneach student
      - in: query
        name: quiz[time_limit]
        description: Time limit to take this quiz, in minutes
      - in: query
        name: quiz[title]
        description: The quiz title
      - in: query
        name: quiz[unlock_at]
        description: The day/time the quiz is unlocked for students
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
  /courses/{course_id}/quizzes/assignment_overrides:
    get:
      summary: Retrieve assignment-overridden dates for quizzes
      description: Retrieve assignment-overridden dates for quizzes.
      operationId: retrieve-assignmentoverridden-dates-for-quizzes
      x-api-path-slug: coursescourse-idquizzesassignment-overrides-get
      parameters:
      - in: query
        name: quiz_assignment_overrides[0][quiz_ids][]
        description: An array of quiz IDs
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Assignment
      - Overrides
  /courses/{course_id}/quizzes/id:
    delete:
      summary: Delete a quiz
      description: Delete a quiz.
      operationId: delete-a-quiz
      x-api-path-slug: coursescourse-idquizzesid-delete
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Id
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