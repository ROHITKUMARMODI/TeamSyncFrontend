
Tech Stack:
Frontend: React.js + TypeScript, Tailwindcss
Backend: Node.js, Express.js with TypeScript
Database: MongoDB with Mongoose
Authentication: Google OAuth + cookie-session for login sessions
Others: REST APIs, Postman, GitHub

Approach:
Google Auth with Sessions: Used cookie-session to store authenticated user sessions after Google login. Protected routes using custom middleware (isAuthenticated).
TypeScript Throughout: Applied type safety in both frontend and backend (e.g., request interfaces, model types).

Modular APIs: Built separate routes and controllers for tasks, projects, workspaces, and members.
Clean UI: Dashboard displays stats like total tasks, completed tasks, and recent projects with tab navigation (Recent Projects, Tasks, Members).

![Screenshot 2025-05-17 110110](https://github.com/user-attachments/assets/bd28393a-b597-40e0-99f7-842f45bf4ffa)
![Screenshot 2025-05-17 120136](https://github.com/user-attachments/assets/2c13b793-f750-4f75-82ea-d72c2a591ebf)
![image](https://github.com/user-attachments/assets/e2a19e96-bc54-493c-be8c-8f5077a91972)
