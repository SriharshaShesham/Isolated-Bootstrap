# Isolated Bootstrap

## What is Isolated Bootstrap?
Most often when we work on projects and we want to add some beauty to it the first thing that strikes our mind is Bootstrap(atleast that is the first thing that strikes my mind). Bootstrap is a wonderful and easy way to style the elements of our project. 

Though it is easy to use bootstrap when we have a single source of styles that are designed by us(single individual), it is really hard to maintain consistency when we have a large team where everyone use their own styles across the application. Another scenario where it is hard to add bootstrap is when our application has a dedicated UI designer and our application have a dedicated masterpage. In the above two scenarios when we add bootstrap styles to the application it will messup the styles of the masterpage or other areas designed by others because bootstrap adds styles globally. 

To prevent such conflicts we isolate the bootstrap styles which would allow us to apply bootstrap to only certain elements on the page but not globally. Another interesting beautify of this isolation is we can load and use multiple bootstrap versions in a single project. 

#### Please note that we are only going to isolate the bootstrap syles i.e., botstrap.css not the javascript files. So if you want the click events and other events to work you must include the bootstrap.js

## Dependencies.
- Less Command Line Interface

## Process of isolating the Bootstrap styles yourself.
#### (You may skip this process and directly download them from below)
1. Download **Less Command Line Interface** from [here](https://github.com/duncansmart/less.js-windows).
2. Download the bootstrap version you are looking for. For this walkthrough I downloaded bootstrap 4 from [here](https://getbootstrap.com/docs/4.0/getting-started/download/).
3. Extract the above two to "C:\IsolateBootstrap\" (you may choose a different directory).
4. Go to the directory where you have extracted the files and open the folder 'css'. 
5. Copy the file "bootstrap.css" to the root folder i.e., "C:\IsolatedBootstrap" folder. 
6. Create a file named "**prefixBootstrap.less**" with contents below. Note that whatever we use in this file will be our prefix. In the below example I have decided to have it prefixed as "**bootstrap4**". 

    ```javascript
     .bootstrap4 {
      @import (less) 'bootstrap.css';
      @import (less) 'bootstrap-theme.css';  /* optional */
    }
    ```
            
7. Open command prompt in this directory("C:\IsolatedBootstrap") and run the below command. 
    
    ```powershell
    .\lessc.cmd prefixBootstrap.less bootstrap4.css --strict-math=on
    ```
    
8. Upon running the command from the previous step a new file is generated with the name "**bootstrap4.css**". Open the file in a text editor and perform the below two steps.
        1. Find all instances of "bootstrap4 body" and replace with "bootstrap4"
        2. Find all instances of "bootstrap4 html" and replace with "bootstrap4"


## Usage
#### To use the bootstrap in our application we do as below:
- Add "bootstrap4.css" to "bootstrap.css":  

    ```html
    <link rel="stylesheet" href="path/to/our/file/bootstrap4.css">
    ```  

- For example we want to add an alert to our page as shown [here](https://getbootstrap.com/docs/4.0/components/alerts/) we wrap the element in the div with **bootstrap4** class:  
        
    ```html
        <div class="bootstrap4">  
            <div class="alert alert-primary" role="alert">  
              This is a primary alert—check it out!  
            </div>  
        </div>
    ```

## Download
##### - [Bootstrap V3 Css](https://raw.githubusercontent.com/SriharshaShesham/Isolated-Bootstrap/master/Bootstrap%20v3/bootstrap3.css)  
##### - [Bootstrap V4 Css](https://raw.githubusercontent.com/SriharshaShesham/Isolated-Bootstrap/master/Bootstrap%20v3/bootstrap4.css)  
