2025-10-09 08:32

Status: Done

Tags: [[CSharp]]

---
# Topic
Understanding how `View()` works in the ASP.NET MVC pattern, and how it automatically maps to the corresponding `.cshtml` files.

---
# Key Takeaways
## 1. MVC Overview
- **Model** -> Handles business logic and data (connected to Oracle DB).
- **View** -> The UI layer (`cshtml` using Razor templates).
- **Controller** -> The brain of the request; receives input, calls Models, returns a View.

## 2. How View() Works
When you write:

```csharp
public IActionResult Index() {
    return View();
}
```

ASP.NET MVC automatically looks for the matching view file using Convention over Configuration:

```
/Views/{ControllerName}/{ActionName}.cshtml
```

So in this example:

```
Views/Home/Index.cshtml
```

If not found, it falls back to:

```
Views/Shared/Index.cshtml
```

That's why you usually don't need to specify the path manually -- the framework already knows where to find it.

## 3. Manually Selecting a View
You can explicitly return another view:

```csharp
return View("Dashboard");
```

This will look for:

```
Views/Home/Dashboard.cshtml
```

Or Use an absolute path:

```csharp
return View("~/Views/Shared/CustomError.cshtml")
```


---
# My Understanding
I find this convention-based file lookup super elegant.
It makes the code cleaner because I don't need to hardcode view paths -- the framework handles it based on controller/action names.
Next, I want to dive deeper into Razor syntax and how data is passed from Controller -> View.

---
# Next Steps
- Learn Razor syntax (`@model`, `@foreach`, `@Html.Partial`, etc.)
- Study data passing (`ViewBag`, `ViewData`, `Model`)
- Understand JWT validation flow after SSO login
- Learn how Oracle integration works (Repository pattern)

---
# Reference

