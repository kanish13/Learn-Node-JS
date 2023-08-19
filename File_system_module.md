To know more about file system module , read file system documentation : https://nodejs.org/dist/latest-v18.x/docs/api/fs.html

Here we gonna look at three functions in it :

* readFile()
* writeFile()
  
readFile() :

The fs.readFile() method is an inbuilt method which is used to read the file. This method read the entire file into buffer. To load the fs module we use require() method. For example: var fs = require(‘fs’);

Syntax: fs.readFile( filename, encoding, callback_function )

writeFile():

The fs.writeFile() method is used to asynchronously write the specified data to a file. By default, the file would be replaced if it exists. The ‘options’ parameter can be used to modify the functionality of the method.

Syntax: fs.writeFile( file, data, options, callback )

Exercise : Write a program to replace the text in a text file 

     
    const fs=require("fs");
    
    fs.readFile("mess.txt","utf-8",function (err,contents) {
    if(err){
        console(err)
        return;
    }
    const re=contents.replace(/hello/g,"bye");
    fs.writeFile("./mess.txt",re,(err)=>{
        if (err) throw err;
        console.log("saved");
    })
    })

    Now if go back to text file you can see the word "hello" has changed to "bye"





