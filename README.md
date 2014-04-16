Buildoop: Hadoop Ecosystem Builder
==================================

The Hadoop Ecosystem Builder -Buildoop- provides interoperable tools, metadata, 
and processes that enable the rapid, repeatable development of a Linux
Hadoop based system.

With Buildoop you can build a complete set of Hadoop ecosystem components based
on RPM or DEB packages, make integration tests for this tools on a RedHat/CentOS,
or Debian/Ubuntu virtual system, and maintain a set of configuration files for
baremetal deployment.

Fundations
----------
The Buildoop is splitted in the following fundations:

1. A main command line program for metadata operations: **buildoop**.
2. A set of **recipes**: The metadata for package and tools building.
3. A set of system integration tests: **SIT framework**.
4. A central repository for **baremetal deployment** configuration.

Technology
----------
From the technology point of view Buildoop is based on:

1. Command line "buildoop" based on **Groovy**.
2. Packaging recipes based on **JSON**.
3. SIT Framework: based on Groovy test scripts, and **Vagrant** for
   virtual development enviroment.
4. Set of **Kickstart**, **Cheff** and **Puppet** files for baremetal deployment.

Folder scheme
-------------

* buildoop:
	Main folder for Buildoop main controler.
	
* conf:
	Buildoop configuration folder, BOM definitions, targets definitions.
	
* deploy:
	Folder for deploy in VM and Baremetal systems. Based on Puppet and Chef.
	
* sit:
	System Integration Testing tests for VM pseudo-cluster system.
	
* recipes:
	Download, build and packaging recipes.
	
* toolchain:
	Tools for cross-compiling for diferent targets.

Read More
---------

http://buildoop.github.io/


GitHub projects forked in Buildoop
----------------------------------

The https://github.com/buildoop project contains a set of
GitHub projects forked from other authors. This forks are 
used by Buildoop in order to make relevant packages in the 
ecosystem.

The list of forked porjects are:

| Recipe Name    | Desc                         | Forked From |
| -------------  |:---------------------------- |:------------|
| Camus          | Kafka Camus is LinkedIn's Kafka HDFS pipeline | Marcelo Valle https://github.com/mvalleavila |
| flume-ng-kafka-sink | Flume to Kafka Sink  | Marcelo Valle https://github.com/mvalleavila/flume-ng-kafka-sink |

- flume-ng-kafka-sink -

	Flume to Kafka Sink fork from Marcelo Valle.

- storm-kafka-0.8-plus -

	Storm Spout for Kafka fork from Thomas Becker (https://github.com/wurstmeister)

- Storm-0.9.1-Kafka-0.8-Test -

	Storm Spout for Kafka fork from Marcelo Valle. The original code is
	patched by Marcelo Valle.

- storm-hbase -

	Storm to HBase connector fork from P. Taylor Goetz (Hortonworks)
	
Pull request flow
------------------

Clone the repository from your project fork:

$ git clone https://github.com/buildoop/buildoop.git

The clone has as active branch the "development branch"

$ git branch
* development

Yo have to make your changes in the "development branch".

$ git add .

$ git commit -m "...."

$ git push origin

When you are ready to purpose a change to the original repository, you have
to use the "Pull Request" button from GitHub interface.

The point is the pull request have to go to the "development branch" so the pull
request revisor can check the change, pull to original "development branch", and 
the last step is to push this "development pull request" to the "master branch".

So the project has two branches:

1. The "master branch": The deployable branch, only hard tested code and ready to use.
2. The "development branch": Where the work is made and where the pull request has to make.


Roadmap
-------

| Feature        | Desc           | State  |
| -------------  |:-------------- | :-----:|
| Core Engine |Core building engine | Done |
| POM versioning | Simple BOM multi-versioning | Done |
| Git repsotory | Download sources from GIT | Done |
| Svn repsotory | Download sources from Subversion | Pending |
| Code refactoring | More elegant code | Forever Pending |
| Cross-Architecture | Cross build from different distributions | Pending |
| DEB Support | Debian/Ubuntu Support | Pending |
| Layers      | Add/Modify features without modify the core folders | Pending |
| SIT | System Integration Tests  |  Pending |

--
Javi Roman <javiroman@redoop.org>
