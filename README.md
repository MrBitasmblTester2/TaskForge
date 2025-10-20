# TaskForge

Description
A web-based task management application built with React and Node.js. TaskForge allows users to sign up, log in, and manage tasks across multiple projects. Users can create, edit, and delete tasks, which are categorized by project and sorted by priority. The backend uses JWT for secure authentication.

## Tech Stack
- React
- Node.js

## Requirements
- Use JWT for user authentication in backend routes (protect routes with middleware that verifies the Authorization header)
- Categorize tasks by project ID and fetch accordingly (use URL params to specify project)
- Display tasks sorted by priority on the client (use Array.sort in React before rendering)

## Installation
1. Clone the repo:
   bash
   git clone https://github.com/yourusername/TaskForge.git
   
2. Backend setup:
   bash
   cd TaskForge/server
   npm install
   
   - Create a `.env` file in the `server` directory with the following variables:
     env
     JWT_SECRET=your_jwt_secret
     PORT=5000
     
3. Frontend setup:
   bash
   cd ../client
   npm install
   
   - Create a `.env` file in the `client` directory with the following variable:
     env
     REACT_APP_API_URL=http://localhost:5000/api
     

## Usage
1. Start the backend server:
   bash
   cd server
   npm start
   
2. Start the frontend development server:
   bash
   cd client
   npm start
   
3. Open your browser and navigate to `http://localhost:3000`.
4. Register a new account or log in.
5. Create or select a project to view its tasks.
6. Add, edit, or delete tasks. Tasks will display sorted by priority.

## Implementation Steps
1. Initialize a Node.js project and install dependencies (express, jsonwebtoken, dotenv).
2. Set up middleware to validate JWT from the Authorization header.
3. Define Express routes for authentication (register, login) and task management (CRUD), protecting relevant routes.
4. Use URL parameters to filter tasks by `projectId` in task routes.
5. Initialize a React app using Create React App.
6. Create authentication context/hooks to manage user login and token storage.
7. Build login and registration forms; integrate with backend JWT auth.
8. Implement project and task management components in React.
9. Fetch tasks for a given project from `/api/projects/:projectId/tasks`.
10. Sort the fetched tasks by their priority property using `Array.sort` before rendering.
11. Add UI elements for adding, editing, and deleting tasks with corresponding API calls.
12. Test protected routes by attempting to access without a valid token.

## API Endpoints
- POST `/api/auth/register` — register a new user
- POST `/api/auth/login` — authenticate and receive a JWT
- GET `/api/projects/:projectId/tasks` — fetch tasks for a specific project (protected)
- POST `/api/projects/:projectId/tasks` — create a new task in a project (protected)
- PUT `/api/projects/:projectId/tasks/:taskId` — update a task (protected)
- DELETE `/api/projects/:projectId/tasks/:taskId` — delete a task (protected)