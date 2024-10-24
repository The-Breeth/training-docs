---
title: FrontEnd
type: docs
weight: 3
prev: docs/Front End/2leaf
next: docs/Front End/4leaf
---

# Tailwind CSS Setup and Integration in a React Project

Here’s how you can set up Tailwind CSS in a React project, along with some examples of cards, drawers, and side panels using Tailwind CSS.

## 1. Create a New React Project

- Install Tailwind CSS and its dependencies:

```
npx create-react-app my-app
cd my-app

```

## 2. Install Tailwind CSS

```
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init

```

## 3. Configure tailwind.config.js

- Inside the newly created tailwind.config.js file, add the paths to all of your template files:

```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    './src/**/*.{js,jsx,ts,tsx}',
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

```
## 4. Add Tailwind Directives to CSS

- Open src/index.css and add the following lines to import Tailwind’s base, components, and utilities styles:

```
@tailwind base;
@tailwind components;
@tailwind utilities;

```

## 5. Start the React Application

You’re all set! Now run your application:

```
npm start

```

### Examples of Components Using TailwindCSS

- **Card Example**:

```
import React from 'react';

const Card = () => {
  return (
    <div className="max-w-sm rounded overflow-hidden shadow-lg m-4 bg-white">
      <img className="w-full" src="https://via.placeholder.com/400" alt="Sunset in the mountains" />
      <div className="px-6 py-4">
        <div className="font-bold text-xl mb-2">Beautiful Mountain</div>
        <p className="text-gray-700 text-base">
          Experience the beauty of nature at its finest with this stunning view of the mountains during sunset.
        </p>
      </div>
      <div className="px-6 pt-4 pb-2">
        <span className="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">#nature</span>
        <span className="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">#mountains</span>
        <span className="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700">#sunset</span>
      </div>
    </div>
  );
};

export default Card;

```

- **Explanation**:

- A simple card with an image, title, description, and tags.
- The Tailwind classes rounded, shadow-lg, and overflow-hidden give it a clean, bordered look.

- **Drawer Example**:

```
import React, { useState } from 'react';

const Drawer = () => {
  const [isOpen, setIsOpen] = useState(false);

  return (
    <div>
      <button
        onClick={() => setIsOpen(!isOpen)}
        className="bg-blue-500 text-white p-3 rounded-md"
      >
        Open Drawer
      </button>

      <div
        className={`fixed top-0 right-0 w-64 bg-white h-full shadow-lg transform transition-transform ${isOpen ? 'translate-x-0' : 'translate-x-full'}`}
      >
        <div className="p-4">
          <button onClick={() => setIsOpen(false)} className="text-gray-500">
            Close
          </button>
          <h2 className="text-2xl font-semibold mt-4">Drawer Content</h2>
          <p className="mt-2 text-gray-700">
            This is a side drawer where you can add some additional content, like navigation or settings.
          </p>
        </div>
      </div>
    </div>
  );
};

export default Drawer;

```

- **Explanation**: 

- This example shows how to create a drawer that slides in from the right.
- The drawer uses Tailwind’s transform and transition-transform classes to handle sliding effects.

### Side Panel Example

``` 
import React, { useState } from 'react';

const SidePanel = () => {
  const [isOpen, setIsOpen] = useState(false);

  return (
    <div className="flex">
      <button
        onClick={() => setIsOpen(!isOpen)}
        className="bg-indigo-500 text-white p-3 rounded-md"
      >
        Toggle Side Panel
      </button>

      <div
        className={`fixed top-0 left-0 h-full w-64 bg-gray-800 text-white transition-transform transform ${isOpen ? 'translate-x-0' : '-translate-x-full'}`}
      >
        <div className="p-4">
          <button onClick={() => setIsOpen(false)} className="text-gray-400">
            Close
          </button>
          <h2 className="text-2xl font-semibold mt-4">Side Panel</h2>
          <ul className="mt-4 space-y-2">
            <li className="hover:bg-gray-700 p-2 rounded">Dashboard</li>
            <li className="hover:bg-gray-700 p-2 rounded">Settings</li>
            <li className="hover:bg-gray-700 p-2 rounded">Profile</li>
          </ul>
        </div>
      </div>
    </div>
  );
};

export default SidePanel;

```

- **Explanation**:
- This side panel uses a similar approach to the drawer but slides in from the left side.
- It’s ideal for use as a sidebar navigation menu.

## Conclusion

With Tailwind CSS integrated into your React project, you can quickly build components like cards, drawers, and side panels with clean, customizable styles. The examples above can be further extended by adding animations, responsive behavior, and more complex layouts depending on your requirements. Tailwind CSS’s utility-first approach makes it easy to style React components efficiently.

```

```
