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
doulaid_webapp->>doulaid_db: User step completion saved
user->>doulaid_webapp: User completes DoulaID milestone
doulaid_webapp->>doulaid_db: User milestone completion saved
doulaid_issuer->>doulaid_webapp: User milestone credential available
```

## Architecture
Webapp System requirements:
* DoulaID webapp available at known url and displayable in user browser
* DoulaID webapp database saves user progress
* DoulaID interacts with decentralized identifier for sign-in and to issue achivement verifiable credentials 
