# Contributing

Thanks for contributing to the Gym Access Frontend. See [README.md](README.md) for setup and project structure.

## Workflow

1. Create a branch from `master` for your change.
2. Make focused changes. Keep each commit to one logical change.
3. Run `npm run lint` and `npm run build` before committing.
4. Open a pull request into `master`.

## Commit Messages

Every commit message must start with a [Conventional Commits](https://www.conventionalcommits.org/) prefix:

| Prefix      | Use for                                              |
| ----------- | ---------------------------------------------------- |
| `feat:`     | A new feature or user-visible behavior               |
| `fix:`      | A bug fix                                            |
| `chore:`    | Maintenance, tooling, dependencies, or cleanup       |
| `docs:`     | Documentation only                                   |
| `refactor:` | Code change that neither fixes a bug nor adds a feature |
| `test:`     | Adding or updating tests                             |

Format: `<prefix>: <short imperative summary>`

Examples:

- `feat: add pass selection for daily access`
- `fix: keep Pay button disabled for invalid emails`
- `chore: remove debug console.log calls`

## Code Style

- Follow the ESLint rules configured for the project (`npm run lint`).
- Do not commit `console.log` or other debug output.
- Keep components focused: date and email inputs live in `src/components/`, page logic in `src/views/`.
