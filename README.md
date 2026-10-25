# Gym Access Frontend

A Vue.js single-page app that lets gym members book and pay for a daily pass.

## Features

- Self-service daily pass booking, with no receptionist involved
- Date picker for choosing the access date
- Email input with format validation
- Pay button that is enabled only when both a date and a valid email are provided
- Payment step is currently a placeholder (shows an alert)

## Tech Stack

- Vue 3
- Vue Router 4 (dependency installed, not yet wired up)
- Vue CLI 4 (`@vue/cli-service`)
- ESLint with `eslint-plugin-vue`
- Tailwind CSS 4 and PostCSS/Autoprefixer (dependencies installed)

## Project Structure

```
public/
  index.html            HTML shell with the #app mount point
src/
  main.js               Creates and mounts the root app
  App.vue               Root component, renders Home
  views/
    Home.vue            Page with the date picker, email input, and Pay button
  components/
    Calendar.vue        Native date input; emits date-selected
    EmailInput.vue      Email input with validation; emits email-entered
  assets/               Static assets
```

## Getting Started

### Prerequisites

- Node.js (LTS recommended)
- npm

### Install

```bash
npm install
```

### Run in development

```bash
npm run serve
```

The app runs at http://localhost:8080 by default.

### Build for production

```bash
npm run build
```

Output is written to `dist/`.

### Lint

```bash
npm run lint
```

## How It Works

1. `Calendar.vue` emits `date-selected` with the chosen date. `Home.vue` stores it in `selectedDate`.
2. `EmailInput.vue` validates the address against a basic pattern (`^[^\s@]+@[^\s@]+\.[^\s@]+$`). It emits the email when valid and an empty string when invalid.
3. `Home.vue` computes `isFormValid` from both values and enables the Pay button when both are set.
4. Clicking Pay currently calls `pay()`, which shows an alert with the email and date.

## Known Limitations

- Payment processing is not implemented; `pay()` in `Home.vue` only shows an alert.
- Vue Router is installed but no routes are defined and it is not registered in `main.js`.
- Tailwind CSS is installed, but no Tailwind configuration or directives are present in the source.
- The email regex is a simple format check and does not confirm the address exists.
- The date input does not restrict past dates.

## Scripts

| Command           | Description                          |
| ----------------- | ------------------------------------ |
| `npm run serve`   | Start the dev server with hot reload |
| `npm run build`   | Create a production build in `dist/` |
| `npm run lint`    | Lint and auto-fix source files       |

## License

MIT
