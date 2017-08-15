# Using AWS Elastic Beanstalk to Deploy Your Hack
## MLH Localhost 

This is a short and simple guide to using Elastic Beanstalk to deploy a hack for an MLH Hackathon.

### 1) Install the EB CLI Tool

Follow the instructions [here at AWS's docs](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html) to install the EB CLI tool. If you're using MacOS, you'll need to have XCode installed, then install the XCode Command Line tools, then install `pip`. Once `eb` is installed using `pip`, you'll have to create the `~/.profile` text file if it doesn't already exist, and add either `export PATH=~/Library/Python/3.4/bin:$PATH` or `export PATH=~/Library/Python/2.7/bin:$PATH` to the `.profile` file, depending on which version of python you have installed (2.7 comes default on the Mac).

### 2) Download This Code

For your first time creating an EB App, you should use this code to make it easy to try out. Fork the repo using the 