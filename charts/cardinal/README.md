# Cardinal Chart

This chart installs [Cardinal](https://github.com/hbjydev/cardinal), a Discord
bot that I develop in TypeScript. It has publicly available Docker builds,
allowing me to deploy it into a Kubernetes environment.

## Configuration

These are the values you can override from the [values.yaml](./values.yaml)
file.

| Variable      | Description                          | Default                                            |
| ------------- | ------------------------------------ | -------------------------------------------------- |
| `token`       | A discord authentication token.      | `'fakeToken'`                                      |
| `environment` | The node.js environment string       | `'production'`                                     |
| `sentryDsn`   | The Sentry DSN to track errors via   | `'fakeDsn'`                                        |
| `dbUri`       | The PostgreSQL database URI to use   | `'postgres://cardinal:password@database/cardinal'` |
| `prefix`      | The command prefix for the bot use   | `'!'`                                              |
| `botOwners`   | A comma-separated list of bot owners | `'1234567890123456'`                               |

> **NOTE:** The `token`, `sentryDsn` and `dbUri` values are secrets, so must be
> input as base64-encoded strings. This will be automated at a later date, but
> for now, you must pass them through a base64 encoder, i.e.
> `echo -n 'secretToken' | base64 -w 0`

## Caveats

Of course, as it's a Discord bot, at the moment it cannot auto-scale
horizontally as containers, as the bot has no sharding capabilities (or needs,
currently).

