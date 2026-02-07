---
name: readeck
description: Readeck is a simple web application that lets you save the precious readable content of web pages you like and want to keep forever. https://readeck.org/
allowed-tools: Bash(curl:*) Bash(jq:*) Read
---

# Browser Automation with agent-browser

Readeck API provides REST endpoints that allow you to interact with the Readeck application, enabling functionalities like saving bookmarks and extracting content. You can access it at <https://readeck-installation/api> and use authentication tokens for secure access. Use Bearer-Token to authenticate with the API.

Read the API Documentation here: <https://codeberg.org/readeck/readeck/src/branch/main/docs/api/base.md>

## Terminology

- Bookmarks are where you save the web content you like.
- The bookmark list is where you'll find all your saved bookmarks.
- You can add as many labels as you want to a bookmark. There is no limit as to what can be a label. You can even add emojis if you like them.
- Annotations: Found some interesting part in an article? You can highlight it!
- The Label List shows all the labels in your bookmark collection, with a number indicating how many bookmarks carry a given label.
- Collections let you easily organize and export your bookmarks by saving search requests of your choice. When you create a new bookmark that matches a collection's criteria, it will appear immediately. Here are some examples:
    - The unread articles (no picture or videos),
    - The archived articles from "wikipedia.org",
    - The pictures with the label "cat",

## Endpoints

GET /bookmarks
GET /bookmarks/{id}
GET /bookmarks/{id}/article
GET /bookmarks/{id}/article.{format} (allowed: epub, md)
GET /bookmarks/labels
GET /bookmarks/labels/{name}
GET /bookmarks/annotations
GET /bookmarks/{id}/annotations
GET /bookmarks/collections
GET /bookmarks/collections/{id}

