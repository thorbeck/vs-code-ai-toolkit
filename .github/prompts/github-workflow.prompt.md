# Generate GitHub Actions Workflow

Create a GitHub Actions workflow for CI/CD pipelines.

## Context

- Platform: GitHub Actions
- Language: TypeScript/Node.js (default)
- Pattern: Modern CI/CD best practices

## Requirements

1. Create workflow YAML with:
   - Descriptive name and triggers
   - Job steps with clear names
   - Environment variables and secrets
   - Caching for dependencies
   - Proper error handling

2. Common workflows to consider:
   - **CI**: Lint, test, build on PR and push
   - **CD**: Deploy to production/staging
   - **Release**: Automated versioning and releases
   - **Security**: Dependency scanning, code analysis

3. Best practices:
   - Use specific action versions (not @main)
   - Cache node_modules for speed
   - Run tests in parallel when possible
   - Fail fast on errors
   - Use matrix strategy for multiple environments

4. Include:
   - Node.js version matrix if needed
   - TypeScript compilation check
   - Test coverage reporting
   - Build artifact upload/download

## Example Structure

```yaml
name: CI

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node-version: [18.x, 20.x]
    
    steps:
      - uses: actions/checkout@v4
      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node-version }}
          cache: 'npm'
      
      - name: Install dependencies
        run: npm ci
      
      - name: Run tests
        run: npm test
      
      - name: Build
        run: npm run build
```

## Output

Generate a complete GitHub Actions workflow file ready to commit.
