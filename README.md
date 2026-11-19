# VaultAuth SSO Frontend Showcase

A small vanilla JavaScript frontend snapshot for exploring an authentication client: account registration and sign-in forms, a backend health indicator, API calls, and browser session state.

## Attribution

This project is copied from [ABhardwaj28/vaultauth-frontend](https://github.com/ABhardwaj28/vaultauth-frontend) for learning and demonstration. The original README is preserved as [`README.source.md`](README.source.md), and the original PRD, frontend planner, and PDF are in `docs/`. The frontend and backend project authors are credited in the source README and PRD. This showcase is not an original implementation or an official VaultAuth release.

## What currently works in this frontend

- Checks the configured backend `/health` endpoint and displays whether it responds.
- Switches between the sign-in and create-account forms.
- Sends registration and login requests to the configured API.
- On a successful login response, stores the returned token, email, and role in `sessionStorage` and shows a signed-in message.
- Clears this tab's session storage when the sign-out button is pressed.

The full email-verification, two-factor, session-management, revocation, and admin flows described in the PRD are planned but are not implemented in this frontend snapshot. The current sign-out handler clears browser state but does not call the backend logout endpoint. The extracted folder does not include the backend source, despite the frontend README referring to a separate backend repository.

## Run locally

The app is plain HTML, CSS, and JavaScript modules. From this directory, start a static web server:

```bash
python3 -m http.server 3000
```

Then open [http://localhost:3000](http://localhost:3000).

`js/config.js` currently points to the VaultAuth reference API at `https://api.vaultauth.proplays2312.eu.org`. The login and registration forms send entered credentials to that configured service. Use test credentials only, or change `API_BASE_URL` to a backend you control before trying the forms. This frontend alone does not create a secure authentication system.

## Project files

- `index.html` — sign-in and registration interface.
- `css/style.css` — dark responsive styling.
- `js/app.js` — form, loading/error feedback, and client-side signed-in state.
- `js/api.js` — health, registration, and login requests.
- `js/config.js` — API URL and client settings.
- `docs/` — copied PRD, implementation planner, and PRD PDF.
- `README.source.md` — source repository README, preserved for attribution and reference.

## Before publishing

Confirm you have permission to republish the copied source. The extracted source folder did not contain a `LICENSE` file, even though its original README says it is MIT licensed; verify the license with the authors before redistributing. Keep the attribution above if sharing this showcase.
