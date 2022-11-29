# Tailwind Tutorial  

Code Editor (VS Code)  
Node Js(nodejs.org)  
NPM Package(if you install Node Js then you don't have to install NPM)  

Open VS Code and in terminal, run:  
`npm -v` - To check npm version  
`node -v` - To check node version  
  
To upgrade npm run following command:  
`npm install -g npm`

create a folder you want to work on  
In terminal run the following command:  
`npm i -d tailwindcss@latest postcss@latest autoprefixer@latest`  
> To install latest version - @latest  
> npm can't run by itself hence it needs a prefixer - autoprefix    
   
Now you can see a `node_modules` folder, package.json and package-lock.json is created   
`node_modules` folder is the package manager for node.js  
`package.json` - dependencies and associated versions we pulled in  
`package-lock.json` -   
  
Next we need to create configuration file, In terminal type:   
`npx tailwindcss init`  
> You can see that `tailwind.config.css` file would be created   


As next step we need to create CSS file because we need to pull in tailwind directives  
Inside the root of our project create a css file (style.css)  
We need to create tailwind directives to replace tailwind code  
In order to say that we need to type the following in css file:  
```
@tailwind base;  
@tailwind components;  
@tailwind utilities;
```  
   
the `@tailwind` will look into `node_modules` > tailwindcss > base / components and utilities  

Now we have to reprocess the above files inside new files. while can be done in multiple ways.    
The method we would be doing is `script inside package.json`  
Which allows to create a new command which can be run in CLI  
  
Edit the package.json as given below:  
```
{
  "dependencies": {
    "autoprefixer": "^10.4.13",
    "postcss": "^8.4.19",
    "tailwindcss": "^3.2.4"
  },
  "scripts": {
    "build-css": "tailwindcss build style.css -o css/style.css"
  }
}
```  
  
Now run the following command in terminal: `npm run build-css`   
A new folder `css > style.css` has been created  
