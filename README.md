Let's get started and create our first Flask app.
Eventually, at the end of this lesson, we'll have created a fan page from The Hobbit.
It will be for Thorin and his company of dwarves, as you can see here.
Right now though, we just want to get a simple Flask app up and running.
This video assumes that you are using our recommended development environment, and have already created your new repository.
I will start off by installing the Flask framework.
To do that, I will type pip3 install Flask, and that will install the framework for us.
Once that's installed, I will just clear my terminal.
In Flask, the naming convention for our main file to run our application is usually run.py or app.py.
For this project, I will just call it run.py by creating a new file using the "touch" command.
Let's open our new file, and the first thing that we need to do is to import the Flask class.
"from flask import Flask". The capital F indicates that it's a class name, so it's important to use a capital F here.
Next, we need to create an instance of this class.
Again, in Flask, the convention is that our variable is called 'app'.
I will type: "app = Flask(__name__)".
We'll come back to this and explain it shortly.
Then, we use the route decorator to tell Flask what URL should trigger the function that follows.
I will create a function called "index", which just returns the string, "Hello, World".
So let's go through this and understand what's happening.
First, we're importing our Flask class.
We're then creating an instance of this and storing it in a variable called 'app'.
The first argument of the Flask class, is the name of the application's module - our package.
Since we're just using a single module, we can use __name__ which is a built-in Python variable.
Flask needs this so that it knows where to look for templates and static files.
We're then using the app.route decorator.
In Python, a decorator starts with the @ symbol, which is also called pie-notation.
Effectively, a decorator is a way of wrapping functions.
We don't need to understand the technicalities of this, but just as in JavaScript, all functions are objects, and can be passed around.
When we try to browse to the root directory, as indicated by the "/", then Flask triggers the index function underneath and returns the "Hello, World" text.
So far, this isn't enough to get our application running, so we need to add some extra functionality to do that.
We can "import os" from the standard Python library, and then we're going to reference this built-in variable and say that:
if name is equal to "main" (both wrapped in double underscores), then we're going to run our app with the following arguments.
The 'host' will be set to os.environ.get("IP"),
and I will set a default of "0.0.0.0".
We're using the os module from the standard library to get the 'IP' environment variable if it exists, but set a default value if it's not found.
It will be the same with 'PORT', but this time, we're casting it as an integer, and I will set that default to "5000", which is a common port used by Flask.
We also need to specify "debug=True", because that will allow us to debug our code much easier during the development stage.
The word 'main' wrapped in double-underscores (__main__) is the name of the default module in Python.
This is the first one that we run, so if this has not been imported, which it won't be, then it's going to be run directly.
Then we want to run our app using the arguments that we've passing inside of this statement.
I will just save the file, and we can now type: "python3 run.py" in the Terminal to start our Flask app.
The app is successfully running now, so let me just open the live preview page.
As you can see, our "Hello, World" text is being returned from our index function.
To stop my app, I can type the quit command in the Terminal, which is Ctrl+C for me.
I can then replay my last entry to restart the app by pushing the 'Up' arrow on my keyboard.
One thing I'd like you to take note of, is that we should never have "debug=True" in a production application, or when we submit our projects for assessment.
This is very important, because having debug=True can allow arbitrary code to be run, and obviously this is a security flaw.
You should only have debug=True while testing your application in development mode, but change it to debug=False before you submit your project.
In this video, we've seen how to create a very simple Flask app.
All it does when our index page is called, is just return the text, "Hello, World".
This is helpful for showing how a Flask app is put together, but it's not very helpful for showing how to render HTML files.
We'll have a look at that in our next video.



