# Store Classes

Implementation of the Fabric Store

+ [DuplicateStoreException](#duplicatestoreexception)
+ [InProcessStore](#inprocessstore)
+ [Node](#node)
+ [Options](#options)
+ [PrepareRequest](#preparerequest)
+ [SessionAttributes](#sessionattributes)
+ [SimpleSurrogateManager](#simplesurrogatemanager)
+ [Store](#store)
+ [SubscriptionManager](#subscriptionmanager)
+ [SurrogateManager](#surrogatemanager)
+ [TransactionManager](#transactionmanager)

## DuplicateStoreException

Is thrown when attempt is made to add a duplicate store to a store node.

#### Public Member Functions

```java
DuplicateStoreException()
```

Inherits from: 
+ fabric.common.exceptions.UsageError

-----

## InProcessStore

In-process implementation of the Store interface for use when a worker is running in-process with a Store. 
The operations work directly on the Store's TransactionManager object.

#### Public Member Functions

Constructor:
```java
InProcessStore (String name, Store c)
```

Notify the store that the transaction tid is being Aborted (can cause AccessException):
```java
void abortTransaction (TransactionID tid)
```

Notify the Store that the transaction tid should be committed (can cause UnreachableNodeException):
```java
void commitTransaction (long transactionID) throws TransactionCommitFailedException
```

Obtain a new, unused object number from the Store:
```java 
long createOnum ()
```

Notifies the store that the transaction is entering the Prepare phase:
```java
void prepareTransaction (long tid, boolean singleStore, boolean readOnly, Collection< _Impl > toCreate, LongKeyMap< Integer > reads, Collection< _Impl > writes) throws TransactionPrepareFailedException
```

```java 
ObjectGroup readObjectFromStore (long onum) throws AccessException
```

```java
ObjectGlob	readEncryptedObjectFromStore (long onum) throws AccessException 
```

#### Protected Member Functions

```java 
List< SerializedObject > getStaleObjects (LongKeyMap< Integer > reads)
```

#### Protected Attributes

```java
final TransactionManager tm
final SurrogateManager sm
RemoteIdentity<RemoteWorker> localWorkerIdentity
```

Inherits from: 
+ fabric.worker.RemoteStore
+ fabric.net.RemoteNode<This>
+ fabric.worker.Store

-----

## Node

The Node class encapsulates the shared resources for multiple stores and workers that run in the same process. 
It also acts as a container for those stores and workers. It is responsible for setting them up and tearing them down.

#### Public Member Functions

Constructor:
```java
Node (Options opts)
```

Setup all workers and stores:
```java
void initialize ()
```

**Main method.** Calls start and outputs errors nicely:
```java
static void main (String[] args)
```

Launch all workers and stores:
```java
void run ()
```

Gracefully tear down all workers and stores:
```java
void shutdown ()
```

Main entry point for the store. This method is useful for applications that wish to embed a fabric store:
```java
static void start (String args[]) throws TerminationException 
```

-----

## Options

#### Public Member Functions

```java
Options (String[] args) throws UsageError 
```

```java
void setDefaultValues ()
```

```java
void validateOptions () throws UsageError 
```

```java
void usageHeader (PrintStream out)
```

#### Public Attributes

```java
String storeName
int threadPool
int timeout

# The worker shell command to run
String [] cmd
```

#### Protected Member Functions

```java
void populateFlags (Set< Flag > flags)
```

```java
int defaultHandler (String[] args, int index)
```

#### Protected Attributes

```java
# Whether to have an interactive shell. A non-interactive shell is useful when the worker is started with a disconnected stdin.
boolean interactiveShell
```

Inherits from: 
+ fabric.common.Options

-----

## PrepareRequest

A convenience class for grouping together the created, modified, and read object sets of a prepare request.

#### Public Member Functions

```java
PrepareRequest (long tid, Collection< SerializedObject > creates, Collection< SerializedObject > writes, LongKeyMap< Integer > reads)
```

#### Public Attributes

```java
final long 	tid
```

The set of created objects:
```java
final Collection< SerializedObject > creates
```

The collection of modified objects:
```java
final Collection< SerializedObject > writes
```

The object numbers and version numbers of the read objects:
```java
final LongKeyMap< Integer > reads
```

-----

## SessionAttributes

(**No Doxygen was created. Could this be because class and methods do not have labelling public/protected/private?**)

#### Member Functions

Constructs a SessionAttributes object corresponding to a dissemination node:
```java
SessionAttributes(Store store, String workerName)
```

Constructs a SessionAttributes object corresponding to a worker node:
```java
SessionAttributes(Store store, String workerName, String workerPrincipalName,
      NodePrincipal worker)
```

#### Attributes

Whether the worker is a dissemination node:
```java
final boolean workerIsDissem
```

The store with which the worker is interacting:
```java
final Store store
```

The name of the remote principal:
```java
final String workerPrincipalName
```

The worker's principal object:
```java
final NodePrincipal workerPrincipal
```

The worker's node:
```java
final RemoteWorker remoteNode
```
-----


## SimpleSurrogateManager

This is a simple surrogate policy. It keeps no state between requests, and simply creates lots of new surrogate objects. 

#### Public Member Functions

Constructor:
```java
SimpleSurrogateManager (final TransactionManager tm)
```

Modify req *(where req is the collections of objects created, modified, and read by this transaction, and req may be 
modified if surrogate objects are created or modified)* so that all references are local. It should do so by creating or 
reusing surrogate objects for all of the non-local references. Any new surrogate objects should be added to the 
req.creates, while any read surrogate objects should be added to req.reads:
```java
void createSurrogates (PrepareRequest req)
```


-----

## Store

(**No Doxygen was created for some reason...**)

Extends: fabric.messages.MessageToStoreHandler

#### Public Member Functions

Constructor which loads configuration files and attempts to create a store's principal certificate:
```java
SimpleSurrogateManager (final TransactionManager tm)
```

Ensure each store's object database has been properly initialized:
```java
public void initialize()
```

```java
public void shutdown()
```

```java
public AbortTransactionMessage.Response handle(RemoteIdentity<RemoteWorker> client, AbortTransactionMessage message) 
		throws AccessException
```

Processes the given request for new OIDs:
```java
public AllocateMessage.Response handle(RemoteIdentity<RemoteWorker> client,AllocateMessage msg) throws AccessException
```

Processes the given commit request:
```java
public CommitTransactionMessage.Response handle(RemoteIdentity<RemoteWorker> client, CommitTransactionMessage message)
      throws TransactionCommitFailedException
```

Processes the given PREPARE request:
```java
public PrepareTransactionMessage.Response handle(RemoteIdentity<RemoteWorker> client, PrepareTransactionMessage msg)
      throws TransactionPrepareFailedException
```

Processes the given read request:
```java
public ReadMessage.Response handle(RemoteIdentity<RemoteWorker> client, ReadMessage msg) throws AccessException
```

Processes the given dissemination-read request:
```java
public DissemReadMessage.Response handle(RemoteIdentity<RemoteWorker> client, DissemReadMessage msg) 
		throws AccessException
```

Processes the given request for the store's SSL certificate chain:
```java
public GetCertChainMessage.Response handle(RemoteIdentity<RemoteWorker> client, GetCertChainMessage msg)
```

Processes the given request for a new node principal by:
 + Getting the store's node object and signing key
 + Creating a principal object on the store and getting the resulting object's onum
 + Creating a certificate that binds the requester's key to both the requester's name and the new principal object's OID 
```java
public MakePrincipalMessage.Response handle(RemoteIdentity<RemoteWorker> client, MakePrincipalMessage msg)
      throws FabricGeneralSecurityException
```

Processes the given staleness check request:
```java
public StalenessCheckMessage.Response handle(RemoteIdentity<RemoteWorker> client, StalenessCheckMessage message)
      throws AccessException
```

#### Public Attributes

```java
public final Node node;
public final TransactionManager tm;
public final SurrogateManager sm;
public final ObjectDB os;
public final X509Certificate[] certificateChain;
public final PublicKey publicKey;
public final PrivateKey privateKey;
public final ConfigProperties config;
```

#### Protected Member Functions

```java
protected SubServerSocket createServerSocket()
```

#### Private Member Functions

Construct ObjectDB with class specified by properties file:
```java
private ObjectDB loadStore()
```


```java
private SubServerSocketFactory createSocketFactory(KeyMaterial keys)
```

```java
private void prepareTransaction(Principal p, long tid, Collection<SerializedObject> serializedCreates, 
      Collection<SerializedObject> serializedWrites, LongKeyMap<Integer> reads)
      throws TransactionPrepareFailedException
```

If principal is null, return bottom principal, otherwise return the string of principal's dns and onum
```java
private String nameOf(Principal p)
```
-----

## SubscriptionManager
(**Not complete because Doxygen not comprehensive**)

Keeps track of who's subscribed to what object. Handles subscriptions for a single store. 

#### Public Member Functions

```java
SubscriptionManager (String store, TransactionManager tm)  
```

```java
void run()
```

Subscribe the given worker to the given onum:
```java
void subscribe(long onum, RemoteWorker worker, boolean dissemSubscribe)
```

Notify the subscription manager that a set of objects has been updated by a particular worker:
```java
void notifyUpdate(LongSet onums, RemoteWorker worker)
```

#### Public Attributes

```java
static final boolean ENABLE_OBJECT_UPDATES = false
```

Inherits from:
 + fabric.common.FabricThread.Impl

-----

## SurrogateManager

A surrogate manager encapsulates the strategy for building and maintaining surrogate objects for inter-store references.

#### Public Member Functions

Modify req so that all references are local. It should do so by creating or reusing surrogate objects for all of the 
non-local references. Any new surrogate objects should be added to the req.creates, while any read surrogate objects 
should be added to req.reads:
```java
void createSurrogates (PrepareRequest req)
```

## TransactionManager

#### Public Member Functions

Constructor
```java
TransactionManager (ObjectDB database)
```

Instruct the transaction manager that the given transaction is aborting:
```java
void abortTransaction (Principal worker, long transactionID) throws AccessException 
```

Execute the commit phase of two phase commit:
```java
void commitTransaction (RemoteIdentity<RemoteWorker> workerIdentity, long transactionID) 
		throws TransactionCommitFailedException 
```

Execute the prepare phase of two phase commit. Validates the transaction to make sure that no conflicts would occur 
if this transaction were committed. Once prepare returns successfully, the corresponding transaction can only fail if 
the coordinator aborts it.

The prepare method must check a large number of conditions:
+ Neither creates, updates, nor reads can have pending commits, i.e. none of them can contain objects for which other 
transactions have been prepared but not committed or aborted.
+ The worker has appropriate permissions to read/write/create
+ Created objects don't already exist
+ Updated objects cannot have been read since the proposed commit time.
+ Updated objects do not have valid outstanding promises
+ Modified and read objects do exist
+ Read objects are still valid (version numbers match) 
```java
void prepare (Principal worker, PrepareRequest req) throws TransactionPrepareFailedException 
```

Returns a Glob containing the specified object. All surrogates referenced by any object in the group will also be in 
the group. This ensures that the worker will not reveal information when dereferencing surrogates:
```java
ObjectGlob getGlob (long onum, RemoteWorker subscriber) throws AccessException
```

Returns an ObjectGroup containing the specified object. All surrogates referenced by any object in the group will also 
be in the group. This ensures that the worker will not reveal information when dereferencing surrogates:
```java
ObjectGroup getGroup (Principal principal, RemoteWorker subscriber, long onum) throws AccessException 
```

```java
long [] newOnums (Principal worker, int num) throws AccessException 
```
