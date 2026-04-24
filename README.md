# Expo Hello World

This is a minimal Expo project that renders a simple Hello World screen.

## What is Expo?

Expo is a toolchain and platform for building React Native apps with a fast local development workflow. It provides project scaffolding, a development server, bundling, and optional native build tooling.

## What is Expo Go?

Expo Go is the mobile app for iPhone and Android that lets you open and test an Expo project directly from a local development server without creating a native build first.

## Run locally

Install dependencies:

```bash
npm install
```

Start the Expo development server:

```bash
npm start
```

Run in the browser:

```bash
npm run web
```

Open on iPhone with Expo Go:

1. Make sure the phone and computer are on the same network.
2. Start the app with `npm start -- --lan`.
3. Scan the QR code from the terminal in Expo Go.

## Prompts used to create this project

These are the prompts used in this session to instruct GitHub Copilot to create and publish the project (swedish):

```text
Jag vill skapa ett Hello World-projekt med Expo Go. Hjälp mig från början till slut: sätta upp projektet, skriva kod för ett GUI som visar texten Hello World, lokal deploy och till sist köra den i en emulator/webbläsare. Visa dom planerade stegen innan du börjar exekvera
```

```text
Vi behöver inte testa för OSX eller Android just nu. Jag vill att du startar en lokal server för expo så att jag komma åt Hello World från min Iphone som har Expo Go installerad.
```

