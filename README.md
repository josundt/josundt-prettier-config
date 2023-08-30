# @josundt/prettier-config #

Standard configuration for Prettier code-style formatter

## Usage ##

1. Make sure your project has an `.editorconfig` file, defining `indent_width`, `indent_style` etc. since
   prettier will use some of these settings to format source code accordingly.

2. Install this package as a dev dependency
    ```bash
    npm install -D -E @josundt/prettier-config
    ```

3. Create a `.prettierrc` file in the root directory of your project with the following content:
    ```json
    "@josundt/prettier-config"
    ```


4. Add the following formatting scripts to your project's package.json file:
    ```json
    {
        // ...
        "scripts": {
            // ...
            "format": "npm run format:html && npm run format:style && npm run format:ts",
            "format:ts": "prettier --config .prettierrc src/**/*.ts test/**/*.ts --write",
            "format:style": "prettier --config .prettierrc src/**/*.{css,scss} --write",
            "format:html": "prettier --config .prettierrc src/**/*.{html,ejs} --write",
            // ...
        }
        // ...
    }
    ```

5. Test the script:
    ```bash
    npm run format
    ```

6. Review all changes and commit.

7. VS Code integration:
    a. Install Prettier extension (`esbenp.prettier-vscode`).
    b. Add the extension to the projects's recommended extensions in the project's `.vscode/extensions.json` file.
    c. Configure the extension's behavior in `.vscode/settings.json`:
    ```json
    {
        // ...
        "[css]": {
            // ...
            "editor.defaultFormatter": "esbenp.prettier-vscode",
            "editor.formatOnPaste": true,
            "editor.formatOnSave": true
        },
        "[scss]": {
            // ...
            "editor.defaultFormatter": "esbenp.prettier-vscode",
            "editor.formatOnPaste": true,
            "editor.formatOnSave": true
        },
        "[html]": {
            // ...
            "editor.defaultFormatter": "esbenp.prettier-vscode",
            "editor.formatOnPaste": true,
            "editor.formatOnSave": true
        },
        "[javascript]": {
            // ...
            "editor.defaultFormatter": "esbenp.prettier-vscode",
            "editor.formatOnPaste": true,
            "editor.formatOnSave": true
        },
        "[json]": {
            // ...
            "editor.defaultFormatter": "esbenp.prettier-vscode",
            "editor.formatOnPaste": true,
            "editor.formatOnSave": true
        },
        "[jsonc]": {
            // ...
            "editor.defaultFormatter": "esbenp.prettier-vscode",
            "editor.formatOnPaste": true,
            "editor.formatOnSave": true
        },
        "[typescript]": {
            // ...
            "editor.formatOnPaste": true,
            "editor.formatOnSave": true,
            "editor.defaultFormatter": "esbenp.prettier-vscode"
        }
        // ...
    }
    ```
    d. Test that files with the extensions in the list above are auto-formatted on save and paste. 
