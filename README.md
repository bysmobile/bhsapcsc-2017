# BHS APCS 2017

## Cloud 9 Setup Instructions
Cloud 9 is an online development environment we are using to develop this app.
It supports code editing and github access as well as running and debugging the app in a web browser.

### Setup Github
1. Create your own github account, if you don't already have one, at: http://www.github.com
2. Go to the [bysmobile/bhsapcsc-2017](https://github.com/bysmobile/bhsapcsc-2017) github page.
3. Click the Fork button in the top right to create a working copy in your own github account. When completed, you should be looking at your forked copy in github.
4. Click the green "Clone or download" button, then click the Copy to Clipboard button to the right of the git URL.

### Setup Cloud9
  1. Find the Cloud9 invitation email from support@c9.io in your frogrock email account. Talk with Mr Sovick if you did not receive an invite.
  2. Click on the link in the email to accept the invitation and create a free Cloud9 account. For "What kind of developer are you" choose "Student". For "How will you use Cloud9" choose "Coursework"
  3. After you have created your Cloud9 account, click the big "Create a new workspace" button.
  4. Set Project Name to "bhsapcs-2017" same as the github repo name
  5. Paste your github forked repo url from step 4 under Setup Github in the "Clone from Git" field
  6. IMPORTANT: Choose node.js as the "Template"
  7. Click "Create Workspace". When completed you should be in the newly created workspace.
 
### Setup Cloud9 Workspace
In the bash tab at the bottom of your main Cloud9 workspace window, you need to enter the following commands:

Switch to your team's branch

    git checkout bhsapcsc-team#-2017 (Replace # with your team number)

Add a remote repo named "upstream" pointing to the original project for pulling updates

    git remote add upstream https://github.com/bysmobile/bhsapcsc-2017.git

Install phonegap so you can run the app in a browser

    npm install phonegap -g

## Running the app from Cloud 9
You can launch an instance of the phonegap server that will allow you to preview your app in a web browser. 
As you make changes to code in Cloud9, the browser should automatically update and show those changes.

Type the following in the bash tab at the bottom of the workspace:

    phonegap serve -p $PORT

After your see the "starting app server" and "listening on ..." messages, 
you should be able to view the app at the following URL:

    http://workspace-username.c9users.io

    *Replace "workspace" with what you named your Cloud9 workspace (e.g. bhsapcs-2017). 
    *Replace "username" with your Cloud9 username.)

*Note: You cannot connect to the ip address displayed after starting phonegap serve (e.g. 172.17.0.110:8080).*

## Git Commands
Here is a list of the most frequent git commands you will need to save your changes to your repo.

Check the status of your local copy to see what you have changed. Also to verify what branch you are on.

    git status

Save your changes to your git repo

    git add --all
    git commit -m "Describe your changes"
    git push
    
*Note: git push will ask you for your git account credentials.  
You can save these by using the following command (substituing your username, password and repo path of course).
You can get the repo path using the green "Clone or Download" button on your repo page in github.*

    git remote set-url origin https://name:password@github.org/repo.git

## Building in PhoneGap
You can also use the build.phonegap.com service to build your app so you can download and test it on a device.
To do this, you will need to log into http://build.phonegap.com using credentials for your team found in the APCS End of Year Projects Google document. See #general in Slack for the link.

1. In Cloud9, change the <name> of your app in the root config.xml file to: "yourname 2017" to avoid confusion on the phonegap Apps page.
2. commit and push your changes to config.xml
3. Click the "+ new app" button at https://build.phonegap.com/apps
4. Paste the Git URL for your fork and enter your team's branch name (e.g. bhsapcsc-team#-2017).
5. Click the "Pull from .git repository" button.
6. After it creates the new build, you will need to refresh the page, then click on the "Ready to Build" button.
7. When you have checked in new code, you can force a rebuild by clicking on the "Update code" button.