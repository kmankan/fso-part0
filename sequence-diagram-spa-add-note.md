sequenceDiagram
    participant browser
    participant server

    Note right of browser: User enters a note and clicks the save button
    Note right of browser: JavaScript prevents default form submission

    browser->>server: POST new_note_spa (JSON: {content, date})
    activate server
    Note over server: Server processes the POST request
    server-->>browser: 201 Created
    deactivate server

    Note right of browser: JavaScript adds note to local list
    Note right of browser: JavaScript updates the display of notes on the page

    Note right of browser: No further HTTP requests are made
