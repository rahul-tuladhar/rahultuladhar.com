title: How to Set Up a Static Site Using Flask and HTML on Render.com
date: 2022-02-06
category: Programming

## Introduction
This is simple post about how to set up a static site using Python and Flask. 

Most of the code can be found from [this blog post by Kaustubh Vaghmare][2]. I found this blog post to be sufficiently detailed enough to get up and running with Flask. 

The flask app he calls `sitebuilder.py` builds static `.html` files which can be hosted on a fair number of free hosting sites such as [Render.com](https://www.render.com). 

### Hosting on Render.com

After running through the code and building the `sitebuilder.py` aka `app.py` you have a working simple static site generator. To make the site accessible on the internet you use a hosting site such as render to host those static `.html` files created and stored in the `/build` directory.

After creating an account and logging into render you will be presented with a dashboard which will be the place where you can see your deployed services. The services we will be deploying will be for a new static site. You can use the `New +` [button](https://dashboard.render.com/select-repo?type=static) on the navbar and select `Static Site`. 

If you have logged into Render.com through your github.com account you will be able to see that reflected in the next screen. You would then be able to give permission to render to view some or all of the repositories in your github account. If you have your project saved up on github already, then you can see the repo name as a possible item to be selected. 

After selecting your repo, you can input some information for your static site service. For your `Build Command` you can input the same build command to build your `.html` files locally: `python <flask_app_file_name.py> build`. In my case I put `python app.py build`. 

Make sure in the `Publish directory` field you input  `./build` as the directory which has your generated static files. I left the rest of the values in the fields on that page with their defaults (besides the Custom Domain). Render.com automatically provides a URL for your static site even if you don't have your own domain. The URL should look something like `static-site-name.onrender.com`. You will be able to access the URL after hitting the `Create Static Site` button at the bottom of the deploy static site page.

### Custom Domains

If you want to specify your own custom domain, you can add that after first createing the static site and seeing it run live on your dashboard. You can click on your service in the list of services. If you go to the `Settings` tab for your service you can see a few options similar to when you first configured your static site to be created. 

Under Custom Domains, you will be able to configure settings to point your custom domain to your newly created static site. You can follow Render's own guidelines on [Custom Domains](https://render.com/docs/custom-domains). Essentially, whereever you may purchase your domain, you can specify in their DNS settings custom records pointing to the services that domain will use. In our case, we want to have a type A record to pointing to the specific IP from Render's docs: `216.24.57.1`. In addition, you would also want to set the type CNAME record to point to your `*.onrender.com` URL.

## Resources

[1]: https://github.com/akprasad/arunkprasad.com 
[2]: https://vkaustubh.github.io/blog/geek/2020-02-23-blogging-with-flask.html
[3]: https://testdriven.io/blog/static-site-flask-and-netlify/
