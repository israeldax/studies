## Same-Origin
A policy that restricts browsers from reading resources from different origins. Two resources are from the same origin only if they have the same domain, protocol, host, and port.

## CORS (Cross Site Resource Sharing)
A way to allow same origin policy when a cross-origin request is needed.

## Cross-Site Scripting Attack
A common security vulnerability, also known as XSS, where an attacker is able to run code on a vulnerability site, thus circumventing the same-origin policy. There are a few common forms of cross-site scripting:
-   ﻿﻿Persistent: A vulnerability that persists beyond a single session, usually from the attacker storing malicious code in the vulnerable database. A common example of this is leaving a comment with code that when appended to the page by the client is executed.
-   ﻿﻿Non-persistent: A vulnerability that does not persist beyond a single session, usually when an attacker takes advantage of how the client processes a URL query parameter to execute malicious code on the client.
-   ﻿﻿DOM-based: A vulnerability that happens exclusively on the frontend without any need for sending data to the server, thus making the attack harder to track.

## Cross-Site Request Forgery Attack
A common security vulnerability, also known as CSRF, where an attacker sends a request to a server and is able to convince the server it was sent by their client. CSRF attacks can usually be prevented by using a CSRF token, a unique token given to the client that a forged request would not be able to replicate.

## OAuth
Open Authorization, a common standard for service authorization. Services can use OAth to allow users to give other services specific API access to portions of their accounts.

## JSON Web Token
A standard for signed JSON tokens, oftentimes referred to by its abbreviation WT. JSON Web Tokens have three sections:
-   ﻿﻿A header with information about the encryption algorithm used.
-   ﻿﻿The payload data.
-   ﻿﻿The signature, which is created by the server using a secret key so that it can determine if it has been tampered with.