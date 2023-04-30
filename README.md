# importFunction()
A simple helper function which enables ESModules containing single-functions to be imported on demand into conventional JS files via dynamic import()

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

### `/my-file-path/increase-by-two.js`
```js
const increaseByTwo = (integer) => {

  return (integer + 2);
}

export default increaseByTwo;
```

### `/my-scripts.js`
```js
const increaseByTwo = importFunction('/my-file-path/increase-by-two.js');

console.log(increaseByTwo(2)); // 4
```


