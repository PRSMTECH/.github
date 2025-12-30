# Contributing to PRSMTECH Projects

Thank you for your interest in contributing to PRSMTECH! This document provides guidelines and workflows to ensure smooth collaboration.

## Table of Contents

- [Team Structure](#team-structure)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Code Style](#code-style)
- [Testing Requirements](#testing-requirements)
- [Pull Request Process](#pull-request-process)
- [Communication](#communication)

## Team Structure

### Backend Team

| Name | Role | GitHub |
|------|------|--------|
| **Prajj** | Backend Developer | @prajj |
| **Bilal** | Backend Developer | @bilal |

### Leadership

| Name | Role | Contact |
|------|------|---------|
| **Jordan Ward** | CEO | admin@prsmtech.com |

## Getting Started

### Prerequisites

Before contributing, ensure you have:

1. Node.js 18+ and pnpm installed
2. Git configured with SSH authentication
3. Access to the relevant repository
4. Local development environment set up

### Setting Up Your Environment

```bash
# Clone the repository
git clone git@github.com:PrsmTechInc/<repository>.git
cd <repository>

# Install dependencies
pnpm install

# Copy environment template
cp .env.example .env.local

# Start development server
pnpm dev
```

### Environment Configuration

Each project has an `.env.example` file. Copy this to `.env.local` and fill in the required values. **Never commit `.env.local` or any file containing secrets.**

## Development Workflow

### Git Workflow

We follow a feature branch workflow with conventional commits.

#### Branch Naming Convention

```
feature/  - New features
fix/      - Bug fixes
docs/     - Documentation updates
refactor/ - Code refactoring
test/     - Test additions/updates
chore/    - Maintenance tasks
```

**Examples:**
- `feature/user-authentication`
- `fix/login-timeout-issue`
- `docs/api-endpoints`

#### Workflow Steps

1. **Create a feature branch from `main`:**
   ```bash
   git checkout main
   git pull origin main
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes and commit:**
   ```bash
   git add .
   git commit -m "feat(scope): add new feature description"
   ```

3. **Push and create a Pull Request:**
   ```bash
   git push origin feature/your-feature-name
   ```

4. **Request review and address feedback**

5. **Squash and merge after approval**

### Conventional Commits

All commits must follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
type(scope): description

[optional body]

[optional footer]
```

#### Commit Types

| Type | Description |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Formatting, no code change |
| `refactor` | Code restructuring |
| `test` | Adding/updating tests |
| `chore` | Maintenance tasks |
| `perf` | Performance improvements |
| `ci` | CI/CD changes |

#### Examples

```bash
# Feature
git commit -m "feat(auth): add OAuth 2.0 integration"

# Bug fix
git commit -m "fix(cart): resolve quantity calculation error"

# Breaking change
git commit -m "feat(api)!: change response format to JSON:API

BREAKING CHANGE: All API responses now follow JSON:API spec"
```

## Code Style

### General Guidelines

1. **TypeScript**: Use TypeScript for all new code
2. **ESLint**: All code must pass ESLint checks
3. **Prettier**: Code formatting is enforced via Prettier
4. **Comments**: Add JSDoc comments for public functions and complex logic
5. **File naming**: Use kebab-case for files (`user-service.ts`)

### TypeScript Standards

```typescript
// Use explicit types for function parameters and return values
function calculateTotal(items: CartItem[]): number {
  return items.reduce((sum, item) => sum + item.price * item.quantity, 0);
}

// Use interfaces for object shapes
interface UserProfile {
  id: string;
  email: string;
  name: string;
  createdAt: Date;
}

// Prefer const over let, never use var
const config = loadConfig();
```

### React/Next.js Standards

```tsx
// Use functional components with TypeScript
interface ButtonProps {
  label: string;
  onClick: () => void;
  variant?: 'primary' | 'secondary';
}

export function Button({ label, onClick, variant = 'primary' }: ButtonProps) {
  return (
    <button className={`btn btn-${variant}`} onClick={onClick}>
      {label}
    </button>
  );
}
```

### Pre-commit Checks

Before committing, ensure:

```bash
# Run linting
pnpm lint

# Run type checking
pnpm typecheck

# Run tests
pnpm test

# Format code
pnpm format
```

## Testing Requirements

### Test Coverage

- **New features**: Must include unit tests
- **Bug fixes**: Must include regression tests
- **Critical paths**: Require integration tests

### Testing Stack

- **Unit Tests**: Vitest or Jest
- **Integration Tests**: Playwright or Cypress
- **API Tests**: Supertest

### Running Tests

```bash
# Run all tests
pnpm test

# Run with coverage
pnpm test:coverage

# Run E2E tests
pnpm test:e2e

# Run specific test file
pnpm test path/to/test.spec.ts
```

### Test File Structure

```
src/
  components/
    Button/
      Button.tsx
      Button.test.tsx    # Unit tests colocated
  services/
    user-service.ts
    user-service.test.ts
tests/
  e2e/
    auth.spec.ts         # E2E tests
  integration/
    api.test.ts          # Integration tests
```

## Pull Request Process

### Before Submitting

1. [ ] Branch is up to date with `main`
2. [ ] All tests pass locally
3. [ ] Linting passes with no errors
4. [ ] TypeScript compiles without errors
5. [ ] No `console.log` statements left in code
6. [ ] Documentation updated if needed

### PR Requirements

1. **Use the PR template** - Fill out all sections
2. **Keep PRs focused** - One feature/fix per PR
3. **Add screenshots** - For any UI changes
4. **Link issues** - Reference related issues
5. **Request reviews** - Tag appropriate reviewers

### Review Process

1. **Automated checks** must pass (CI/CD pipeline)
2. **At least one approval** required for merge
3. **Address all comments** before merging
4. **Squash commits** when merging

### Merge Guidelines

- Use **Squash and Merge** for feature branches
- Ensure commit message follows conventional format
- Delete branch after merge

## Communication

### Channels

| Channel | Purpose |
|---------|---------|
| GitHub Issues | Bug reports, feature requests |
| GitHub Discussions | General questions, RFC discussions |
| Email | Direct communication with leadership |

### Response Times

| Priority | Response Time |
|----------|---------------|
| Critical | Within 4 hours |
| High | Within 1 business day |
| Normal | Within 3 business days |
| Low | Within 1 week |

### Issue Labels

| Label | Description |
|-------|-------------|
| `bug` | Something isn't working |
| `feature` | New feature request |
| `enhancement` | Improvement to existing feature |
| `documentation` | Documentation updates |
| `good first issue` | Good for newcomers |
| `help wanted` | Extra attention needed |
| `priority: high` | High priority issue |
| `priority: low` | Low priority issue |

## Additional Resources

- [Project README](./README.md)
- [Code of Conduct](./CODE_OF_CONDUCT.md)
- [Security Policy](./SECURITY.md)
- [License](./LICENSE)

## Questions?

If you have questions about contributing, please:

1. Check existing documentation
2. Search closed issues/discussions
3. Open a new discussion
4. Email admin@prsmtech.com for sensitive matters

---

**Thank you for contributing to PRSMTECH!**

*PRSMTECH Contributing Guidelines v1.0*
