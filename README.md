# fastmac

> Use a MacOS shell (for free!)

I don't have a Mac, but I often want to test my software on a Mac, or build software for folks using Macs. Rather than shelling out thousands of dollars to buy a Mac, it turns out we can use GitHub Actions to give us access to one for free! Note that this only gives us access to a terminal shell, not a full GUI. Here's how to proceed:

## Clone template

First, [click here](https://github.com/fastai/fastmac/generate) to create a copy of this repo in your account. Type `fastmac` under "repository name" and then click "Create repository from template". After about 10 seconds, you'll see a screen that looks just like the one you're looking at now, except that it'll be in your repo copy.

**NB**: Follow the  rest of the instructions in repo copy you just made, not in this fastai repo.

## Run the `mac` workflow

Next, <a href="../../actions?query=workflow%3Amac">click here</a> to go to the GitHub actions screen for the `mac` workflow, and then click the "Run workflow" dropdown on the right, and then click the green "Run workflow" button that appears.

<img width="365" src="https://user-images.githubusercontent.com/346999/92965396-91320680-f42a-11ea-9bc3-90682e740343.png" />

## Access the shell using ssh or browser

After a few seconds, you'll see a spinning orange circle. Click the "mac" hyperlink next to it.

On the next screen, you'll  see another spinning orange circle, this time with "build" next to it. Click "build".

This will show the progress of your Mac that's getting ready for you. After a while, the "Setup tmate session" section will open, and once it's done installing itself, it will repeatedly print lines like this:
```
WebURL: https://tmate.io/t/rXbusP3qkYsfALDSLMQZVwG3d

SSH: ssh rXbusP3qkYsfALDSLMQZVwG3d@sfo2.tmate.io
```

Copy and paste the ssh line (e.g `ssh rXbusP3qkYsfALDSLMQZVwG3d@sfo2.tmate.io` in this case) into your terminal (Windows users: I strongly recommend you use [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) if possible) and press <kbd>Enter</kbd>.

You'll see a welcome message. Press <kbd>q</kbd> to remove it, and you'll be in a Mac shell! The shell already has [brew](https://brew.sh/) installed, so you can easily add any software you need.

Instead of using ssh in your terminal, you can paste the "WebURL" value into your browser, to get a terminal in your browser. Whilst this is adequate if you're in a situation that you can't access a terminal (e.g. you have to do some emergency work on your phone or tablet), it's less reliable than the ssh approach and not everything works.

## Stop your session

Your session will run for up to six hours. When you're finished, you should close it, since otherwise you're taking up a whole computer that someone else could otherwise be using!

To close the session, click the red "Cancel workflow" on the right-hand side of the Actions screen (the one you copied the `ssh` line from).

## Use a Linux (Ubuntu) shell

If you need to access a Linux shell, instead of MacOS, follow all the same steps as above, except (<a href="../../actions?query=workflow%3Amac">click this link</a>) instead of the one mentioned above. And click "linux" instead of "mac" to access your session.

## Using ssh to connect to other servers

fastmac (or linux) can be handy if you're out and about but need to safely access one of your servers. You can ssh from your fastmac/linux instance to your servers, as long as you've set up a GitHub secret containing the ssh private key needed to connect to your server.

