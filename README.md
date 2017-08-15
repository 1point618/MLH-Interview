# Using AWS Elastic Beanstalk to Deploy Your Hack
## MLH Localhost 

This is a short and simple guide to using Elastic Beanstalk to deploy a hack for an MLH Hackathon.

### 1) Sign up for AWS



### 2) Install the EB CLI Tool

Follow the instructions [here at AWS's docs](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html) to install the EB CLI tool.

If you're using MacOS, you'll need to have XCode installed, then install the XCode Command Line tools, then install `pip`. Once `eb` is installed using `pip`, you'll have to create the `~/.profile` text file if it doesn't already exist, and add either `export PATH=~/Library/Python/3.4/bin:$PATH` or `export PATH=~/Library/Python/2.7/bin:$PATH` to the `.profile` file, depending on which version of python you have installed (2.7 comes default on the Mac).

Once you've done everything and run the `source` command, run `$ eb status` to make sure `eb` is installed and working correctly. 

### 3) Download This Ruby App

For your first time creating an EB App, you should use this code to make it easy to try out. Fork the repo using the "Fork" button at the top of this page. 

![Location of "Fork"](https://raw.githubusercontent.com/1point618/MLH-Interview/master/images/fork.png?token=AA1hXgt90f8ge9BB3MtjzCshA4lX4Q6jks5Zm4huwA%3D%3D)

Once you've done that, click on the green "Clone or Download" button on your version of the repository and either use the "git clone" command to download the code locally, or download the .zip from GitHub.

### 4) Deploy to Elastic Beanstalk

Now that you have a simple "Hello World" Ruby app on your computer and the EB command line tool installed, it's time to deploy the 

