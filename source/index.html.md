---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - python
  - javascript

toc_footers:
  - <a href='https://tiikr.com'>Tiikr</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - workflows
  - instances
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to Tiikr API! The Tiikr API is built on HTTP.

- Built-in HTTP capabilities for passing parameters and authentication.
- Has predictable resource-oriented URLs
- Responds with standard HTTP response codes to indicate errors
- Returns JSON.

We have language bindings in Shell, http, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Base URL

All API calls referenced in our documentation start with a base URL.

Our base URL is:

`https://manage.tiikr.com/api/v1`

# Authentication

Tiikr API uses basic authentication to authenticate requests.
Authentication to the API is performed via HTTP Basic Auth.
Provide your username and password as the basic auth username and password value.

<aside class="notice">
  Only users with an **Owner** or **Administrator** role in the company can access Tiikr API.
</aside>

Contact us if you do not know your username and password.

> You must replace <code>username</code> and <code>password</code> with your actual username and password.

```python
# We recommend to use requests library
# https://requests.readthedocs.io/en/master/user/install/#install

import requests

request = requests.get("https://manage.tiikr.com/api/v1/test", auth=(username, password))
response = request.json()

```

```javascript
let request = new XMLHttpRequest();

request.open("GET", "https://manage.tiikr.com/api/v1/test", true);
request.withCredentials = true;
request.setRequestHeader("Authorization", "Basic " + btoa("username:password"));

request.send();
request.onload = () => {
  console.log(JSON.parse(request.response));
};
```
