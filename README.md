# Wiring Up Loopback With AngularJs - Part 1

Open terminal / cmd(command-line)

```
$ git clone 
$ cd loopback-getting-started
$ npm install
$ node . # then browse to localhost:3000
```

A simple person list using AngularJS on the client-side and LoopBack on the
server-side.

## Prerequisites

### Tutorials

- [Getting started with LoopBack]


## Procedure

### Create the application

##### Application information

- Name: `getting-started-loopback`
- Directory to contain the project: `getting-started-loopback`

```
$ slc loopback:model person
... # follow the prompts
```

### Run the application

From the project root, enter `node .` and browse to [`localhost:3000`](http://localhost:3000)
to view the application.


This tutorial will walk through the initial steps to create a basic LoopBack application. The application you’ll create is in the loopback-getting-started GitHub repository. To make it easy for you to pick up the tutorial at any point, there are tags for each step of the tutorial.
You can run through the steps to create the app and get a sense for some of the things LoopBack can do:
1.	Installing StrongLoop
2.	Creating Simple App using StrongLoop


#### 1.Installing StrongLoop

   StrongLoop’s Node API platform consists of:
•	LoopBack, an open-source Node application framework based on Express.
•	StrongLoop Process Manager and related devops tools for Node applications.
### What you’re going to do
   Follow the instructions for your operating system:
### Installing on MacOS
##### Install compiler tools
If you want features such as application profiling or monitoring, you may need to install compiler tools before you start.  
Install:
-	[Apple Xcode](https://angularjs.org/)
-	Depending on your version of MacOS and Xcode, you may need to also install the command-line tools.  To install them in Xcode:
1.	Click Xcode > Preferences.
2.	Choose Downloads.
3.	Click the install button next to “Command-line Tools”.
Most versions of OSX come with Python by default.  If for some reason you don’t have it, download and install Python.
Xcode license issues

If you see errors such as:

~~~
Enter the following command to validate your Xcode license, then reinstall 
~~~
Then you recently upgraded or installed Xcode and haven’t agreed to the license yet. 

### StrongLoop:
 
- Set directory permissions
- Set directory privileges
- To install Node and StrongLoop , you need permissions to write to directories:
~~~
	/usr/local/bin 
	/usr/local/lib/node_modules 
~~~
If you see errors such as:
 
  
~~~
Either change the rights for the specified directories, or run the command using sudo.
~~~
Then you don’t have the required rights to create files or directories.

#  Install Node.js
If you haven’t already installed Node, download the native installer from [NODE](https://nodejs.org/) and run it.

### Install StrongLoop
Follow these steps:
-	Open a Terminal window.
-	Enter this command:
~~~
$ sudo npm install -g strongloop
~~~
If you didn’t set your file and directory privileges as instructed above, use this command (not recommended):

# Installing on Windows
### Installing Compiler tools
- Configuring Python directory
- Npm uses node-gyp to compile native modules, and node-gyp requires Python.  If you installed Python in a non-standard directory, run this command to configure your setup:
~~~
$ npm config set python /path/to/python
~~~
where /path/to/python  is the directory where Python is installed.

### Install the following:
-	Python (v2.7.3 recommended, v3.x.x is not supported). 
-	Microsoft Visual Studio C++ 2013 (or later) for Windows Desktop.  The Express version works well.
#### For Windows 7:
-	For 64-bit builds of Node and native modules you will also need the Windows 7 64-bit SDK.  If the install fails, try uninstalling any C++ 2010 x64&x86 Redistributable that you have installed first.
-	If you get errors that the 64-bit compilers are not installed you may also need the compiler update for the Windows SDK 7.1.
- [Python]
- npm uses Python 2.7 (not 3.x, and not 2.6.x or earlier) to install packages with compiled add-ons (such as strong-agent, or websocket support).
- Download Python 2.7.x from https://www.python.org/downloads/windows/
- 	Download latest stable 2.7.x Windows MSI Installer, either x86 or x86-64, as appropriate
- Run installer, and make sure to add to Path:
- Accept the default, Install for all users.
- Accept default “c:\Python27” for Python files.
- Enable the option Add python.exe to Path.
~~~
Install Git
~~~
The Node package manager tool, npm, uses Git to download packages from Github. 
To install Git:
-	Go to http://git-scm.com/download,
-	Download the version for Windows.  Currently this is version 1.9.4.
-	Run installer:
--	Accept default install location
--	Accept or modify Components
--	Accept start menu folder
--	Modify `Adjusting your PATH environment` to “Use Git from Windows Command Prompt”
--	Accept default “Configuring the line ending conversions”
Configuration
###### By default, Git on Windows does not support paths longer than 260 characters; to avoid errors you must enable long paths with the following command:
`C:\> git config --system core.longpaths true`
Install Node.js
-	Go to http://nodejs.org/download/.
-	Download the latest `Windows Installer (.msi)`, 32 or 64-bit, as appropriate.
-	Run the installer.
- Install latest version of npm
--The version of npm installed as part of the Node installation has known issues on Windows. To avoid these problems, install the latest version of npm:
`C:\> npm install -g npm`

### Install StrongLoop

-	After installing the prerequisites as instructed above, restart your machine to ensure all configuration changes have taken effect.
-	Open a Windows Command Prompt. 
-	Install StrongLoop:
-  `C:\> npm install -g strongloop`

##	Creating Simple App Using  StrongLoop
#### Create new application
To create a new application, run the LoopBack application generator:
If using StrongLoop tools:
 ```
 slc loopback
 ```

The LoopBack generator will greet you with some friendly ASCII art and prompt you for the name of the application.
Enter `getting-started-loopback`. Then the generator will prompt you for the name of the directory to contain the project; press Enter to accept the default (the same as the application name):
~~~
 _-----_
    |       |    .--------------------------.
    |--(o)--|    |  Let's create a LoopBack |
   `---------´   |       application!       |
    ( _´U`_ )    '--------------------------'
    /___A___\
     |  ~  |
   __'.___.'__
 ´   `  |° ´ Y `
[?] What's the name of your application? loopback-getting-started
[?] Enter name of the directory to contain the project: getting-started-loopback
~~~
 
Then the tool will ask you what kind of application to create:
 ~~~
? What kind of application do you have in mind? (Use arrow keys)
❯ api-server (A LoopBack API server with local User auth)
  empty-server (An empty LoopBack API, without any configured models or datasources)
  hello-world (A project containing a controller, including a single vanilla Message and
    a single remote method)
  notes (A project containing a basic working example, including a memory database)
~~~
Press Enter to accept the default selection, `api-server`.
The generator will then display messages as it scaffolds the application including:
~~~

~~~
1.	Initializing the project folder structure.
2.	Creating default JSON files.
3.	Creating default JavaScript files.
4.	Downloading and installing dependent Node modules (as if you had manually done npm install).
Create models
Now that you’ve scaffolded the initial project, you’re going to create a person model that will automatically have REST API endpoints.
Go into your new application directory, then run the LoopBack model generator:
 ~~~
$ cd getting-started-loopback
~~~
#### Model Information
- Name: `person`
  - Data source: `db (memory)`
  - Base class: `PersistedModel`
  - Expose over REST: `Yes`
  - Custom plural form: *Leave blank*
  - Properties:
    - `name`
      - String
      - Required
    - `description`
      - String
      - Required
using StrongLoop tools: sh $ slc loopback:model
The generator will prompt for a model name.  Enter `person`:
~~~
[?] Enter the model name: person
~~~
It will ask if you want to attach the model to any data sources that have already been defined.  
At this point, only the default in-memory data source is available.  Press Enter to select it:
 ~~~
...
[?] Select the data-source to attach person to: (Use arrow keys)
❯ db (memory)
~~~
Then the generator will prompt you for the base class to use for the model.  Since you will eventually connect this model to a persistent data source in a database, press down-arrow to choose PersistedModel, then press Enter:
  ~~~
[?] Select model's base class: (Use arrow keys)
  Model
❯ PersistedModel
  ACL
  AccessToken
  Application
  Change
  Checkpoint
~~~
PersistedModel is the base object for all models connected to a persistent data source such as a database.
One of the powerful advantages of LoopBack is that it automatically generates a REST API for your model.  The generator will ask whether you want to expose this REST API.
Hit Enter again to accept the default and expose the Person model via REST: 
~~~
[?] Expose person via the REST API? (Y/n) Y
~~~
LoopBack automatically creates a REST route associated with your model using the plural of the model name.  By default, it pluralizes the name for you (by adding “s”), but you can specify a custom plural form if you wish.  See Exposing models over REST for all the details.  
Press Enter to accept the default plural form `(persons)`:
~~~
[?] Custom plural form (used to build REST URL):
~~~
 
Next, you’ll be asked whether you want to create the model on the server only or in the /common directory, where it can potentially be used by both server and client LoopBack APIs.  Keep, the default, common, even though in this application you’ll only be working with server-side models:
 ~~~
? Common model or server only?
❯ common
  server
~~~
Every model has properties.  Right now, you’re going to define one property, “name,” for the person model.  
Select string as the property type (press Enter, since string is the default choice):
 ~~~
Let's add some person properties now.
Enter an empty property name when done.
[?] Property name: name
   invoke   loopback:property
[?] Property type: (Use arrow keys)
❯ string
  number
  boolean
  object
  array
  date
  buffer
  geopoint
  (other)
~~~
End the model creation process by pressing Enter when prompted for the name of the next property.
The model generator will create two files in the application’s common/models directory that define the model: person.jsonand person.js.
Run the application
Start the application by node .:
 ~~~
$ node .
...
Browse your REST API at http://0.0.0.0:3000/explorer
Web server listening at: http://0.0.0.0:3000/
~~~
Open your browser to http://0.0.0.0:3000/ (on some systems, you may need to use http://localhost:3000 instead).  You’ll see the default application response that displays some JSON with some status information; for example:
{"started":"2016-09-10T21:59:47.155Z","uptime":42.054}
Now open your browser to http://0.0.0.0:3000/explorer or http://localhost:3000/explorer.  You’ll see the StrongLoop API Explorer:
 



Through a set of simple steps using LoopBack, you’ve created a `person` model, specified its properties and then exposed it through REST. 

