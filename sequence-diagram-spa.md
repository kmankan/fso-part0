sequenceDiagram
    participant browser
    participant server

    Note right of browser: User clicks the save button on the form
    browser->>server: POST new_note
    activate server
    Note over server: Server processes the request and issues a 302 redirect
    server-->>browser: 302 Redirect to /notes
    deactivate server

    browser->>server: GET /notes
    activate server
    Note over server: Server sends HTML document for notes page
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET /main.css
    activate server
    Note over server: Server sends CSS file
    server-->>browser: CSS file
    deactivate server

    browser->>server: GET /main.js
    activate server
    Note over server: Server sends JavaScript file
    server-->>browser: JavaScript file
    deactivate server

    browser->>server: GET /data.json
    activate server
    Note over server: Server sends JSON data of all notes
    server-->>browser: JSON data of notes
    deactivate server

    Note right of browser: Browser renders the updated notes list
