2. The Requirements (requirements.md)
Think of this as: the “Minimum Viable Intelligence” list
Functional Requirements (What it does)
	•	Users can create or join a decision group
	•	Users can submit a decision and a confidence score
	•	The system records outcomes once they are known
	•	A leaderboard shows individual and group accuracy over time
	•	Users can view past decisions and how confidence compared to results
Non Functional Requirements (How it feels)
	•	Fast: feedback should appear in under 1 second
	•	Fair: scores cannot be edited after submission
	•	Simple: no complex setup, works like a group chat with structure
AI Specific Requirements
	•	The app must function without AI (AI enhances, not blocks decisions)
	•	If AI is unavailable, decisions are still logged and scored
	•	AI feedback must be explainable in plain language


User Stories
	•	As an administrator or developer, we should be able to go into the app and see all of the users that have created accounts so that we see how many people are using the platform.
	◦	Acceptance Criteria
Admin should be able to see every user in the app, and know how many users are using the app.
	•	As a user, I should be able to prompt the AI whether or not I am connected to WiFi, so I can use the app anywhere.
	◦	Acceptance Criteria
User should be able to make their predictions in the app without WiFi
	•	As a user, I should be able to add/remove people from my team as a team leader, so I can manage my teammates. 
	◦	Acceptance Criteria
User should be able to see how many users are on their team, their  names, and should be able to see the predictions they are making on the app.
User should be able to remove or add users to the team when necessary.
	•	As a user I should be able to enter a confidence score for my decision, so the AI tool can analyze the chance of success based on the entered score.
	◦	Acceptance Criteria
User should be able to enter a confidence score as a percentage which the AI tool will use to analyze the chance of success.
	•	As a competitive group member I want to see a leaderboard that tracks how accurate I am overtime, so I can have a reality check.
	◦	Acceptance Criteria
Users can see their given confidence scores compared to the score returned by the AI.
User needs to be within 10% of the AI-given score to move up in the leaderboard.
If User is low on the leaderboard, they should have a warning in the app.
	•	As a user I need to be able to read and accept the terms and conditions for the app, so that I can fully understand the terms and potential risks of the app.
	◦	Acceptance Criteria
Users can read, or listen to the terms and conditions and must through before accepting and using the app.

