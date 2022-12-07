### Exercise 04
sequenceDiagram
browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note

note over server: Server sends status code of 302 that redirects the browser


browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
server-->>browser: HTML-code
browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
server-->>browser: main.css
browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
server->>browser: main.js

note over browser: browser starts executing js-code that requests JSON data from server 


browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
server-->>browser: [{"content":"testando","date":"2022-12-06T19:03:55.775Z"}, ...]

note over browser: browser executes the event handler that renders notes to display

