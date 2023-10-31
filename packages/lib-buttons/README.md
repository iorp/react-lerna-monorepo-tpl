# Usage
## Install
npm install 




## How this was done(not necessary to use ):  Creating a Simple React Component Library template with Rollup and Babel
 
### Step 1: Project Setup and Installation

mkdir router
cd router
npm init -y

Install the necessary dependencies:

npm install react react-dom @babel/core @babel/preset-env @babel/preset-react rollup rollup-plugin-babel --save-dev

### Step 2: Create Project Files and Directories

Create the following project structure and files:

router/
  ├── src/
  │     ├── DemoButton.js
  ├── dist/
  ├── .babelrc
  ├── rollup.config.js
  ├── package.json

### Step 3: Configure Babel

Create a .babelrc file in the project root with the following content:

{
  "presets": ["@babel/preset-env", "@babel/preset-react"]
}

### Step 4: Create a React Component

Create a simple React component inside src/DemoButton.js:

// src/DemoButton.js
import React from 'react';

function DemoButton({ text }) {
  return <button>{text}</button>;
}

export default DemoButton;

### Step 5: Configure Rollup

Create a rollup.config.js file in the project root with the following content:

// rollup.config.js
import babel from 'rollup-plugin-babel';

export default {
  input: 'src/index.js', // Corrected input path
  output: {
    file: 'dist/router.js',
    format: 'cjs',
  },
  plugins: [babel()],
}

### Step 6: Update package.json

Update your package.json to include the build script:

{
  "name": "router",
  "version": "1.0.0",
  "description": "A demo React component library",
  "main": "dist/router.js",
  "scripts": {
    "build": "rollup -c"
  },
  "peerDependencies": {
    "react": "^16.8.0",
    "react-dom": "^16.8.0"
  }
}


### Step 7: Build the Library

Run the build script to generate the component library:

npm run build

### Step 8: Link the Library
npm link 
After running the build, your component library should be available in the dist directory. This setup explicitly uses Babel to transpile JSX code before passing it to Rollup, ensuring the correct bundling of your React component library.
