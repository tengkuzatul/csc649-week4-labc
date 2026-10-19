# Tech Stack Evaluation

## Project
Study planner: a web app that helps a student see all assignment deadlines
in one list and get reminders.

## Requirements that drive the decision
- FR2: The system shall show all tasks sorted by due date.
- FR3: The system shall send a reminder before a task is due.
- NFR1: The task list shall load within 2 seconds.
- NFR2: A reminder shall arrive within 1 minute of its scheduled time.
- NFR3: A student shall see only their own tasks.

## Options
- Option A: Static website (HTML and JavaScript) on GitHub Pages. Tasks are
  stored in the student's own browser.
- Option B: Python web app (Flask) with a SQLite database on a cloud host,
  with student logins.
- Option C: A low-code app builder with a ready-made database.

## Decision matrix
Weight: how important the criterion is for MY project (1 = low, 5 = high).
Score: how well each option does (1 = poor, 5 = excellent).

| Criterion                          | Weight | A score | B score | C score |
|------------------------------------|--------|---------|---------|---------|
| Fits my requirements               | 5      | 3       | 5       | 3       |
| Skills I already have              | 4      | 5       | 3       | 4       |
| Time to build before my deadline   | 4      | 5       | 3       | 4       |
| Free hosting and tools             | 3      | 5       | 3       | 2       |
| Performance and security needs     | 4      | 4       | 4       | 2       |
| Room to grow later                 | 2      | 2       | 4       | 1       |
| **Total (weighted)**               |        | **90**  | **82**  | **63**  |

How the totals were calculated (weight x score):
- A: (5x3) + (4x5) + (4x5) + (3x5) + (4x4) + (2x2) = 15 + 20 + 20 + 15 + 16 + 4 = 90
- B: (5x5) + (4x3) + (4x3) + (3x3) + (4x4) + (2x4) = 25 + 12 + 12 + 9 + 16 + 8 = 82
- C: (5x3) + (4x4) + (4x4) + (3x2) + (4x2) + (2x1) = 15 + 16 + 16 + 6 + 8 + 2 = 63

Why these weights:
- "Fits my requirements" is 5 because the reminder and privacy requirements decide whether the app is useful.
- "Skills" and "Time" are 4 because I have only 2 weeks and I know HTML better than Flask.
- "Free hosting" is 3 because I can pay nothing, but the free tiers are enough for a prototype.
- "Room to grow" is only 2 because this is a prototype, not a product.

## Decision record
- **Context:** A 2-week prototype of a study planner. I know HTML and basic Python. I cannot pay for hosting.
- **Decision:** Option A, a static website on GitHub Pages.
- **Reasons:** It scored highest (90 against 82). It is free, I can finish it in 2 weeks, and it deploys with the same pipeline from the lab. Because tasks stay in the student's own browser, each student sees only their own tasks (NFR3) without needing a login system.
- **Consequences:** Easy: free hosting, fast pages (NFR1), and no server to maintain. Harder: a static site cannot send reminders when the page is closed, so NFR2 is met only while the page is open. Tasks also do not sync between a phone and a laptop.
- **Risks and next review:** If testers say reminders must work when the page is closed, Option B becomes the better choice (it scored 5 for "fits my requirements"). I will review the decision after the first user test.