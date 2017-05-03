# fsdse-techbasics

![GitHub Logo](https://s3.ap-south-1.amazonaws.com/greyatom-social/logo.png)

## Lets Get Rolling - Student Pre-Read
Before this lesson , we recommend you go through
* [Ubuntu](https://en.wikipedia.org/wiki/Ubuntu_(operating_system))
* [Unix_shell](https://en.wikipedia.org/wiki/Unix_shell)

## Learning Objectives

After this lesson, you'll be able to
* Navigate through files and folders
* Do different action and with files and folders
* Add/Edit Files using terminal editor

## Agenda

* List
*
*

## Slides

*
*

## Assignment 1

### Navigating the Linux Filesystem & Working With Files and Directories
* Clone repo from https://github.com/commit-live-students/fsdse-techbasics
* There is a multi cuisine hotel which take a order on phone and the orders are recorded in order.txt
* Change directory to folder fsdse-techbasics
  - List down what there in folder
  - List down hidden files in folder
* Check what kind of file is orders.txt
* Display the content of file orders.txt
* Let's explore order.txt more and try to solve query below using head, tail commands
  - Get first 10 orders
  - Get last 10 orders
  - Get last 3 orders
  - Get first 4 orders
  - Get order from 10 to last
  - Get all order, except last 10 order
* Create a new folder named 'orders'
* Copy orders.txt file in the orders folder
* Rename orders folder to 'orders_backup'
* We don't need tmp folder, delete a folder named tmp
* We don't need tmp.txt file, delete a file name 'tmp.txt'
* Lets add below orders to the list using nano command
  - American Pizza
  - Italian Pizza
* Now again repeat all above get exercises using head and tail commands. Result will be different this time as new two orders are added to list

## Assignment 2

### Linux Users, Groups & Permissions

Download Anaconda, make it executable

* The best way to install Anaconda is to download the latest Anaconda installer bash script, verify it, and then run it.
* Find the latest version of Anaconda for Python 2.7 at the [Anaconda Downloads Page](https://www.continuum.io/downloads))
* Next, change to the /tmp directory on your server. This is a good directory to download ephemeral items, like the Anaconda bash script, which we won't need after running it.
```
cd /tmp
```
* Use curl to download the link that you copied from the Anaconda website
```
curl -O https://repo.continuum.io/archive/Anaconda2-4.3.1-Linux-x86_64.sh
```
* Now let make Anaconda file executable
```
chmod +x Anaconda2-4.3.1-Linux-x86_64.sh
```
* How to install and run Anaconda is covered in next section.

## Assignment 3

### install Anaconda

* Now you ready have executable Anaconda bash script downloaded in previous assignment. Now let's go ahead and install it. Now we can run the script:
```
bash Anaconda2-4.3.1-Linux-x86_64.sh
```
* You’ll receive the following output:
```
output

Welcome to Anaconda2 2-4.3 (by Continuum Analytics, Inc.)

In order to continue the installation process, please review the license
agreement.
Please, press ENTER to continue
```
* Press ENTER to continue and then press ENTER to read through the license. Once you’re done reading the license, you’ll be prompted to approve the license terms:
```
output

Do you approve the license terms? [yes|no]
```
* As long as you agree, type yes. At this point, you’ll be prompted to choose the location of the installation. You can press ENTER to accept the default location, or specify a different location to modify it
```
output

Anaconda2 will now be installed into this location:
/home/username/anaconda2

  - Press ENTER to confirm the location
  - Press CTRL-C to abort the installation
  - Or specify a different location below

[/home/username/anaconda2] >>>

```
* The installation process will continue, it may take some time. Once it’s complete you’ll receive the following output:
```
Output
...
installation finished.
Do you wish the installer to prepend the Anaconda2 install location
to PATH in your /home/username/.bashrc ? [yes|no]
[no] >>>
```
* Type yes so that you can use the conda command. You’ll next see the following output:
```
Output

Prepending PATH=/home/username/anaconda2/bin to PATH in /home/username/.bashrc
A backup will be made to: /home/username/.bashrc-anaconda2.bak
...

```
* You can also say No and can manually add Anaconda path to .bashrc file. Open your terminal and type below command
```
export PATH="/home/username/anaconda2/bin"
```
* This will add Anaconda path to .bashrc file. You can do it by editing .bashrc file using nano command and add path.
* In order to activate the installation, you should source the ~/.bashrc file:
```
source ~/.bashrc
```
* Once you have done that, you can verify your install by making use of the conda command, for example with list:
```
conda list
```
* You’ll receive output of all the packages you have available through the Anaconda installation:
```
Output
# packages in environment at /home/username/anaconda2:
#
_license                  1.1                      py35_1  
_nb_ext_conf              0.3.0                    py35_0  
alabaster                 0.7.9                    py35_0  
...
```
Updating Anaconda
* You should regularly ensure that Anaconda is up-to-date so that you are working with all the latest package releases.
To do this, you should first update the conda utility:
```
conda update conda
```
* When prompted to do so, type y to proceed with the update.Once the update of conda is complete, you can update the Anaconda distribution:
```
conda update anaconda
```
* Again when prompted to do so, type y to proceed.This will ensure that you are using the latest releases of conda and Anaconda.
* Let's quick check our installation of anaconda using python script. NumPy is the fundamental package for scientific computing with Python which comes with default installation of anaconda.
* Create a new file named "test_anaconda.py" and insert below code
```
def quicksort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) / 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quicksort(left) + middle + quicksort(right)

print quicksort([3,6,8,10,1,2,1])
```
* Now run code by typing in terminal
```
python test_anaconda.py
```
* it shoulf output as below
```
output
[1, 1, 2, 3, 6, 8, 10]
```

Uninstalling Anaconda

* If you are no longer using Anaconda and find that you need to uninstall it, you should start with the anaconda-clean module which will remove configuration files for when you uninstall Anaconda.
```
conda install anaconda-clean
```
* Type y when prompted to do so.
* Once it is installed, you can run the following command. You will be prompted to answer y before deleting each one. If you would prefer not to be prompted, add --yes to the end of your command:
```
anaconda-clean
```
* This will also create a backup folder called .anaconda_backup in your home directory:
```
Output
Backup directory: /home/username/.anaconda_backup/2017-04-25T191831
```
* You can now remove your entire Anaconda directory by entering the following command:
```
rm -rf ~/anaconda2
```
* Finally, you can remove the PATH line from your .bashrc file that Anaconda added. To do so, first open nano:
```
nano ~/.bashrc
```
* Then scroll down to the end of the file (if this is a recent install) or type CTRL + W to search for Anaconda. Delete or comment out the following lines:
```
# added by Anaconda2 2-4.3 installer
export PATH="/home/username/anaconda2/bin:$PATH"
```
* When you’re done editing the file, type CTRL + X to exit and y to save changes.Anaconda is now removed from your server.

## Assignment 4

### Setup github token in .profile

* Many API's require you to acquire an access token. While you will need to use this access token in your application when accessing their API, you do not want to expose your token to users or anyone who has access to the code base of your application

* The assignment here we will be using here to protect our API keys is what I like to call 'backside-secrets'. We will create an environment variable on our server that contains the API key that we want to protect. Whenever we need to access the key, we will use environment variable in code

* Follow this article and get the  personal access token for github and set in .profile page so that it can be available in script code
```
https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/
```
* Once you have personal access token, do the following at the command prompt
```
echo set GITHUB_TOKEN='personal-access-token-here' >> ~/.profile
```
* Run `source ~/.profile` if you want to update the current shell with the changes
* Let's see how you can get your token in python script. Create a file name `test_env.py` and enter below
```
import os
print os.environ['GITHUB_TOKEN']
```
* Run your file using python `python test_env.py`. It should print your previously set github token


## Assignment 5

### What Happens When You Type Address In Address Bar
* Watch this couple of videos
  - https://www.youtube.com/watch?v=xIuBmOufbls
  - https://www.youtube.com/watch?v=7_LPdttKXPc
* Watch this videos for how a web browser builds and displays a web page
  - https://www.youtube.com/watch?v=DuSURHrZG6I

## Assignment 6

### Set up SSH for GitHub
* Add a new SSH key to your GitHub account using below links
  - [Generating a new SSH key and adding it to the ssh-agent](https://en.wikipedia.org/wiki/Ubuntu_(operating_system)
  - [Adding a new SSH key to your GitHub account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)
* Once your done with setting up SSH key for github create a new repo on your github account. Clone github repo using SSH url.
* Do some changes in repo/file and try to push changes to github repo again. Now it should not ask any credentials while pushing changes to github repo as it must use your SSH key for credentials and authentication now.

## Assignment 7
* Download chrome applicatiom Postman from url https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop/related?hl=en
* For more info on postman watch videos here at https://www.youtube.com/watch?v=8veXJ9YGlFI&list=PLM-7VG-sgbtD8qBnGeQM5nvlpqB_ktaLZ
* `GET` request
  - Get user detail - https://api.github.com/users/PradeepJaiswar
  - Get orgs repos - https://api.github.com/orgs/commit-live-students/repos
  - Get repo info - https://api.github.com/repos/commit-live-students/fsdse-techbasics
  - Get repo readme - https://api.github.com/repos/commit-live-students/fsdse-techbasics/readme
  - Get repo contents info - https://api.github.com/repos/PradeepJaiswar/ember-mailbox/contents/
  - Get repo file contents - https://api.github.com/repos/PradeepJaiswar/ember-mailbox/contents/package.json
* Exercise
  - [Create a file in repo using rest api](https://developer.github.com/v3/repos/contents/#create-a-file)
  - [Update a file in repo using rest api](https://developer.github.com/v3/repos/contents/#update-a-file)
  - [Delete a file in repo using rest api](https://developer.github.com/v3/repos/contents/#delete-a-file)
* Note - Base url for all rest api is `https://api.github.com/`

## Assignment 8
* Go to https://www.kaggle.com/ and create a new account. (skip if you already have a Kaggle account)

### Download dataset from Kaggle using terminal
* In order to download the data, you need to be logged in into Kaggle
* One solution is to export your cookies and tell wget to use your cookies when downloading the data
* Use this plugin on chrome to get cookie data (https://chrome.google.com/webstore/detail/cookietxt-export/lopabhfecdfhgogdbojmaicoicjekelh)
* Save it as cookies.txt. If you are doing on server you will have to upload the cookies.txt on your server
* Now use wget to download files
`wget -x -c --load-cookies cookies.txt -P data -nH --cut-dirs=5 https://www.kaggle.com/c/diabetic-retinopathy-detection/download/trainLabels.csv.zip
`
* Above command will use your exported cookies to download the file to a folder called data
