```markdown
# subs-check Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and conventions used in the `subs-check` Go repository. You'll learn about file naming, import/export styles, commit message patterns, and how to write and run tests in this codebase. The guide also provides suggested commands for common workflows to streamline your development process.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `subsCheck.go`, `parseSubs.go`

### Import Style
- Use **relative imports** within the project.
  - Example:
    ```go
    import "./utils"
    ```

### Export Style
- Use **named exports** for functions, types, and variables.
  - Example:
    ```go
    // In subsCheck.go
    package subscheck

    func CheckSubs() error {
        // implementation
    }
    ```

### Commit Message Patterns
- Commit types are **mixed**, but commonly use the `feat` prefix.
- Commit messages are concise, averaging 34 characters.
  - Example: `feat: add subtitle parsing logic`

## Workflows

### Adding a New Feature
**Trigger:** When implementing new functionality  
**Command:** `/add-feature`

1. Create a new Go file using camelCase naming.
2. Write your feature using named exports.
3. Use relative imports for any internal dependencies.
4. Write corresponding tests in a file matching `*.test.*`.
5. Commit your changes with a message starting with `feat:`.
   - Example: `feat: implement subtitle sync`
6. Open a pull request for review.

### Running Tests
**Trigger:** When verifying code correctness  
**Command:** `/run-tests`

1. Locate test files matching the pattern `*.test.*`.
2. Use Go's testing tools to run tests.
   - Example:
     ```sh
     go test ./...
     ```
3. Review test output and fix any failing tests.

### Refactoring Code
**Trigger:** When improving code structure or readability  
**Command:** `/refactor-code`

1. Identify code to refactor.
2. Rename files or functions using camelCase and named exports as needed.
3. Update relative imports if file names change.
4. Run tests to ensure nothing is broken.
5. Commit with an appropriate message (e.g., `refactor: improve parsing logic`).

## Testing Patterns

- Test files follow the `*.test.*` naming convention.
  - Example: `subsCheck.test.go`
- The testing framework is not explicitly specified, but standard Go testing tools are likely used.
- Tests are written alongside implementation files, focusing on named exports.

  Example test structure:
  ```go
  // subsCheck.test.go
  package subscheck

  import "testing"

  func TestCheckSubs(t *testing.T) {
      err := CheckSubs()
      if err != nil {
          t.Errorf("CheckSubs failed: %v", err)
      }
  }
  ```

## Commands

| Command        | Purpose                                   |
|----------------|-------------------------------------------|
| /add-feature   | Start the process of adding a new feature |
| /run-tests     | Run all tests in the codebase             |
| /refactor-code | Begin a code refactoring workflow         |
```
