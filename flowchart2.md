flowchart TD
    A[User navigates to /spa page] --> B[Browser sends GET /spa]
    B -->|304 Not Modified| C[HTML loaded from cache or server]

    C --> D[Browser sends GET /main.css]
    D -->|304 Not Modified| E[CSS loaded]

    C --> F[Browser sends GET /spa.js]
    F -->|304 Not Modified| G[SPA JavaScript loaded]

    G --> H[SPA JavaScript starts executing]
    H --> I[JS sends GET /data.json]
    I -->|304 Not Modified| J[Notes JSON data loaded]

    J --> K[SPA renders notes without full page reload]
