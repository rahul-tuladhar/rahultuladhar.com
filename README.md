# Personal Website

This repo holds the files for [rahultuladhar.com](https://rahultuladhar.com). 

## Getting started

# Installation
There are not many requirements, but you can install them using:

```pip install -r requirements.txt```

# Running the server

Since this is a flask app, you can use the command:

```python app.py```

to run the flask app.

# Build the static files

The flask server is useful for serving the static files for local development. You can use the command:

```python app.py build```

In order to build the pure `html` files in the `/build` directory. These are then served on a static hosting site such as [Render.com](https://www.render.com).

More information can be found on [this post](https://rahultuladhar.com/how-to-setup-static-site). 

### Credits
- https://github.com/akprasad/arunkprasad.com 
- https://vkaustubh.github.io/blog/geek/2020-02-23-blogging-with-flask.html
- https://testdriven.io/blog/static-site-flask-and-netlify/