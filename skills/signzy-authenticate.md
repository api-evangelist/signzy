---
name: Authenticate with Signzy
description: Obtain a Signzy access token and use it correctly on every call.
api: openapi/signzy-openapi.yml
operations: [login, logout]
---

# Authenticate with Signzy

Signzy uses a LoopBack-style token flow. There is no OAuth and no Bearer prefix.

## Steps

1. **Get a token** — call `login` (`POST /api/customers/login`) with a JSON body
   `{ "username": "<account username>", "password": "<account API key>" }`.
   The response `id` field is your access token; `ttl` is its lifetime in seconds.
2. **Send the token** — on every subsequent request set the `Authorization`
   header to the **raw token value** (the `id`) — do **not** prefix it with
   `Bearer`. A `?access_token=` query parameter also works but is discouraged.
3. **Refresh before expiry** — tokens are short-lived. When you get a `401`,
   call `login` again for a fresh token rather than retrying blindly.
4. **Log out** — call `logout` (`POST /api/customers/logout`) to invalidate the
   token when done (returns `204`).

## Rules

- Treat the username/API key and issued token as high-value secrets.
- `401` means the token is missing/expired — re-login. See
  `errors/signzy-problem-types.yml`.
- No idempotency key is supported; do not assume safe automatic retries of
  write/verification calls (`conventions/signzy-conventions.yml`).
