0.5. Create a diagram depicting the situation where the user goes to the single-page app version of the notes app at https://studies.cs.helsinki.fi/exampleapp/spa.

sequenceDiagram
participant User
participant Browser
participant Server

    User->>Browser: Goes to address https://studies.cs.helsinki.fi/exampleapp/spa
    Browser->>Server: Request Method: GET
    Server-->>Browser: HTML document
    Status Code: 200 OK

    Browser->>Server: GET /main.css
    Server-->>Browser: CSS file
    Status Code: 200 OK

    Browser->>Server: GET /main.js
    Server-->>Browser: JavaScript file
    Status Code: 200 OK

    Note right of Browser: JavaScript suoritetaan, joka hakee muistiinpanot JSON-muodossa

    Browser->>Server: GET /data.json
    Server-->>Browser: JSON-data (Status 200 OK)

    Browser-->>User: Shows notes in the app.
