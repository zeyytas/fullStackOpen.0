flowchart TD
    A[User types note and clicks Save button] --> B[Browser sends POST to /new_note]
    B -->|Server responds with 302 Redirect| C[Browser navigates to /notes]

    C --> D[Browser sends GET /notes]
    D -->|Server returns HTML| E[HTML received]
    
    E --> F[Browser sends GET /main.css]
    F -->|304 Not Modified| G[CSS loaded from cache]

    E --> H[Browser sends GET /main.js]
    H -->|304 Not Modified| I[JS loaded from cache]

    I --> J[Browser executes JS code]
    J --> K[JS sends GET /data.json]
    K -->|200 OK with updated notes| L[Browser renders updated notes on the page]
