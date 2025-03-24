# React Portfolio Template

Welcome to the **React Portfolio Template**! This repository is a template to help you quickly set up and customize your personal website or portfolio. Use this template as a base for showcasing your projects, skills, and experience.

## Getting Started

To get started, you’ll need to follow a few steps to set up and deploy this template on your own. This guide will walk you through the setup process, necessary prerequisites, and instructions for deploying to Netlify.

### Prerequisites

Before you begin, make sure you have the following:
- **A Netlify account**: [Sign up here](https://www.netlify.com/) if you don’t have one.
- **Basic HTML, CSS, and JavaScript knowledge**: This template uses a standard React setup (with [Vite](https://vite.dev/)). Deep knowledge of React is not critical, but it will be helpful to have some basic understanding of HTML, CSS, and JavaScript.

### Installation

1. **Fork the Repository**
   - Click the "Fork" button on the top right of this repository page to create a copy under your GitHub account.
  
2. **Clone Your Forked Repository (optional)**
   - Clone the forked repository to your local machine to make edits:
     ```bash
     git clone https://github.com/YOUR-USERNAME/portfolio-vanilla-template.git
     ```

3. **Navigate to the Project Directory (optional)**
   - Enter the directory to access project files:
     ```bash
     cd portfolio-vanilla-template
     ```

4. **Customize Your Portfolio**
   - Open the React files (described below in the [customize code](#customize-the-code) section) in the project to personalize your portfolio.
   - Update the content, links, and any other information specific to your profile.
  
### Project Structure

Here’s a quick overview of the project structure:

```
/portfolio-vanilla-template
├── public/                # Static assets (unchanging files like images, icons, etc.)
│   ├── images/            # (IMPORTANT) Directory with your images (change these)
│   ├── favicon.ico
│   └── vite.svg
├── src/                   # Main source code for the React app
│   ├── assets/            # Media assets like images, fonts, and icons
│   ├── components/        # (IMPORTANT) Reusable UI components (buttons, cards, navbar, etc.)
│   ├── utils/             # Utility functions and custom hooks
│   ├── App.tsx            # (IMPORTANT) Root component that defines the app structure
│   ├── main.tsx           # React entry point, rendering App.tsx
│   └── index.css          # (IMPORTANT) Global CSS styles
├── .eslintrc.js           # ESLint configuration for code linting
├── .gitignore             # Git ignore file
├── package.json           # Project dependencies and scripts
├── tsconfig.json          # TypeScript configuration
└── vite.config.ts         # Vite configuration for building the app
```

Within each of these files, there are a comments with `TODO:` tags, explaining where to change their contents. As noted above, the important files/folders that you should look at **first** are:

- **`public/images`**
- **`src/App.tsx`**
- **`src/components`**
- **`src/index.css`**

### Customize the Code

#### Replace Images

Replace each image withing the `public/images` directory with images that suit you. Be sure to keep the **SAME** filenames of each image, for example, replacing `public/images/actvities/activity1.jpeg` would look something like this:

1. Find and download an image for that activity.
2. Ensure the image is of type `JPEG`, if not convert it locally or using a tool such as [Cloud Convert (JPEG Converter)](https://cloudconvert.com/jpeg-converter).
3. Drag and drop the `JPEG` into the `public/images/activities` folder (you should now have the original `activity1.jpeg` and some `newImage.jpeg`).
4. **Delete** the original `activity1.jpeg` (right-click on the file, then hit delete).
5. **Rename** the `newImage.jpeg` (whatever it is currently called) to `activity1.jpeg`.
6. Repeat steps 1-5 for each image...

#### Replace Content

Replacing content is *technically* easier, but will involve a bit more work overall. To do so, you should navigate to the `src/App.tsx` file and read through it briefly. You will notice a series of "comments" for each component with the keyword `TODO`. Navigate to whichever file the `TODO` says and follow the instructions in that file. It might seem like a bit of an "Easter-egg hunt", but the result is a highly-organized, composable app, not unlike those that are used on real websites!


### Deployment

Once your portfolio is set up locally, you can deploy it to Netlify.

1. **Login to Netlify**
   - Go to [Netlify](https://www.netlify.com/) and log in to your account.

2. **Create a New Site**
   - Select “Add new site” from the dashboard and choose “Import an existing project.”
   - Select “GitHub” as your deployment method and connect your GitHub account if prompted.

3. **Select Your Repository**
   - Choose your forked repository `portfolio-vanilla-template` from your GitHub account.

4. **Configure Build Settings**
   - Since this is a static site, you won’t need a build command or any advanced configuration.
   - Click “Deploy Site” to start the deployment process.

5. **Publish and Access Your Portfolio**
   - Once the deployment is complete, you’ll get a Netlify domain (e.g., `portfolio-vanilla-template.netlify.app`).
   - **However**, I'd suggest adding a `Site Name` (i.e. `firstname-lastname`) that will be displayed instead of `portfolio-vanilla-template`.

### Making Updates

To update your portfolio in the future:
1. Make changes in your local repository.
2. Commit and push changes to your GitHub repository:
   ```bash
   git add .
   git commit -m "Update portfolio"
   git push origin main
   ```
3. Netlify will automatically redeploy your site when it detects changes to your `main` branch of the repository.

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config({
  extends: [
    // Remove ...tseslint.configs.recommended and replace with this
    ...tseslint.configs.recommendedTypeChecked,
    // Alternatively, use this for stricter rules
    ...tseslint.configs.strictTypeChecked,
    // Optionally, add this for stylistic rules
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config({
  plugins: {
    // Add the react-x and react-dom plugins
    'react-x': reactX,
    'react-dom': reactDom,
  },
  rules: {
    // other rules...
    // Enable its recommended typescript rules
    ...reactX.configs['recommended-typescript'].rules,
    ...reactDom.configs.recommended.rules,
  },
})
```
## License
This project is open source and available under the [MIT License](LICENSE).
