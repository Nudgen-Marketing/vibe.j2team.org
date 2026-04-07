```markdown
# vibe.j2team.org Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill introduces the core development patterns and conventions used in the `vibe.j2team.org` TypeScript codebase. It covers file naming, import/export styles, commit message conventions, and testing patterns. By following these guidelines, contributors can maintain consistency and quality across the project.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - **Example:**  
    `userProfile.ts`, `apiClient.ts`

### Import Style
- Use **alias imports** to reference modules.
  - **Example:**  
    ```typescript
    import { fetchUser } from 'services/userService';
    ```

### Export Style
- Use **named exports** for all modules.
  - **Example:**  
    ```typescript
    // In userProfile.ts
    export function getUserProfile(id: string) { ... }
    ```

### Commit Messages
- Follow **Conventional Commits** with the `feat` prefix for features.
  - **Example:**  
    ```
    feat: add user authentication logic
    ```

## Workflows

### Feature Development
**Trigger:** When adding a new feature  
**Command:** `/feature`

1. Create a new branch for your feature.
2. Implement the feature using camelCase file naming and named exports.
3. Use alias imports for dependencies.
4. Write or update relevant tests (`*.test.*` files).
5. Commit changes using the `feat` prefix and a clear message.
6. Open a pull request for review.

### Testing
**Trigger:** Before merging or deploying changes  
**Command:** `/test`

1. Identify or create test files matching the `*.test.*` pattern.
2. Run the test suite using the project's test runner.
3. Ensure all tests pass before proceeding.

## Testing Patterns

- Test files follow the `*.test.*` naming pattern (e.g., `userProfile.test.ts`).
- The specific testing framework is **unknown**, but tests should be colocated with or near the code they verify.
- Write tests for all new features and significant changes.

  **Example:**
  ```typescript
  // userProfile.test.ts
  import { getUserProfile } from './userProfile';

  test('should return user profile for valid ID', () => {
    expect(getUserProfile('123')).toEqual({ id: '123', name: 'Alice' });
  });
  ```

## Commands
| Command    | Purpose                                 |
|------------|-----------------------------------------|
| /feature   | Start a new feature development workflow|
| /test      | Run the test suite                     |
```
