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

These are the prompts used in this session to instruct GitHub Copilot to create and publish the project (translated from Swedish):

```text
I want to create a Hello World project with Expo Go. Help me from start to finish: set up the project, write code for a GUI that displays the text Hello World, deploy it locally, and finally run it in an emulator/browser. Show the planned steps before you start executing.
```

```text
We do not need to test for macOS or Android right now. I want you to start a local Expo server so that I can access Hello World from my iPhone, which has Expo Go installed.
```

