<img width="603" height="541" alt="Screenshot 2026-02-18 at 9 53 57 PM" src="https://github.com/user-attachments/assets/72be2605-7058-4ca2-8d41-3ec4a5c4f5de" />
flowchart LR

    %% Actors
    SG[👮 Security Guard]
    R[🏠 Resident]
    A[🛠 Society Admin]

    %% System Boundary

    subgraph mygat_Application

        UC1((Log Visitor Entry))
        UC2((Record Visitor Exit))
        UC3((Login via OTP))
        UC4((Verify Phone Number))
        UC5((Receive Visit Notification))
        UC6((Approve / Deny Visitor))
        UC7((Register Account))
        UC8((Verify Resident Registration))
        UC9((Deactivate / Ban User))

    end

    %% Actor Connections
    SG --> UC3
    SG --> UC1
    SG --> UC2

    R --> UC3
    R --> UC7
    R --> UC5
    R --> UC6

    A --> UC3
    A --> UC8
    A --> UC9

    %% Relationships
    UC3 -. include .-> UC4
    UC1 --> UC5
    UC6 --> SG
