![Diagram](./images/cabbar0-4.png)


sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Writes a new note and clicks Save
    Browser->>Server: Send POST request to create a new note
    Server-->>Browser: Receive request, process, and create the note
    Browser->>Server: Send GET request for updated notes
    Server-->>Browser: Respond with updated notes
    Browser-->>User: Display updated notes to the user
