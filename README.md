# Development Guidelines for Live Projects

## Introduction
This document outlines mandatory guidelines that all team members must follow when working on our live projects. These guidelines ensure code quality, maintain security, and prevent potential issues in production.

## 1. Before Creating a Pull Request
- Run ALL tests locally - no exceptions
- Test your feature manually with different scenarios
- Check your code for any console logs or debug statements
- Remove any commented-out code
- Make sure your branch is up to date with the main branch

## 2. Code Quality Standards
- Write clear, descriptive variable and function names
- Keep functions small and focused on one task
- Add comments only for complex logic, not obvious code
- Follow the existing code style and patterns
- Use proper indentation and formatting
- Remove unused imports and variables

## 3. Pull Request Guidelines
- Keep PRs small and focused on one feature/fix
- Write clear PR descriptions explaining what and why
- Include screenshots for UI changes
- List any important changes that reviewers should focus on
- Respond to review comments within 24 hours

## 4. Testing Requirements
- Write tests for new features
- Test edge cases (empty states, error states)
- Check mobile responsiveness for UI changes
- Test with different user roles if applicable
- Verify that existing features still work

## 5. Security and Configuration
- Never commit API keys or passwords
- Don't push sensitive data even by accident
- Use environment variables for all secrets
- Be extra careful when changing configuration files
- Double-check database changes and migrations

## 6. Version Control Practices
- Write clear commit messages
- Keep commits focused and logical
- Don't commit commented code
- Don't commit package-lock.json unless you've added packages
- Create feature branches from the latest main branch

## 7. Documentation Requirements
- Update README if you change setup steps
- Document new environment variables
- Add JSDoc comments for complex functions
- Update API documentation for new endpoints
- Document any breaking changes

## 8. Error Handling
- Always handle possible errors
- Add proper error messages for users
- Log important errors for debugging
- Don't show technical errors to users
- Test error scenarios

## 9. Performance Considerations
- Optimize images before committing
- Don't load unnecessary data
- Use pagination for large data sets
- Keep bundle sizes in check
- Remove console.log statements

## Important Reminders
- These guidelines are mandatory, not suggestions
- Violations will result in PR rejection
- Ask for help if you're unsure about anything
- Better to ask questions than to break something
- Keep an eye on the size of your changes

## Consequences of Not Following Guidelines

Not following those guidelines can cause serious problems for our live projects, cause PRs to be rejected, hence causing delays and extra work for everyone. More importantly, backend, ignoring these could lead to data loss or security problems. So read them every day before starting your work, until they are engraved in your everyday strategy.

For any questions or clarifications about these guidelines or consequences, please reach out to your team lead
