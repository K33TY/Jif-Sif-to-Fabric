# Installing Sif on Mac OSX

Below I have provided the Sif 1.0.3 distribution's read me file, and my experience following this on MacOSX:

### READ ME

```
            SIF: Servlet Information Flow
            -----------------------------

SIF (Servlet Information Flow) is a novel software framework for
building high-assurance web applications, using language-based
information-flow control to enforce security. Explicit, end-to-end
confidentiality and integrity policies can be given either as
compile-time program annotations, or as run-time user requirements.
Compile-time and run-time checking efficiently enforce these policies.

The design, including the trust assumptions, of SIF are described in
the 2007 paper "SIF: Enforcing Confidentiality and Integrity inWeb
Applications", published in the Proceedings of the 16th USENIX
Security Symposium, August 2007, by Stephen Chong, K. Vikram, and
Andrew C. Myers.

Since you are reading this file, you have already downloaded and unpacked
the SIF distribution.  Your installation directory contains the following
sub-directories:

  - src:      the complete source code of the SIF framework
  - lib:      needed JAR files
  - examples: several example SIF web applications
  - sig-src:  Jif signatures for SIF classes
  
In addition a version of the Jif compiler is included 
in this release: jif-3.1.1.zip. The compiler must be
installed if you want to compile SIF web applications.


Installing
----------

To run SIF web applications, you require a Java Servlet
container. This distribution assumes that Apache Tomcat is used. To
some of the example web applications, you will also require a MySQL
database.

To install the SIF framework, the Tomcat installation directory must
be set. This can either be done by setting the environment variable
$CATALINA_HOME, or by editing the file config.properties found in this
directory.

In order to run SIF servlets, appropriate class files and jars must be
copied to the Tomcat installation directory.

1. Jif class files

   In the Jif installation directory, build the jar files by executing
   "ant jar". This produces the following jar files:
        $JIF/lib/jif.jar
        $JIF/lib/jifsig.jar
        $JIF/lib/jiflib.jar
        $JIF/lib/jifrt.jar

    Move the files jif.jar, jiflib.jar and jifrt.jar (but not
    jifsig.jar!) to the directory $CATALINA_HOME/shared/lib:

       cp $JIF/lib/jif{,lib,rt}.jar $CATALINA_HOME/shared/lib
    
    On Windows:    
    Move the Jif runtime shared library file ($JIF/lib/jifrt.dll on
    Windows platforms) to $CATALINA_HOME/bin, or set the PATH variable
    to include the directory $JIF/lib.

    On Unix/Linux:
    Set the LD_LIBRARY_PATH environment variable to include the
    directory "$JIF/lib", which is where the runtime shared library
    file libjifrt.so is located. Note that this environment variable
    must be exported so that it is visible to the Tomcat web server:

      setenv LD_LIBRARY_PATH ${LD_LIBRARY_PATH}:$JIF/lib
    
 2. Third party jar files

    Several jar files are needed to run SIF web applications. In
    particular, two Jakarta Commons jar files are needed: FileUpload
    and IO. Both are available for download from
    http://jakarta.apache.org/commons. After downloading these files,
    they may either by placed directly in $CATALINA_HOME/shared/lib,
    or placed in SIF's lib directory, whereupon they will be copied to
    $CATALINA_HOME/shared/lib when "ant install-quick" is executed.

    Also, if a MySQL database is needed (as in some of the example web
    applications), a MySQL Java connector will be needed, available
    for download from http://www.mysql.com/products/connector/j. This
    file may either by placed directly in $CATALINA_HOME/shared/lib,
    or placed in SIF's lib directory, whereupon it will be copied to
    $CATALINA_HOME/shared/lib when "ant install-quick" is executed.

 3. SIF class files and needed jar files

    The SIF class files can be automatically installed into the Tomcat
    installation directory by executing "ant install-quick". This
    copies the class files to the directory
    $CATALINA_HOME/shared/classes, and also copies files from the lib
    directory to $CATALINA_HOME/shared/lib.
    
 4. SIF servlet class files

    All the SIF examples in this distribution can be automatically
    installed into the Tomcat installation directory by executing "ant
    install-all".  Alternatively, a specific example servlet can be
    installed by changing the working directory to the example servlet
    directory (e.g., examples/hello) and executing "ant install". This
    copies the appropriate class files and other resources (e.g.,
    web.xml) to the directory $CATALINA_HOME/webapps/<example-name>.
    
After these files have been installed, Tomcat can be started, and the
SIF servlets accessed at the appropriate URL (for example,
"http://localhost:8080/hello").


Compiling the SIF Framework
---------------------------

To compile the SIF framework, you require Apache Ant (available from
http://ant.apache.org), and the Jif 3.1 compiler (included in this
distribution, as the file jif-3.1.1.zip). If needed, please unpack
and install the Jif 3.1 compiler.

Before compiling the SIF framework, the installation directories of
Jif and Tomcat must be set. This can either be done by setting the
environment variables $JIF and $CATALINA_HOME, or by editing the file
config.properties found in this directory.

The J2EE servlet API jar file must be in the class path. This can be found
in $CATALINA_HOME/common/lib:

  setenv CLASSPATH ${CLASSPATH}:$CATALINA_HOME/common/lib/servlet-api.jar

The Jakarta Commons FileUpdate and IO jars must also be on the class
path, or in the lib directory. Details of where they can be downloaded
from are given above.

To compile the SIF framework, execute

  ant all


Compiling SIF Web Applications
------------------------------

To compile a web application written in Jif that relies on the SIF
framework, you require the Jif 3.1 compiler (available from
http://www.cs.cornell.edu/jif).

The J2EE servlet API jar file must be in the class path. This can be found
in $CATALINA_HOME/common/lib:

  setenv CLASSPATH ${CLASSPATH}:$CATALINA_HOME/common/lib/servlet-api.jar

The Jakarta Commons FileUpdate and IO jars must also be on the class
path. Details of where they can be downloaded from are given above.

The SIF signature classes must be added to the signature
classpath. The signature classes can be found in $SIF/lib/sifsig.jar,
or, if you have compiled SIF, in $SIF/sig-classes. The signature
classes can be most easily added to the signature classpath by
specifying the -addsigcp option to the Jif compiler. The SIF classes,
found in $SIF/lib/sif.jar and $SIF/classes, must also be on the
classpath.

Thus, to compile a web application, the compilation command may look like

  $JIF/bin/jifc -addsigcp $SIF/lib/sifsig.jar \
     -cp "$SIF/lib/sif.jar:$CLASSPATH" MyApp.jif


Notes for developing SIF Web apps
---------------------------------

1. In sublasses of Servlet, no code in field initializers or
   constructors will be executed, due to the fact that Tomcat is
   responsible for creating the Servlet, and Tomcat does not follow
   the Jif conventions for constructing Jif objects (i.e., it doesn't
   call the appropriate translation of the constructor).
```

### Issues

    1. After installing Tomcat, which is a prerequisite for Sif,  I followed the steps of creating the necessary jars for JIF as per the read me. However, there was no "/shared/lib" folder off of my Tomcat directory. There was only a "/lib" directory. I was not sure whether to create said directory or simply copy the necessary files into the "/lib" directory. 
    Another issue I had dealt with the fact that setenv is not actually a command that can be run on MacOSX. Instead, I followed the procedure I used to set environment variables for the other applications I had previously installed by editing ~/.bash_profile, making it contain `export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:$JIF/lib`
