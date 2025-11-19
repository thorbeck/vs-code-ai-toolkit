# Generate Fetch API Client

Create a type-safe fetch wrapper with error handling for calling APIs.

## Context

- Language: TypeScript
- Pattern: Fetch API with proper error handling
- Types: Full request/response typing
- Errors: Custom error classes

## Requirements

1. Create fetch wrapper function with:
   - Generic type parameters for request/response
   - Error handling and retry logic
   - Request/response interceptors
   - Timeout handling

2. Define TypeScript types for:
   - API response structure
   - Error responses
   - Request configuration options

3. Include features:
   - Base URL configuration
   - Default headers (Content-Type, Accept)
   - Authentication token handling
   - Response transformation

4. Error handling:
   - Network errors
   - HTTP error status codes
   - Timeout errors
   - JSON parsing errors

## Example Structure

```typescript
interface FetchConfig extends RequestInit {
  timeout?: number;
  baseUrl?: string;
  token?: string;
}

interface ApiResponse<T> {
  data: T;
  status: number;
  message?: string;
}

async function fetchApi<T>(
  endpoint: string,
  config?: FetchConfig
): Promise<ApiResponse<T>> {
  // Implementation
}
```

## Output

Generate a reusable, type-safe fetch client with error handling.
