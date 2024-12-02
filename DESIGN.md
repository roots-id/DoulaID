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
doulaid_webapp->>doulaid_db: User Saved
user->>doulaid_webapp: User completes DoulaID step
user->>doulaid_webapp: User uploads DoulaID step evidence
doulaid_webapp->>doulaid_db: User step completion saved
user->>doulaid_webapp: User completes DoulaID step
doulaid_webapp->>doulaid_db: User step completion saved
doulaid_issuer->>doulaid_webapp: User achievement credential available
doulaid_issuer->>user_agent: User key state lookup
doulaid_issuer->>user_agent: User milestone credential issued
user_agent->>doulaid_issuer: User credential verified
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
