Exercise 0.6

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: The user submits a new note
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa <br/> Body: { <br/> "content": "test post spa" <br/> date: "2024-12-24T14:56:37.108Z" <br/>}
    activate server
    server-->>browser: Response 201 Created
    deactivate server

    Note right of browser: The browser dynamically updates the list of notes on the page
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, { "content": "new note", "date": "2024-12-24" }]
    deactivate server

    Note right of browser: The browser re-renders the updated notes list
