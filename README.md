Playwright QA Training Suite
Welcome to the Playwright QA Training Suite! This repository contains a simple Playwright test automation project designed to help you learn the basics of end-to-end web testing.

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

Node.js (LTS version recommended): Playwright runs on Node.js. Download from https://nodejs.org/.

VS Code (Visual Studio Code): Your code editor. Download from https://code.visualstudio.com/.

Git: For cloning the repository. Download from https://git-scm.com/.

2. Getting Started (Local Setup)
Follow these steps to get the test suite up and running on your local machine.

2.1 Clone the Repository
Open your terminal or Git Bash and run the following command to clone this repository:

git clone YOUR_REPO_URL

Replace YOUR_REPO_URL with the actual URL of this GitHub repository (you can find it by clicking the "Code" button on the GitHub page and copying the HTTPS URL).

Then, navigate into the cloned directory:

cd playwright-qa-training # Or whatever you named the cloned folder

2.2 Install Dependencies
This project uses npm (Node Package Manager) to manage its dependencies. With your terminal open in the project's root directory, run:

npm install

This command will read the package.json file and install all necessary packages (like Playwright itself and TypeScript) into the node_modules folder.

2.3 Install Playwright Browsers
Playwright needs specific browser binaries to run tests. After npm install, run this command to download them:

npx playwright install

This will download Chromium, Firefox, and WebKit browsers.

3. Running Tests
You can run tests from your terminal or using the integrated Playwright Test extension in VS Code.

3.1 Standard Run (Headless)
To run all tests in "headless" mode (meaning no browser window will open, tests run in the background), use:

npx playwright test

Results will be displayed in your terminal.

3.2 Running in UI Mode (Interactive GUI)
This is highly recommended for learning and debugging! It opens an interactive GUI where you can see tests run step-by-step, inspect elements, view snapshots, and debug.

npx playwright test --ui

A new browser window/tab will open with the Playwright UI. You can click the "Play" button next to test files or individual tests to run them. Explore the timeline, actions, and "Before/After" snapshots.

3.3 Running Specific Tests
Run a specific test file:

npx playwright test tests/example.spec.ts

Run a specific test by name (or part of the name):

npx playwright test -g "login to Sauce Demo"

(Replace "login to Sauce Demo" with the actual test title from your .spec.ts file).

4. Project Structure Overview
Here's a quick look at the main folders and files in this project:

playwright-qa-training/
├── node_modules/         # Contains all installed Node.js packages (ignored by Git)
├── tests/                # Your Playwright test files (.spec.ts)
│   └── example.spec.ts   # An example test file
├── utils/                # (Optional) Folder for reusable utility functions (e.g., loginToSauceDemo)
│   └── auth.ts
├── playwright.config.ts  # Playwright configuration file (defines testDir, baseURL, etc.)
├── package.json          # Project metadata and lists dependencies
├── package-lock.json     # Locks dependency versions for consistent installs
├── tsconfig.json         # TypeScript configuration file
└── .gitignore            # Specifies files/folders to ignore in Git

5. Key Playwright Concepts to Explore
As you go through the tests and write your own, pay attention to these core Playwright concepts:

test and expect: The building blocks of Playwright tests.

page fixture: The central object for interacting with the browser.

Locators (page.locator, getByRole, getByText, etc.): How Playwright finds elements on the page.

Actions (.click(), .fill(), .navigate()): How Playwright interacts with elements.

Assertions (expect(...).toBeVisible(), .toHaveText(), .toHaveURL()): How you verify expected outcomes.

baseURL in playwright.config.ts: How to set a global base URL for your tests.

UI Mode (npx playwright test --ui): Your best friend for debugging!

6. Troubleshooting
"No tests found":

Ensure you are in the project's root directory when running npx playwright test.

Check your playwright.config.ts file: testDir: './tests' should be correctly set.

Verify your test files are actually inside the tests folder and end with .spec.ts.

Browser not launching / Playwright errors:

Make sure you ran npx playwright install successfully.

Ensure Node.js is correctly installed and in your system's PATH.

Dependencies not found:

Run npm install again to ensure all packages are installed.