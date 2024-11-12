## Pure React 

### Step 3: Create a New React Project

1. **Open Terminal in VS Code**: You can open the terminal in VS Code by going to `View` > `Terminal` or using the shortcut `` Ctrl + ` ``.
    
2. **Run Create React App**: In the terminal, navigate to the directory where you want to create your new project and run the following command:
    
    sh
    
    Salin kode
    
    `npx create-react-app my-first-react-app`
    
    Replace `my-first-react-app` with your desired project name. This command sets up a new React project with all the necessary configurations.
    
3. **Navigate to Project Directory**: Once the project is created, navigate into the project directory:
    
    sh
    
    Salin kode
    
    `cd my-first-react-app`
    

### Step 4: Start the Development Server

1. **Run the Project**: Start the React development server by running:
    
    sh
    
    Salin kode
    
    `npm start`
    
    This command starts the development server and opens your React app in the default web browser. You should see the default React welcome page.

### Step 5: Open the Project in VS Code

1. **Open the Project Folder**: In VS Code, go to `File` > `Open Folder...` and select your project folder (`my-first-react-app`).

### Step 6: Explore the Project Structure

- **public/**: Contains the `index.html` file and other static assets.
- **src/**: Contains the source code for your React application.
    - **index.js**: The entry point for the React application.
    - **App.js**: The main component of your application.

### Step 7: Modify the App Component

1. **Open App.js**: In the `src` folder, open the `App.js` file.
    
2. **Edit App.js**: Replace the default code with a simple "Hello World" example:
    
    jsx
    
    Salin kode
    
    `import React from 'react';  function App() {   return (     <div className="App">       <h1>Hello World</h1>     </div>   ); }  export default App;`
    
3. **Save the File**: Save the changes (`Ctrl + S` or `File` > `Save`).
    
4. **View the Changes**: The development server should automatically reload, and you should see "Hello World" displayed in your browser.

## Deactivate git

To deactivate Git from your current React project, you need to remove the `.git` directory within your project folder. This directory is what Git uses to store all its configuration, history, and other data related to version control. Here’s how you can do it:

### Using Command Line

1. **Open Terminal**: Open a terminal or command prompt in your project directory.
2. **Run the Removal Command**:
   - On macOS/Linux:
     ```sh
     rm -rf .git
     ```
   - On Windows:
     ```sh
     rmdir /s /q .git
     ```

### Using File Explorer/Finder

1. **Show Hidden Files**: Ensure that your file explorer is set to show hidden files because the `.git` directory is hidden by default.
   - **Windows**: In File Explorer, go to the `View` tab and check the `Hidden items` checkbox.
   - **macOS**: Press `Command + Shift + .` (Command + Shift + Period) to toggle the visibility of hidden files.
   - **Linux**: In your file manager, you can usually press `Ctrl + H` to show hidden files.

2. **Navigate to Your Project Directory**: Open your project directory in the file explorer.
3. **Delete the `.git` Directory**: Locate the `.git` directory, right-click it, and select `Delete`.

### Confirming Deactivation

To confirm that Git has been deactivated for your project, open your terminal or command prompt in your project directory and run:

```sh
git status
```

You should see an error message like this:

```
fatal: not a git repository (or any of the parent directories): .git
```

This indicates that the `.git` directory has been successfully removed and your project is no longer under Git version control.

### Summary

By removing the `.git` directory, you deactivate Git for your project. You can reinitialize it manually in the future whenever you’re ready to start using Git again by running `git init` in your project directory. This will create a new `.git` directory and set up Git for version control.

