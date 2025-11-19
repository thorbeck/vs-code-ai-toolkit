# Generate API Endpoint

Generate a new API endpoint with proper TypeScript types, error handling, and validation.

## Context

- Language: TypeScript
- Pattern: RESTful API
- Error handling: Try-catch with proper HTTP status codes
- Validation: Input validation with type checking

## Requirements

1. Create endpoint handler function with:
   - Proper TypeScript types for request/response
   - Input validation
   - Error handling with appropriate status codes
   - JSDoc comments

2. Define TypeScript interfaces for:
   - Request body/params
   - Response data
   - Error responses

3. Include common HTTP methods considerations:
   - GET: Query parameters
   - POST/PUT: Body validation
   - DELETE: Confirmation patterns

4. Add basic tests structure if requested

## Example Structure

```typescript
// Types
interface CreateUserRequest {
  email: string;
  name: string;
}

interface UserResponse {
  id: string;
  email: string;
  name: string;
  createdAt: string;
}

// Handler
async function createUser(req: Request, res: Response): Promise<void> {
  try {
    // Validation
    // Business logic
    // Response
  } catch (error) {
    // Error handling
  }
}
```

## Output

Generate the complete endpoint code with types, handler, and error handling.
