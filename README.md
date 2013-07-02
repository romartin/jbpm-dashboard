Teiid Dashboard Builder
=======================

jBPM Dashboard Builder is a web application for the visual composition of dashboards. A dashboard is composed by a set of
 business indicators (aka Key Performance Indicators) which are feed from data coming from heterogeneous sources of information
like databases or CSV files.

The project itself is a customization of the [Dashboard Builder](https://github.com/droolsjbpm/dashboard-builder) project.
This customization has the following goals in mind:

* To replace the whole tooling look&feel with jBPM's branding.
* To offer a tight integration between Dashbuilder and jBPM at the data connectivity layer.

If you discover pitfalls, tips and tricks not described in this document,
please update it using the [markdown syntax](http://daringfireball.net/projects/markdown/syntax).


Building the project
--------------------

If you want to build the project please, proceed as indicated:

1. Prerequisites:

  This guide assumes you have Java JDK 1.6 (set as JAVA_HOME), and Maven 3.0.4+ (set as MAVEN_HOME) in your system.
  The <code>java</code> and <code>mvn</code> commands must be added to the executable's path as well.

2. Open a terminal window, go to the project root directory and type the following command:

        $ mvn clean install -Dfull -DskipTests

  This command compiles, builds and runs the application. It'll last a few minutes (but only for the first time) because
  the maven build process needs to download a lot of third-party libraries.


Quickstart Demo
-------------------

To execute a quick demo, first see "Building the project", the proceed as indicated:

1. Go to the <code>builder/target</code> directory and unzip the teiid-dashbuilder-demo-installer.zip file to
  a given directory (the [target_directory]). You should get a directory structure like this:

         [target_directory]/jbpm-dashboard-demo
                              README.md
                              start-demo.sh
                              realm.properties
                              /db
                              /log

2. Open a command window and execute the <code>start-demo.sh</code> script:

        $ cd [target_directory]/jbpm-dashbuilder-demo
        $ sh start-demo.sh

  NOTE: The application uses an auto-deployable embedded H2 database which it's automatically created when you start
  the app for the very first time. The database initialization procedure takes a few minutes. Furthermore, you should
  take into account that the H2 database downgrades the application performance compared with other databases like
  PostgreSQL, MySQL, which are normally used in production environments.

3. Once the application is started, open a browser and type the URL: <code>http://localhost:8080/jbpm-dashboard</code>.
The following user/password are available by default:

     <code>root/root</code>: to sign-in as the superuser     
     <code>demo/demo</code>: to sign-in as an end user

  On start-up, the application installs automatically some ready-to-use sample dashboards, for demo and learning purposes.

  To stop the application close the terminal window or type the "Ctrl + C" command.

4. Application database

The application database will be generated automatically when you start the application for the first time.
If you want to restore the application to its initial state you can:

* Stop the application (if running).
* Delete the database files in the <code>/db</code> directory.
* Re-Start the application.

JBoss Application Server
-------------------------

To deploy the dashbuilder war to a JBoss Application Server, please, take a look at the following guide 
[builder/README.md](https://github.com/droolsjbpm/jbpm-dashboard/blob/master/builder/README.md).


