
# Project
Create your first angular project  with README to help you to start from zero. Check Instructions.txt  to build  the  same project  from scratch and understand how angular works the  way it does by  following instructions. Please note  that this project is just a dummy project with just an input text element on screen interacting with the angular. The sole idea is only to undertand basics  of how angular works by following instructions.txt.

# MyFirstApp

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 10.0.0.


## Installation procedures

install nodejs from nodejs.org (npm comes automatically with it)

Go to command prompt

check node version with : `node -v`

check npm version with : `npm -v`

install angular command line interface by command : `npm install -g @angular/cli@latest`
[note g is for global, @latest is optional which stands for latest version]

check angular cli version with : `ng --version`  [Note ng stands for angular]



## Create first dummy app

Go to cmd

Navigate to location where you want to create your project

(type `cmd` in path of file explorer to open cmd there itself -- shortcut to open cmd at any location)

create project by command:  `ng new my-first-app`
[Note it will occupy approx 300mb of space with 38000 items aoorox]

Would you like to add Angular routing? No

Which stylesheet format would you like to use? CSS



Congrats your project is created.

Now navigate inside your newly created project with: `cd my-fist-app`

Now run the server with : `ng serve` [by this angular live development server will run on localhost:4200 by default]

You can also host it on a custom port with this instead : `ng serve --port 3100` [Here 3100 can be replaced with your desired port number]

Now go to the address in browser where app is hosted [Ex:-   locahost:4200 , the page will show my-fist-app is running]


## Editing our app

### How root page  is  rendered on server boot


index.html is the main file which is loaded on server boot.

index.html file then calls a custom tag <app-root> present in the body of index file.

The configuration of app-root component is stored in app.component.ts file under @component configuration

Also its corresponding html file and css file also placed under same @component configuration

Which inturns calls the corresponding html i.e app.commponent.html and css i.e app.compoonent.css and renders it as the body of index.html

But how this app-root is loaded in the  first place by angular, keep reading

main.ts  in the root directory of project is  the starting file  from where execution starts.

In main.ts , you see code like below

1.  `import { AppModule } from './app/app.module';`
2.  `platformBrowserDynamic().bootstrapModule(AppModule)`

2nd line  tells angular framework to start AppModule. This AppModule is present in the path app->src->app.module.ts which is confirmed by line 1.
Now  app.module.ts  contains below code

1.  `import { AppComponent } from './app.component';`
2.  `bootstrap: [AppComponent]`

line 2 tells angular to run app to find the AppComponent-component whose cofigiguration is present in app.component.ts confirmed by line 1 in the  path src->app->app.component.ts.



### Edit  the  model

Variables inside `{variable_name}` are called model or data

One can  bind  this  data in to an element as well to reflect changes and save to model dynamically.



### Example

Change  `{title}`  to `{name}` in app.component.html and define the name's value which you want to render on the  screen by  editing it in app.component.ts file.

Now You can see the  value of name rendered on screen. This  till here  implements  one way binding on data from code to screen unidirectionally.

Now lets bind this model to an another element (ex- textbox here)  to repond to changes  in runtime to change the  value of name  dynamically.

insert `<input type  ="text" [(ngModel)] ="name"/>` tag to render an input element of type text which initiializes with `{name}` model and binds to model.

Now any change  in input text  will automatically change the name value.   This is two way binding.



## install bootstrap to your project and  add to package.json

stop the server

now type command

1. `npm install --save bootstrap@3`  

[Note  here  @3 represents version number  which is optional, avoiding which automatically installs latest version]

Now check module node_modules->bootstrap->dist->css->bootstrap.min.css
This  is  where  your bootstrap css filee is.

Now tell the  angular that  you want to use  this bootstrap css file in your index.html file  for styling by adding this  path in angular.json file under
projects->my-first-app->architect->build->styles.

paste the  below code

   `"node_modules/bootstrap/dist/css/bootstrap.min.css",`
   
exactly above `"src/styles.css"`

Now stop server by ctrl+c  and boot the server and verify its  running properly.




