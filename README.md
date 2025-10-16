# High Risk: Widespread CORS Misconfiguration Leading to Sensitive Technical Information Leak

**Target:** [https://settings.services.mozilla.com](https://settings.services.mozilla.com)  
**Reported To:** Mozilla Security Team  

---

## 1. Summary of Vulnerability

| Detail | Value |
|--------|-------|
| **Vulnerability Type** | Cross-Domain Misconfiguration (CORS) / Sensitive Information Disclosure |
| **Risk Rating** | High (Upgraded due to content of leak) |
| **Affected Service** | Mozilla Settings Service (Kinto API) |
| **Widespread Vulnerability Scope** | Affects the base API path: `/v1/` and other unauthenticated endpoints like `/changeset` |
| **Full URL Example** | [https://firefox.settings.services.mozilla.com/v1/](https://firefox.settings.services.mozilla.com/v1/) |

---

## 2. Technical Description

The server hosting the specified endpoints, including the base API URL, responds with the critical HTTP header:

```http
Access-Control-Allow-Origin: *

<img width="327" height="203" alt="image" src="https://github.com/user-attachments/assets/22296cb1-7fa8-4262-aaae-26dddb8235d4" />
