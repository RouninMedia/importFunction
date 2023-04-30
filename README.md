# importFunction()
A simple helper function which utilises dynamic import() to enable conventional JS files to import, asynchronously, ESModules containing single-functions, on demand / whenever needed.
_____

## `importFunction()`

```js
const importFunction = async (URL) => {
          
  const importedESModuleObject = await import(URL);
  return importedESModuleObject.default;
}
```

____

## Example:

### `/path-to-esmodule/increase-by-two.js`
```js
const increaseByTwo = (integer) => {

  return (integer + 2);
}

export default increaseByTwo;
```

### `/my-scripts.js`
```js
const myAsyncFunction = async () => {

  const increaseByTwo = await importFunction('/path-to-esmodule/increase-by-two.js');

  console.log(increaseByTwo(2)); // 4
}
```


