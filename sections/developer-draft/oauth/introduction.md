# APEX Cloud OAuth 2.1

## Introduction

This user guide is intended for API Publishers and Developers (Consumers).

This guide explains how to implement the [OAuth](https://datatracker.ietf.org/doc/html/rfc6749) [2.1](https://oauth.net/2.1/) Authorization Code Flow to allow a Corppass user to grant a third-party client application access to the Corppass user’s
protected resources.

The guide provides step-by-step instructions for a Client Application Developer to simulate the Corppass User and develop the Authorization Code Flow.

### Prerequisites

> Before continuing, please ensure that you have already prepared:
>
> 1. [At least 1 application](/sections/consuming/v2/create-application.md)
> 1. [At least 1 API Key](/sections/consuming/v2/api-keys.md)
> 1. [Subscribed to an OAuth 2.1 protected API](/sections/consuming/v2/subscribe-api.md)
>
> If you need a recap on the above, you may start at our [prerequisite chapter for consuming APIs](/sections/consuming/v2/introduction.md)

### Contents

- [Terminology](sections/oauth/terminology.md) - Definition of Terms
- [Pre-onboarding](sections/oauth/pre-onboarding.md) - Complete these steps first
- [Creating the OAuth Client](sections/oauth/client.md) - Creating OAuth Client ID and Authorization URL
- [Using OAuth 2.1 Auth](sections/oauth/authz-token.md) - How to implement the OAuth flow in your application
- [Authorization Profile](sections/oauth/authorization-profile.md) - Which Authorization Profile to select
- [Testing Business API](sections/oauth/api-test.md) - Using OAuth token in your application

### References

- [JSON Web Key Set (JWKS)](sections/oauth/create-jwks-endpoint.md)
- [OAuth 2.1 Token Specifications](sections/oauth/token-specifications.md)
- [OAuth 2.1 Sample Codes](sections/oauth/sample-codes.md)
- [OAuth 2.1 Endpoints](sections/oauth/endpoints.md)
- [Debugging OAuth 2.1 authentications](sections/troubleshooting/oauth.md)
