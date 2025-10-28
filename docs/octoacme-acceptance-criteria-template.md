# OctoAcme — Acceptance Criteria Template

## Purpose
Provide a structured format for writing clear, testable acceptance criteria that align stakeholders and enable efficient delivery.

---

## Standard Acceptance Criteria Format

### User Story
**As a** [persona/role]  
**I want** [goal/action]  
**So that** [business value/benefit]

### Acceptance Criteria

Use the Given-When-Then format for clarity and testability:

**Scenario 1:** [Brief scenario name]
- **Given** [initial context or precondition]
- **When** [action or event occurs]
- **Then** [expected outcome]
- **And** [additional expected outcomes, if any]

**Scenario 2:** [Brief scenario name]
- **Given** [initial context or precondition]
- **When** [action or event occurs]
- **Then** [expected outcome]

### Non-Functional Requirements (if applicable)
- **Performance:** [response time, throughput expectations]
- **Security:** [authentication, authorization, data protection needs]
- **Accessibility:** [WCAG compliance, keyboard navigation, screen reader support]
- **Usability:** [user experience standards, error handling]
- **Reliability:** [uptime requirements, error rates]

### Definition of Done
- [ ] Code implemented and follows team standards
- [ ] Unit tests written with adequate coverage
- [ ] Integration tests added (if applicable)
- [ ] Code reviewed and approved
- [ ] Documentation updated
- [ ] Acceptance criteria validated by Business Analyst or Product Manager
- [ ] QA Lead sign-off (if required)
- [ ] Deployed to staging and smoke tested
- [ ] Release notes updated

### Out of Scope
- [Explicitly list what is NOT included in this work item]
- [Helps prevent scope creep and clarifies boundaries]

---

## Example: User Authentication Feature

### User Story
**As a** new user  
**I want** to create an account with my email and password  
**So that** I can access personalized features and save my preferences

### Acceptance Criteria

**Scenario 1:** Successful account creation
- **Given** I am on the registration page
- **When** I enter a valid email, strong password, and accept terms
- **And** I click the "Create Account" button
- **Then** My account is created in the system
- **And** I receive a confirmation email
- **And** I am redirected to the welcome page

**Scenario 2:** Invalid email format
- **Given** I am on the registration page
- **When** I enter an invalid email format (e.g., "notanemail")
- **And** I click the "Create Account" button
- **Then** I see an error message "Please enter a valid email address"
- **And** The account is not created

**Scenario 3:** Weak password
- **Given** I am on the registration page
- **When** I enter a password shorter than 8 characters
- **And** I click the "Create Account" button
- **Then** I see an error message "Password must be at least 8 characters"
- **And** The account is not created

**Scenario 4:** Duplicate email
- **Given** An account already exists with email "user@example.com"
- **When** I try to register with the same email
- **Then** I see an error message "An account with this email already exists"
- **And** I am offered a "Forgot Password?" link

### Non-Functional Requirements
- **Performance:** Registration completes within 2 seconds under normal load
- **Security:** 
  - Passwords are hashed using bcrypt with minimum 10 rounds
  - Confirmation emails expire after 24 hours
  - Rate limiting: max 5 registration attempts per IP per hour
- **Accessibility:** Form is fully keyboard navigable and screen reader compatible
- **Usability:** Real-time password strength indicator shows weak/medium/strong

### Definition of Done
- [x] Code implemented following team coding standards
- [x] Unit tests for validation logic with 90%+ coverage
- [x] Integration tests for registration flow
- [x] Code reviewed and approved by senior developer
- [x] API documentation updated with new endpoints
- [x] Security review completed
- [x] Manual QA testing on staging environment
- [x] Deployed to staging and smoke tested
- [x] Release notes drafted

### Out of Scope
- Social login (Google, Facebook) - planned for future release
- Two-factor authentication - separate work item
- Account verification via SMS - not in current roadmap
- Password recovery flow - covered in separate user story

---

## Tips for Writing Good Acceptance Criteria

### Do's
✓ Use clear, specific language  
✓ Make criteria testable and measurable  
✓ Include both positive and negative scenarios  
✓ Consider edge cases and error conditions  
✓ Align with business value in the user story  
✓ Collaborate with Developers, QA, and stakeholders to refine  
✓ Keep criteria independent and atomic  

### Don'ts
✗ Use vague terms like "user-friendly" or "fast" without definition  
✗ Mix multiple features in one set of criteria  
✗ Specify implementation details (leave that to developers)  
✗ Forget error handling and edge cases  
✗ Write criteria that can't be objectively verified  
✗ Skip collaboration with QA and Developers  

---

## Common Pitfalls to Avoid

1. **Ambiguity:** "The system should work well under load"
   - ✓ Better: "The system handles 1000 concurrent users with <2s response time"

2. **Missing error cases:** Only describing the happy path
   - ✓ Better: Include scenarios for validation errors, timeouts, and failures

3. **Implementation details:** "Use a React component with Redux state"
   - ✓ Better: Focus on behavior, not technology choices

4. **Unmeasurable criteria:** "Users should find it easy to use"
   - ✓ Better: "Users complete the task in under 3 clicks without errors"

5. **Scope creep:** Adding "nice-to-have" features as acceptance criteria
   - ✓ Better: Keep focused on core requirements, document future enhancements separately

---

## Collaboration Points

### Business Analyst + Product Manager
- Ensure acceptance criteria align with business goals
- Validate that scenarios cover key user journeys
- Prioritize criteria for MVP vs. future iterations

### Business Analyst + Developers
- Review technical feasibility of criteria
- Clarify any ambiguous requirements
- Discuss implementation approach and effort

### Business Analyst + QA Lead
- Ensure criteria are testable
- Identify test scenarios and edge cases
- Align on Definition of Done

### Business Analyst + UX Designer
- Validate usability requirements
- Ensure design specifications match acceptance criteria
- Review user flow consistency

---

## Related Templates and Resources

- [Project Planning Guide](octoacme-project-planning.md) - Backlog Item Template
- [Execution and Tracking](octoacme-execution-and-tracking.md) - Quality practices
- [Cross-Functional Collaboration Checklist](octoacme-collaboration-checklist.md)
- [Roles and Personas](octoacme-roles-and-personas.md) - Business Analyst role definition
