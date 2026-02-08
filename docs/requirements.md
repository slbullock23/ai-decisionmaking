# 📋 The Requirements
*The “Minimum Intelligence” list*

This document outlines what the system must do, how it should feel to users, and the minimum AI expectations required for a usable product.

---

## 1. Functional Requirements (What It Does)

- Users can create or join a decision group  
- Users can submit a decision along with a confidence score  
- The system records outcomes once results are known  
- A leaderboard displays individual and group accuracy over time  
- Users can view past decisions and compare confidence levels to outcomes  

---

## 2. Non-Functional Requirements (How It Feels)

- **Fast**  
  - Feedback should appear in under 1 second  

- **Fair**  
  - Scores cannot be edited after submission  

- **Simple**  
  - No complex setup  
  - Feels like a group chat, but with structure  

---

## 3. AI-Specific Requirements

- The app must function without AI  
- AI enhances decisions but never blocks them  
- If AI is unavailable, decisions are still logged and scored  
- AI feedback must be explainable in plain language  

---

## 4. User Stories

### Administrator / Developer

**As an administrator or developer**,  
I want to see all registered users  
so that I can track platform usage.

**Acceptance Criteria**
- Admin can view every user account  
- Admin can see the total number of users  

---

### Offline Access

**As a user**,  
I want to prompt the AI whether or not I am connected to WiFi  
so that I can use the app anywhere.

**Acceptance Criteria**
- User can make predictions without an internet connection  

---

### Team Management

**As a team leader**,  
I want to add or remove people from my team  
so that I can manage my group effectively.

**Acceptance Criteria**
- User can see:
  - Number of users on the team  
  - Teammate names  
  - Predictions made by teammates  
- User can add or remove members as needed  

---

### Confidence Scoring

**As a user**,  
I want to enter a confidence score for my decision  
so that the AI can analyze the chance of success.

**Acceptance Criteria**
- User can enter a confidence score as a percentage  
- AI uses this score to analyze decision quality  

---

### Leaderboard & Accuracy Tracking

**As a competitive group member**,  
I want to see a leaderboard that tracks my accuracy over time  
so that I can reality-check my predictions.

**Acceptance Criteria**
- Users can compare:
  - Their confidence scores  
  - AI-generated confidence or evaluation  
- User must be within 10% of the AI-generated score to move up the leaderboard  
- Users ranked low receive a warning in the app  

---

### Terms and Conditions

**As a user**,  
I want to read and accept the terms and conditions  
so that I understand the risks and rules of the app.

**Acceptance Criteria**
- Users can read or listen to the terms and conditions  
- Users must scroll through the full content before accepting  
- Acceptance is required before using the app  
