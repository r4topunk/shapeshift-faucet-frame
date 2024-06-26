# Frames.js Next Faucet

Simple Faucet app using Frames.js and Next.

## How It Works

The application is straightforward. The same API that creates the Frames will also control user claims and, using the private key from the wallet, send the tokens.

## Dependencies

The application uses [Supabase](https://supabase.com/docs/guides/api) to store information about user interactions. Therefore, it is necessary to create an account on the platform, create a table, and use it with the application.

The table should have the following columns:

```
id : int8 : primary
claimed_at : timestamptz : now()
fid : numeric
f_address : string
eth_address : string
```

## Environment Variables

The faucet includes four environment variables, which are:

- `WALLET_PRIVATE_KEY` for the private key of the wallet that will be used to send the tokens
- `SUPABASE_URL` for the access URL for Supabase
- `SUPABASE_KEY` for the access key for Supabase
- `WEBSITE_URL` for the URL where the Frame will be hosted; this variable should only be added in production

## Development

To develop your own version of the Faucet, start by cloning the repository:

```bash
git clone https://github.com/r4topunk/shapeshift-faucet-frame.git
cd shapeshift-faucet-frame
```

Then, install the packages:

```bash
pnpm install
```

Edit the `.env`:

```bash
cp .env.example .env
```

To launch in development mode use the command:

```bash
pnpm run dev
```

## Deployment

Because the development was done using Next.js, deployment can be carried out on Vercel. Additionally, since the development was done with Next, a web page will be created to host the site and receive requests.

When you click on the Frame image within Warpcast, you will be sent to the Frame's webpage; in this case, the page will be the one generated by Next. You can edit it in `app/page.tsx`.
