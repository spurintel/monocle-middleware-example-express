# monocle-middleware-express

## Development

### Building

```bash
docker compose build --no-cache
```

### Running

```bash
docker compose --env-file .env.spur-managed up
```

#### Environment Variables

You can use openssl to generate a cookie secret:

```bash
openssl rand -base64 32
```

If you are using a spur managed environment, you will need to create a `.env.spur-managed` file in the root of the project. This file should contain the following environment variables:

```bash
DECRYPTION_METHOD=spur-managed
SITE_TOKEN=
VERIFY_TOKEN=
COOKIE_SECRET=
```

For a user managed environment, you will need to create a `.env` file in the root of the project. This file should contain the following environment variables:

```bash
DECRYPTION_METHOD=spur-managed
SITE_TOKEN=
PRIVATE_KEY=
COOKIE_SECRET=
```

If you are running the project locally, you will also need to include a variable to disable the IP checks:

```bash
NODE_ENV=development
LOCAL=true
```


### Stopping

```bash
docker compose down
```

### Testing
Navigate to `http://localhost:3000` in your browser.