# FUTURE_CS_03 - API Security Risk Analysis

## Overview

This repository contains my work for Future Interns Cyber Security Task 3: **API Security Risk Analysis**.

I selected the Cat Facts API from the public APIs repository and tested it using Postman. The purpose was to inspect API requests, responses, headers, authentication requirements and possible security risks in a safe and read-only way.

## API Selected

| Item | Details |
|---|---|
| API Name | Cat Facts API |
| Source | https://github.com/public-apis/public-apis |
| API Documentation | https://catfact.ninja |
| API Type | Public demo API |
| Authentication | No Auth |
| HTTPS | Yes |
| Data Type | Public cat facts |

## Objective

- Test a public API using Postman
- Review API documentation before testing
- Send safe read-only GET requests
- Inspect response body and response headers
- Check whether authentication or tokens are required
- Identify possible API security risks
- Explain the impact in simple language
- Suggest basic remediation steps

## Tools Used

| Tool | Purpose |
|---|---|
| Postman | Used to send API requests and inspect responses |
| Browser | Used to view API documentation and the public APIs repository |
| Cat Facts Swagger Documentation | Used to understand available endpoints and parameters |
| GitHub | Used to store the final report, screenshots and README |
| MS Word | Used to prepare the final report |

## Endpoints Tested

| Request | Purpose |
|---|---|
| `GET https://catfact.ninja/fact` | Tested the basic random fact endpoint |
| `GET https://catfact.ninja/fact?max_length=50` | Tested the `max_length` query parameter |
| `GET https://catfact.ninja/facts?max_length=70&limit=5` | Tested multiple returned records using query parameters |

## Testing Approach

The Cat Facts API documentation was reviewed first to understand the available endpoints and supported parameters. After that, the endpoints were tested in Postman using safe GET requests only.

The response body was checked to understand what data was returned by the API. The response headers were also reviewed to check content type, rate limiting, CORS behavior, server information and other visible security-related headers.

No attempt was made to exploit, bypass, overload or attack the API.

## Observations

| Area | Observation |
|---|---|
| Authentication | The tested endpoints did not require an API key, bearer token or login |
| Request method | The API was tested using safe GET requests |
| Response format | The API returned JSON responses |
| Data sensitivity | The response only contained public cat fact data |
| HTTPS | The API used HTTPS |
| Query parameters | Parameters such as `max_length` and `limit` controlled the response |
| Rate limiting | Response headers showed rate limit information |
| CORS | The API allowed requests from any origin using `Access-Control-Allow-Origin: *` |

## Security Findings

| Finding | Risk Level | Explanation |
|---|---|---|
| Public unauthenticated access | Low | The API does not require authentication. This is acceptable because it returns public data, but public APIs should still have abuse protection. |
| Query parameter input | Low | The API accepts user-controlled query parameters such as `max_length` and `limit`. These values should be validated by the server. |
| CORS allows any origin | Low | The response header allowed requests from any origin. This is acceptable for public non-sensitive data, but it would be risky for private APIs. |
| Rate limiting present | Positive | The headers showed rate limit information, which helps reduce abuse of a public API. |
| No sensitive data exposed | Positive | The API response only returned cat facts and did not expose private user data, passwords or tokens. |



