Citrus samples ![Logo][1]
==============

Sample applications
---------

The Citrus samples applications try to demonstrate how Citrus works in
different integration test scenarios. The projects are executable with Maven
or ANT and should give you a detailed picture how Citrus testing works.

In the reference documentation you can also find detailed descriptions of the sample
applications.

Preconditions
---------

See the preconditions for using the Citrus sample applications:

* Java 1.6 or higher
Installed JDK 1.6 or higher plus JAVA_HOME environment variable set
up and pointing to your Java installation directory

* Apache Maven 3.0.x or higher
The sample projects are executable via Apache Maven (http://maven.apache.org/). You need
ANT installed and running an your machine in order to use this way of executing the
sample applications.

* Apache ANT 1.8.x or higher
The sample projects are executable via Apache ANT (http://ant.apache.org/). You need
ANT installed and running an your machine in order to use this way of executing the
sample applications.

In each of the samples folders you will find the Maven pom.xml and ANT executable build script (build.xml) files.

Development
---------
If you want to compile and build the citrus-samples locally you need to also have the latest SNAPSHOT version of Citrus core [repo][4] built on that machine. This is because the samples
reference the latest SNAPSHOT versions of Citrus. Just clone and build and install the Citrus core [repo][4] locally before doing so with the citrus-samples.

Overview
---------

The Citrus samples section contains following projects:

* FlightBooking (/flightbooking)
* Greeting (/greeting)
* BookStore (/bookstore)
* Incident (/incident)
* Camel News (/camel-news)
* Java EE (/javaee)

The projects cover following message transports and technologies:

| Transport          | JMS | Http | SOAP | Channel | Camel | Arquillian | JDBC | SYNC | ASYNC |
|--------------------|:---:|:----:|:----:|:-------:|:-----:|:----------:|:----:|:----:|:-----:|
| FlightBooking      |  X  |  X   |      |         |       |            |  X   |      |   X   |
| Greeting           |  X  |      |      |    X    |       |            |      |  X   |   X   |
| BookStore          |  X  |      |  X   |         |       |            |      |  X   |       |
| Incident           |  X  |  X   |  X   |         |       |            |      |  X   |   X   |
| Camel News         |     |      |      |         |   X   |            |      |      |       |
| Java EE            |  X  |  X   |      |         |       |     X      |      |  X   |   X   |

Pick your sample application for try out and got to the respective folder.

Running the samples
---------

All samples hold a web application project (war folder) and a Citrus test project (citrus-test). First of all start
the sample application within the war folder. You can do this either by calling "mvn jetty:run" command using an
embedded Jetty Web Server Container or you call "mvn package" and deploy the resulting war archive to a separate
Web container of your choice.

Once the sample application is deployed and running you can execute the Citrus test cases in citrus-test folder.
Open a separate command line terminal and navigate to the citrus-test folder.

Execute all Citrus tests by calling "mvn integration-test". You can also pick a single test by calling "mvn integration-test -Dtest=TestName".
You should see Citrus performing several tests with lots of debugging output in both terminals (sample application server
and Citrus test client). And of course green tests at the very end of the build.

You can also use Apache ANT to execute the tests. Run the following command to see which targets are offered:

> ant -p

Buildfile: build.xml

Main targets:

citrus.run.single.test  Runs a single test by name
citrus.run.tests        Runs all Citrus tests
create.test             Creates a new empty test case
Default target: citrus.run.tests

The different targets are not very difficult to understand. You can run all tests, a single test case by its name or create
new test cases.

Just try to call the different options like this:

> ant citrus.run.tests

Information
---------

For more information on Citrus see [www.citrusframework.org][2], including
a complete [reference manual][3].

 [1]: http://www.citrusframework.org/images/brand_logo.png "Citrus"
 [2]: http://www.citrusframework.org
 [3]: http://www.citrusframework.org/reference/html/
 [4]: https://github.com/christophd/citrus
