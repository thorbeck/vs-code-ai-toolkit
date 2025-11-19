# Generate TypeScript Types

Generate TypeScript types/interfaces from example data or API responses.

## Context

- Language: TypeScript
- Pattern: Strong typing with interfaces
- Style: Descriptive names, proper nesting

## Requirements

1. Analyze the provided data structure (JSON, API response, etc.)
2. Generate TypeScript interfaces with:
   - Proper property types
   - Optional properties marked with `?`
   - Nested types extracted to separate interfaces
   - Union types where appropriate
   - Array types properly defined

3. Consider:
   - Readonly properties where appropriate
   - Utility types (Pick, Omit, Partial, etc.)
   - Generic types if patterns repeat
   - Enums for fixed sets of values

4. Add JSDoc comments for:
   - Complex types
   - Business logic constraints
   - Format expectations (dates, URLs, etc.)

## Example Input

```json
{
  "user": {
    "id": "123",
    "email": "user@example.com",
    "profile": {
      "name": "John Doe",
      "age": 30
    },
    "roles": ["admin", "user"]
  }
}
```

## Example Output

```typescript
interface User {
  id: string;
  email: string;
  profile: UserProfile;
  roles: UserRole[];
}

interface UserProfile {
  name: string;
  age: number;
}

type UserRole = 'admin' | 'user' | 'guest';
```

## Output

Generate complete TypeScript type definitions from the provided data.
