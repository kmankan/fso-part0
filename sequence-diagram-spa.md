sequenceDiagram
    participant browser
    participant server

    browser->>server: GET /spa
    activate server
    Note over server: Server sends the HTML document for the SPA
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET /spa/main.css
    activate server
    Note over server: Server sends the CSS file for styling
    server-->>browser: CSS file
    deactivate server

    browser->>server: GET /spa/spa.js
    activate server
    Note over server: Server sends the JavaScript file specific to SPA
    server-->>browser: JavaScript file
    deactivate server

    browser->>server: GET /spa/data.json
    activate server
    Note over server: Server sends the initial data as JSON
    server-->>browser: JSON data of notes
    deactivate server

    Note right of browser: Browser executes JavaScript to render the notes on the page
