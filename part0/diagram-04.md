0.4. Create a diagram depicting the situation where the user creates a new note on the page https://studies.cs.helsinki.fi/exampleapp/notes by writing something into the text field and clicking the Save button.

sequenceDiagram
participant User
participant Browser
participant Server

    User -->> Browser
    user writes a note "Hello world!" and presses "Save" button.

    Browser-->> Server
    Server adds new note to list on https://studies.cs.helsinki.fi/exampleapp/new_note
    Request Method: POST

    Server-->> Browser
    HTTP 302 Found

    Browser-->> Server    Browser redirects to updated page https://studies.cs.helsinki.fi/exampleapp/notes
    Request Method: GET

    Server-->> Browser
    Status Code: 200 OK
    HTML document

    Browser-->> Server
    Request URL: https://studies.cs.helsinki.fi/exampleapp/main.css
    Request Method: GET

    Server-->> Browser
    Status Code: 200 OK
    activates css file

    Browser-->> Server
    Request URL: https://studies.cs.helsinki.fi/exampleapp/main.js
    Request Method: GET

    Server-->> Browser
    Status Code: 200 OK
    activates js file

    Browser starts to execute JavaScript code and fetches JSON from the server.

    Browser-->> Server
    Request URL:https://studies.cs.helsinki.fi/exampleapp/data.json
    Request Method:GET

    Server-->> Browser
    JavaScript is running in the browser and uses JSON to create a list of notes.
    Status Code:200 OK

    Browser -->> User
    Browser shows an updated page with note "Hello world!".
