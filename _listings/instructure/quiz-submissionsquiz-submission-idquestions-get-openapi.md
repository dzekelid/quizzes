---
swagger: "2.0"
x-collection-name: Instructure
x-complete: 0
info:
  title: Instructure Canvas Quiz Submissions API Get all quiz submission questions.
  description: Get all quiz submission questions..
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
    get:
      summary: Get a single quiz
      description: Get a single quiz.
      operationId: get-a-single-quiz
      x-api-path-slug: coursescourse-idquizzesid-get
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Id
    put:
      summary: Edit a quiz
      description: Edit a quiz.
      operationId: edit-a-quiz
      x-api-path-slug: coursescourse-idquizzesid-put
      parameters:
      - in: query
        name: quiz[notify_of_update]
        description: If true, notifies users that the quiz has changed
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Id
  /courses/{course_id}/quizzes/id/reorder:
    post:
      summary: Reorder quiz items
      description: Reorder quiz items.
      operationId: reorder-quiz-items
      x-api-path-slug: coursescourse-idquizzesidreorder-post
      parameters:
      - in: query
        name: order[][id]
        description: The associated item&#39;s unique identifier
      - in: query
        name: order[][type]
        description: 'The type of item is either &#39;question&#39; or &#39;group&#39;nn        n        n          Allowed
          values: question, group'
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Id
      - Reorder
  /courses/{course_id}/quizzes/id/submission_users/message:
    post:
      summary: Send a message to unsubmitted or submitted users for the quiz
      description: Send a message to unsubmitted or submitted users for the quiz.
      operationId: send-a-message-to-unsubmitted-or-submitted-users-for-the-quiz
      x-api-path-slug: coursescourse-idquizzesidsubmission-usersmessage-post
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Id
      - Submission
      - Users
      - Message
  /courses/{course_id}/quizzes/id/validate_access_code:
    post:
      summary: Validate quiz access code
      description: Validate quiz access code.
      operationId: validate-quiz-access-code
      x-api-path-slug: coursescourse-idquizzesidvalidate-access-code-post
      parameters:
      - in: query
        name: access_code
        description: The access code being validated
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Id
      - Validate
      - Access
      - Code
  /courses/{course_id}/quizzes/quiz_id/extensions:
    post:
      summary: Set extensions for student quiz submissions
      description: Set extensions for student quiz submissions.
      operationId: set-extensions-for-student-quiz-submissions
      x-api-path-slug: coursescourse-idquizzesquiz-idextensions-post
      parameters:
      - in: query
        name: extend_from_end_at
        description: The number of minutes to extend the quiz beyond the quiz&#39;s
          currentnending time
      - in: query
        name: extend_from_now
        description: The number of minutes to extend the quiz from the current time
      - in: query
        name: extra_attempts
        description: Number of times the student is allowed to re-take the quiz over
          thenmultiple-attempt limit
      - in: query
        name: extra_time
        description: The number of extra minutes to allow for all attempts
      - in: query
        name: manually_unlocked
        description: Allow the student to take the quiz even if it&#39;s locked for
          everyonenelse
      - in: query
        name: user_id
        description: The ID of the user we want to add quiz extensions for
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Extensions
  /courses/{course_id}/quizzes/quiz_id/groups:
    post:
      summary: Create a question group
      description: Create a question group.
      operationId: create-a-question-group
      x-api-path-slug: coursescourse-idquizzesquiz-idgroups-post
      parameters:
      - in: query
        name: quiz_groups[][assessment_question_bank_id]
        description: The id of the assessment question bank to pull questions from
      - in: query
        name: quiz_groups[][name]
        description: The name of the question group
      - in: query
        name: quiz_groups[][pick_count]
        description: The number of questions to randomly select for this group
      - in: query
        name: quiz_groups[][question_points]
        description: The number of points to assign to each question in the group
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Groups
  /courses/{course_id}/quizzes/quiz_id/groups/{id}:
    delete:
      summary: Delete a question group
      description: Delete a question group.
      operationId: delete-a-question-group
      x-api-path-slug: coursescourse-idquizzesquiz-idgroupsid-delete
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Groups
      - Id
    get:
      summary: Get a single quiz group
      description: Get a single quiz group.
      operationId: get-a-single-quiz-group
      x-api-path-slug: coursescourse-idquizzesquiz-idgroupsid-get
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Groups
      - Id
    put:
      summary: Update a question group
      description: Update a question group.
      operationId: update-a-question-group
      x-api-path-slug: coursescourse-idquizzesquiz-idgroupsid-put
      parameters:
      - in: query
        name: quiz_groups[][name]
        description: The name of the question group
      - in: query
        name: quiz_groups[][pick_count]
        description: The number of questions to randomly select for this group
      - in: query
        name: quiz_groups[][question_points]
        description: The number of points to assign to each question in the group
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Groups
      - Id
  /courses/{course_id}/quizzes/quiz_id/groups/{id}/reorder:
    post:
      summary: Reorder question groups
      description: Reorder question groups.
      operationId: reorder-question-groups
      x-api-path-slug: coursescourse-idquizzesquiz-idgroupsidreorder-post
      parameters:
      - in: query
        name: order[][id]
        description: The associated item&#39;s unique identifier
      - in: query
        name: order[][type]
        description: 'The type of item is always &#39;question&#39; for a groupnn        n        n          Allowed
          values: question'
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Groups
      - Id
      - Reorder
  /courses/{course_id}/quizzes/quiz_id/ip_filters:
    get:
      summary: Get available quiz IP filters.
      description: Get available quiz ip filters..
      operationId: get-available-quiz-ip-filters
      x-api-path-slug: coursescourse-idquizzesquiz-idip-filters-get
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Ip
      - Filters
  /courses/{course_id}/quizzes/quiz_id/questions:
    get:
      summary: List questions in a quiz or a submission
      description: List questions in a quiz or a submission.
      operationId: list-questions-in-a-quiz-or-a-submission
      x-api-path-slug: coursescourse-idquizzesquiz-idquestions-get
      parameters:
      - in: query
        name: quiz_submission_attempt
        description: The attempt of the submission you want the questions for
      - in: query
        name: quiz_submission_id
        description: If specified, the endpoint will return the questions that were
          presentednfor that submission
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Questions
    post:
      summary: Create a single quiz question
      description: Create a single quiz question.
      operationId: create-a-single-quiz-question
      x-api-path-slug: coursescourse-idquizzesquiz-idquestions-post
      parameters:
      - in: query
        name: question[answers]
        description: no description
      - in: query
        name: question[correct_comments]
        description: The comment to display if the student answers the question correctly
      - in: query
        name: question[incorrect_comments]
        description: The comment to display if the student answers incorrectly
      - in: query
        name: question[neutral_comments]
        description: The comment to display regardless of how the student answered
      - in: query
        name: question[points_possible]
        description: The maximum amount of points received for answering this questionncorrectly
      - in: query
        name: question[position]
        description: The order in which the question will be displayed in the quiz
          in relationnto other questions
      - in: query
        name: question[question_name]
        description: The name of the question
      - in: query
        name: question[question_text]
        description: The text of the question
      - in: query
        name: question[question_type]
        description: The type of question
      - in: query
        name: question[quiz_group_id]
        description: The id of the quiz group to assign the question to
      - in: query
        name: question[text_after_answers]
        description: no description
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Questions
  /courses/{course_id}/quizzes/quiz_id/questions/{id}:
    delete:
      summary: Delete a quiz question
      description: Delete a quiz question.
      operationId: delete-a-quiz-question
      x-api-path-slug: coursescourse-idquizzesquiz-idquestionsid-delete
      parameters:
      - in: query
        name: id
        description: The quiz question&#39;s unique identifier
      - in: query
        name: quiz_id
        description: The associated quiz&#39;s unique identifier
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Questions
      - Id
    get:
      summary: Get a single quiz question
      description: Get a single quiz question.
      operationId: get-a-single-quiz-question
      x-api-path-slug: coursescourse-idquizzesquiz-idquestionsid-get
      parameters:
      - in: query
        name: id
        description: The quiz question unique identifier
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Questions
      - Id
    put:
      summary: Update an existing quiz question
      description: Update an existing quiz question.
      operationId: update-an-existing-quiz-question
      x-api-path-slug: coursescourse-idquizzesquiz-idquestionsid-put
      parameters:
      - in: query
        name: id
        description: The quiz question&#39;s unique identifier
      - in: query
        name: question[answers]
        description: no description
      - in: query
        name: question[correct_comments]
        description: The comment to display if the student answers the question correctly
      - in: query
        name: question[incorrect_comments]
        description: The comment to display if the student answers incorrectly
      - in: query
        name: question[neutral_comments]
        description: The comment to display regardless of how the student answered
      - in: query
        name: question[points_possible]
        description: The maximum amount of points received for answering this questionncorrectly
      - in: query
        name: question[position]
        description: The order in which the question will be displayed in the quiz
          in relationnto other questions
      - in: query
        name: question[question_name]
        description: The name of the question
      - in: query
        name: question[question_text]
        description: The text of the question
      - in: query
        name: question[question_type]
        description: The type of question
      - in: query
        name: question[quiz_group_id]
        description: The id of the quiz group to assign the question to
      - in: query
        name: question[text_after_answers]
        description: no description
      - in: query
        name: quiz_id
        description: The associated quiz&#39;s unique identifier
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Questions
      - Id
  /courses/{course_id}/quizzes/quiz_id/reports:
    get:
      summary: Retrieve all quiz reports
      description: Retrieve all quiz reports.
      operationId: retrieve-all-quiz-reports
      x-api-path-slug: coursescourse-idquizzesquiz-idreports-get
      parameters:
      - in: query
        name: includes_all_versions
        description: Whether to retrieve reports that consider all the submissions
          or only thenmost recent
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Reports
    post:
      summary: Create a quiz report
      description: Create a quiz report.
      operationId: create-a-quiz-report
      x-api-path-slug: coursescourse-idquizzesquiz-idreports-post
      parameters:
      - in: query
        name: include
        description: Whether the output should include documents for the file and/or
          progressnobjects associated with this report
      - in: query
        name: quiz_report[includes_all_versions]
        description: Whether the report should consider all submissions or only the
          most recent
      - in: query
        name: quiz_report[report_type]
        description: The type of report to be generated
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Reports
  /courses/{course_id}/quizzes/quiz_id/reports/{id}:
    delete:
      summary: Abort the generation of a report, or remove a previously generated
        one
      description: Abort the generation of a report, or remove a previously generated
        one.
      operationId: abort-the-generation-of-a-report-or-remove-a-previously-generated-one
      x-api-path-slug: coursescourse-idquizzesquiz-idreportsid-delete
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Reports
      - Id
    get:
      summary: Get a quiz report
      description: Get a quiz report.
      operationId: get-a-quiz-report
      x-api-path-slug: coursescourse-idquizzesquiz-idreportsid-get
      parameters:
      - in: query
        name: include
        description: Whether the output should include documents for the file and/or
          progressnobjects associated with this report
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Reports
      - Id
  /courses/{course_id}/quizzes/quiz_id/statistics:
    get:
      summary: Fetching the latest quiz statistics
      description: Fetching the latest quiz statistics.
      operationId: fetching-the-latest-quiz-statistics
      x-api-path-slug: coursescourse-idquizzesquiz-idstatistics-get
      parameters:
      - in: query
        name: all_versions
        description: Whether the statistics report should include all submissions
          attempts
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Statistics
  /courses/{course_id}/quizzes/quiz_id/submissions:
    get:
      summary: Get all quiz submissions.
      description: Get all quiz submissions..
      operationId: get-all-quiz-submissions
      x-api-path-slug: coursescourse-idquizzesquiz-idsubmissions-get
      parameters:
      - in: query
        name: include[]
        description: Associations to include with the quiz submission
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Submissions
    post:
      summary: Create the quiz submission (start a quiz-taking session)
      description: Create the quiz submission (start a quiz-taking session).
      operationId: create-the-quiz-submission-start-a-quiztaking-session
      x-api-path-slug: coursescourse-idquizzesquiz-idsubmissions-post
      parameters:
      - in: query
        name: access_code
        description: Access code for the Quiz, if any
      - in: query
        name: preview
        description: Whether this should be a preview QuizSubmission and not count
          towards thenuser&#39;s course record
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Submissions
  /courses/{course_id}/quizzes/quiz_id/submissions/self/files:
    post:
      summary: Upload a file
      description: Upload a file.
      operationId: upload-a-file
      x-api-path-slug: coursescourse-idquizzesquiz-idsubmissionsselffiles-post
      parameters:
      - in: query
        name: name
        description: The name of the quiz submission file
      - in: query
        name: on_duplicate
        description: How to handle duplicate names
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Submissions
      - Self
      - Files
  /courses/{course_id}/quizzes/quiz_id/submissions/{id}:
    get:
      summary: Get a single quiz submission.
      description: Get a single quiz submission..
      operationId: get-a-single-quiz-submission
      x-api-path-slug: coursescourse-idquizzesquiz-idsubmissionsid-get
      parameters:
      - in: query
        name: include[]
        description: Associations to include with the quiz submission
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Submissions
      - Id
    put:
      summary: Update student question scores and comments.
      description: Update student question scores and comments..
      operationId: update-student-question-scores-and-comments
      x-api-path-slug: coursescourse-idquizzesquiz-idsubmissionsid-put
      parameters:
      - in: query
        name: attempt
        description: The attempt number of the quiz submission that should be updated
      - in: query
        name: fudge_points
        description: Amount of positive or negative points to fudge the total score
          by
      - in: query
        name: questions
        description: A set of scores and comments for each question answered by the
          student
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Submissions
      - Id
  /courses/{course_id}/quizzes/quiz_id/submissions/{id}/complete:
    post:
      summary: Complete the quiz submission (turn it in).
      description: Complete the quiz submission (turn it in)..
      operationId: complete-the-quiz-submission-turn-it-in
      x-api-path-slug: coursescourse-idquizzesquiz-idsubmissionsidcomplete-post
      parameters:
      - in: query
        name: access_code
        description: Access code for the Quiz, if any
      - in: query
        name: attempt
        description: The attempt number of the quiz submission that should be completed
      - in: query
        name: validation_token
        description: The unique validation token you received when this Quiz Submission
          wasncreated
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Submissions
      - Id
      - Complete
  /courses/{course_id}/quizzes/quiz_id/submissions/{id}/events:
    get:
      summary: Retrieve captured events
      description: Retrieve captured events.
      operationId: retrieve-captured-events
      x-api-path-slug: coursescourse-idquizzesquiz-idsubmissionsidevents-get
      parameters:
      - in: query
        name: attempt
        description: The specific submission attempt to look up the events for
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Submissions
      - Id
      - Events
    post:
      summary: Submit captured events
      description: Submit captured events.
      operationId: submit-captured-events
      x-api-path-slug: coursescourse-idquizzesquiz-idsubmissionsidevents-post
      parameters:
      - in: query
        name: quiz_submission_events[]
        description: The submission events to be recorded
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Submissions
      - Id
      - Events
  /courses/{course_id}/quizzes/quiz_id/submissions/{id}/time:
    get:
      summary: Get current quiz submission times.
      description: Get current quiz submission times..
      operationId: get-current-quiz-submission-times
      x-api-path-slug: coursescourse-idquizzesquiz-idsubmissionsidtime-get
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quizzes
      - Quiz
      - Id
      - Submissions
      - Id
      - Time
  /courses/{course_id}/quiz_extensions:
    post:
      summary: Set extensions for student quiz submissions
      description: Set extensions for student quiz submissions.
      operationId: set-extensions-for-student-quiz-submissions
      x-api-path-slug: coursescourse-idquiz-extensions-post
      parameters:
      - in: query
        name: extend_from_end_at
        description: The number of minutes to extend the quiz beyond the quiz&#39;s
          currentnending time
      - in: query
        name: extend_from_now
        description: The number of minutes to extend the quiz from the current time
      - in: query
        name: extra_attempts
        description: Number of times the student is allowed to re-take the quiz over
          thenmultiple-attempt limit
      - in: query
        name: extra_time
        description: The number of extra minutes to allow for all attempts
      - in: query
        name: manually_unlocked
        description: Allow the student to take the quiz even if it&#39;s locked for
          everyonenelse
      - in: query
        name: user_id
        description: The ID of the user we want to add quiz extensions for
      responses:
        200:
          description: OK
      tags:
      - Courses
      - Course
      - Id
      - Quiz
      - Extensions
  /quiz_submissions/{quiz_submission_id}/questions:
    get:
      summary: Get all quiz submission questions.
      description: Get all quiz submission questions..
      operationId: get-all-quiz-submission-questions
      x-api-path-slug: quiz-submissionsquiz-submission-idquestions-get
      parameters:
      - in: query
        name: include[]
        description: Associations to include with the quiz submission question
      responses:
        200:
          description: OK
      tags:
      - Quiz
      - Submissions
      - Quiz
      - Submission
      - Id
      - Questions
    post:
      summary: Answering questions
      description: Answering questions.
      operationId: answering-questions
      x-api-path-slug: quiz-submissionsquiz-submission-idquestions-post
      parameters:
      - in: query
        name: access_code
        description: Access code for the Quiz, if any
      - in: query
        name: attempt
        description: The attempt number of the quiz submission being taken
      - in: query
        name: quiz_questions[]
        description: Set of question IDs and the answer value
      - in: query
        name: validation_token
        description: The unique validation token you received when the Quiz Submission
          wasncreated
      responses:
        200:
          description: OK
      tags:
      - Quiz
      - Submissions
      - Quiz
      - Submission
      - Id
      - Questions
  /quiz_submissions/{quiz_submission_id}/questions/id/flag:
    put:
      summary: Flagging a question.
      description: Flagging a question..
      operationId: flagging-a-question
      x-api-path-slug: quiz-submissionsquiz-submission-idquestionsidflag-put
      parameters:
      - in: query
        name: access_code
        description: Access code for the Quiz, if any
      - in: query
        name: attempt
        description: The attempt number of the quiz submission being taken
      - in: query
        name: validation_token
        description: The unique validation token you received when the Quiz Submission
          wasncreated
      responses:
        200:
          description: OK
      tags:
      - Quiz
      - Submissions
      - Quiz
      - Submission
      - Id
      - Questions
      - Id
      - Flag
  /quiz_submissions/{quiz_submission_id}/questions/id/unflag:
    put:
      summary: Unflagging a question.
      description: Unflagging a question..
      operationId: unflagging-a-question
      x-api-path-slug: quiz-submissionsquiz-submission-idquestionsidunflag-put
      parameters:
      - in: query
        name: access_code
        description: Access code for the Quiz, if any
      - in: query
        name: attempt
        description: The attempt number of the quiz submission being taken
      - in: query
        name: validation_token
        description: The unique validation token you received when the Quiz Submission
          wasncreated
      responses:
        200:
          description: OK
      tags:
      - Quiz
      - Submissions
      - Quiz
      - Submission
      - Id
      - Questions
      - Id
      - Unflag
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