---
title: Front End
type: docs
weight: 2
next: docs/Front End/1leaf
prev: docs/Getting Started/1leaf
sidebar:
  open: false
---

### Frontend Project Overview

The frontend of this project is developed using Vite as the build tool and Tailwind CSS for styling. The structure is designed for scalability and maintainability, following standard practices in modern React and TypeScript development.

#### Tech Stack
- **Vite**: Used for faster builds and optimized performance.
- **Tailwind CSS**: Used for styling with utility-first CSS, ensuring consistency and minimal CSS bloat.
- **TypeScript (TSX)**: All components and logic are written in TypeScript to ensure type safety.
- **React**: The core UI framework for building dynamic interfaces.

### Folder Structure

```plaintext
└── 📁frontend
    └── 📁config
        └── local.ts
        └── development.ts
        └── production.ts
        └── index.ts
    └── 📁public
        └── logo.svg
    └── 📁src
        └── 📁api
            └── index.ts
        └── 📁App
            └── App.css
            └── App.tsx
        └── 📁assets
            └── react.svg
        └── 📁Components
            └── Footer.tsx
            └── index.ts
            └── NavBar.tsx
        └── 📁config
            └── config.ts
            └── errors.ts
            └── global.ts
            └── index.ts
            └── local.ts
            └── testData.ts
        └── 📁hooks
            └── index.ts
        └── 📁middlewares
            └── index.ts
        └── 📁Pages
            └── Home.tsx
            └── index.ts
        └── 📁Routes
            └── Home.tsx
        └── 📁utils
            └── commonFunctions.ts
            └── index.ts
            └── inputFieldsFunctions.ts
        └── .DS_Store
        └── index.css
        └── main.tsx
        └── vite-env.d.ts
    └── .DS_Store
    └── eslint.config.js
    └── index.html
    └── package-lock.json
    └── package.json
    └── postcss.config.js
    └── README.md
    └── tailwind.config.js
    └── tsconfig.app.json
    └── tsconfig.json
    └── tsconfig.node.json
    └── vite.config.ts
    └── waypoint.yaml
```

### Key Directories

1. **📁config**
   - Contains environment-specific configuration files (`local.ts`, `development.ts`, `production.ts`) and shared configuration logic (`index.ts`).

2. **📁public**
   - Stores static assets like `logo.svg` that do not require processing by Vite.

3. **📁src**
   - **api**: API integration layer (`index.ts`).
   - **App**: The root component (`App.tsx`) and global styling for the app (`App.css`).
   - **assets**: Contains visual assets like `react.svg`.
   - **Components**: Reusable UI components such as `BlogCard.tsx`, `NavBar.tsx`, and modals for different forms and registration steps.
   - **config**: Application-wide configuration logic (`config.ts`, `global.ts`) and test data.
   - **hooks**: Reusable custom hooks (`index.ts`).
   - **middlewares**: Middleware logic for the application.
   - **Pages**: All route-based pages like `About.tsx`, `Login.tsx`, `BlogPage.tsx`, and more.
   - **Routes**: Contains logic for routing, with `Events.tsx` and `GeekSquad.tsx`.
   - **utils**: Utility functions like `commonFunctions.ts` and `inputFieldsFunctions.ts`.

4. **📁Root Files**
   - Configuration files for various tools: `eslint.config.js`, `tailwind.config.js`, `vite.config.ts`, `tsconfig.json`, etc.
   - Build configuration (`package.json`, `postcss.config.js`).
   - Entry point for Vite (`index.html`) and the main application (`main.tsx`).

### Development Flow

- **Local Development**: Configuration for local development is in `config/local.ts`.
- **Styling**: Tailwind CSS is used for all styling purposes, with the configuration in `tailwind.config.js`.
- **Build Process**: Vite is used for building and bundling the application. Scripts and build processes are defined in the `package.json`.

### References

- [Vite Documentation](https://vitejs.dev/guide/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [React Documentation](https://reactjs.org/docs/getting-started.html)
- [ESLint Documentation](https://eslint.org/docs/user-guide/getting-started)
- [PostCSS Documentation](https://postcss.org/)
- [Node.js Documentation](https://nodejs.org/en/docs/)
- [Vite Configuration](https://vitejs.dev/config/)
- [TSConfig Reference](https://www.typescriptlang.org/tsconfig)