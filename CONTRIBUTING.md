# Contributing to @mrcointreau/shared-config

Thank you for your interest in contributing to @mrcointreau/shared-config! This document provides guidelines and instructions for contributing.

## Code of Conduct

Please be respectful and constructive in all interactions. We are committed to providing a welcoming and inclusive environment for everyone.

## Getting Started

### Prerequisites

- Node.js 22 or later
- npm

### Setup

1. Fork the repository
2. Clone your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/shared-config.git
   cd shared-config
   ```
3. Install dependencies:
   ```bash
   npm install
   ```
4. Create a branch for your changes:
   ```bash
   git checkout -b feat/your-feature-name
   ```

## Development Workflow

### Building

```bash
npm run build
```

This creates the `dist/` directory with the publishable package.

### Project Structure

```
shared-config/
├── .github/workflows/   # Reusable GitHub Actions workflows
├── actions/             # Composite actions
├── configs/             # Shared ESLint and Prettier configs
└── scripts/             # Build scripts
```

## Making Changes

### Commit Messages

This project uses [Conventional Commits](https://www.conventionalcommits.org/). All commit messages are validated by commitlint.

Format:
```
type(scope): brief description
```

Types:
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation only
- `style` - Code style (formatting, semicolons, etc.)
- `refactor` - Code change that neither fixes a bug nor adds a feature
- `test` - Adding or updating tests
- `chore` - Maintenance tasks

Examples:
```
feat(eslint): add new rule for import sorting
fix(workflows): correct node version in CI
docs: update README with usage examples
chore: update dependencies
```

### Pull Request Process

1. Ensure your commits follow the conventional commit format
2. Target the `main` branch for all changes
3. Fill out the pull request description
4. Wait for CI checks to pass (commit lint validation)
5. Request review from maintainers
6. Address any feedback

### Branch Strategy

| Branch    | Purpose                        |
| --------- | ------------------------------ |
| `main`    | Development (auto-releases beta versions) |
| `release` | Stable releases (manual trigger) |

## Reporting Issues

### Bug Reports

When reporting bugs, please include:

- A clear, descriptive title
- Steps to reproduce the issue
- Expected vs actual behavior
- Environment details (Node version, OS, etc.)
- Relevant workflow logs if applicable

### Feature Requests

For feature requests, please include:

- A clear description of the feature
- The problem it solves
- Any alternative solutions considered

## Questions?

If you have questions, feel free to open an [issue](https://github.com/mrcointreau/shared-config/issues) or [discussion](https://github.com/mrcointreau/shared-config/discussions).

---

Thank you for contributing!
