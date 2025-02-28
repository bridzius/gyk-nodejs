# GYK NodeJS uzduotis

1. Sukurti Node.js projekta, naudojant `npm`.
2. Patikrinti `package.json`, ar turi reikalingus parametrus naudoti ESM.
3. Sukurti pagalbini moduli `utils`.
4. `utils` modulyje sukurti ir eksportuoti funkcija, kuri parodo platforma, cpu kieki ir atminties kieki (`totalmem`), naudojant `os` API.
5. Sukurti `server` moduli.
6. Naudojant `http` API, sukurti serveri, kuris grazintu suformatuota sistemine informacija, gauta is `utils`.

```js
const os = require("os");
console.log("Platforma:", os.platform());
console.log("CPU branduoliai:", os.cpus().length);
```

```js
const http = require("http");
const server = http.createServer((req, res) => {
  res.writeHead(200, { "Content-Type": "text/plain" });
  res.end("Sveiki iš Node.js serverio!");
});
server.listen(3000, () =>
  console.log("Serveris veikia per http://localhost:3000")
);
```
