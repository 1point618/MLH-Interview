# Using AWS Elastic Beanstalk to Deploy Your Hack
## MLH Localhost 

This is a short and simple guide to using Elastic Beanstalk to deploy a hack for an MLH Hackathon. This tutorial focuses on computers running MacOS. The general steps are the same, but the specific commands slightly different on Linux and Windows, and for those you should check out our longer [blog post](https://news.mlh.io/deploy-your-hack-in-3-steps-intro-to-aws-and-elastic-beanstalk-02-20-2015) on the subject.

### 1) Sign up for & in to AWS

If you haven't already, go to [aws.amazon.com](http://aws.amazon.com) and create a new AWS account. 

We've provided $100 in free AWS hosting for this hackathon, so once you've created your account go to the link we've provided and sign up for that. You'll need to ensure that you stay logged into your AWS account for this tutorial.

### 2) Download This Ruby App

For your first time creating an EB App, you should use this code to make it easy to try out. Fork the repo using the "Fork" button at the top of this page. 

![Location of "Fork"](https://github.com/1point618/MLH-Interview/blob/master/images/fork.png)

Once you've done that, click on the green "Clone or Download" button on your version of the repository and either use the `git clone` command to create a local version of the code. 

If `git` doesn't work or isn't installed, you'll need to install XCode from the Apple App Store, then type in `xcode-select --install` on the command line to install the command line tools.

### 3) Install the EB CLI Tool

Follow the instructions [here at AWS's docs](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html) to install the EB CLI tool. These instructions are a bit hard to follow if you don't know the command line well, so we'll run through them here.

On MacOS, you'll likely have to install `pip` by running `$ sudo easy_install pip` in the terminal, unless you've already done this for another project.

Then run `$ pip install awsebcli`. This installs the `eb` tool, but doesn't set it up to run on the CLI yet. To do that, you'll have to create the `~/.profile` text file if it doesn't already exist by navigating to your user directory (`$ cd ~`) and opening the `.profile` folder with a text editing tool like vim or pico, and then add either `export PATH=~/Library/Python/3.4/bin:$PATH` or `export PATH=~/Library/Python/2.7/bin:$PATH` to the `.profile` file, depending on which version of python you have installed (2.7 comes default on the Mac, and you can find which version you have installed by running `$ python -V`). This tells your terminal to look in this particular directory when trying to run commands. 

Finally, run `$ source ~/.profile` to refresh your terminal window to use the rule you just created. Try running `$ eb status` to make sure `eb` is installed and working correctly—you'll get an error, but it will be about your credentials not being correct, rather than a typical "command not found" error.

### 4) Deploy to Elastic Beanstalk

Now that you have a simple "Hello World" Ruby app on your computer and the EB command line tool installed, it's time to deploy to the cloud! This only takes a few commands, although each command will run you through a few questions. For the most part, you can just hit "enter" to take the default option.

So, navigate to your code directory, then run `$ eb init` there. Then:

1. Select the region closest to your now.
2. Go to [your AWS console security settings](https://console.aws.amazon.com/iam/home?#/security_credential), create a new key-pair, and copy-paste both the public and private key into your terminal when asked.
3. Enter a name (default is fine).
4. Select Ruby version to use (2.2, which should be the default).
5. Run SSH (Y)
6. Keypair: Create a keypair by simply selecting the default prompts. This is bad security practice, but works fine for the hackathon. You'll need to change it if you plan on hosting this publically.

You've not initialized the Elastic Beanstalk environment. Now you need to upload the code. Run `$ eb create`.

1. Enter the environment name (default is fine).
2. Enter the DNS prefix (default).
3. Load balancer: Select the "classic" load balancer.

From here the code will upload and the environment will be created with it—virtual servers, a load balancer, a virtual network, and anything else you app needs. This will take several minutes.

Once the process finishes, you should be able to find a line that begins with `CNAME` and includes a URL. Copy/paste that URL to your web browser, append "/hi" to the end, and hit "enter". It should look something like this:

![Hello World!](https://github.com/1point618/MLH-Interview/blob/master/images/hello.png)

























