# Porting Jif-Sif Calendar App to Fabric

To port the software successfully, it is essential to know what are the Calendar's capabilities and ensure that these all get transferred over into the new distribution. It is also essential to know the capabilities of each language itself, namely the differences between Jif and Fabric, in order that functional limitations can be determined. If some functionality cannot easily transfer, it will be necessary to explore possible workarounds.

### Capabilities
Here we have a list of the Sif calendar's capabilities<sup>[1](https://www.cs.cornell.edu/andru/papers/sif.pdf)</sup>:

  1. Authenticated Users may create, edit, and view events.

### Ideas to port capabilities from Sif-Jif distribution to Fabric
For each capability, we need to figure out how to implement this in Fabric, determining which limitations exist and testing different workarounds.

### References
[1. Chong, Vikram, and Myers. "SIF: Enforcing Confidentiality and Integrity in Web Applications."](https://www.cs.cornell.edu/andru/papers/sif.pdf)
