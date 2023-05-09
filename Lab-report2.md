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

Image 1:

![image](String_Server_1.png)

In this image, a word "Hello" is added, which called the function of `handleRequest()`. The argument for this function is the url, `localhost:8000/add-message?s=Hello`. For this argument, the function initiated a new variable called "parameters" to store the query part of this url, and the eventually get the value of the content to add, which is after the "=", "Hello" specifically.


Image 2:

![image](String_Server_2.png)

In this image, a string "How are you" is added. The same function as the last image is called, which is `handleRequest()`. The argument is still the url, but the value of content to add is changed to "How are you". Nevertheless, the function reacted as the last image and added this string to the content list.


*Part 2*
