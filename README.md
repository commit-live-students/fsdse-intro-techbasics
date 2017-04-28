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

## Assignments

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

### Linux Users, Groups & Permissions

#### Download Anaconda, make it executable

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
* Note :: How to install and run Anaconda is covered in Anaconda section in detail
