Hadoop, Web and other Unix Tools [![Build Status](https://travis-ci.org/harisekhon/toolbox.svg?branch=master)](https://travis-ci.org/harisekhon/toolbox)
================================

A few of the Hadoop, Web and other nifty tools I've written over the years that are generally useful across environments. All programs have --help to list the available options.

For many more tools, see the Advanced Nagios Plugins Collection which contains many Hadoop, NoSQL, Web and infrastructure monitoring cli programs that integrate with Nagios - https://github.com/harisekhon/nagios-plugins.

### Setup ###

The 'make' command will initialize my library submodule and  use 'sudo' to install the required CPAN modules:

```
git clone https://github.com/harisekhon/toolbox
cd toolbox
make
```

#### OR: Manual Setup ####

Enter the toolbox directory and run git submodule init and git submodule update to fetch my library repo and then install the CPAN modules as mentioned further down:

```
git clone https://github.com/harisekhon/toolbox
cd toolbox
git submodule init
git submodule update
```

Then proceed to install the CPAN modules below by hand.

###### CPAN Modules ######

Install the following CPAN modules using the cpan command, use sudo if you're not root:

```
sudo cpan LWP::Simple LWP::UserAgent Text::Unidecode Time::HiRes XML::Validate
```

You're now ready to use these programs.


### Jython for Hadoop Utils ###

A couple of the Hadoop utilities listed below require Jython (as well as Hadoop to be installed and correctly configured or course)

```
hadoop_hdfs_time_block_reads.jy
hadoop_hdfs_files_native_checksums.jy
hadoop_hdfs_files_stats.jy
```

Jython is a simple download and unpack and can be fetched from http://www.jython.org/downloads.html

Then add the Jython untarred directory to the $PATH or specify the /path/to/jython_dir/bin/jython explicitly:

```
/path/to/jython-x.y.z/bin/jython -J-cp `hadoop classpath` hadoop_hdfs_time_block_reads.jy --help
```

The ```-J-cp `hadoop classpath` ``` bit does the right thing in finding the Hadoop java classes required to use the Hadoop APIs.
