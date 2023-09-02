[Diagram](mermaid-diagram-2023-09-02-221116.png)


sequenceDiagram
    participant browser
    participant spa
    participant server
    participant user

    Note right of user: User types a new note and clicks Save

    user->>browser: Interact with SPA
    browser->>spa: Capture user input
    activate spa
    spa->>server: POST /api/notes (Create new note)
    activate server
    server-->>spa: New note saved successfully
    deactivate server
    spa->>browser: Update UI with new note
    deactivate spa

    Note right of browser: SPA updates the page without a full refresh
