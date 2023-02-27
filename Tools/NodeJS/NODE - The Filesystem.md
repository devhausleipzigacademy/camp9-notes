
One of the most important aspects of any server-side application is the ability to read and write files. In NodeJS, the [[NODE - The Filesystem|Filesystem]] module provides this functionality. ^580fde

## The Filesystem Module

The Filesystem module in NodeJS provides an API for interacting with the file system. The module provides methods for reading and writing files, as well as manipulating directories.

To use the Filesystem module in NodeJS, you need to import it using the `require` function:

```JS
const fs = require('fs');
```

Once you have imported the module, you can use its methods to interact with the file system.

## Reading Files

To read a file using the Filesystem module in NodeJS, you can use the `fs.readFileSync` method. This method takes one argument: the path to the file:

```JS
const data = fs.readFileSync('/path/to/file.txt');
console.log(data);
```

The `fs.readFileSync` method reads the entire contents of the file into memory and returns it as a [[NODE - BUFFER|buffer]].

If you want to read a file as a string, you can pass the `'utf8'` encoding as the second argument to `fs.readFileSync`:

```JS
const data = fs.readFileSync('/path/to/file.txt', 'utf8');
console.log(data);
```

## Writing Files

To write a file using the Filesystem module in NodeJS, you can use the `fs.writeFileSync` method. This method takes two arguments: the path to the file and the data to write:

```JS
fs.writeFileSync('/path/to/file.txt', 'Hello, World!');
console.log('The file has been saved!');
```

The `fs.writeFileSync` method writes the data to the file, overwriting any existing contents. If you want to append data to a file, you can use the `fs.appendFileSync` method instead:

```JS
fs.appendFileSync('/path/to/file.txt', 'Hello, World!');
console.log('The data has been appended to the file!');
```


## Creating and Removing Directories

To create a directory using the Filesystem module in NodeJS, you can use the `fs.mkdirSync` method. This method takes one argument: the path to the directory:

```JS
fs.mkdirSync('/path/to/directory');
console.log('The directory has been created!');
```

To remove a directory using the Filesystem module in NodeJS, you can use the `fs.rmdirSync` method. This method takes one argument: the path to the directory:

```JS
fs.rmdirSync('/path/to/directory');
console.log('The directory has been removed!');
```