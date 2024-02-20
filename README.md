# cra-template-greg-no-typescript

This template is on npmjs.com associated with the
account `gregsandell / greg.sandell@gmail.com`.

Reliable instructions can be found at: [How to create a Create React App Template](https://medium.com/@ryanschultz_95315/how-to-create-a-create-react-app-template-cf4de92aeb93). 
You need to be logged into npmjs in the terminal for these commands
to work.  Run `npm login`, using the information in your `~/.npmrc` file.

## Text of How to create a Create React App Template
In case medium.com paywall-blocks you.

How to create a Create React App Template
Ryan Schultz

I will walk you through every step of creating your own create react app template

If you are not familiar with CRA (Create React App), it is a bootstrap tool that generates a basic React application for you. The app it creates already has many things built into it. You can learn more about what is included here. It includes the basic building blocks to get you started with a vanilla react application.

In order to follow this tutorial you will need to have an npm account. To create one, click here. You will also have to have nodejs and npm installed, download and install it from here.

What I am going to show you is how to create a template that will allow you to add in other libraries that will already be included when you generate a react app with this template. This could include authentication libraries, linting libraries, user interface libraries or anything else you would want included. Now that I told you what it is we are going to create, let’s get on with the tutorial.

1. Create a directory for our create-react-app template.
   Let’s create a directory and for this example I am going to call ours "cra-template-mui-moment". Whatever you want to name your template, it must start with "cra-template-". This is so that when we publish the template to npm, the create-react-app utility can find it.

2. Create a `template.json` File
   Inside our newly created directory, we need to create a "template.json” file. This is the configuration file that is used by create-react-app. Here is where you would add any libraries that you want to be included when an application is generated using your template. In this example we are going to add Material-UI and MomentJS. We are also going to add the libraries from the cra-template default. We will also add a silly useless script called "say-hi” .

```json
{
   "package": {
      "dependencies": {
         "@testing-library/jest-dom": "^5.14.1",
         "@testing-library/react": "^12.0.0",
         "@testing-library/user-event": "^13.2.1",
         "web-vitals": "^2.1.0"
         "@emotion/react": "^11.7.1",
         "@emotion/styled": "^11.6.0",
         "@mui/material": "^5.3.0",
         "moment": "^2.29.1"
      },
     "scripts": {
       "say-hi": "echo 'hi'"
     }
  }
}
```
In this configuration file, everything under the package key will be added to the package.json file of our generated application. Any values you add for "dependencies" and "scripts" will be merged with the create-react-app defaults. Values for any other keys will be used as-is, overwriting any matching create-react-app defaults.

3. Initialize NPM
   Open a terminal and go into the "cra-template-mui-moment” directory we created in step #1 and run the following command.

`npm init`

This is where we name our package for npm, remember that it must start with "cra-template-" , so for our example we will use "cra-template-mui-moment” . For everything else, you can just enter through to use the default values. You should now have a package.json file and your template.json file.

4. Create a template directory
   Now we need to create a directory called "template” inside our "cra-template-mui-moment” directory. This directory is going to hold any files we want to copy over when the template is used. Here is an example:

cra-template-mui-moment/
├── README.md (for npm)
├── template.json
├── package.json
├── template/
│   ├── gitignore
│   ├── index.js (or index.tsx)
│   ├── public/
│   │   └── index.html
│   ├── README.md (for projects created from this template)
│   └── src/
Note: The gitignore file will be renamed .gitignore automatically, this is not a typo.

Since we added Material-UI libraries above, we need to add some link tags to the index.html file inside the public directory. So add the following between the <head></head> tags inside the index.html file. This adds the stylesheets we need to support the Material-UI fonts and icons.

<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,700&display=swap" />
<link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons" />
You can also add the README.md files, one in the main directory that is displayed in the NPM Library Repository and one in the template sub-directory that is copied over when your template is used.

4. Publish to NPM
   This is the last and final step to getting your template up and running. Simply run the following command from the base of your "cra-template-mui-moment” directory.

`npm publish`
If everything went without error, then you now have a template published to npm and in order to use the template you only need to run one command.

`npx create-react-app some-app-name --template mui-moment`
Just substitute "some-app-name” for the name of the app you want to create and change "mui-moment” to the name of your template without the "cra-template-” .

Useful Resources
ReactJS: https://reactjs.org/

Create-React-App: https://create-react-app.dev/

NPM: https://www.npmjs.com/

NodeJS: https://nodejs.org/

Material-UI: https://mui.com/

MomentJS: https://momentjs.com/
