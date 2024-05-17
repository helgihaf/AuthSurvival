# AuthSurvival


## OAuth 2 and 2.1
Recommended flows are:
* Server-side:	Authorization Code + PKCE
* SPA:			Authorization Code + PKCE
* Native app:		Authorization Code + PKCE
* Server-side:	Client Credentials

## Authorization Code + PKCE
* Client generates code_verifier (random code)
* Client requests authorization and sends code_challenge = sha256(code_verifier)
* Gets back authorization code
* Requests authorization token using code and code_verifier
* Server calculates sha256(code_verifier) and compares to original code requests, if ok then responds with token

## Cookies
* Created by web servers
* Stored on browser
* Belong to a specific url/domain
* Automatically transmitted as part of http calls to that domain
* A cookie marked `Secure` can only be transmitted via https
* SameSite=None: Cookie always transmitted when site is hit (example: image downloaded, navigated to site etc)
* SameSite=Lax: Cookie only transmitted when user navigates to your site 
* SameSite=Strict: Cookie only transmitted within site.
