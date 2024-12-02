# DoulaID Design

## Ecosystem
The following diagram of a DoulaID webapp and the integration with the **Cardano Watcher** providing verification via the Cardano blockchain:
![Ecosystem](DoulaID_Ecosystem.png)

## Flow of events
The following sequence diagrams show a simplified flow of events for the registration, step completion, and verification of milestone completion:

### DoulaID user created, completed steps saved, and verifiable credentials issued
```mermaid
sequenceDiagram
actor user
user->>doulaid_webapp: Create User
user->>user_agent: User agent created
doulaid_webapp->>doulaid_db: User Saved
doulaid_webapp->>doulaid_webapp: Repeat the following, per step
user->>doulaid_webapp: User completes DoulaID step (1 to 5)
user->>doulaid_webapp: User uploads step (1 to 5) DoulaID step evidence
doulaid_webapp->>doulaid_db: User step (1 to 5) completion saved
doulaid_issuer->>doulaid_webapp: User achievement credential available
doulaid_issuer->>user_agent: User receives step (1 to 5) verifiable credentials
doulaid_webapp->>doulaid_webapp: View completed Step 1 Doula certifications
doulaid_webapp->>doulaid_webapp: View Step 2 NPI
doulaid_webapp->>doulaid_webapp: View Step 3 Doula Business
doulaid_webapp->>doulaid_webapp: View Step 4 ePREP
doulaid_webapp->>doulaid_webapp: View Step 5 Medicaid ID
user_agent->>doulaid_verifier: User credential verified
```

## Architecture
Webapp System requirements:
* DoulaID webapp available at known url and displayable in user browser
* DoulaID webapp database saves user progress
* DoulaID interacts with decentralized identifier for sign-in and to issue achivement verifiable credentials 
* DoulaID issuer/verifier verifies user key state seen in Cardano Watcher

## UX Designs
For the current webapp FIGMA designs see here: https://www.figma.com/proto/SAIEqYczR7VTmEzxcJcgLo/RootsID?node-id=31-607&t=jRlcbIHjCQQP2BCF-1
<img width="1417" alt="image" src="https://github.com/user-attachments/assets/92dfea41-4bbe-4b13-bc46-a9459b2f8d23">
The future looking mobile design is:
https://www.doulaid.com/doulaid-app
