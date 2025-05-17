<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="RefBucket API Documentation">
    <title>RefBucket API Documentation</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/normalize/8.0.1/normalize.min.css">
    <style>
        body { font-family: Arial, sans-serif; line-height: 1.6; margin: 20px; max-width: 800px; margin: auto; }
        h1, h2, h3 { color: #333; }
        code { background: #f4f4f4; padding: 2px 4px; border-radius: 4px; }
        pre { background: #f4f4f4; padding: 10px; overflow: auto; }
        .example { background: #eef; padding: 10px; border: 1px solid #ddd; margin-top: 10px; }
    </style>
</head>
<body>
    <h1>RefBucket API Documentation</h1>

    <h2>Description</h2>
    <p>This API allows users to capture and categorize URLs from a Chrome extension, saving them into specific categories like Article, Video, and more.</p>

    <h2>Base URL</h2>
    <code>https://sheets.googleapis.com</code>

    <h2>Endpoints</h2>
    <p><strong>Description:</strong> Returns the values from a specified range in your Google Sheet.</p>
    <pre><code>GET /spreadsheets/1q40f6djrhHSStT9FhT6ODuQ0WuaOG3fwrpzd99huXOQ/values/Sheet1!A1:D10</code></pre>

    <h3>Parameters</h3>
    <ul>
        <li><strong>range (required):</strong> The range of cells to fetch, e.g., Sheet1!A1:D10.</li>
        <li><strong>majorDimension (optional):</strong> Specifies the dimension of the data (ROWS or COLUMNS). Default is ROWS.</li>
        <li><strong>category (required):</strong> The category to filter URLs by (e.g., Article, Website, Video, Report, Blog).</li>
    </ul>

    <h2>Response</h2>
    <pre><code>{
    "count": 100,
    "metrics": {
        "total_urls_saved": 100,
        "average_urls_per_day": 5,
        "citation_ready_count": 85,
        "estimated_saved_time": "2 hours"
    },
    "results": [
        {
            "id": 1,
            "category": "Article",
            "url": "https://example.com/article1",
            "timestamp": "2025-05-07T12:00:00Z",
            "user_id": "User123"
        }
    ]
}</code></pre>

    <h2>Errors</h2>
    <ul>
        <li><strong>400 Bad Request:</strong> The request was malformed or missing required parameters.</li>
        <li><strong>401 Unauthorized:</strong> The API key was invalid or missing.</li>
        <li><strong>404 Not Found:</strong> The specified sheet or range does not exist.</li>
        <li><strong>500 Internal Server Error:</strong> An unexpected error occurred on the server.</li>
    </ul>
</body>
</html>
