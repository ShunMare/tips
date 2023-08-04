---
title: Resolving OpenAI API Authentication Errors in Azure Functions by Correctly Setting Environment Variables
published: true
description: description
tags: OpenAI, Azure
---
**Problem:**
Your application hosted on Azure is not able to authenticate with the OpenAI API despite having the API key set as an environment variable.

**Cause:**
The environment variable name set in Azure does not match the one used in the application code.

**Solution:**
Ensure that the name of the environment variable set in Azure matches the one your application is trying to access.

---

**Step-by-step guide:**

1. Go to the Azure Functions settings screen.

2. Change the name of the environment variable `ChatGPT_key` to `OPENAI_API_KEY`. The value remains the same.

3. Save the changes and restart Azure Functions.

After these steps, Azure Functions should correctly recognize the `OPENAI_API_KEY` environment variable, and your application should successfully authenticate with the OpenAI API.
