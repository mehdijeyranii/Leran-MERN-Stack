# [Setting Up the Development Environment](#custom-id)

To set up the development environment for MERN Stack, you need to follow a few key steps. Here’s the initial setup for installing and configuring various tools:

## 1. Install Node.js and npm

Node.js is an environment for running JavaScript on the server, and npm is a package manager for installing and managing Node packages. First, you need to install them.

- Go to the official **[Node.js](https://nodejs.org/en)** website and download the LTS (Long Term Support) version.
- After installation, enter the following commands in the terminal or Command Prompt to ensure they are installed correctly:

```bash
node -v
npm -v
```

These commands will display the version numbers of Node.js and npm installed on your system.

## 2. Create a New Project

Create a new folder for your project and navigate into it:

```bash
mkdir server | backend
cd server | backend
```

Then, use the `npm init` command to create a new project:

```bash
npm init -y
```

This command creates a `package.json` file, which stores the project information and its dependencies.

## 3. Install TypeScript and Configure

To use TypeScript in your project, first, install it:

```bash
npm install --save-dev typescript ts-node @types/node @types/express
```

These packages will help you use **_TypeScript_** in your MERN project.

Then, create a `tsconfig.json` file to specify the TypeScript configurations. The initial content of this file can look like this:

```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "outDir": "./dist"
  },
  "include": ["src/**/*.ts"],
  "exclude": ["node_modules"]
}
```

This configuration specifies how TypeScript compiles your code, such as the target ECMAScript version, module system, and strict type-checking options. The `outDir` option specifies the folder where the compiled JavaScript files will be saved.

## 4. Install Express.js and other packages
Express.js is a framework for creating APIs and web applications. To install it, use the following command:
```bash
npm install express mongoose cors dotenv
```
- **mongoose**: Used for connecting to MongoDB and performing operations on the database.
- **cors**: Used for managing Cross-Origin requests.
- **dotenv**: Used for managing environment variables in your project.
## 5. Create the project structure
Create a suitable structure for your project. For example:

```bash
src/
  |-- controllers/
  |-- models/
  |-- routes/
  |-- server.ts
```
In the `src/` folder, create the main server file (e.g., `server.ts`), and then write your application using Express and TypeScript.

## 6. Running the project with ts-node
To run the application, use `ts-node`, which allows you to run TypeScript files directly:
```bash
npx ts-node src/server.ts
```
To use **`nodemon`** for running a TypeScript project, you need to install `nodemon` and `ts-node` as development dependencies. Then, you can use `nodemon` to watch for file changes and automatically run them.

---
### 1️⃣ Install nodemon and ts-node as development dependencies:
```bash
npm install --save-dev nodemon ts-node
```
---

### 2️⃣ Configure `nodemon` to use `ts-node`
Add a script in your `package.json` to run the project with `nodemon`:
```json
"scripts": {
  "dev": "nodemon --exec ts-node src/server.ts"
}
```
This command tells `nodemon` to execute the project using `ts-node` every time a file changes.

---

### 3️⃣ Run the project with `nodemon`
To run the project using `nodemon`, use the following command:
```bash
npm run dev
```
With this setup, `nodemon` will automatically restart the project whenever there are changes in your TypeScript files.

>The `--exec` flag in `nodemon` specifies the command to execute when a change is detected in the files being watched. This allows you to run a specific command (e.g., `ts-node`, `node`, or any other command) instead of the default `node` command.
>
>In the case of running a TypeScript project, the `--exec` flag is used to specify `ts-node` as the command to execute the TypeScript file, rather than using `node` directly, which would not work for TypeScript files without compilation.
>For example:
>```bash
>nodemon --exec ts-node src/server.ts
>```
>This tells `nodemon` to run `ts-node` every time a file changes, so it can directly execute TypeScript files without needing to compile them first.

## 7. Install MongoDB (Optional for Local Development)
For local development, you can install MongoDB on your system. Visit the MongoDB website, download the appropriate version, and install it. Alternatively, you can use MongoDB Atlas to use a cloud database.

With these settings, your MERN Stack development environment is ready. If you have any questions or issues at any stage, feel free to ask for help.