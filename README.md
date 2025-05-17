
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
![image](https://github.com/user-attachments/assets/fca3f8b7-4825-4984-bb42-4de41f946927)
![image](https://github.com/user-attachments/assets/791cd5a1-d532-4d2a-b878-f27bef17ff0a)
![image](https://github.com/user-attachments/assets/e889a1ab-2e1f-43c7-a53e-5c0b95acfca9)
##ERD

#Users

+----------------+
| users          |
+----------------+
| _id (PK)       |
| name           |
| email          |
| role_id (FK)   |
+----------------+
       |         
       |  (M:1) Each user has one role
       |
       |-------------------+
                           |
                     +---------+
                     | roles   |
                     +---------+
                     | _id (PK)|
                     | role_name|
                     +---------+
#Accounts

users (1) ----------- (1:1) accounts

+-------------------+      +------------------+
| users             |      | accounts         |
+-------------------+      +------------------+
| _id (PK)          |      | _id (PK)         |
| name              |      | user_id (FK)     |
+-------------------+      | login_info       |
                           | created_at       |
                           +------------------+
#WorkSpaces

users (1) ----------- (0..*) workspaces

+-------------------+      +-------------------+
| users             |      | workspaces        |
+-------------------+      +-------------------+
| _id (PK)          |      | _id (PK)          |
+-------------------+      | name              |
                           | created_by (FK)   |
                           | created_at        |
                           +-------------------+
 #Members   
 +-----------------+
workspaces (1) ----------- (0..*) members (0..*) ----------- (1) users
                                 \                     /
                                  \                   /
                                    ----> roles (1)

+-------------------+      +-----------------+      +-------------------+
| workspaces        |      | members         |      | users             |
+-------------------+      +-----------------+      +-------------------+
| _id (PK)          |      | _id (PK)        |      | _id (PK)          |
+-------------------+      | workspace_id FK |      +-------------------+
                           | user_id FK      |
                           | role_id FK      |
 
workspaces (1) ----------- (0..*) members (0..*) ----------- (1) users
                                 \                     /
                                  \                   /
                                    ----> roles (1)

+-------------------+      +-----------------+      +-------------------+
| workspaces        |      | members         |      | users             |
+-------------------+      +-----------------+      +-------------------+
| _id (PK)          |      | _id (PK)        |      | _id (PK)          |
+-------------------+      | workspace_id FK |      +-------------------+
                           | user_id FK      |
                           | role_id FK      |
                           +-----------------+
#Projects
workspaces (1) ----------- (0..*) projects
users (1) ---------------- (0..*) projects
+-------------------+      +------------------+
| workspaces        |      | projects         |
+-------------------+      +------------------+
| _id (PK)          |      | _id (PK)         |
+-------------------+      | name             |
                           | workspace_id (FK)|
                           | created_by (FK)  |
                           | created_at       |
                           +------------------+
#Tasks

projects (1) ----------- (0..*) tasks
users (1) --------------- (0..*) tasks (assigned_to)

+-------------------+      +------------------+
| projects          |      | tasks            |
+-------------------+      +------------------+
| _id (PK)          |      | _id (PK)         |
+-------------------+      | title            |
                           | project_id (FK)  |
                           | assigned_to (FK) |
                           | status           |
                           | due_date         |
                           +------------------+
