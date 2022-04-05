## Code

```js
const {existsSync, renameSync, readdirSync} = require('fs')
const {join, extname} = require('path')
const dir = process.argv[2]

function safeRename(oldName) {
  let randomStr = String(Math.random()).split('.')[1]
  let newName = randomStr+extname(oldName)
  existsSync(join(dir, newName)) ? safeRename(oldName) : renameSync(join(dir, oldName), join(dir, newName))
}

readdirSync(dir).forEach(filename => {
  safeRename(filename)
})
```



## Usage

```shell
node index.js E:/images
```

