# Java Cheat ![logo](logo.png)

Java information and cheatsheets.

1.  [Getting started](getting-started.md)
1.  Code
    1. [Main.java](Main.java): main Java 7 cheat
    1. [HelloWorld.java](HelloWorld.java)
    1. [Binary compatibility](binary-compatibility/)
    1. [ClassNotFoundException](class-not-found/)
    1. [JNI](jni/)
    1. [WatchService](watch-service/)
1.  Introduction
    1.  [Implementations](implementations.md)
        1. [OpenJDK](openjdk.md)
    1.  [Style guides](style-guides.md)
1.  Tools
    1. [java utility](java-utility.md)
    1. [Javadoc](javadoc/)
    1. [javac](javac/)
    1. [JAR](jar.md)
1.  [JVM](jvm.md)
    1. [Bytecode](bytecode/)
1.  Third party
    1. [JUnit](junit/)
    1. [Maven](maven/)
    1. [Tomcat](tomcat.md)
1.  [update-java-alternatives](update-java-alternatives.md)
1.  [Bibliography](bibliography.md)

## WIP

1.  Code
    1. [Java 8](java8/)
    1. [JMX](jmx.md)
1.  Tools
    1. [jconsole](jconsole.md)
    1. [JAVA_HOME](java-home.md)
    1. [JDB](jdb.md)
    1. [javap](javap.md)
1.  Third party
    1. [Spring](spring/)
    1. [Jasmin](jasmin/)
    1. [Java Decompiler](java-decompiler.md)
    1. [Mockito](mockito/)
    1. [Ant](ant.md)
    1. [Formal verification](formal-verification.md)

## Standards

The language and the JVM standards can be found at: <http://docs.oracle.com/javase/specs/> Those only contain the language specification, not the Java Class Library.

Note that they are two separate standards:

- the Java language specification (JLS), which determines on a high level what the language does
- the JVM specification specifies (JVMS), which determines on a lower level how the bytecode is interpreted

### Java Community Process

### JCP

<https://jcp.org>

The Java standard is not completely controlled by Oracle, but maintained by a committee composed of many large organizations: <http://en.wikipedia.org/wiki/Java_Community_Process>

### JSR

### Java Specification Requests

RFC of the JCP. E.g., Servlets are specified in JSR 315: <https://jcp.org/aboutJava/communityprocess/final/jsr315/>

## Documentation

Tutorials: <http://docs.oracle.com/javase/tutorial/> Download them under the downloads section.

Docs: <http://docs.oracle.com/javase/7/docs/> see under the downloads section.

JCL reference: <http://docs.oracle.com/javase/7/docs/api/> TODO: is that official?

## JRE vs JDK

The JVM is included in the Java Runtime Environment (JRE), which also contains things like all the compiled standard library `.class` files. JRE does not contain for example `javac` which is only needed by developers: it is an end user package.

For development, one must have the Java Developer Kit (JDK), which includes things like:

- `javac` which transforms `.java` files into `.class` files,
- `javadoc` which generates HTML documentation from comments. JDK also includes the JRE.

Java was present in LSB, but got removed from LSB 4.1 because of licensing issues. [Source](http://www.h-online.com/open/news/item/Java-removed-from-Linux-Standard-Base-4-1-1205368.html).

### JCL

Java Class Library.

<http://en.wikipedia.org/wiki/Java_Class_Library>

Name of the stdlib `.class` implementation. Present in the JRE.

## Editions

Java comes different forms for different applications.

Both the libraries and the JVM change between those implementations.

- SE: standard edition. Intended for for personal desktops / laptops.
- EE
- ME: micro edition. For portable devices such as cell phones.

Each of those has their own implementations. Oracle implements all.

Source: <http://stackoverflow.com/questions/2857376/difference-between-java-se-ee-me>

### EE

Contains "Enterprise" APIs, which is a generic term for APIs mostly useful for large enterprises.

<http://stackoverflow.com/questions/106820/what-is-java-ee>

Sources:

- <http://stackoverflow.com/questions/3821640/what-is-difference-between-tomcat-and-jboss-and-glassfish>
- <http://stackoverflow.com/questions/23563340/glassfish-vs-tomcat>
- <http://stackoverflow.com/questions/327793/how-would-you-compare-apache-tomcat-glassfish-as-production-servers>

Implementations include:

- GlassFish
- TomEE
- WildFly (old JBoss)
- IBM Websphere
- Oracle Weblogic

#### Tomcat

Apache Tomcat implements only JavaServer Pages and Servlets, which are only a part of the full EE.

#### Jetty

<http://eclipse.org/jetty/>

Like Tomcat, an implementation of Servlets.

Seems to be easier to deploy than Tomcat, and specially good as a development server.

<http://stackoverflow.com/questions/302977/tomcat-vs-jetty>

#### GlassFish

GlassFish is the reference implementation of many parts of the API, but not all. [This table](https://java.net/projects/javaee-spec/pages/Specifications) summarizes reference implementations.

For example, [GlassFish is the reference for Servlets](https://jcp.org/aboutJava/communityprocess/final/jsr315/), but not for JSONP.

It is open source, started by Sun, and sponsored by Oracle.

Oracle has dropped support for it in 2013 in favor of it's Oracle Weblogic, but it still is the reference implementation. TODO does it still support?

#### WildFly

#### JBoss

JBoss, now renamed as WildFly is another open source EE implementation <http://en.wikipedia.org/wiki/WildFly> TODO why another? Maintained by RedHat.

## Versions

1.7 is commonly referred to as Java 7, 1.8 as Java 8 and so on.

Java 8 was released in March 2014.

You can get version with:

    java -version
    javac -version

Sample output:

    1.8.0-ea

More verbose version:

    java -fullversion
    javac -fullversion

Sample output:

    1.8.0-ea-b97

You can switch between multiple Java versions on a single machine with `update-java-alternatives`.

### Project coin

Project that decided which proposed language extensions should or not be added to Java 7: <https://blogs.oracle.com/darcy/entry/project_coin_final_five>

### J2SE

Old name used for Java between versions 1.2 and 1.5.

The 2 was from the 1.2 which introduced major changes.

## Classpath

<http://en.wikipedia.org/wiki/Classpath_%28Java%29>

Where Java will look for user defined classes.

Command line option:

    javac -classpath /some/path

Environment variable:

    export CLASSPATH=/some/path
