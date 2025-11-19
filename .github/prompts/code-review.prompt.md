# Code Review Checklist

Review the selected code for quality, security, and best practices.

## Review Criteria

### TypeScript & Types
- [ ] Proper type annotations (no `any` unless justified)
- [ ] Interface/type definitions for objects
- [ ] Return types on functions
- [ ] Null/undefined handling

### Code Quality
- [ ] Clear, descriptive names for variables and functions
- [ ] Functions are focused and single-purpose
- [ ] No code duplication
- [ ] Comments where complexity requires explanation
- [ ] No console.log statements in production code

### Error Handling
- [ ] Try-catch blocks where appropriate
- [ ] Proper error types and messages
- [ ] Failed promises are handled
- [ ] User-friendly error messages

### Security
- [ ] Input validation and sanitization
- [ ] No hardcoded secrets or credentials
- [ ] Proper authentication/authorization checks
- [ ] XSS prevention (escaped output)
- [ ] SQL injection prevention (parameterized queries)

### Performance
- [ ] Efficient algorithms and data structures
- [ ] No unnecessary loops or operations
- [ ] Async operations handled properly
- [ ] Memory leaks prevented (cleanup in useEffect, etc.)

### Testing
- [ ] Edge cases considered
- [ ] Error paths tested
- [ ] Happy path tested

### Git & GitHub
- [ ] Commit messages are clear
- [ ] No sensitive data in commits
- [ ] Branch naming follows conventions

## Output Format

Provide feedback in this structure:

**✅ Good:**
- List positive aspects

**⚠️ Suggestions:**
- List improvements with code examples

**🔴 Issues:**
- List critical problems that must be fixed

**💡 Optional:**
- List nice-to-have improvements
