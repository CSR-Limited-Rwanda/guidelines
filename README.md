# Development Guidelines for Live Projects

## Introduction
This document outlines mandatory guidelines that all team members must follow when working on our live projects. These guidelines ensure code quality, maintain security, and prevent potential issues in production.

## UI/UX Guidelines
### Design Consistency
- Follow established design system and patterns
- Maintain consistent spacing and alignment
- Use approved color schemes and typography
- Ensure accessibility standards are met
- Document any new UI patterns

### User Experience
- Design for mobile-first approach
- Consider loading states and transitions
- Implement proper error states
- Ensure responsive design across devices
- Validate user flows before implementation

## Frontend Guidelines
### Code Quality
- Write clear, descriptive component names
- Keep components small and focused
- Remove console.logs and debuggers
- Follow existing code patterns
- Use proper TypeScript/PropTypes

### Performance
- Optimize images before committing
- Implement proper code splitting
- Keep bundle sizes in check
- Use proper caching strategies
- Optimize rendering performance

### Testing
- Write unit tests for components
- Test responsive breakpoints
- Verify browser compatibility
- Test error states and loading
- Check accessibility compliance

## Backend Guidelines
### Data Security
- Never commit API keys or secrets
- Use environment variables
- Implement proper data validation
- Secure all API endpoints
- Follow authentication best practices

### Database
- Write safe database migrations
- Back up data before migrations
- Implement proper indexing
- Handle data relationships carefully
- Document schema changes

### Testing Requirements
- Write comprehensive unit tests for all services
- Test all edge cases in business logic
- Mock external services appropriately
- Write integration tests for critical flows
- Test database queries and migrations
- Cover error scenarios and exceptions
- Test with different user permissions
- Verify API response formats
- Test pagination and filtering
- Ensure proper error handling coverage

### API Design
- Follow REST/GraphQL conventions
- Implement proper error handling
- Document all endpoints
- Version APIs appropriately
- Implement rate limiting
## API URL Structure

The following is the standard structure for API endpoints:
When access resources level api endpoint, you can use resource-id or resource-slug.

### Base Structure:

`{app-name}/{feature}/{resource}/{resource-id}/{action}`

1. **Collection-level Endpoint:**  
   **URL:** `app-name/feature/items/`  
   **Purpose:** Used for listing all items or creating a new item.  
   **Methods:**

      - `GET` — List all items.

2. **Collection-level Endpoint:**  
   **URL:** `app-name/feature/items/new/`  
   **Purpose:** Used for creating a new item.  
   **Methods:**

      - `POST` — Create a new item.

3. **Single Resource Endpoint:**  
   **URL:** `app-name/feature/items/{item-id}/`  
   **Purpose:** Used for retrieving item by its ID.  
   **Methods:**

      - `GET` — Retrieve the item.
4. **Single Resource Endpoint:**  
   **URL:** `app-name/feature/items/{item-id}/delete/`  
   **Purpose:** Used for  deleting a specific item by its ID.  
   **Methods:**

      - `DELETE` — Delete the item.

4. **Update Endpoint:**  
   **URL:** `app-name/feature/items/{item-id}/update/`  
   **Purpose:** Used for updating a specific item by its ID.  
   **Methods:**

      - `PUT` — Replace the entire resource.
      - `PATCH` — Partially update the resource.

5. **Action-specific Endpoint (e.g., Delete, Archive):**  
   **URL:** `app-name/feature/items/{item-id}/delete/`  
   **Purpose:** Used for performing a specific action on an item, such as soft delete.  
   **Methods:**

      - `POST` — Perform the action (e.g., soft delete).

6. **Filtered or Nested Resources:**

      - **URL:** `app-name/feature/items/category/{category-id}/`
      - **URL:** `app-name/feature/items/status/{status}/`  
        **Purpose:** Retrieve items filtered by category or status.  
        **Methods:**
      - `GET` — Retrieve filtered data.

7. **Bulk Actions:**  
   **URL:** `app-name/feature/items/bulk-delete/`  
   **Purpose:** Used for performing bulk operations on multiple resources.  
   **Methods:**

      - `POST` — Perform bulk actions (e.g., delete multiple items).

8. **Search and Query Parameters:**  
   **URL:** `app-name/feature/items/?search=term&filter=value`  
   **Purpose:** Retrieve items using search or filter criteria.  
   **Methods:**
      - `GET` — Retrieve filtered data.

### Notes:

- **Plural nouns** are used for resources (e.g., `items`, `categories`) for consistency.
- **HTTP methods** imply the action (`POST`, `PUT`, `PATCH`, `DELETE`), except for specific actions like `/update/` or `/delete/`.
- **Language specifics** in python, instead of (`resource-id` or `resource-slug`) you should use (`resource_id` or `resource_slug`).
- **Preferences** based on teams and standard preferences, you can add ( a tailing slash `/`) at the end of the endpoint or not. But make sure it's consistent
- Avoid including verbs in endpoints, except for special actions (e.g., `/update/`, `/delete/`).

---


## Common Guidelines
### Pull Request Process
- Run ALL tests locally
- Keep PRs focused and small
- Write clear PR descriptions
- Include necessary screenshots
- Respond to reviews within 24 hours

### Version Control
- Write clear commit messages
- Keep branches up to date
- Don't commit node_modules
- Create feature branches
- Follow branching strategy

### Documentation
- Update README when needed
- Document environment variables
- Add API documentation
- Document breaking changes
- Keep docs up to date


## Consequences of Not Following Guidelines
Not following these guidelines can cause serious problems for our live projects, causing PRs to be rejected and creating delays and extra work for everyone. More importantly:

- UI/UX violations can lead to inconsistent user experience and accessibility issues
- Frontend violations can cause performance problems and poor user experience
- Backend violations could lead to data loss or security vulnerabilities

Read these guidelines every day before starting your work until they are engraved in your everyday strategy.

For any questions or clarifications, please reach out to your team lead.
