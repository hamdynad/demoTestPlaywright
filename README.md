Playwright QA Training Suite
Welcome to the Playwright QA Training Suite! This repository contains a simple Playwright test automation project designed to help you learn the basics of end-to-end web testing with TypeScript.

Table of Contents
Prerequisites

Getting Started (Local Setup)

2.1 Clone the Repository

2.2 Install Dependencies

2.3 Install Playwright Browsers

Running Tests

3.1 Standard Run (Headless)

3.2 Running in UI Mode (Interactive GUI)

3.3 Running Specific Tests

Project Structure Overview

Key Playwright Concepts to Explore

Troubleshooting

1. Prerequisites
Before you begin, ensure you have the following installed on your machine:

Node.js (LTS version recommended): Playwright runs on Node.js.

Download Node.js

VS Code (Visual Studio Code): Your preferred code editor.

Download VS Code

Git: For cloning the repository and managing code versions.

Download Git

2. Getting Started (Local Setup)
Follow these steps to get the test suite up and running on your local machine.

2.1 Clone the Repository
Open your terminal (or Git Bash) and run the following command to clone this repository:

git clone YOUR_REPO_URL

Note: Replace YOUR_REPO_URL with the actual HTTPS URL of this GitHub repository. You can find it by clicking the "<> Code" button on the GitHub page and copying the HTTPS URL.

Then, navigate into the cloned directory:

cd playwright-qa-training # Or the name of your cloned folder

2.2 Install Dependencies
This project uses npm (Node Package Manager) to manage its dependencies. With your terminal open in the project's root directory, run:

npm install

This command will read the package.json file and install all necessary packages (like Playwright itself and TypeScript) into the node_modules folder.

2.3 Install Playwright Browsers
Playwright needs specific browser binaries (Chromium, Firefox, WebKit) to run tests. After npm install, run this command to download them:

npx playwright install

3. Running Tests
You can run tests directly from your terminal or using the powerful Playwright Test extension integrated within VS Code.

3.1 Standard Run (Headless)
To run all tests in "headless" mode (meaning no browser window will open, tests run silently in the background), use:

npx playwright test

Test results will be displayed directly in your terminal.

3.2 Running in UI Mode (Interactive GUI)
This mode is highly recommended for learning, debugging, and developing new tests! It opens an interactive graphical user interface (GUI) where you can:

See tests run step-by-step in a visible browser.

Inspect elements on the page.

View "Before" and "After" snapshots of each action.

Debug effectively with detailed logs and network requests.

Use the "Pick locator" tool to easily find element selectors.

To launch UI Mode:

npx playwright test --ui

A new browser window/tab will open with the Playwright UI. Click the "Play" button next to test files or individual tests to execute them.

3.3 Running Specific Tests
Run a specific test file:

npx playwright test tests/example.spec.ts

Run a specific test by its title (or part of the title):

npx playwright test -g "login to Sauce Demo"

Note: Replace "login to Sauce Demo" with the exact title of the test you want to run from your .spec.ts file.

4. Project Structure Overview
Here's a quick overview of the main folders and files in this project:

playwright-qa-training/
├── node_modules/         # Automatically installed packages (ignored by Git)
├── tests/                # Your Playwright test files (.spec.ts)
│   └── example.spec.ts   # An example test file demonstrating basic flow
├── utils/                # (Optional) Folder for reusable utility functions (e.g., loginToSauceDemo)
│   └── auth.ts           # Example utility for authentication
├── playwright.config.ts  # Playwright configuration: defines testDir, baseURL, browsers, etc.
├── package.json          # Project metadata, scripts, and lists dependencies
├── package-lock.json     # Locks dependency versions for consistent installs
├── tsconfig.json         # TypeScript compiler configuration
└── .gitignore            # Specifies files/folders to ignore in Git

5. Key Playwright Concepts to Explore
As you go through the existing tests and begin writing your own, focus on understanding these core Playwright concepts:

test and expect: The fundamental building blocks for defining tests and assertions.

page fixture: The central object that represents a browser tab and allows you to interact with the web page.

Locators (page.locator, getByRole, getByText, etc.): Playwright's powerful way to find and interact with elements on the page.

Actions (.click(), .fill(), .navigate()): Methods used to simulate user interactions with web elements.

Assertions (expect(...).toBeVisible(), .toHaveText(), .toHaveURL()): How you verify that your application behaves as expected.

baseURL in playwright.config.ts: A global setting that simplifies navigation by allowing relative URLs in page.goto().

UI Mode (npx playwright test --ui): Your essential tool for visual debugging and test development.

6. Troubleshooting
If you encounter any issues, try these common fixes:

"No tests found":

Ensure your terminal is open in the project's root directory (playwright-qa-training/).

Verify your playwright.config.ts file has testDir: './tests' correctly set.

Check that your test files are inside the tests folder and end with .spec.ts.

Browser not launching / Playwright errors:

Make sure you ran npm install and npx playwright install successfully.

Ensure Node.js is correctly installed and accessible via your system's PATH.

Dependencies not found:

Run npm install again to ensure all packages are installed.

If you continue to face problems, don't hesitate to ask your trainer or refer to the official Playwright documentation.

Happy Testing!