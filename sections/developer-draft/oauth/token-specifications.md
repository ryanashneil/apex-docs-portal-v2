# OAuth 2.1 Token Specifications

This page provides the token specifications for the OAuth 2.1 token request.

## Token Request

| Specification  | Information                         |                                                                                                                                   |
| -------------- | ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Token Endpoint | **{Token Endpoint}**                |                                                                                                                                   |
| Method         | POST                                |                                                                                                                                   |
| Content-Type   | 'application/x-www-form-urlencoded' |                                                                                                                                   |
| Body           | **key**                             | **Specification**                                                                                                                 |
|                | 'code'                              | string obtained from [authorization flow](/sections/oauth/authz-token?id=_7-client-extracts-authorization-code-from-redirect-uri) |
|                | 'client_assertion'                  | **{client assertion}** specified below                                                                                            |
|                | 'client_id'                         | String of Client ID obtained during [onboarding of your OAuth Client](/sections/oauth/client)                                     |
|                | 'client_assertion_type'             | 'urn:ietf:params:oauth:client-assertion-type:jwt-bearer'                                                                          |
|                | 'grant_type'                        | 'authorization_code'                                                                                                              |
|                | 'redirect_uri'                      | String of exact redirect URI of Client Application in URL encoded format                                                          |
|                | 'code_verifier'                     | String of PKCE Code Verifier generated in [here](/sections/oauth/authz-token?id=_2-token-endpoint-request)                        |

### Client Assertion

**{client_assertion}** is a JSON formatted list of claims based on RFC7523. A sample code to generate the signed client assertion is [here](/sections/oauth/sample-codes?id=generate-client-assertion).

| Claim | Information                                                                                                                                                                                  |
| ----- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 'iss' | Issuer, also equal to Client ID obtained in the [onboarding steps](/sections/oauth/client)                                                                                                   |
| 'sub' | Subject, also equal to Client ID obtained in the [onboarding steps](/sections/oauth/client)                                                                                                  |
| 'aud' | Audience, also equal to Authorization Token Endpoint                                                                                                                                         |
| 'kid' | Key ID, also equal to the JWT Key ID (public key of the keyset used to sign the client_assertion) in the JWKS Endpoint described in [Initial Setup](/sections/oauth/create-jwks-endpoint.md) |
| 'jti' | JWT ID, an arbitrary value to identify the Access Token request, like a session ID                                                                                                           |
| 'iat' | Current epoch time of epoch time, in seconds                                                                                                                                                 |
| 'exp' | Expiry time in Linux time + 5 minutes, in seconds                                                                                                                                            |

### Decoded Client Assertion (Sample)

```
# header
{
  "typ": "JWT",
  "alg": "ES256",
  "kid": "your-kid-id"
}

# payload
{
  "jti": "3Xb4Wzas5wm41rGwUOMnN8zS9i9xh41c44N6kaafgwE",
  "iss": "client-id",
  "sub": "client-id",
  "aud": "https://sandbox.api.gov.sg/oauth/cp/v2/token",
  "iat": 1725552624,
  "exp": 1725552924
}
```
