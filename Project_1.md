Create a QR code for the link that user provide and save the link in the text file:

    
    /* 
    1. Use the inquirer npm package to get user input.
    2. Use the qr-image npm package to turn the user entered URL into a QR code image.
    3. Create a txt file to save the user input using the native fs node module.
    */
    import inquirer from "inquirer";
    import qr from "qr-image";
    import fs from "fs";
    
    inquirer
      .prompt([{
        message:"Ente URL",
        name:"URL"
    },
      ])
      .then((answers) => {
        const a=answers.URL;
    const x="\n";
    const b=a+x;
      
        var qr_svg = qr.image(a);
    qr_svg.pipe(fs.createWriteStream('qr.png'));
    fs.appendFile("./URL.txt",b,(err)=>{
        if (err) throw err;
        console.log("saved");
    })
      })
      .catch((error) => {
        if (error.isTtyError) {
          // Prompt couldn't be rendered in the current environment
        } else {
          // Something else went wrong
        }
      });
