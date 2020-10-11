# Web Front End

## HTML Structure

```
<!DOCTYPE html>

<html>

<head>
    <title>Page Title</title>
</head>

<body>
    <h1>A Photo of a Beautiful Landscape</h1>
    <a href="https://www.w3schools.com/tags">HTML tags</a>
    <p>Here is the photo</p>
    <img src="photo.jpg" alt="Country Landscape">
</body>

</html>
```

As you progress through the lesson, you'll find that the <head> tag is mostly for housekeeping like specifying the page title and adding meta tags. Meta tags are in essence information about the page that web crawlers see but users do not. The head tag also contains links to javascript and css files, which you'll see later in the lesson.

The website content goes in the <body> tag. The body tag can contain headers, paragraphs, images, links, forms, lists, and a handful of other tags. Of particular note in this example are the link tag <a> and the image tag <img>.

Both of these tags link to external information outside of the html doc. In the html code above, the link <a> tag links to an external website called w3schools. The href is called an attribute, and in this case href specifies the link.

The image <img> tag displays an image called "photo.jpg". In this case, the jpg file and the html document are in the same directory, but the documents do not have to be. The src attribute specifies the path to the image file relative to the html document. The alt tag contains text that gets displaced in case the image cannot be found.

Full tags: https://www.w3schools.com/tags/default.asp

HTML Validator: https://validator.w3.org/#validate_by_input

## Div and Span

```
<div>
   <p>This is an example of when to use a div elements versus a span element. A span element goes around <span>a small chunk of html</span></p>
</div>
```

## Id and Class

```
<div id="top">
    <p class="first_paragraph">First paragraph of the section</p>
    <p class="second_paragraph">Second paragraph of the section</p>
</div>

<div id="bottom">
    <p class="first_paragraph">First paragraph of the section</p>
    <p class="second_paragraph">Second paragraph of the section</p>
</div>
```

IDs uniquely identify a piece of content and should only be used once per HTML page
Classes group multiple pieces of content together

## Bootstrap library

Bootstrap is one of the easier front-end frameworks to work with. Bootstrap eliminates the need to write CSS or JavaScript. Instead, you can style your websites with HTML. You'll be able to design sleek, modern looking websites more quickly than if you were coding the CSS and JavaScript directly.

Starter Template: https://getbootstrap.com/docs/4.0/getting-started/introduction/#starter-template

Column Grid Explanation: https://getbootstrap.com/docs/4.0/layout/grid/

Containers and Responsive Layout: https://getbootstrap.com/docs/4.0/layout/overview/

Images:https://getbootstrap.com/docs/4.0/content/images/

Navigation Bars:https://getbootstrap.com/docs/4.0/components/navbar/

Font Colors:https://getbootstrap.com/docs/4.0/utilities/colors/

## Plotly

Plotly, although a private company, provides open source libraries for both JavaScript and Python.

Because the web app you're developing will have a Python back-end, you can use the Python library to create your charts. Rather than having you learn more JavaScript syntax, you can use the Python syntax that you already know. 

# The Backend

## Flask

What is Flask?
Flask. A web framework takes care of all the routing needed to organize a web page so that you don't have to write the code yourself!

When you type "http://www.udacity.com" into a browser, your computer sends out a request to another computer (ie the server) where the Udacity website is stored. Then the Udacity server sends you the files needed to render the website in your browser. The Udacity computer is called a server because it "serves" you the files that you requested.

The HTTP part of the web address stands for Hypter-text Transfer Protocol. HTTP defines a standard way of sending and receiving messages over the internet.

When you hit enter in your browser, your computer says "get me the files for the web page at www.udacity.com": except that message is sent to the server with the syntax governed by HTTP. Then the server sends out the files via the protocol as well.

There needs to be some software on the server that can interpret these HTTP requests and send out the correct files. That's where a web framework like Flask comes into play. A framework abstracts the code for receiving requests as well as interpreting the requests and sending out the correct files.

Why Flask?

First and foremost, you'll be working with Flask because it is written in Python. You won't need to learn a new programming language.
Flask is also a relatively simple framework, so it's good for making a small web app.
Because Flask is written in Python, you can use Flask with any other Python library including pandas, numpy and scikit-learn. In this lesson, you'll be deploying a data dashboard and pandas will help get the data ready.

Using Flask in the Classroom Workspace

Open a Terminal and type (Flask already set up):

```
python worldbank.py
```

That assumes you are in the default workspace directory within Terminal. That will get the server running.

Seeing your App in the Workspace

Once the server is running, open a new terminal window and type

```
env | grep WORK
```

This command will return the Linux environmental variables that contain information about your classroom workspace. The env command will list all the environmental variables. The | symbol is a pipe for sending output from one command to another. The grep command searches text, so grep WORK will search for any text containing the word WORK.

The command should return two variables:

```
WORKSPACEDOMAIN=udacity-student-workspaces.com
WORKSPACEID=viewc7f3319f2
```

Your WORKSPACEID variable will be different but the WORKSPACEDOMAIN should be the same. Now, open a new web browser window, and type the following in the address bar:

```
http://WORKSPACEID-3001.WORKSPACEDOMAIN
```

In this example, that would be: https://viewc7f3319f2-3001.udacity-student-workspaces.com/

DON'T FORGET TO INCLUDE -3001. You should be able to see the web app. The number 3001 represents the port for accessing your web app.

Creating New Pages

To create a new web page, you first need to specify the route in the routes.py as well as the name of the html template.

```
@app.route('/new-route')
def render_the_route():
    return render_template('new_route.html')
```

The route name, function name, and template name do not have to match; however, it's good practice to make them similar so that the code is easier to follow.

The new_route.html file must go in the templates folder. Flask automatically looks for html files in the templates folder.

What is @app.route?

To use Flask, you don't necessarily need to know what @app.route is doing. You only have to remember that the path you place inside of @app.route() will be the web address. And then the function you write below @app.route is used to render the correct html template file for the web address.

In Python, the @ symbol is used for decorators. Decorators are a shorthand way to input a function into another function. Take a look at this code. Python allows you to use a function as an input to another function:

```
def decorator(input_function):

    return input_function

def input_function():
    print("I am an input function")

decorator_example = decorator(input_function)
decorator_example()
```

Running this code will print the string:

I am an input function

Decorators provide a short-hand way of getting the same behavior:

```
def decorator(input_function):
    print("Decorator function")
    return input_function

@decorator
def input_function():
    print("I am an input function")

input_function()
```

This code will print out:

Decorator function
I am an input function

Instead of using a decorator function, you could get the same behavior with the following code:

```
input_function = decorator(input_function)
input_function()
```

Because @app.route() has the . symbol, there's an implication that app is a class (or an instance of a class) and route is a method of that class. Hence a function written underneath @app.route() is going to get passed into the route method. The purpose of @app.route() is to make sure the correct web address gets associated with the correct html template. This code

```
@app.route('/homepage')
def some_function()
  return render_template('index.html')
```

is ensuring that the web address 'www.website.com/homepage' is associated with the index.html template.

# Deployment

Heroku is just one option of many for deploying a web app, and Heroku is actually owned by Salesforce.com.

The big internet companies offer similar services like Amazon's Lightsail, Microsoft's Azure, Google Cloud, and IBM Cloud (formerly IBM Bluemix). However, these services tend to require more configuration. Most of these also come with either a free tier or a limited free tier that expires after a certain amount of time.

Remember to remove the the line app.run(host='0.0.0.0', port=3001, debug=True) in the myapp.py file before deploying to Heroku; however, to run the web app from within the Udacity workspace, you do need that line of code


##Instructions Deploying from the Classroom

Here is the code used in the screencast to get the web app running:

First, a new folder was created for the web app and all of the web app folders and files were moved into the folder:

```
mkdir web_app
mv -t web_app data worldbankapp wrangling_scripts worldbank.py
```

The next step was to create a virtual environment and then activate the environment:

```
conda update python
python3 -m venv worldbankvenv
source worldbankenv/bin/activate
```

Then, pip install the Python libraries needed for the web app

```
pip install flask pandas plotly gunicorn
````

The next step was to install the heroku command line tools:

```
curl https://cli-assets.heroku.com/install-ubuntu.sh | sh
https://devcenter.heroku.com/articles/heroku-cli#standalone-installation
heroku —-version
```

And then log into heroku with the following command

```
heroku login
```

Heroku asks for your account email address and password, which you type into the terminal and press enter.

The next steps involved some housekeeping:

```
remove app.run() from worldbank.py
```

type ```cd web_app``` into the Terminal so that you are inside the folder with your web app code.
Then create a proc file, which tells Heroku what to do when starting your web app:

```
touch Procfile
```

Then open the Procfile and type:

```
web gunicorn worldbank:app
```

Next, create a requirements file, which lists all of the Python library that your app depends on:

```
pip freeze > requirements.txt
```

And initialize a git repository and make a commit:

```
git init
git add .
git commit -m ‘first commit’
```

Now, create a heroku app:

```
heroku create my-app-name
```

where my-app-name is a unique name that nobody else on Heroku has already used.

The heroku create command should create a git repository on Heroku and a web address for accessing your web app. You can check that a remote repository was added to your git repository with the following terminal command:

```
git remote -v
```

Next, you need to push your git repository to the remote heroku repository with this command:

```
git push heroku master
```
Now, you can type your web app's address in the browser to see the results.
