0.6. Create a diagram depicting the situation where the user creates a new note using the single-page version of the app.

sequenceDiagram
participant User
participant Browser
participant Server

    User->>Browser: User writes a note "Hello world!" and presses "Save" button.
    Note right of Browser: JavaScript activates sending a form, doesnot upload the page.

    Browser->>Server
    Request Method: POST /new_note_spa
    Server-->>Browser: HTTP 201 Created

    Note right of Browser: JavaScript updates the page by adding new note to the list.

    Browser-->>User: Updated list with note:"Hello world!"
