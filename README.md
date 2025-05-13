# oauth2-proxy-entraid-sample

Sample how to proxy any web app with the oauth2-proxy, enforcing an MS EntraID login.

## Localhost

To run this setup locally you need to create a new EntraID app registration first. Follow the
instructions [here](https://oauth2-proxy.github.io/oauth2-proxy/configuration/providers/ms_entra_id#configure-app-registration).

The app registration needs:

- `http://localhost:4180/oauth2/callback` as **web redirect url**
- the api permission (delegated)
  - `email`
  - `offline_access`
  - `openid`

Put the tenant id and the app registration client id into the [env file](./.env).

Create a new client secret for the app registration and put it into the env file.

Follow this [documentation](https://oauth2-proxy.github.io/oauth2-proxy/configuration/overview#generating-a-cookie-secret) to create a cookie secret and put it into the env file.

OPTIONAL: Add a valid email domain ending to the env file to limit users that can sign in (\* allows all email domains).

Run the sample inside the root dir of this project:

```shell
docker compose up -d
```

Open the [sample](http://localhost:4180/) and login.
