This file is a timeline of necessary steps of work as of October 9th. 
More was done prior to this date, but I have not recorded actions.

### Jump to a specific date

 * [Oct 9](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-9)
 * [Oct 10](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-10)
 * [Oct 11](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#october-11)

### October 9
**Manage to get the Calendar app "sort of" working.** 

I had already set up the mysql server and database two weeks ago, but had been having issues with Tomcat. I switched to Jetty, and started putting all the necessary dependencies in the `$jetty\webapps\calendar\WebINF` directory under the subdirectories `classes` and `lib`.

> <span style="color:red">[TODO:](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Log.md#list-of-todos)</span> At a later date, I will want to figure out how to do this in a higher directory as per the Tomcat examples (which weren't working). However, as of now, the webapp was not finding `.jars` that I put in `$jetty\lib` and it was also not registering the `$jetty\shared` directory that I had tried to create (which was a similar issue I was having with Tomcat).

I had to grab class files from the Jif distribution and `.jar` dependency files each time I loaded the page until I stopped seeing errors. Eventually, I was able to connect to the database and log into the calendar. I was able to manipulate views and view other user's calendars. However, I was not able to add an event to the calendar and got stuck on the following error:

![no meetLbl method found](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Images/noMeetLabelMethod.png "no meetLbl method found")

Thus, I also do not know if I am able to delete or edit calendar events. I noticed some usability issues that annoyed me with the webforms, as well. I will address this if I get main functionality working.

### October 10
**Reformat significant portions of the code to make it more human readable.** 

The code for the Jif-Sif distribution of the calendar has significant readability concerns. There were many nested if statements without brackets, and it was difficult to tell which portions of code belonged where because of the excessive use of newline characters breaking up comparisons and identation not clearly indicating where the context of statements end. 

These all the Java files, which are found in `web/WEB-INT/classes/calendar`, are formatted in this hard to read way, and I could not tell what was going on until I fixed this. As it took some time with the longer file, I may not do all of them in one day, and I am also considering trying to build the calendar from scratch and add functionality instead of trying to specifically 'port' this calendar's functionality in a method-to-method manner.

I reformatted the longest file, the 6315 line `ShowCalendarSessAction.java` file, to be 4366 lines (even after adding many brackets and white space). 

*Example snippet:*

![not readable](https://github.com/K33TY/Jif-Sif-to-Fabric/blob/master/Docs/Images/notReadable.png "hard to read...")


### October 11
**Began Git Log file.**

I wanted to have an easy to access place to keep track of my work flow and to save necessary thoughts and links that resulted from this. 

**Reading about Java servelets since I have no prior experience with using them.**

# List of TODOs

  * Learn about servelets
  * Research how to create Jetty webapp that does not need dependencies directly put into application folder and can be put in a shared location
  * Automated build for calendar (build.xml / properties.in) incorporating Jetty
  * Fix calendar usability issues: fields empty themselves when trying to change other parameters

