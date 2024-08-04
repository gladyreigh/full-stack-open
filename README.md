# Notes App Diagrams

This repository contains sequence diagrams for the notes app exercises. The diagrams are created using Mermaid syntax for GitHub Markdown.

## Diagrams

- [New Note Creation Diagram](#0.4-new-note-creation-diagram)
- [Single Page App Loading Diagram](#0.5-single-page-app-loading-diagram)
- [New Note Creation in Single Page App Diagram](#0.6-new-note-creation-in-single-page-app-diagram)

## 0.4: New Note Creation Diagram

This diagram illustrates the sequence of events when a user creates a new note by writing something into the text field and clicking the Save button on the page `https://studies.cs.helsinki.fi/exampleapp/notes`.

```mermaid
sequenceDiagram
    participant browser
    participant server

    %% User creates a new note
    browser->>browser: User types note content
    browser->>browser: User clicks Save button
    
    %% JavaScript code sends the new note to the server
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: Response (success or failure)
    deactivate server

    %% Optional: The browser might update the UI to reflect the new note
    Note right of browser: The browser updates the UI to display the new note
