

---

## Process 1: Initialize and Set Up the Project

This process outlines the steps to initialize a new project with Tailwind CSS and Vite.



Make sure that Node.js is installed on your system. If it is not, you can install it from [here](https://nodejs.org/en/download/package-manager/current).

### Step 1: Create new project environment with node js
Open your terminal and run the following command to initialize a new project:

```sh
npm init -y
```


### 2. Install Required Packages (This is using Vite; you can use one of your choice)

```sh
npm install -D tailwindcss postcss autoprefixer vite vite-plugin-html
```

### 3. Initialize Tailwind CSS Configuration

```sh
npx tailwindcss init -p
```

### 4. Create and Edit a CSS File

Create a file named `style.css` in your project root and add the following content:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Include this `style.css` file in your HTML files:

```html
<link rel="stylesheet" href="/style.css">
```

### 5. Update Tailwind CSS Configuration

In your `tailwind.config.js` file, update the `content` array to include:

```js
content: ["*"],
```

### 6. Update `package.json` Scripts

Add the following script to your `package.json` file:

```json
"scripts": {
  "start": "vite"
}
```

### 7. Start the Development Server

Run the following command to start the development server:

```sh
npm run start
```

### Additional Configuration

To view all the configuration options, run:

```sh
npx tailwindcss init confsuyog --full
```

### Build Node Modules

Before running the above command, ensure you have all required node modules by running:

```sh
npm install
```
(Note: Node.js must be installed on your system.)

## Pushing the Site to Production

### Update `package.json` Scripts for Production

Add the following commands to the `scripts` section of your `package.json`:

```json
"scripts": {
  "start": "vite",
  "build": "vite build"
}
```

### Build the Project for Production

Run the following command to build the project:

```sh
npm run build
```

This will generate a `dist` folder containing the production files. Run the build command again if you make any changes:

```sh
npm run build
```

### Setting Up Multiple HTML Pages

To handle multiple HTML files, create a `vite.config.js` file in your project root and add the following lines:

```js
import { defineConfig } from 'vite';
import { createHtmlPlugin } from 'vite-plugin-html';

export default defineConfig({
  build: {
    rollupOptions: {
      input: {
        main: '/index.html',
        about: '/about.html',
        contact: '/contact.html',
        // add more pages as you create them 
      },
    },
  },
  plugins: [
    createHtmlPlugin({
      minify: false, // turn this to true if you want to minify HTML files
    }),
  ],
});

// created by @suyog coding 
```

### Directory Structure

After setting up, your project structure should look like this:

```plaintext
project_name/
├── index.html
├── about.html
├── contact.html
├── style.css
├── tailwind.config.js
├── vite.config.js
└── package.json
```

### Final Checklist

- [ ] Ensure all commands have been executed successfully.
- [ ] Verify that all required files (HTML, CSS, config files) are in place.
- [ ] Run `npm run build` to generate production files.

### Useful Links

- [Vite Documentation](https://vitejs.dev/guide/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs/installation)

This completes the setup of the project with Tailwind CSS and Vite. Enjoy coding!
```

