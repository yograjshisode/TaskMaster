# Design Documentation for TaskMaster

## 1. Introduction

### Project Overview

- Build the web based application which manages the different stages for tasks.
- This application will offere a clear and simplified view of task progress for management team by organizing tasks into distinct stages including To-Do, Doing, and Done.

### Scope

- **Included:** Task creation and tracking through stages, user assignment, roles and permissions using REST API.
- **Excluded:** User Interface, API's for reports like tasks by stages/users.

## 2. Functional Requirements

### Feature List

- **Task Management:** Create, edit, and delete tasks. Assign tasks to user.
- **Task State Changes:** Handle task stage changes.
- **User Roles:** Define roles such as Admin, Manager, and User with specific permissions.

### User Roles and Permissions

- **Admin:** Full access to manage tasks and users.
- **Manager:** Full access to manage tasks. No permission to manage the users.
- **User:** Create and update tasks assigned to them.

## 3. Non-Functional Requirements

### Performance

- The application should update task statuses in real-time with minimal latency.

### Scalability

- Capable of handling a growing number of tasks and users without significant performance degradation.

### Security

- Secure user authentication and authorization.

### Usability

- Swagger API documentation with proper description for API's and fields.

## 4. Architecture Design

### System Architecture

- **Server-Side:** Python with FastAPI for handling server-side logic and API endpoints.
- **Database:** MySQL for storing tasks, user data, and project information.

### Technology Stack

- **Back-End:** Python, FastAPI
- **Database:** MySQL

### Data Flow

- User will commununicate with the server using swagger, postman or REST SDK/utilities. The server processes requests and interacts with the database to store and retrieve information.

## 5. Database Design

### Schema Design

- **Tasks Collection:**

  - `taskId`: Unique identifier
  - `title`: Task title
  - `description`: Detailed task description
  - `status`: Current stage (To-Do, Doing, Done)
  - `assignedTo`: User ID of the assignee
  - `createdAt`: Timestamp of task creation
  - `updatedAt`: Timestamp of last update
- ***Users Collection:***

  - `userId`: Unique identifier
  - `username`: User's name
  - `email`: User's email address
  - `role`: User's role (Admin, Manager, User)
  - `passwordHash`: Encrypted password

## 7. API Design

### API Endpoints

- **GET /tasks:** Retrieve a list of all tasks. Additinal optional filtyers will be available for project, user, stage.
- **POST /tasks:** Create a new task.
- **PUT /tasks/🆔** Update an existing task.
- **DELETE /tasks/🆔** Delete a task.
- **GET /users:** Retrieve a list of users.
- **POST /users:** Create a new user.
- **PUT /users/🆔** Update user information.

### Request and Response Formats

- **Request Payload:** JSON format including task details like title, description, and status.
- **Response Format:** JSON response with task details or status messages.

### Authentication

- **JWT (JSON Web Tokens):** Secure API access with token-based authentication.

## 8. Deployment and Environment

### Hosting

- **Hosting Provider:** Use a cloud service provider such as AWS for deployment.

### Deployment Strategy

- **Continuous Integration/Continuous Deployment (CI/CD):** Automate deployment processes with CI/CD pipelines for consistent updates.

## 9. Testing

### Testing Strategy

- **Unit Testing:** Test individual components and functions.
- **Integration Testing:** Verify that different parts of the application work together as expected.
- **End-to-End Testing:** Simulate user interactions to test the complete workflow.

### Test Cases

- **Task Creation:** Ensure tasks can be created and saved correctly.
- **Task Movement:** Verify tasks can be moved between stages.
- **User Authentication:** Test login and role-based access.

### Quality Assurance

- **Code Reviews:** Regular reviews to maintain code quality.
- **Automated Tests:** Use automated testing tools to catch regressions and bugs.

### Documentation

- **User Guides:** Instructions for using the application.
- **API Documentation:** Detailed information for developers using the API.

## 11. Timeline and Milestones

### Project Timeline

- **Project Kickoff:** Start Date
- **Initial Development:** [Start Date - End Date]
- **Testing Phase:** [Start Date - End Date]
- **Deployment:** [Deployment Date]
- **Post-Launch Support:** [Start Date - End Date]

### Deliverables

- **MVP (Minimum Viable Product):** Basic version with core functionalities.
- **Full Release:** Complete version with all planned features.

## 12. Risk Management

### Risk Assessment

- **Technical Risks:** Potential issues with technology stack compatibility or performance.
- **Operational Risks:** Risks related to project management and resource availability.

### Mitigation Strategies

- **Risk Monitoring:** Regularly assess and address risks.
- **Contingency Planning:** Prepare alternative plans for critical risks.

## 13. Appendices

### Glossary

- Definitions of terms used in the documentation.

### References

- References to any external documents or resources used in the design process.
