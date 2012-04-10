Quick WP Install
----------------

Quick WP Install is a program that quickly sets up a throwaway copy of WordPress. These sites are meant to be cheap fast installations to tinker on, etc. Do not use for production sites or for anything important.

### Installation

To install on OSX, run the following commands in terminal:

    git clone git://github.com/johnpbloch/quick-wp-install.git ~/quick-wp-install
    mkdir ~/bin
    ln -fs ~/quick-wp-install/quick-wp ~/bin/quick-wp
    ln -fs ~/quick-wp-install/delete-quick-wp ~/bin/delete-quick-wp

You need to make sure `$HOME/bin` is in your environment's `PATH` variable. An easy way to do this is to add `PATH="$PATH:$HOME/bin"` to your `.bash_profile` or `.bashrc` file.

You'll need WP-CLI installed as well, which you can find [on Github](https://github.com/wp-cli/wp-cli).

You'll also need a MySQL database called `test` and a user named `test` with a password '`test`' that has all privileges on the `test` database.

### Use

To install a fresh WordPress installation using the default settings, simply type

    quick-wp

The installation program also has a few command line arguments:

    --path    The filesystem path in which to install WordPress
              Paths do not need to be absolute, and also supports
              a tilde (~) to signify the current user's home.
    
    --url     The url from which this WordPress installation will
              be accessible.
    
    --name    The site name of the new site.
    
    --slug    May be used to customize both path and url partially.
              If provided, the slug will be used to name the folder
              used (~/Sites/<slug>) as well as the URL
              (http://localhost/<slug>). A sequence of three pound
              signs (###) will be replaced by the site's id number.
              The default slug is 'qt###'.

To remove a WordPress installation, use the command

    delete-quick-wp <id>

The id should be an integer specifying the site id from the installation program's database table. Alternatively, you can use the --all flag to delete all instances of your quick-wp sites.

#### License

GPLv2


--------------------------------

Also, I'm really sorry about the bad code... improvements coming... I hope.
