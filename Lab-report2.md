# **Servers and Bugs**
*Part 1*

String Server Function Code

```
public String handleRequest(URI url) {
    if (url.getPath().contains("/add-message")) {
        String parameters = url.getQuery();
        String query = parameters.split("=")[1];
        content.add(query);
    }
    return String.join("\n", content) + "\n";
}
```

