# Awesome Javascript/typescript Code Snippets

## Useful Code snippets for daily tasks 

### ListDirectory: Gather a list of files and directories names using Nodejs:

```javascript
// v1 - standalone usage: 
const fs = require("fs");
const targetDir = "./";
fs.readdir(targetDir, (err, files) => {
  files.forEach((file) => {
    console.log(file);
  });
});
// -----
// v2 - async for code useage
const fs = require("fs");

const listDirectory = (targetDir = "./") =>
  new Promise((res, rej) =>
    fs.readdir(targetDir, (err, files) => (err ? rej(err) : res(files)))
  );

listDirectory()
  .then(console.log)
  .catch(console.log);
// -----
// v3 - Synchron:
const fs = require("fs");

const listDirectory = (targetDir = "./") => fs.readdirSync(targetDir);
console.log(listDirectory());

```