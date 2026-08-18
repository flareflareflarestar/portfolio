> **Source text**<br />
> If you are getting a 401 Unauthorized error when making requests to the `/v1/sync` endpoint, there are a few reasons this might happen. First check your API key in the headers. Make sure it has `Bearer ` before it with a space. People forget the space all the time and it breaks. Also check if your key expired. Expired keys give 401s too. You can generate a new one in the developer dashboard under settings -> keys. If you get a 429 Too Many Requests error instead, that means you hit the rate limit. Free tier accounts can only make 60 requests per minute. Paid accounts get 1000/min. If you hit 429 you just have to wait a minute or implement exponential backoff in your code so your application retries automatically after waiting. Sometimes people get 500 Internal Server Error when syncing large payloads over 10MB. The payload size limit isn't explicitly documented everywhere yet but if your JSON payload is too big the server crashes with a 500. Reduce your payload size or split it into chunks of 2MB each. If that still doesn't work, make sure your Content-Type header is set to `application/json` because if you send plain text or urlencoded data it might throw a 400 Bad Request or a 500 depending on the parser.

---

# Troubleshooting API Auth and Sync Issues

| Error Code | Possible Causes | Common Solutions |
|:---|:---|:---|
| **400 Bad Request** | Incorrect `Content-Type` header | Set `Content-Type` header to `application/json` |
| **401 Unauthorised** | Missing `Bearer ` prefix<br />Expired API key | Include the `Bearer ` prefix<br />Generate new API key |
| **429 Too Many Requests** | Exceeded rate limit (60/min for free accounts, 1,000/min for paid accounts) | Try again later<br />Implement exponential backoff so application retries automatically after waiting |
| **500 Internal Server Error** | Payload exceeds size limit (10 MB)<br />Incorrect `Content-Type` header | Reduce payload size or split into chunks of 2 MB<br />Set `Content-Type` header to `application/json` |

!!! tip "Rate Limit Best Practice"
    Implementing **exponential backoff** helps prevent your application from hitting rate limits repeatedly during peak traffic.

# Retrospective

## The Challenge

The original source documentation provided troubleshooting steps for common API errors as a single dense paragraph. Key information such as causes and solutions were buried in prose, making it difficult for developers to quickly locate solutions.

## Key Improvements Made

- Converted the prose into a structured reference table: Grouped information into three columns to make it easier for developers to directly locate the error they are encountering.
- Standardised action oriented language: Rewrote passive explanations into imperative steps.
- Highlighted critical constraints: Clearly separated distinct root causes to ensure multi-cause errors are easy to diagnose.

## Impact

By transforming the narrative text into a compact, scannable table, developer time-to-resolution is significantly reduced.
