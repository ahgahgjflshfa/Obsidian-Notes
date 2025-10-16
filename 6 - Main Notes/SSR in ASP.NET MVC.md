2025-10-16 14:37

Status: In Progress

Tags: [[CSharp]], [[Server]]

---
# Topic
Understanding Server-Side Rendering in ASP.NET MVC

---
# Summary


---
# Key Takeaways
## 1. What SSR Means
Server-Side Rendering (SSR) means that HTML pages are generated on the server, not in the browser.
When a user sends a request:
```flow
Browser -> Controller -> Model / DB -> Razor View Engine -> HTML -> Browser
```

The Controller prepares data, the View (Razor) renders that data into HTML, and the browser receives the **final HTML page**.

Unlike modern SPA (Single Page Application) setups, there is **no sperate frontend** layer that renders views with JavaScript.

Therefore, ASP.NET MVC is **tightly coupled** — the frontend and backend live in the same application, making it *not a* "frontend-backend separated" architechture.

## 2. MVC Request Lifecycle
1. **IIS** receives the HTTP request and passes it to the application pool process (`w3wp.exe`).
2. The **Routing** module determines which Controller and Action to invoke.
3. The **Controller** executes logic and retrieves data (often from a service or database).
4. The **Razor View Engine** merges the `.cshtml` template with the Model to produce HTML.
5. The **HTML** response is returned to the browser.

This entire process happens -- the browser only displays the final HTML.

## 3. Routing in ASP.NET MVC
- **Conventional routing**: defined in `RouteConfig.cs` as `/{controller}/{action}/{id?}`
- **Attribute routing**: allows `[Route("path")]` directly on actions.
- **Purpose**: Human-readable URLs, SEO friendliness, and clear controller mapping.

---
# My Understanding


---
# Next Steps


---
# Reference

