# Pre-onboarding

Before consuming OAuth 2.1 APIs, you need to complete the following steps:

1. [Corppass Setup](#step-1-corppass-setup)
2. [APEX Setup](#step-2-apex-setup)
3. [Create JWKS endpoint](#step-3-create-jwks-endpoint)

## Step 1: Corppass Setup

The Software Developer (SWD) will often need to simulate the payroll process and role-play the company submitter.

The Company which is registered with Corppass (which SWD is in) will need to [register the User (SWD) to the Corppass Digital Service (e-service ID) - **"Apex Cloud"**](https://docs.developer.tech.gov.sg/docs/complete-apex-user-guide/sections/onboarding/introduction?id=corppass-for-non-government-users).

## Step 2: APEX Setup

Refer to [Developer Onboarding for Corppass users](https://docs.developer.tech.gov.sg/docs/complete-apex-user-guide/sections/onboarding/corppass-onboarding).

APEX will automatically create the consumer Organization (**CP\_\<UEN\>**) for the company which the User (SWD) is registered to and add the user into this Organization.

Do double-check that you are onboarded to this Organization.

## Step 3: Create JWKS endpoint

Refer to [JSON Web Key Set (JWKS)](sections/oauth/create-jwks-endpoint.md) on the requirement for the JWKS. Host the JWKS generated on a publicly accessible URL, e.g. `https://{SWD_Domain}/.well-known/keys.json`.

> Note: You will use the key-id ('kid') in later requests.
