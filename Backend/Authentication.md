---
tags:
  - backend
  - concept
  - solid
type: concept
status: solid
source: https://www.youtube.com/watch?v=iX8g4LqF8p8
up:
  - "[[Backend MOC]]"
---

# Authentication

Up: [[Backend MOC]] · Related: [[Sharding]] (same statelessness argument, data layer)

Source : https://www.youtube.com/watch?v=iX8g4LqF8p8

Authentication : verifies that the user or service trying to access the system is who they claim to be.

- JWT --> just a token format
- OAuth2 --> Authorization framework
---

Authentication -- answers who the user is
Authorization -- what they can access within the system

Basic Auth Methods
- base64 encoded form of username:password
- present in the header with the key - Authentication
- server side checks the correctness of the username and password
- Cons
	- easily reversible
	- only secure with https
	- not recommended in prod

Digest Authentication Flow :
- md5 hashed version for authentication
- better than basic auth - uses MD5 hashing
- outdated

API Key Authentication : 
- send with each request in the headers
	- Authorization or X-api-key
- server side validates the scope of access

Session based authentication :
- login with credentials -> create sessions (uses session store) - web server creates and returns a session id -> the session id is set as the session cookie
- upcoming request - containing cookie - we validate the session id from the session table
- challenge 
	- it is stateful
	- cannot scale for distributed system

---
Token Based Auth
- JWT Bearer Token Authentication
	- login with credentials -> authentication server validate credentials - stateless -> return JWT token (user_id, expiry_ts)
	- Unique feature : JWT token string - signed token string - contains information
	- Client makes request with Bearer token (Authorization header field) - read the info from the token

- Access and Refresh Token Lifecycle
	- Modern system also use
		- Access tokens - short lived
			- API calls to the server - 45 min to 1 hr
		- Refresh tokens - long lived - 7 to 30 days
			- Get new access tokens
	- Login request -> auth server -> access token and refresh token are returned
	- Store refresh tokens in httpOnly cookies - never in localStorage - as it can be accessed via js
---
OAuth2 and OIDC
- OAuth2
	- authorization framework
		- what can the app access on behalf of the user
	- first redirect you to the consent screen - show permission request - return authorization code to the app
	- exchange code for token for access token
	- This doesnt says who the user is - it just says what the user can do ---- the difference

- OIDC : Open ID Connect
	- Adds authentication on top of OAuth2
	- Exchange code for tokens
		- Returns access token and ID token
			- access token is for OAuth and ID token is JWT - used for verification
---
- SSO and Identity Protocols
	- SSO - is a user experience
		- global session is stored in session storage
			- that can be used by multiple services
	- SSO uses identity protocols under the hood
		- SAML IdP : Security Assertion Markup Language
			- XML based protocol
		- OIDC IdP

---

## Connections

- **Stateful → stateless** is the whole arc of this note. Session auth pins a user to one server; JWT removes that. [[Sharding]] makes the identical move for data, and [[Distributed Systems MOC]] tabulates the pattern.
- **Auth middleware is the Proxy pattern** — it sits in front of the real handler, exposes the same interface, controls access. See [[Design Patterns]].
- **Token storage** is where most real bugs live: httpOnly cookies vs localStorage.

## Open questions

- [ ] JWT revocation — you can't un-issue a signed token. Blocklist? Short expiry only?
- [ ] Where does mTLS fit for service-to-service?
- [ ] Auth in [[GraphQL]] — one endpoint, so where do the checks go?
