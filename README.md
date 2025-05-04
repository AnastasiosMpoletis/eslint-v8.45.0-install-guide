# ESLint Older Versions Install Guide for Udemy. React - The Complete Guide 2025 (incl. Next.js, Redux) by Maximilian Schwarzmüller Projects.

## How to install eslint v8.45.0:
1. Make sure to have the **ESLint extension** downloaded and enabled in VSCode (Identifier dbaeumer.vscode-eslint).
    ![image](https://github.com/user-attachments/assets/90ba8f4c-35ec-47b5-aa14-13e2c135f7b1)
2. Delete ```node_modules``` from root folder, if there are any.<br>
    ![image](https://github.com/user-attachments/assets/34208089-d00b-4f75-a1dc-a718a47f1e8e)
3. Delete ```^``` from ```package.json``` ```"eslint": "^8.45.0"```.
    ![image](https://github.com/user-attachments/assets/b8bf1ad7-5da8-4f72-b572-d9b09344f151)
4. Run in root folder: 
    ```go 
    npm install
    ```
5. Check ```eslint``` version. Run in root folder: 
    ```go
    npx eslint --version 
    ```
  	Should be the same as the version from ```package.json``` (v8.45.0).
6. Create ```.eslintrc.cjs``` in root folder with content:
	```go
    // .eslintrc.cjs
    module.exports = {
      root: true,
      parserOptions: {
        ecmaVersion: "latest",
        sourceType: "module",
        ecmaFeatures: {
          jsx: true,
        },
      },
      env: {
        browser: true,
        es2021: true,
      },
      plugins: ["react", "react-hooks"],
      extends: [
        "eslint:recommended",
        "plugin:react/recommended",
        "plugin:react-hooks/recommended",
      ],
      rules: {
        "react/prop-types": "off",
        "react/react-in-jsx-scope": "off"
      },
      settings: {
        react: {
          version: "detect",
        },
      },
    };
    ```
7. Run in root folder: 
    ```go
    npm run lint -- --fix
    ```
