# Smart Utility Toolkit

Lab Assignment 1 — Web Dev III (Node.js & Express Backend)

This project uses only built-in Node.js modules. No external npm packages or Express are required.

## Requirements
- Install Node.js
- Open this folder in VS Code or a terminal

## Programs and commands

### 1. CLI calculator
```bash
node calculator.js add 10 5
node calculator.js subtract 10 5
node calculator.js multiply 10 5
node calculator.js divide 10 5
```

Operations: `add`, `subtract`, `multiply`, `divide`.

### 2. Custom modules
```bash
node app.js
```
`app.js` imports `modules/isEven.js` and `modules/logger.js`.

### 3. HTTP server
```bash
node server.js
```
Open these addresses in your browser:
- http://localhost:3000/
- http://localhost:3000/about
- http://localhost:3000/contact
- http://localhost:3000/unknown (404 response)

Press `Ctrl+C` in the server terminal to stop it.

### 4. File manager
Run these commands one at a time:
```bash
node fileManager.js create "Hello Node.js"
node fileManager.js read
node fileManager.js update "Learning the fs module"
node fileManager.js read
node fileManager.js delete
```
The create command intentionally avoids overwriting an existing `test.txt` file.

### 5. Dice generator
```bash
node dice.js
node dice.js 5
```
The optional number specifies how many times to roll the dice (1–1000).

## Folder structure
```text
smart-utility-toolkit/
├── calculator.js
├── app.js
├── server.js
├── fileManager.js
├── dice.js
├── README.md
└── modules/
    ├── isEven.js
    └── logger.js
```
