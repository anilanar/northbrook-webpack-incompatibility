# How to reproduce

```
npm install
cd packages/main
npm run build
```

## To see webpack's module resolution error in detail

```
npm run build:detailed
```

The relevant part is the following:

```
using description file: /absolute-path-to-project-dir/packages/main/node_modules/@nwi/other/package.json
(relative path: ./absolute-path-to-project-dir/packages/other/my-main-field/index.js)
```

So basically, webpack assumes that the absolute path in the main field is a
relative path:

```
actual: /absolute-path-to-project-dir
webpack thinks: ./absolute-path-to-project-dir
```
