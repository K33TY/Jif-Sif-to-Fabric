This file is a timeline of necessary steps of work as of October 9th. 
More was done prior to this date, but I have not recorded actions.

## Jump to a specific date

 * [Oct 9](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-9)
   * Manage to get the Calendar app "sort of" working.
 * [Oct 10](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-10)
   * Reformat significant portions of the code to make it more human readable.
 * [Oct 11](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-11)
   * Began Git Log file.
   * Recompile Jif with MeetLbl Method.
   * Investigated capabilities of the Jif-Sif Calendar Application.
 * [Oct 12](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-12)
   * Reading about Java servelets since I have no prior experience with using them.
 * [Oct 20](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-20)
   * Creating attack plan.
 
## Jump to TODO List or Finished Task List.

I have created a [TODO list](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#list-of-todos) which I will add tasks that I need to remember to do later. Once I am done with any of these tasks, I will move it to the [Finished Task List](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#finished-tasks).
 
-------------

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
> Note that this is different from SIF's servlet. [TODO:](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#list-of-todos) Investigate and understand SIF's servelet.

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

-------------

# List of TODOs

  * Learn about SIF's servlet
  * Research how to create Jetty webapp that does not need dependencies directly put into application folder and can be put in a shared location
  * Automated build for calendar (build.xml / properties.in) incorporating Jetty
  * Fix calendar usability issues: fields empty themselves when trying to change other parameters
  
-------------
  
# Finished Tasks

  * Learn about servlets in Java
