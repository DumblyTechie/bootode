# Working with Bootstrap 5, Node & Sass  
  
## Prerequisites  
Before you start, make sure you have Node.js and npm installed. You'll also need to initialize npm in your project folder if you haven't already:  
  
> npm init -y  
  
  
## Step 1: Install Bootstrap & Icons  
First, use npm to install the packages. This will add them to your node_modules folder.  
  
> npm install bootstrap bootstrap-icons  
  
  
## Step 2: Create a file named main.scss (or any name you like)  
In this file, you must define your custom variables (like colors) before you import the main Bootstrap Sass file.   
This allows your variables to override Bootstrap's defaults. Always ensure that the bootstrap sass is included below the custom variables  
  
- Override default variables  
 (Find all variables in node_modules/bootstrap/scss/_variables.scss)   
$primary: #7952B3; // Changed primary color to purple   
$danger: #D92027; // Changed danger color to a different red   
$font-family-base: 'Georgia', serif; // Changed the default font  
  
- Import all of Bootstrap's Sass @import "node_modules/bootstrap/scss/bootstrap";   
- Import Bootstrap Icons (this is optional, you can still link the CSS separately)   
@import "node_modules/bootstrap-icons/font/bootstrap-icons.scss"; //   
- Add your own custom styles   
> .custom-header {   
> 	background-color: $primary;   
> 	color: white;   
> 	padding: 1rem;   
> 	border-radius: $border-radius;
> }  
  
  
## Step 3. Compile Your Sass  
You need a way to compile your main.scss into a regular main.css file that the browser can read. The easiest way is to use the sass package.  
First, install the Sass compiler:  
  
> npm install -g sass  
  
Now, tell Sass to "watch" your file. It will automatically re-compile it into main.css every time you save a change.  
  
> sass --watch main.scss:main.css  
  
Note: This will create a main.css and main.css.map file in your directory.  
  
## Step 4. Update Your index.html  
Finally, change your index.html to link to your newly compiled CSS file instead of the one from node_modules.  
