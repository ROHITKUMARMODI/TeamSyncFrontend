
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
![image](https://github.com/user-attachments/assets/6f77865e-c333-44a5-9995-6d3d20ea6eff)
![image](https://github.com/user-attachments/assets/ff36eac6-cf4f-4acc-a29d-e37308e22897)
![image](https://github.com/user-attachments/assets/f731f4f5-ef77-4d45-b0cd-21401de3c411)
![image](https://github.com/user-attachments/assets/2573000a-410a-42e5-971a-09b419560258)
![image](https://github.com/user-attachments/assets/1407dd15-500d-4c62-8969-61b874249921)
![image](https://github.com/user-attachments/assets/8f168bb2-bb14-45da-a202-1fdd3cf51e44)

                           +------------------+
