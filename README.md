# A Virtual Machine for Getting Started with Ruby on Rails

__We want to make it easy for you to create Ruby on Rails applications.__

One hurdle we have seen for Rails newcomers is installing and configuring Ruby on Rails on their computers.  This tool sets up of a Ruby on Rails development environment.  Follow the steps below. If you have questions, please feel free to [create an issue (really!)](http://github.com/railsmn/railsmn-dev-box/issues).


## Getting started

### Step 1 - Install stuff  
Install 3 packages (programs).  

* [Git](http://git-scm.com/) - [downloads page](http://git-scm.com/downloads)  
  + choose Operating System specific package  

* [VirtualBox](https://www.virtualbox.org) - [downloads page](https://www.virtualbox.org/wiki/Downloads)  
  + click on system specific link under "VirtualBox platform packages"  

* [Vagrant](http://vagrantup.com) - [downloads page](http://downloads.vagrantup.com/)  
  + click on latest edition  
  + choose Operating specific package  


### Step 2 - Build Vagrant Virtual Machine   
**Windows Users: Go directly to step 2b**

In the terminal application,  

    git clone git://github.com/railsmn/railsmn-dev-box.git
    cd railsmn-dev-box
    vagrant up

#### Step 2b - Windows Users Only:
If you would like to have access to the open_camp project files *outside* of your Vagrant box (ie: to use your favorite text editor on Windows - like Notepad++ or similar) follow these steps before running the 'vagrant up' command.

1.	Create a folder on your Windows computer (typically in the Desktop or 'My Documents' directory) - your open_camp project will be accessible from here.
2.	In your GithubUI application, clone the repository available at git://github.com/railsmn/railsmn-dev-box.git - see http://windows.github.com/help.html for more info on how to do this.	
3.	Once downloaded, open the 'railsmn-dev-box' folder on your computer, using File Explorer.
4.	Now, go back to the folder you created in Step 1, and copy the [FULL PATH](http://technet.microsoft.com/en-us/magazine/ff678296.aspx)
5.	Next, we want to edit the 'Vagrantfile' file. Open it with your favorite text editor, and edit the line that reads: ```config.vm.share_folder "open_camp_directory", "/home/vagrant/open_camp", "**Windows Folder Path**"```

	Replace the 'Windows Folder Path' text with the FULL PATH that you copied in Step 4.

	**IMPORTANT:** Windows will, by default, paste something like this ```"C:\Users\Mo\Desktop\open_camp_folder"``` Make sure that you change out the backwards slashes, and replace them with forward slashes. The end result should look something like this:
	```config.vm.share_folder "open_camp_directory", "/home/vagrant/open_camp", "C:/Users/Mo/Desktop/open_camp_folder"```
6. 	In your Git Shell (ie: Start -> Applications -> Github -> Git Shell), CD into the directory from Step 2 (ie: Where the ```Vagrantfile``` exists). 
7.	Run the ```vagrant up``` command.
* 	More information about this process is available on the [Vagrant project's website](http://docs-v1.vagrantup.com/v1/docs/config/vm/share_folder.html)

### Step 2 (all users) continued
The above commands,   
- Download the base Linux image  
- Create and start the Vagrant Virtual Machine  
- Can take anywhere from 3-45 minutes, depending on your machine and internet connection.  

### Step 3 - SSH into Virtual Machine
In the terminal application,  

    vagrant ssh    # NOTE: now you have SSH-ed into the Vagrant Virtual Machine (VM)

    vagrant@rails-dev-box:~$

### Step 4 - Create a Rails app  
Using the same SSH connection from Step 3,  
    
    rails new open_camp -d postgresql  
    cd open_camp


### Step 5 - Edit the ````database.yml```` file
Use your text editor and open the   ````open_camp/config/databse.yml````  file.  

Change  ````username````  from  ````open_camp````  to  ````vagrant````.  
  
Change  ````encoding````  from  ````unicode````  to  ````SQL_ASCII````.  

Make sure you do this for both the Development and Test databases.  


### Step 6 - Start the Rails server
Using the same SSH connection from Step 4,   

```
rake db:create
```

```
rails server
```

Open your browser and go to [localhost:3000](http://localhost:3000).  


## What's In The Box

* Git
* RVM
* Ruby 2.0.0 (binary RVM install)
* Bundler
* SQLite3, MySQL, and Postgres
* System dependencies for nokogiri, sqlite3, mysql, mysql2, and pg
* Databases and users needed to run the Active Record test suite
* Node.js for the asset pipeline
* Memcached



## Virtual Machine Management

To __exit__ SSH connection to Vagrant Virtual Machine, 

    exit        # option 1

    # press ^D  # option 2


To __suspend__ virtual machine,  
    
    # from your computer

    vagrant suspend


To __resume__ virtual machine,  
    
    # from your computer

    vagrant resume


To __shutdown/halt__ virtual machine,  
    
    # from your computer 

    vagrant halt


To __resume__ virtual machine,  

   # from your computer  

   vagrant up


To get __status__ of virtual machine,  

    # from your computer

    vagrant status


To completely delete virtual machine,  

    # from your computer

    vagrant destroy   # DANGER: all is gone


Please check the [Vagrant documentation](http://vagrantup.com/v1/docs/index.html) for more information on Vagrant.


## Credits 

This is a renamed fork of [rails-dev-box](https://github.com/rails/rails-dev-box). Big Thanks to [Xavier Noria](https://github.com/fxn) and other contributors for their efforts. You guys rock. Thanks!
