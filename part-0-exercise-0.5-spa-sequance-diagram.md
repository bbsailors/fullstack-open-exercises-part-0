![Diagram](mermaid-diagram-2023-09-02-215356.png)

sequenceDiagram
    participant browser
    participant spa
    participant api_server
    participant user

    Note right of user: User types a new note and then clicks Save button

    browser->>spa: User interaction
    spa->>browser: Capture user input

    spa->>api_server: POST /api/notes
    activate api_server
    api_server-->>spa: New note saved successfully and will be displayed on browser
    deactivate api_server

    spa->>browser: Update UI with new note

    Note right of browser: SPA updates the page without a full refresh
