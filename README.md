# Polyglot-Jif-Fabric Stack
Installation configurations that work on Mac OSX. 

[TL;DR Skip Down to Installation instructions](https://github.com/K33TY/Polyglot-Jif-Fabric-Stack/blob/master/README.md#prerequisites)

### Information about this Stack

 * [Polyglot](https://www.cs.cornell.edu/projects/polyglot/)
 * [Jif](https://www.cs.cornell.edu/jif/)
 * [Fabric](https://www.cs.cornell.edu/projects/fabric/)

### Installation Backstory

I previously attempted to install this environment on Mac OS Yosemite 10.10.5, but I ran into multiple configuration issues. I could not run Polyglot on the commandline due to [Java Toolprovider](https://docs.oracle.com/javase/7/docs/api/javax/tools/ToolProvider.html) continuously returning null regarding there being a compiler, even when my classpaths and paths were correctly configured and a javac was in the bin directory. I managed to run Polyglot for some reason on Eclipse, but I could not figure out why this was operating differently than from the commandline. However, in attempting to install Jif, Eclipse was no longer recognizing that Polyglot had been built and could access the Toolprovider. 

---

# Install!

## Prerequisites

The current specifications used for this installation. (It is probable that different operating systems and earlier/later versions of Java JDK will work, but I managed with the following settings.)

* Mac OS Sierra 10.12.6
* Oracle Java JDK v 1.8.0_101-b13
* [Apache Ant](http://ant.apache.org/) : Install as per provided instructions

## Edit ~/.bash_profile

This ensures that the necessary environment variables, paths, and classpaths are set (Note, you need to change \<path\> to the actual paths to the respective directories):

```
~/.bash_profile 
export JAVA_HOME=$(/usr/libexec/java_home -v 1.8.0_101)
export ANT_HOME=<path>/apache-ant-1.10.1
export POLYGLOT=<path>/polyglot
export JIF=<path>/jif
export FABRIC=<path>/fabric
export PATH="$PATH:/usr/local/bin:${ANT_HOME}/bin:${POLYGLOT}/bin:${JAVA_HOME}/bin"
export CLASSPATH=${CLASSPATH}:${POLYGLOT}/classes:${POLYGLOT}/bin:${POLYGLOT}/lib/java_cup.jar:${POLYGLOT}/lib/polyglot.jar:${POLYGLOT}/lib/jflex.jar:${JAVA_HOME}
```

## Polyglot

  1. Ensure javac is in your path and that JFlex.jar is in your classpath or in the Polyglot lib directory
  2. cd $POLYGLOT
  3. ant
  4. If you run *jlc*, then you will be able to tell if it is running correctly. (I had no issues once upgrading to Sierra)

## Jif

## Fabric
