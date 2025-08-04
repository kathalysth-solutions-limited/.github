# Contributing Guidelines

This document outlines our development standards, workflow, and best practices at Kathalysth.

## 📁 Project Structure

### Standard Folder Structure

```javascript
src/
├── components/
│   ├── ui/                    # shadcn/ui components
│   ├── common/                # Reusable components
│   └── feature-name/          # Feature-specific components
├── hooks/                     # Custom React hooks
├── lib/                       # Utility functions
├── types/                     # TypeScript type definitions
├── constants/                 # Application constants
└── __tests__/                 # Test files
```

## 🔄 Git Workflow (GitFlow)

### Branch Structure
- `main` - Production-ready code
- `develop` - Integration branch for features
- `feature/feature-name` - New features
- `hotfix/issue-description` - Critical production fixes
- `release/version-number` - Release preparation

### Branch Naming Convention
feature/user-authentication
hotfix/payment-processing-bug
release/v1.2.0

## 📝 Commit Standards

### Conventional Commits Format

<type>(<scope>): <description>
[optional body]
[optional footer(s)]

### Types
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

### Examples
```bash
feat(auth): add user login functionality
fix(payment): resolve checkout validation error
docs(readme): update installation instructions
test(user-service): add unit tests for user creation
```

# 🧪 Testing Requirements

## Coverage Requirements
* **Minimum Coverage**: 80%
* **Critical Functions**: 95% coverage required

## Testing Strategy
* **Unit Tests**: All utility functions and business logic
* **Integration Tests**: API endpoints and component interactions  
* **E2E Tests**: Critical user workflows

## Test File Naming
```javascript
src/
├── components/
│   ├── user-profile.tsx
│   └── __tests__/
│       └── user-profile.test.tsx
└── lib/
    ├── auth-utils.ts
    └── __tests__/
        └── auth-utils.test.ts
```

# 🔍 Code Standards

## ESLint Configuration

```javascript
{
  "extends": [
    "@next/eslint-config-next",
    "eslint:recommended",
    "@typescript-eslint/recommended"
  ],
  "rules": {
    "@typescript-eslint/no-unused-vars": "error",
    "@typescript-eslint/explicit-function-return-type": "warn",
    "prefer-const": "error",
    "no-var": "error"
  }
}
```
## Prettier Configuration
```javascript
{
  "semi": true,
  "trailingComma": "es5",
  "singleQuote": true,
  "printWidth": 80,
  "tabWidth": 2
}

```
## TypeScript Standards
* Use strict TypeScript configuration
* Define interfaces for all data structures
* Use proper typing for function parameters and return values
* Avoid `any` type - use `unknown` or proper types

# 🎨 UI/UX Standards

## Design Principles
* **Mobile-first**: Design for mobile, enhance for desktop
* **Accessibility**: Follow WCAG 2.1 guidelines
* **Performance**: Optimize for Core Web Vitals
* **Consistency**: Use shadcn/ui components consistently

## Responsive Breakpoints

```css
/* Mobile */
@media (max-width: 768px) { }

/* Tablet */
@media (min-width: 769px) and (max-width: 1024px) { }

/* Desktop */
@media (min-width: 1025px) { }
```

## Animation Guidelines
* Use Framer Motion for all animations
* Keep animations under 300ms for micro-interactions
* Provide `prefers-reduced-motion` alternatives

# 🔄 Development Workflow

## 1. Starting New Work

```bash
# Switch to develop branch
git checkout develop
git pull origin develop

# Create feature branch
git checkout -b feature/your-feature-name
```

## 2. Development Process
* Write tests first (TDD approach recommended)
* Implement functionality
* Ensure all tests pass
* Run linting and formatting

## 3. Code Review Process
* Push branch to GitHub
* Create Pull Request to `develop`
* Ensure CI/CD checks pass
* Request review from tech leads
* Address feedback
* Merge after approval

## 4. PR Requirements
* All tests passing
* Code coverage meets requirements
* ESLint/Prettier checks pass
* TypeScript compilation successful
* Descriptive PR title and description
* Screenshots for UI changes

# 🚀 CI/CD Pipeline

## GitHub Actions Workflow
Our pipeline automatically:
* Runs tests and linting
* Checks TypeScript compilation
* Verifies code coverage
* Builds the application
* Deploys to staging (develop branch)
* Deploys to production (main branch)

## Pipeline Requirements
All checks must pass before merge:
* Unit tests
* Integration tests
* ESLint checks
* TypeScript compilation
* Security scans

# 📋 Definition of Done

## For Features
* Code implemented according to requirements
* Unit tests written and passing
* Integration tests added where applicable
* Code reviewed and approved
* Documentation updated
* Responsive design implemented
* Accessibility requirements met
* Performance benchmarks met

## For Bug Fixes
* Root cause identified
* Fix implemented
* Test added to prevent regression
* Code reviewed and approved
* Fix verified in staging environment

# 🚨 Important Notes
* **Never assume**: Ask questions if requirements are unclear

# 📞 Getting Help
* **Technical questions**: Ask tech leads in Slack
* **Code review feedback**: Discuss in PR comments or Slack
* **Architecture decisions**: Consult with Staff developers
* **Process questions**: Check with tech leads

**Remember**: These guidelines ensure code quality, maintainability, and team collaboration. When in doubt, ask!

