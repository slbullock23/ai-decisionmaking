1. The Proposal (proposal.md)

Think of this as: the “What problem are we actually solving?” pitch

Problem Statement
    Groups make decisions all the time: friends, teams, clubs, student orgs, but those decisions are usually inconsistent. The loudest voice wins, confidence is not measured, and there is no record of who was actually right. Existing tools like group chats, polls, and spreadsheets capture opinions, not decision quality. There is no way to tell if a group decision is better than a single person’s guess.

Target Users
    Small Focused groups (5 to 20 people) making repeat decisions:
    Students working on projects
    Friends debating sports outcomes
    Clubs deciding budgets or events
    Beginner finance or banking clubs practicing risk assessment
    Sports, banking, and similar domains are test environments, not the end goal. They are structured, measurable, and give fast feedback, which makes them ideal for validating group decision intelligence.

Solution Overview
    A collaborative decision making app where users submit:
        A decision (for example, “Approve this loan,” “Team A will win,” “We should fund this event”)
        A confidence score (for example, 1 to 10 or a percentage)

The system aggregates all the inputs, tracks outcomes, and uses AI to:
    Flag disagreements
    Highlight missing perspectives
    Show when the group may be overconfident or divided

Over time, the app shows who is accurate, when groups outperform individuals, and how confidence aligns with reality.

Tech Stack Justification
    Python (backend): strong for data analysis, probability, and AI integration
    Web framework: simple, responsive UI for fast group interaction
    AI API: used as an advisor, not a decision maker
