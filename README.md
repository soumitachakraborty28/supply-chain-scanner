# Supply Chain Security Scanner

A GitHub App that scans the dependencies in a pull request and warns developers about vulnerable or suspicious packages before the code is merged.

## Problem

Installing one package pulls in dozens of hidden ones. A single vulnerable or malicious package (like log4j or the xz backdoor) can put every project that uses it at risk.

## How It Works

1. A PR changes `package.json`, `package-lock.json` or `requirements.txt`.
2. GitHub sends a webhook to our server.
3. The Engine extracts the dependencies and checks them against the OSV database and our own risk rules (typosquatting, very new packages, suspicious install scripts).
4. The app comments on the PR with the risky packages and the reasons.
5. A dashboard shows scan history and a dependency graph with risky packages highlighted.

## Tech Stack

Node.js, TypeScript, Express, React, React Flow, PostgreSQL, Docker, GitHub Actions, OSV API
