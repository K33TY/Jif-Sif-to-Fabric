# Porting Jif-Sif Calendar App to Fabric

To port the software successfully, it is essential to know what are the Calendar's capabilities and ensure that these all get transferred over into the new distribution. It is also essential to know the capabilities of each language itself, namely the differences between Jif and Fabric, in order that functional limitations can be determined. If some functionality cannot easily transfer, it will be necessary to explore possible workarounds.

### Capabilities and Parameters
Here we have an overview of the Sif calendar<sup>[1](https://www.cs.cornell.edu/andru/papers/sif.pdf)</sup>:

  1. Authenticated users may create, edit, and view events.
  2. Events have a time, title, list of attendees, and description.
  3. Events are controlled by expressive security policies, and application users are able to customize these policies.
  4. Users can only edit an event if the user acts for the creator of the event.
  5. Only the event creator or attendees may view details of an event (title, attendees, and description).
  6. An event may specify an additional list of users who may view the time of the event.
  7. If a user may view the time of an event, but not the details, then the user will see "Busy" as the event description.
  
Definition: A user's calendar is the set of all events for which the user is either the creator or attendee. 

#### Capabilities

  1. Update session state with date to display
  2. Update session state with which user's calendar to display
  3. Fresh id for new event
  4. Update and retrive info from database
  5. Go to View/Edit Event page
  6. Error editing event
  7. Changing attendees or viewers of an event
  8. Delegation to CalRoot

### Ideas to port capabilities from Sif-Jif distribution to Fabric
For each capability, we need to figure out how to implement this in Fabric, determining which limitations exist and testing different workarounds.

### References
[1. Chong, Vikram, and Myers. "SIF: Enforcing Confidentiality and Integrity in Web Applications."](https://www.cs.cornell.edu/andru/papers/sif.pdf)
