# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default tseslint.config({
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

- Replace `tseslint.configs.recommended` to `tseslint.configs.recommendedTypeChecked` or `tseslint.configs.strictTypeChecked`
- Optionally add `...tseslint.configs.stylisticTypeChecked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and update the config:

```js
// eslint.config.js
import react from 'eslint-plugin-react'

export default tseslint.config({
  // Set the react version
  settings: { react: { version: '18.3' } },
  plugins: {
    // Add the react plugin
    react,
  },
  rules: {
    // other rules...
    // Enable its recommended rules
    ...react.configs.recommended.rules,
    ...react.configs['jsx-runtime'].rules,
  },
})
```
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

