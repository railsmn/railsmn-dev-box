# A Virtual Machine for Getting Started with Ruby on Rails

__We want to make it easy for you to create Ruby on Rails applications.__

One hurdle we have seen for Rails newcomers is installing and configuring Ruby on Rails on their computers.  This tool sets up of a Ruby on Rails development environment.  Follow the steps below. If you have questions, please feel free to [create an issue (really!)](http://github.com/railsmn/railsmn-dev-box/issues).


## Getting started

### Step 1 - Install stuff  
Install these packages (programs).  

* [Git](http://git-scm.com/) - [downloads page](http://git-scm.com/downloads)
* [VirtualBox](https://www.virtualbox.org) - [downloads page](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](http://vagrantup.com) - [downloads page](http://downloads.vagrantup.com/)


### Step 2 - Build Vagrant Virtual Machine   
In the terminal application,  

    git clone git://github.com/railsmn/railsmn-dev-box.git
    cd railsmn-dev-box
    vagrant up

TODO - what about in Windows?

The aboove commands,   
- download the base Linux image  
- start the Vagrant Virtual Machine  
- take about 3 minutes  


### Step 3 - SSH into Virtual Machine
In the terminal application,  

    vagrant ssh    # NOTE: now you have SSH-ed into the Vagrant Virtual Machine (VM)

    vagrant@rails-dev-box:~$

### Step 4 - Create a Rails app  
Using the same SSH connection from Step 3,  
    
    rails new opencamp -d postgresql  



### Step 4 - Edit the ````database.yml```` file
Use your text editor and open the   ````custom_app/config/databse.yml````  file.  

Change  ````username````  from  ````opencamp````  to  ````vagrant````.  
  
Change  ````encoding````  from  ````unicode````  to  ````SQL_ASCII````.  


### Step 5 - Start the Rails server
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
