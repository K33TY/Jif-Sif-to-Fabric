This file is a timeline of necessary steps of work as of October 9th. 
More was done prior to this date, but I have not recorded actions.

## Jump to a specific date

 * Aug 22-Sep 6
   * Researching, reading about Fabric
 * [Sep 6-24](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#september-6-24)
   * Fighting with setting up the environment on my Mac (or getting Ubuntu on Parallels to stop being so annoying)
   * Wasted some time trying to Dockerize the Polyglot-Jif-Sif-Fabric Stack
 * Sep 25
   * Created git repository.
   * Begin [documentation](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Polyglot-Jif-Fabric-Stack.md) regarding how to to install the stack needed for Fabric (Ant/Polyglot/Jif/Fabric), specifically because of issues on Mac OSX
 * [Oct 2](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Sif-On-MacOSX.md)
   * Documentation for SIF on a Mac
 * [Oct 9](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-9)
   * Manage to get the Calendar app "sort of" working.
 * [Oct 10](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-10)
   * Requested for meetLbl method in LabelUtil because could not find it in the source code.
   * Reformat significant portions of the code to make it more human readable.
 * [Oct 11](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-11)
   * Began Git Log file.
   * Recompile Jif with meetLbl method.
   * Investigated capabilities of the Jif-Sif Calendar Application.
 * [Oct 12](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-12)
   * Reading about Java servelets since I have no prior experience with using them.
 * Oct 13-19 
   * Other class projects and midterms week
 * [Oct 20](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-20)
   * Creating attack plan.
 * [Oct 21](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-21)
   * Trying to understand Fabric infrastructure.
   * Restore the missing color changing functionality in the SIF version so that I can at least see what it does.
 * [Oct 22](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-22)
   * Started a base directory for my implementation for fabric repo, and trying to decide application architecture.
 * [Oct 23-25](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-23-25)
   * Identify some other tasks that need to be done.
   * Updated documentation to include stuff I found documented in a Word file, but it was missing a few days because of a weird crash after I upgraded to Sierra (should have saved the file instead of leaving it open in another workspace), which is part of why I started using Git instead.
   * Think about a lot of questions regarding Fabric, specifically relating to calendar.
 * [Oct 26](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-26)
   * Trying every single Fabric example and looking at the type of files in each directory.
   * Trying to better understand how the signatures in the java classes work.
   * Adding to other repo holding [calendar codebase](https://github.com/K33TY/Fabric-Calendar)
 * [Oct 27](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-27)
   * Discover Doxygen, using it to sift through Fabric codebase
   * Discover about Pastry for dissemination
 * [Oct 28-31](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-28-31)
   * Restructure architecture of calendar application
   * Investigate how persistence works (using Berkeley DB)
 * Oct 31-Nov 3 
   * [External Documentation for Calendar](https://k33ty.github.io/Fabric-Calendar/)
   * Reading through more of the Java implementation of the Fabric Language
 * [Nov 4-5](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#november-4-5)
   * Discover important directories in the Fabric Language which will be useful for using the language
   * Trying to figure out what the hardcoded variables might be in the Fabric java classes in the examples
 * [Nov 6](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#november-6)
   * Learn about closures
 * [Nov 7](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#november-7)
   * Spend time learning from Tom
 * [Nov 9-12](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#november-9-12)
   * Exploring Fabric language classes and example files more
 * [Nov 13](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#november-13)
   * Look at Jif Calendar again
   * Look at Sif `.fab` files
 * [Nov 14](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#november-14)
   * Working on build.xml file
   * Trying to compile project
   * Trying to add to fabric.util
 * [Nov 15-16](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#november-15-16)
   * Work on architecture
   * Writing methods
   
## Jump to TODO List or Finished Task List.

I have created a [TODO list](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#list-of-todos) which I will add tasks that I need to remember to do later. Once I am done with any of these tasks (or decide that it is not something I should focus on anymore), I will move it to the [Finished Task List](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#finished-tasks).

## Adding to Calendar Codebase Repo ##
[Calendar](https://github.com/K33TY/Fabric-Calendar)
 
-------------

## September 6-24
**Fighting to get the environment set up.** 

I had a lot of issues with installing Polyglot.

Originally, my specifications were:
  + OSX 10.10.5
  + Java JDK 8u111
  
I managed to get Ant installed quite easily, however I kept encountering issues with Polyglot:

```
Obit:polyglot Elizabeth$ jlc
Exception in thread "main" java.lang.ExceptionInInitializerError
Caused by: polyglot.util.InternalCompilerError: Java compiler not found.  Does java that runs Polyglot have javac along with it?
	at polyglot.main.Main.javaCompiler(Main.java:85)
	at polyglot.main.Main.<clinit>(Main.java:74)
```

However, the path seemed correct:

```
Obit:polyglot Elizabeth$ echo $JAVA_HOME
/Library/Java/JavaVirtualMachines/jdk1.8.0_144.jdk/Contents/Home
```

I double checked that the javac executable existed in this path by navigating through the directory structure. It did.

After investigating Polyglot’s github repo, I found that Java is calling the getSystemJavaCompiler() method from ToolProvider.

I decided to uninstall and reinstall my JRE and JDK (because they were not the same version), and updated both to the most recent release: 8u144.

However, this was to no avail and I continued scouring Stackoverflow articles and forums for a solution, but nothing I tried seemed to fix this.

I managed to get stack installed on Ubuntu, but I was extremely annoyed with this set up. There were issues with Ubuntu on Parallels randomly crashing and all the hotkeys from the MacOSX overriding the Linux hotkeys.

Tried a lot of things trying to get the environment working on the Mac. Installing packages through Homebrew, uninstalling and reinstalling different versions of java JRE and JDK.

I had verified with Yizhou that I have essentially set up Polyglot in the same way, except that I was using Java 8u111 and 8u144, and he has Java 8u101. I tried using that version, but it still had issues, so I decided to try an even older version of Java to see what would happen. I tried downgrading Java 1.7, but this broke Ant.

This is the environment variables that I set on my Mac by editing ~/.bash_profile
```
export JAVA_HOME=$(/usr/libexec/java_home -v 1.8.0_101)
export ANT_HOME=/Users/Elizabeth/Desktop/MEng_Project/apache-ant-1.10.1
export POLYGLOT=/Users/Elizabeth/Desktop/MEng_Project/polyglot
export PATH="$PATH:${ANT_HOME}/bin:${POLYGLOT}/bin:${JAVA_HOME}/bin"
export CLASSPATH=${CLASSPATH}:${POLYGLOT}/classes:${POLYGLOT}/bin:${POLYGLOT}/lib/java_cup.jar:${POLYGLOT}/lib/jflex.jar:${JAVA_HOME}
```

**Looked at SIF Calendar**

I downloaded SIF to take a look at the example implementation of the calendar. The structure of this code initially seemed familiar when I had only clicked the java file from the src-java directory. However, as I continued to drill down into other folders, I started to get progressively more confused. One majorly bewildering occurrence dealt with the “String jlc$ClassType$jif” and the peculiar hashes that seemed to follow. Luckily, I found an explanation in SIF: Enforcing Confidentiality and Integrity in Web Applications:

> SIF is implemented in about 4040 non-comment, non-blank lines of Java code. An additional 960 lines of Jif code provide signatures for the Java classes that web applications interact with. Jif signatures provide security annotations for Java classes, and expose only a subset of the actual methods and fields to clients. SIF web applications are compiled against the Jif signatures, but linked at run time against the Java classes. Some Java Servlet framework functionality makes reasoning about information security infeasible. Using signatures and wrapper classes, SIF necessarily limits access to this functionality, but without preventing implementation of full-fledged web applications. 
> 
> (Chon, Vikram, and Meyers, 2)

**Random notes**

This

Runtime labels vs. compile time labels. JIF doesn’t allow compile time labels.

Computing labels is expensive because it deals with lattice joins and so forth.

Issues with downgrading?

## October 9
**Manage to get the Calendar app "sort of" working.** 

I had already set up the mysql server and database two weeks ago, but had been having issues with Tomcat. I switched to Jetty, and started putting all the necessary dependencies in the `$jetty\webapps\calendar\WebINF` directory under the subdirectories `classes` and `lib`.

> [TODO:](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#list-of-todos) At a later date, I will want to figure out how to do this in a higher directory as per the Tomcat examples (which weren't working). However, as of now, the webapp was not finding `.jars` that I put in `$jetty\lib` and it was also not registering the `$jetty\shared` directory that I had tried to create (which was a similar issue I was having with Tomcat).

I had to grab class files from the Jif distribution and `.jar` dependency files each time I loaded the page until I stopped seeing errors. Eventually, I was able to connect to the database and log into the calendar. I was able to manipulate views and view other user's calendars. However, I was not able to add an event to the calendar and got stuck on the following error:

![no meetLbl method found](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Images/noMeetLabelMethod.png "no meetLbl method found")

Thus, I also do not know if I am able to delete or edit calendar events. I noticed some usability issues that annoyed me with the webforms, as well. I will address this if I get main functionality working.

-------------

## October 10
**Reformat significant portions of the code to make it more human readable.** 

The code for the Jif-Sif distribution of the calendar has significant readability concerns. There were many nested if statements without brackets, and it was difficult to tell which portions of code belonged where because of the excessive use of newline characters breaking up comparisons and identation not clearly indicating where the context of statements end. 

These all the Java files, which are found in `web/WEB-INT/classes/calendar`, are formatted in this hard to read way, and I could not tell what was going on until I fixed this. As it took some time with the longer file, I may not do all of them in one day, and I am also considering trying to build the calendar from scratch and add functionality instead of trying to specifically 'port' this calendar's functionality in a method-to-method manner.

I reformatted the longest file, the 6315 line `ShowCalendarSessAction.java` file, to be 4366 lines (even after adding many brackets and white space). 

*Example snippet:*

![not readable](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Images/notReadable.png "hard to read...")

-------------

## October 11
**Began Git Log file.**

I wanted to have an easy to access place to keep track of my work flow and to save necessary thoughts and links that resulted from this. 

**Recompile Jif with MeetLbl Method.**

Jed let me know that some code had been deleted four years ago, and he pushed changes to the master Jif repository.I could not get this to compile anymore (following my own documentation which I had used previously). 

![not compiling](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Images/jniHnotFound.png "cannot get this header to add to MacOSX gcc because it apparently claims that clang is throwing an error of not seeing the input files that clearly exist in the directory I tried to use.")

I wound up commenting out the lines 473 and 547 in the build.xml file because I didn't think I would need the unix runtime. It built and I was able to run the Jif-Sif calendar application!

**Investigated capabilities of the Jif-Sif Calendar Application.**
I found that the calendar was lacking in many capabilities outlined in the paper. Specifically, there is no time indicated in the calendar, so the user only knows the day that the event occurs, but not a time. (Perhaps this is not an issue for an example calendar, but it is something I noticed.) 

## October 12
**Reading about Java servelets since I have no prior experience with using them.**
Java Server Page - webpages embedded with Java code requiring a JSP engine such as Tomcat to turn the JSP into a servlet displaying the HTML code embedded within the JSP.

Servlets - unlike JSP are pure Java classes that require that it's classes are within the classpath, and the location depends on the servlet engine.

*The `Servlet` interface* 
> Note that this is different from SIF's servlet. [DONE:](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#finished-tasks) Investigate and understand SIF's servelet.

```java
package javax.servlet;

public interface Servlet
{ 
    public void destroy();
    public ServletConfig getServletConfig();
    public String getServletInfo();
    public void init(ServletConfig config)
        throws ServletException;
    public void service(ServletRequest request,
        ServletResponse response)
        throws ServletException, java.io.IOException;
}
```

*Implementing `Servlet` interface* (Two ways): 
 1. Subclass from a class taht already implements the interface
 2. Implement directly
 
 Some methods:
  * `service`: is the only method that the servlet **must** implement, and it takes two arguments: the object with information about the browser's request and the object containing information regarding what response to give to the browser. 
  * `init`: a method that is called just after loading the servlet the first time, since a servlet might need to initialize once before handling any requests (for example to connect to a database). 
  * `destroy`: is a method to ensure necessary cleanup of open files and closing of database connections and network connections.
  * `setContentType`: a way to set the content type of the response to `text/html` or `text/xml`
  * `response.getWriter`: returns the response's writer, and can be used with a `PrintWriter` to be an output stream for writing to the response. 
  * `response.getOutputStream`: same as getWriter except for binary data 
  
## October 20
**Creating attack plan.**

[Link](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Plan-of-attack.md): This also contains a timeline for what I am hoping to get done when.

## October 21
**Trying to understand infrastructure.**

Want to make some diagrams for Calendar application so that I have a clear picture of what needs to be programmed. Wonder if this is how remote Fabric method calls work, the syntax for labelling and annotation is not there):

*removed inaccurage diagram*

I'm also trying to understand how Fabric's implementation of the SIF servlet works. Searching for information about the SIF servlet lead me to an [article](http://www.cs.cornell.edu/andru/papers/fabric-sosp09.pdf) that I skimmed through, but it looks like invaluable information and so I am going to print it out and read it more carefully today.

I understand that I can start multiple nodes on my machine, and use the provided CA (which is insecure but probably sufficient for testing), but I'm not sure if this will be sufficient for testing my application. 

Unsure how data duplicates across multiple storage nodes, and if not, how would a worker node know where to access the object? [TODO:](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#list-of-todos) May need to dig through Fabric source code, because I am confused how it works...

**Missing Functionality**
The calendar app in the version of sif that I downloaded is missing it's preamble.js file, and therefore cannot access the onkeypress events that alledgedly change the color. [DONE:](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#finished-tasks) Will need to see if someone can locate preamble.js file for the SIF Calendar.

Found that preamble.js is in the src folder in sif and not in the example folders. Tried several ways of trying to get it to load in Jetty, but so far it's not working. [DONE:](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#finished-tasks) Get the preamble.js file loaded in Jetty or switch back to Tomcat if this doesn't work. 

I spent a few hours trying to get Jetty to recognize the preamble and then trying to get my mac to recognize the keypress events. To fix the problem with Jetty, I tried changing the path in the Servlet.java file to be within the webapp's directory. Then, after rebuilding sif, Jetty was loading the preamble. However, was having issues still with the keypress. I was not getting any output in the developer console for the code called from the body tag element:

```html
<body onkeypress="actionDown(event);" onkeyup="actionUp(event);" onload="initialize();">
```

So, I wrote a few test html files to see what was working or not, and realized that I was having issues with the above method. I instead decided to use javascript within the preamble instead:

```html
document.addEventListener("DOMContentLoaded", function(event) { 
    document.addEventListener("keydown", actionDown, false);
    document.addEventListener("keyup", actionUp, false);
});
```
After this, I was able to see output in the console when I pressed keys, but I was not getting the expected behavior. I had a lot of trouble with the code that was supposed to register the alt key in combination with another key code. Without one or the other, and without the flag, the preamble was working (but extrememly annoying because now you couldn't type without the legend taking over.)

The original function was as follows, but it was not working in any of my three browsers:
```javascript
// A = 97, B = 98, ..., H = 104, I = 105, J = 106, K = 107, L = 108, ..., O = 111, P = 112, Q = 113, R = 114, S = 115, ..., W = 119
function actionDown(e) {
    if(!e) e = window.event;
    if(!flag && e.altKey) {
        if(e.charCode == 113) { // Q: simple coloring
            flag = true;
            colorScheme = 113;
        } else if (e.charCode == 119) { // W: HSV coloring
            flag = true;
            colorScheme = 119;
        } else if (e.charCode == 105) { // I: Toggle between black background and white background
            isBkBlack = !isBkBlack;
        } else if (e.charCode == 111) { // O: Toggle between integrity and confidentiality
            isInteg = !isInteg;
        } else if (e.charCode == 114) { // R: Saturation based color
            flag = true;
            colorScheme = 114;
        } else if(e.charCode == 108) { //  L: Display Legend
            displayLegend();
        }

        if(flag) {
            conf(getColorFunc());
        }
    } 
}
```

This kind of got the colors to work:
```javascript
// A = 97, B = 98, ..., H = 104, I = 105, J = 106, K = 107, L = 108, ..., O = 111, P = 112, Q = 113, R = 114, S = 115, ..., W = 119
function actionDown(e) {
	if(!e) { e = window.event; }
	
	var key = e.keyCode ? e.keyCode : e.which ? e.which : e.charCode;
	console.log( "Code: " + e.code );
	console.log( "KeyDown: " + key );
	
	if(!flag && e.altKey) {
		console.log( "AltKey was true" );
		
		if (key == 81 || key == 113) { // Q: simple coloring
			console.log( "Q key was pressed" );
			flag = true;
			colorScheme = 113;
        } else if (key == 87 || key == 119) { // W: HSV coloring
            console.log( "W key was pressed" );
            flag = true;
            colorScheme = 119;
        } else if (key == 73 || key == 105) { // I: Toggle between black background and white background
            console.log( "I key was pressed" );
            isBkBlack = !isBkBlack;
        } else if (key == 79 || key == 111) { // O: Toggle between integrity and confidentiality
            console.log( "O key was pressed" );
            isInteg = !isInteg;
        } else if (key == 82 || key == 114) { // R: Saturation based color
            console.log( "R key was pressed" );
            flag = true;
            colorScheme = 114;
        } else if(key == 76 || key == 108) { //  L: Display Legend
            console.log( "L key was pressed" );
            displayLegend();
        }
		
		if(flag) {
			conf(getColorFunc());            
		}
	}
	console.log("\n");
}
```

## October 22
**Started a base directory for my implementation for fabric repo, and trying to decide application architecture.**
Because of the choice between datashipping and function shipping, it becomes important to decide how to cluster objects within this model, especially considering the fact that nodes will grab groups of related objects from storage nodes at once. Some ideas I had:

**Objects**
  + User 
    * uid
    * method to authenticate user
    * a method to grab user's calendar data from persistent store
    * array of events they own, and therefore can read and write 
    * array of events they attend, and therefore can read
    * array of events they can see as "busy"
  + Event
    * uid (owner of event)
    * name (of event)
    * start time
    * end time
    * note
    * list of attendees
    * list of viewers
  + Store
    * hashmap of uid mapped to arrays of events they own
    * hashmap of uid mapped to arrays of events they attend
    * hashmap of uid mapped to arrays of events they may view
    
This formatting should allow the storage node to retrieve entire calendar for a user once authenticated, when user adds event, let the method edit both cached copy in this session as well as doing remote call on the store, so that any effected user's arrays may also be updated.

**Nodes**
  + Persistent node must be the storage node, otherwise new calendar instantiated.
  + Temporal nodes are the "session" worker nodes, and these get authenticated by logging into a user. Once this happens, grab all objects related to user from storage node to populate their calendar. 
  + Q: *how will the new node know of the dns of the storage node, should make default for this instance?*
  
**Methods to consider**
  + Think that it may be useful to let the atomic methods revolve around locking events and not the exterior objects holding them. 
  
**Possible extensions**
  + Considering allowing there to be an acceptance/declination of event option and a way to leave an event? 
  + Do we want events ordered by time, and also do we want an expanded view for days?
  + Allow creators of events to transfer ownership of event to others

**Things to figure out**
  + How does the date utility work in this scenario?
  
## October 23-25

> I finished reading [Fabric: A Platform for Secure Distributed Computation and Storage](http://www.cs.cornell.edu/andru/papers/fabric-sosp09.pdf), and found that this article was a comprehensive overview of Fabric that was both dense but also extremely intriguing. It renewed my excitement about the language when I realized the capabilities of the language and all the considerations that were put into its design. I think a that portions of this paper would be useful to add to the current documentation for Fabric as it greatly aided in my overall understanding of how Fabric works and what function it serves. I thought I had read this paper previously, but I am certain at this point that I hadn't read it and confused it with the longer paper that I had attempted to read earlier in the semester. I definitely recommend this one.

**Identify some more necessary tasks that need to be done**

[TODO:](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#list-of-todos) Identify methods in JIF/SIF and Fabric that the calendar calls. Create a list to see what crosses over.

More questions to answer:
  * Does Fabric have an HTML class?
  * Should the calendar implement a dissemination layer? If so, how to do this. Otherwise, is it sufficient for demo to ignore this since there is no wire for worker to traverse within...
  * Are storage nodes only persistent during their lifespan? What happens if I stop running the program, or shut down the node? How to deal with availability of information if storage node fails? Does this mean that on a true implementation that there should be multiple storage nodes at different servers? How extensive should this example be?

> I am imagining a session node starts when someone tries to access calendar. Then, logging in, if user does not exist yet, create an object for the user, allow password creation. If user exists already, authenticate user, and if authenticated, acquire user from storage node based on username. When user closes page or logs off, commit the user object to storage node. (But what happens if user has some transactions on other objects, namely other users calendars that they added to viewers or attendees, and it has not committed due to optimistic transaction possibly rolling back their operation?)
  
## October 26

**Trying every single Fabric example and looking at the type of files in each directory.**

(I had previously only ran the SIF examples thinking that they were directly related to the calendar.) Some examples have .fil, some .fab, and some both. Some implement SIF, while one is using JSP, while others rely solely on textbased output. Not all the examples have README files, and a few of the examples didn't seem to do anything. For example, I tried to run fabnfs, and didn't manage to see what it was supposed to do... The majority of the applications with README files were relatively simple to run. Simply compile the directory using ant and run the executables in the bin folder to start the nodes, initialize stores, and then run the application. I noticed that while compiling with ant, almost all the were complaining that I should recompile with -Xlint:unchecked for details of input files using unchecked or unsafe operations.

**Skel README**
```  
This is a template for creating fabric examples. Many of our examples have
multiple versions - maybe the example is modeled in java and then ported to
fabil, or modeled in jif and ported to fabric, and this directory layout and
build file are designed for this scenario.

To create an example, copy this directory and perform the following steps:

1. Write your source code in the appropriate src/ subdirectory
2. Update the build file, replacing "skel" with the name of your example
3. Create etc/keys/node and etc/config/node for any fabric nodes required to
   run your example
4. Create shell scripts in bin/ to run your example
5. Replace this README with documentation for your example
```

**Trying to understand how signatures work**

I managed to confuse myself by reading about [JIF's interaction with Java](https://www.cs.cornell.edu/jif/doc/jif-3.3.0/misc.html#java), specifically because the examples that I was looking at did not seem like interfaces, but do not contain the method that I thought as per the manual that it should. Also, not sure I understood what I was reading regarding how the signatures are implemented. Will have to look at this again or clarify this later...

## October 27

**Discover Doxygen**
This is making it a lot easier to sift through the fabric language codebase, however some of the classes are not fully self-documenting as large amounts of methods are overlooked (or do not have document comments), and some of the classes are not receiving any love from Doxygen at all.

Currently, I am assuming that the fabric code that is implemented is from the system directory, but if so, what are the other directories? I could be entirely wrong in this assumption.

It is interesting that even ```<br>``` is implementing security labels. I'm guess that it's a covert channel because an adversary could assume that there are some content between some breaks?

I had been wondering what pastry was, and am now assuming that it is related to this:
 + [Free Pastry README](https://www.freepastry.org/FreePastry/README-1.3.html)
 + [Cornell paper about pastry](https://www.cs.cornell.edu/people/egs/615/pastry.pdf)
 
 **Investigating Fabric's implementation of SIF, and trying to understand all the parameters**
 > + The label L is an upper bound on the information contained in the node. 
 > + The label E is an upper bound on the information gained by knowing that this node is present in the HTML sent to the client.
 
## October 28-31
Restructuring code to have the Fabric language be more of a consideration in the design of the architecture.
Have questions regarding the store that I've been trying to go through Fabric source code to figure out. 

## October 31-November 3
Working on [External Documentation for Calendar](https://k33ty.github.io/Fabric-Calendar/)

## November 4-5
Within the directories: `signatures/fabric/*` there are several useful directories from which objects must inherit in the Calendar implementation. Knowing this helps make the demo code a lot more understandable. Begin going through this code and some of the demos again.

I had no idea that Java could implement an interface with an inner class, and I'm not sure what doing this causes... (Looking at example code from Fabric examples)

Trying to figure out what the hardcoded variables might be in the Fabric java classes in the examples, (the ones with numbers on the end seem to have some arbitrary number, and not sure what these numbers mean):
  * $commit323
  * $label30
  * $tm235
  * $e234
  * $currentTid34
  * $backOff30
  * $classHash
  
## November 6
Learn about closures since I didn't know what they were, and realizing that it's sprinkled throughout the examples codebase.
This was a useful Google Tech Talk: https://www.youtube.com/watch?v=0zVizaCOhME

## November 7
**Spend time with Tom**

Tom explained the compiler stack to me, and how some of the strange syntax issues worked. 

One point to remember: the methods/constructors in Fabric and FabIL have the `where` clause which allows strengthening of policies and ensuring that the correct information flow is required by the methods in question.

## November 9-12
**Exploring Fabric language classes and some example files**

After I realized that I had been looking at compiler generated code, and wasted a lot of the semester being confused by that, I decided to review the correct files relating to the examples files in Fabric, as well as the language files. (Only looks at *fabric language* `.fab` or *fabric immediate language* `.fil` files, since all the respective .java classes are autogenerated)

## November 13
**Jif Calendar**

Revisted the Jif calendar file again. Noticed that the only Java class is the `CalendarDB.java` file. `CalendarDB.jif` does essentially nothing, and most of the database functionality is in the CalendarDB class. This can later be converted to Fabric store calls. 

**Sif**

Revist Sif `.fab` files as well, especially considering the Jif calendar (and the Fabric travel application) import or extend these classes. I know that I will have to use them in the calendar as well.

## November 14
**Creating a build.xml file**

Created a build.xml file so that I could build the Fabric application. Had some issues with the directory mapping, but seemed to get it working by creating a local configuration file hardcoding my `${fabric.home}` path.

**Trying to build the calendar application**

Found that my understanding of the syntax is wrong. Trying to figure out what data structure to use for some of the objects in the Calendar, and also trying to figure out how to properly instantiate the different kinds of objects.

**Trying to add to fabric.util**

Tried to add to fabric.util since the Date class that is implemented in jif.util is not there. Having issues with some forms of instantiation.

## November 15-16
**Work on Architecture**

Finally got the architecture organized how I think it makes sense. 

Calendar package
  + Main - Main entrypoint for application (hopefully)
  + Calendar - The calendar object
  + Config - Configuration for the calendar
  + FrontPage - Front page of servlet
  + User - User object
  + Event sub package
    + OwnerEvent - events owned by principal P
    + AttendeeEvent - events principal P is attending
    + ViewerEvent - events principal P may view
    + CreateEvent
    + CreateEditEvent
    + FinishEditEvent
  + Principal sub package
    + CalendarRoot - can act on all servlet related final objects
    + ServletPrincipal - can act on all servlet related mutable objects
    + UserPrincipal - can only act on objects that UserPrincipal has CI rights 
  + Session sub package
    + CalendarSessionState
    + ChangeDisplayDateAction
    + EditEventAction
    + FinishEditEventReceiver
    + FinishEditingEvent
    + SelectDisplayUser
    + ShowCalendar
    + ShowCalendarSessAction
  + Utility sub package
    + DateUtil
    + Declassifier

Login Package ("borrowed" from Travel example, but reformatted for readability concerns)

**Writing Methods**

Started writing methods for the calendar application, but having trouble compiling things. Essentially, I'm still very lost as to how classes interweave and who things are instantiated.

-------------

# List of TODOs

  * Research how to create Jetty webapp that does not need dependencies directly put into application folder and can be put in a shared location
  * Automated build for calendar (build.xml / properties.in) incorporating Jetty
  * Fix calendar usability issues: fields empty themselves when trying to change other parameters
  * Dig through Fabric source code to answer some questions that are confusing me
  * Identify important methods that will need to be referenced from fabric util/lang/servlet
  * Answer all the questions in October 22 and 23
  
-------------
  
# Finished Tasks

  * Learn about servlets in Java
  * Learn about SIF's servlet
  * Locate SIF distribution preamble.js file.
  * Get preamble.js to load in Jetty
