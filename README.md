# vite-reactjs-tailwind-starter

vite js starter for reactjs with tailwind css & support for auth, my most used libraries, custom hooks etc

## steps to create a vite project

1. `yarn create vite`
1. follow the prompt on your terminal to select the type of project & how to start the dev server.

## cleaning up default vite starter

1. remove
   `import logo from './logo.svg'`
   ` import './App.css'`
   lines from `App.jsx`
1. remove line `6` from `App.jsx`
1. remove `<header>` element from `App.jsx`

1. remove/clean `App.css`
1. for a tailwindcss project I prefer cleaning everything from `index.css` file as well.
1. create a public folder at root (`project_name/public`)and add `_redirects` in order to prevent `file not found` error in netlify

## setting up tailwindcss

1. create a file `tailwind.css` at `/src/` and add `@tailwind base; @tailwind components; @tailwind utilities;` in it

1. make sure there's a `index.css` file already present at `/src/`

1. use the command `npx tailwind init` to create a `tailwind.config.js` file at root directory. Inside `tailwind.config.js` file add the following command inside purge array. `"./src/**/*.jsx"`
   & `darkmode: "class"` if you want to add toggle dark mode functionality
1. finally, add the following script to start tailwind jit and make it watch for changes.
   `"build-css": "npx tailwindcss -i ./src/tailwind.css -o ./src/index.css --minify --jit --purge='./src/**/*.jsx' -w"`

   NOTE: use `npm run build-css` command to run this script instead of `yarn run build-css`
