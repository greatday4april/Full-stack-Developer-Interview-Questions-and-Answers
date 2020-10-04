# Full-stack Developer Interview Questions and Answers

## <a name='toc'>Table of Contents</a>

- [Architecture](#architecture)
- [Concurrency](#concurrency)
- [General Questions](#general)
- [WEB](#web)
- [SQL](#sql)
- [NoSQL](#nosql)
- [Transactions](#transcations)
- [Scalability](#scalability)
- [Load balancing](#load-balancing)
- [Cloud computing](#cloud-computing)
- [Distributed](#distributed)
- [Cache](#cache)
- [Networking](#networking)
- [Operating system](#os)
- [Functional programming](#functional-programming)
- [Reactive programming](#reactive-programming)
- [Git](#git)
- [DevOps](#devOps)
- [Agile, Scrum, XP](#agile)
- [UML](#uml)
- [Other](#other)
- [Machine learning](#machine-learning)
- [Big Data](#big-data)
- [Image processing](#image-processing)
- [Cryptography](#cryptography)
- [Security](#security)

#### [[⬆]](#toc) <a name='architecture'>Architecture:</a>

- _Design principles_. ([_DRY_](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself), [_KISS_](https://en.wikipedia.org/wiki/KISS_principle), [_separation of concerns_](https://en.wikipedia.org/wiki/Separation_of_concerns), [_single source of truth_](https://en.wikipedia.org/wiki/Single_source_of_truth),
- [_Microservices_](https://en.wikipedia.org/wiki/Microservices) are a style of software architecture that involves delivering systems as a set of very small, granular, independent collaborating services.
  - Pros of _microservices_ (The services are easy to replace, Services can be implemented using different programming languages, databases, hardware and software environment, depending on what fits best)
- [_MVC_]()
- [_REST_](https://en.wikipedia.org/wiki/Representational_state_transfer) (Representational state transfer), [_RPC_](https://en.wikipedia.org/wiki/Remote_procedure_call)
- [_Idempotent operation_](https://en.wikipedia.org/wiki/Idempotence) (The PUT and DELETE methods are referred to as idempotent, meaning that the operation will produce the same result no matter how many times it is repeated)
- _Nullipotent operation_ (GET method is a safe method (or nullipotent), meaning that calling it produces no side-effects)
- [_Naked objects_](https://en.wikipedia.org/wiki/Naked_objects), [_Restful objects_](https://en.wikipedia.org/wiki/Restful_Objects).
- Why do you need _web server_ (tomcat, jetty)?
- [_Inheritance_](<https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)>) vs [_Composition_](https://en.wikipedia.org/wiki/Object_composition) (Inheritance - is-a relationship, whether clients will want to use the subclass type as a superclass type. Composition - has-a or part-of relationship).
- [_Multiple inheritance (diamond) problem_](https://en.wikipedia.org/wiki/Multiple_inheritance#The_diamond_problem)
- Advantages of using _modules_. (reuse, decoupling, namespace)
- Drawbacks of not using [_separation of concerns_](https://en.wikipedia.org/wiki/Separation_of_concerns)
  - Adding new features will take an order of magnitude longer
  - Impossible to optimize
  - Extremely difficult to test
  - Fixing and debugging can be a nightmare (fixing something in one place can lead to something else breaking that seems completely unrelated).

#### [[⬆]](#toc) <a name='concurrency'>Concurrency:</a>

- What is [_deadlock_](https://en.wikipedia.org/wiki/Deadlock), [_livelock_](https://en.wikipedia.org/wiki/Deadlock#Livelock)? (Deadlock is a situation in which two or more competing actions are each waiting for the other to finish, and thus neither ever does. A livelock is similar to a deadlock, except that the states of the processes involved in the livelock constantly change with regard to one another, none progressing.)
- [_Deadlock avoidance_](https://www.geeksforgeeks.org/deadlock-prevention). (prevention, detection, avoidance (Mutex hierarchy), and recovery)
- What is [_starvation_](<https://en.wikipedia.org/wiki/Starvation_(computer_science)>)? (a problem encountered in concurrent computing where a process is perpetually denied necessary resources to process its work)
- What is [_race condition_](https://en.wikipedia.org/wiki/Race_condition)? (Behavior of software system where the output is dependent on the sequence or timing of other uncontrollable events)
- What is [_happens-before_](https://en.wikipedia.org/wiki/Happened-before) relation?
- What is [_thread contention_](https://stackoverflow.com/questions/1970345/what-is-thread-contention)? (Contention is simply when two threads try to access either the same resource or related resources in such a way that at least one of the contending threads runs more slowly than it would if the other thread(s) were not running). Contention occurs when multiple threads try to acquire a lock at the same time
- What is a [_thread-safe_](https://en.wikipedia.org/wiki/Thread_safety) function? (Can be safely invoked by multiple threads at the same time)
- [_Publish/Subscribe_](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern) pattern
- What is [_2-phase locking_](https://en.wikipedia.org/wiki/Two-phase_locking)? (Growing phase, shrinking phase. Guarantees serializablity for transactions, doesn't prevent deadlock).
- What is the difference between _thread_ and _process_? (Threads (of the same process) run in a shared memory space, while processes run in separate memory spaces)
- What is [_false sharing_](https://en.wikipedia.org/wiki/False_sharing), [_cache pollution_](https://en.wikipedia.org/wiki/Cache_pollution), _cache miss_, [_thread affinity_](https://en.wikipedia.org/wiki/Processor_affinity), [_ABA-problem_](https://en.wikipedia.org/wiki/ABA_problem), [_speculative execution_](https://en.wikipedia.org/wiki/Speculative_execution)?
- What is a

  - [_obstruction-free_](https://en.wikipedia.org/wiki/Non-blocking_algorithm#Obstruction-freedom) - if all other threads are paused, then any given thread will complete its operation in a bounded number of steps
  - [_lock-free_](https://en.wikipedia.org/wiki/Non-blocking_algorithm#Lock-freedom) - if multiple threads are operating on a data structure, then after a bounded number of steps one of them will complete its operation
  - [_wait-free_](https://en.wikipedia.org/wiki/Non-blocking_algorithm#Wait-freedom) - every thread operating on a data structure will complete its operation in a bounded number of steps, even if other threads are also operating on the data structure algorithm?

- What is [_sequential consistency_](https://en.wikipedia.org/wiki/Sequential_consistency)? (The result of any execution is the same as if the operations of all the processors were executed in some sequential order, and the operations of each individual processor appear in this sequence in the order specified by its program).
- What is a [_memory barrier_](https://en.wikipedia.org/wiki/Memory_barrier)? (A memory barrier, also known as a membar, memory fence or fence instruction, is a type of barrier instruction that causes a CPU or compiler to enforce an ordering constraint on memory operations issued before and after the barrier instruction)
- Synchonization aids in Java
  - CountDownLatch
  - CyclicBarrier
  - Phaser
  - ReentrantLock
  - Exchanger
  - Semaphore
  - LinkedTransferQueue
- What is _data race_? (When a program contains two conflicting accesses that are not ordered by a [happens-before](https://docs.oracle.com/javase/specs/jls/se12/html/jls-17.html#jls-17.4.5) relationship, it is said to contain a data race. Two accesses to (reads of or writes to) the same variable are said to be conflicting if at least one of the accesses is a write. But see [this](https://stackoverflow.com/questions/16615140/is-volatile-read-happens-before-volatile-write/16615355#16615355))
- Java [_memory model_](https://docs.oracle.com/javase/specs/jls/se12/html/jls-17.html#jls-17.4)
  - A program is correctly synchronized if and only if all sequentially consistent executions are free of data races
  - Correctly synchronized programs have sequentially consistent semantics. If a program is correctly synchronized, then all executions of the program will appear to be sequentially consistent
  - Causality requirement for incorrectly synchronized programs: [link](https://pdfs.semanticscholar.org/c132/11697f5c803221533a07bd6db839fa60b7b8.pdf)
- What is _monitor_ in Java? (Each object in Java is associated with a monitor, which a thread can lock or unlock)
- What is _safe publication_?
- What is _wait_/_notify_?
- [_Amdahl's law_](https://en.wikipedia.org/wiki/Amdahl%27s_law)? (Speedup = 1 / (1 - p + p / n))
- [_Dining philosophers problem_](https://en.wikipedia.org/wiki/Dining_philosophers_problem) (Resource hierarchy (first take lower-indexed fork), arbitrator, communication (dirty/clean forks)).
- [_Produces/consumer_](https://en.wikipedia.org/wiki/Producer%E2%80%93consumer_problem) problem.
- [_Readers/writers_](https://en.wikipedia.org/wiki/Readers%E2%80%93writers_problem) problem.
- [_Transactional memory_](https://en.wikipedia.org/wiki/Software_transactional_memory)
- [_Coroutine_](https://en.wikipedia.org/wiki/Coroutine)

#### [[⬆]](#toc) <a name='general'>General Questions:</a>

- [_Polymorphism_](<https://en.wikipedia.org/wiki/Polymorphism_(computer_science)>) (Variable of type Shape could refer to an object of type Square, Circle... Ability of a function to handle objects of many types)
- [_Encapsulation_](<https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)>) (Packing of data and functions into a single component)
- [_Virtual function_](https://en.wikipedia.org/wiki/Virtual_function) (Overridable function)
- [_Virtual method table_](https://en.wikipedia.org/wiki/Virtual_method_table)
- [_Dynamic binding_](https://en.wikipedia.org/wiki/Late_binding) (Actual method implementation invoked is determined at run time based on the class of the object, not the type of the variable or expression)
- How does [_garbage collector_](<https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)>) work? (Mark and sweep: mark: traverse object graph starting from root objects, sweep: garbage collect unmarked objects. Optimizations: young/old generations, incremental mark and sweep)
- [_Tail recursion_](https://en.wikipedia.org/wiki/Tail_call) (A tail call is a subroutine call performed as the final action of a procedure)
- [_Semantic versioning_](http://semver.org)

#### [[⬆]](#toc) <a name='web'>WEB:</a>

- WEB security vulnerabilities ([_XSS_](https://en.wikipedia.org/wiki/Cross-site_scripting), [_CSRF_](https://en.wikipedia.org/wiki/Cross-site_request_forgery), [_session fixation_](https://en.wikipedia.org/wiki/Session_fixation), [_SQL injection_](https://en.wikipedia.org/wiki/SQL_injection), [_man-in-the-middle_](https://en.wikipedia.org/wiki/Man-in-the-middle_attack), [_buffer overflow_](https://en.wikipedia.org/wiki/Buffer_overflow))
- _CSRF prevention_ (CSRF-token)
- What is [_JSONP_](https://en.wikipedia.org/wiki/JSONP), [_CORS_](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing)? (A communication technique used in JavaScript programs running in web browsers to request data from a server in a different domain, something prohibited by typical web browsers because of the same-origin policy)
- [_HTTPS_](https://en.wikipedia.org/wiki/HTTPS) negotiation steps.
- What is HTTP Strict Transport Security ([_HSTS_](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security))? (Prevents Man in the Middle attacks)
- Browser-server communication methods: WebSocket, EventSource, Comet(Polling, Long-Polling, Streaming)
- [_Character encoding_](https://en.wikipedia.org/wiki/Character_encoding)
- What is [_role-based access control_](https://en.wikipedia.org/wiki/Role-based_access_control) and [_access control list_](https://en.wikipedia.org/wiki/Access_control_list)?
- What is session and persistent cookies, sessionStorage and [localStorage](https://en.wikipedia.org/wiki/Web_storage#Local_and_session_storage)?
- How to implement _remember-me_? (http://jaspan.com/improved_persistent_login_cookie_best_practice)
- Authentication using cookies, [_JWT_](https://en.wikipedia.org/wiki/JSON_Web_Token) (JSON Web Tokens).

#### [[⬆]](#toc) <a name='sql'>SQL:</a>

- _SQL join types_ (inner join, left/right outer join, full outer join, cross join)
  ![Join types](https://habrastorage.org/files/7ff/b2c/3a2/7ffb2c3a25b74dcf9eec013282b9cfb4.png "Join types"))
- _SQL normal forms_
  1. The domain of each attribute contains only atomic values, and the value of each attribute contains only a single value from that domain
  1. No non-prime attribute in the table is functionally dependent on a proper subset of any candidate key
  1. Every non-prime attribute is non-transitively dependent on every candidate key in the table. BCNF.Every non-trivial functional dependency in the table is a dependency on a superkey.)
- _Isolation levels_ and Anomalies

| Isolation_level\Anomaly | Lost_update (because of rollback) | Dirty_read | Non_repeatable_reads second_lost_update | Phantoms  | Write_skew |
| :---------------------- | :-------------------------------: | :--------: | :-------------------------------------: | :-------: | :--------: |
| Read Uncommitted        |                 -                 | may occur  |                may occur                | may occur | may occur  |
| Read Committed          |                 -                 |     -      |                may occur                | may occur | may occur  |
| Repeatable Read         |                 -                 |     -      |                    -                    | may occur | may occur  |
| Snapshot                |                 -                 |     -      |                    -                    |     -     | may occur  |
| Serializable            |                 -                 |     -      |                    -                    |     -     |     -      |

#### [[⬆]](#toc) <a name='nosql'>NoSQL:</a>

- Types of NoSQL databases?
  - Document Stores (MongoDB, Couchbase)
  - Key-Value Stores (Redis, Volgemort)
  - Column Stores (Cassandra)
  - Graph Stores (Neo4j, Giraph)

#### [[⬆]](#toc) <a name='transactions'>Transactions:</a>

- [_ACID_](https://en.wikipedia.org/wiki/ACID)
- [_2-phase commit protocol_](https://en.wikipedia.org/wiki/Two-phase_commit_protocol)
- [_3-phase commit protocol_](https://en.wikipedia.org/wiki/Three-phase_commit_protocol)
- What is _pessimistic_ / [_optimistic_](https://en.wikipedia.org/wiki/Optimistic_concurrency_control) locking?

#### [[⬆]](#toc) <a name='scalability'>Scalability:</a>

- Horizontal and vertical scaling.
- How to scale database? (Data partitioning, sharding(vertical/horizontal), replication(master-slave, master-master)).
- _Denormalization_.
- What is _synchronous multimaster replication_? (Each server can accept write requests, and modified data is transmitted from the original server to every other server before each transaction commits)
- What is _asynchronous multimaster replication_? (Each server works independently, and periodically communicates with the other servers to identify conflicting transactions. The conflicts can be resolved by users or conflict resolution rules)
- When to use messaging queue?
- MongoDB, Redis.
- Hadoop basics.

#### [[⬆]](#toc) <a name='load-balancing'>Load balancing:</a>

- sticky/non-sticky sessions
- _Sticky sessions_ vs storing sessions in Redis.

#### [[⬆]](#toc) <a name='cloud-computing'>Cloud computing:</a>

- What is [_cloud computing_](https://en.wikipedia.org/wiki/Cloud_computing)? (Cloud computing platform is a fully automated server platform that allows users to purchase, remotely create, dynamically scale, and administer system)
- [_Amazon web services_](https://en.wikipedia.org/wiki/Amazon_Web_Services)
- [_Google Cloud Platform_](https://en.wikipedia.org/wiki/Google_Cloud_Platform)
- [_Microsoft Azure_](https://en.wikipedia.org/wiki/Microsoft_Azure)

#### [[⬆]](#toc) <a name='distributed'>Distributed:</a>

- [_Consensus_](<https://en.wikipedia.org/wiki/Consensus_(computer_science)>)
- [_Raft_](<https://en.wikipedia.org/wiki/Raft_(computer_science)>) ([In Search of an Understandable Consensus Algorithm](https://raft.github.io/raft.pdf))
- [_Paxos_](<https://en.wikipedia.org/wiki/Paxos_(computer_science)>)
- What is [_CAP theorem_](https://en.wikipedia.org/wiki/CAP_theorem)? [Illustrated proof](https://mwhittaker.github.io/blog/an_illustrated_proof_of_the_cap_theorem/). [CAP-FAQ](http://www.the-paper-trail.org/page/cap-faq) (It is impossible for a distributed computer system to simultaneously provide all three of the following guarantees: _consistency_, _availability_, _partition tolerance_). [Gilbert and Lynch's paper](https://users.ece.cmu.edu/~adrian/731-sp04/readings/GL-cap.pdf). ["Please stop calling databases CP or AP"](https://martin.kleppmann.com/2015/05/11/please-stop-calling-databases-cp-or-ap.html)).
  ![CAP theorem](http://guide.couchdb.org/draft/consistency/01.png "CAP theorem")
- What is _map-reduce_? (Word count example)
- _Sharding counters_.
- Distributed software:
  - Distributed streaming platforms: **kafka**
  - Distributed key-value store: **zookeeper**, **etcd**, **Consul**
  - Map-reduce: **hadoop**, **spark**
  - Distributed file system: **hbase**
  - Cluster management: **kubernetes**, **docker-swarm**, **mesos**
- [Herlihy’s consensus hierarchy](https://en.wikipedia.org/wiki/Read-modify-write). Every shared object can be assigned a consensus number, which is the maximum number of processes for which the object can solve wait-free consensus in an asynchronous system.

```
1 Read-write registers
2 Test-and-set, swap, fetch-and-add, queue, stack
⋮ ⋮
∞ Augmented queue, compare-and-swap, sticky byte
```

- [_Consistency models_](https://en.wikipedia.org/wiki/Consistency_model):
  - [_Sequential consistency_](https://en.wikipedia.org/wiki/Sequential_consistency)
  - [_Causal consistency_](https://en.wikipedia.org/wiki/Causal_consistency)
  - [_Eventual consistency_](https://en.wikipedia.org/wiki/Eventual_consistency)
  - [_Monotonic Read Consistency_](https://en.wikipedia.org/wiki/Consistency_model#Monotonic_Read_Consistency)
  - [_Monotonic Write Consistency_](https://en.wikipedia.org/wiki/Consistency_model#Monotonic_Write_Consistency)
  - [_Read-your-writes Consistency_](https://en.wikipedia.org/wiki/Consistency_model#Read-your-writes_Consistency)
  - [_Writes-follows-reads Consistency_](https://en.wikipedia.org/wiki/Consistency_model#Writes-follows-reads_Consistency)
- _Consensus number_. Maximum number of threads for which objects of the class can solve consensus problem.
- [_Logical clock_](https://en.wikipedia.org/wiki/Logical_clock)
- [_Vector clock_](https://en.wikipedia.org/wiki/Vector_clock)

#### [[⬆]](#toc) <a name='cache'>Cache:</a>

- What is _write-through_ and _write-behind_ caching? (write-through (synchronous), write-behind (asynchronous))
- HTTP cache options?

#### [[⬆]](#toc) <a name='networking'>Networking:</a>

- OSI model (Physical, Data link, Network, Transport, Session, Presentation, Application)
- Multithreading vs select
- [_Switch_](https://en.wikipedia.org/wiki/Network_switch), [_hub_](https://en.wikipedia.org/wiki/Ethernet_hub), [_router_](<https://en.wikipedia.org/wiki/Router_(computing)>)
- [_TCP congestion_](https://en.wikipedia.org/wiki/TCP_congestion_control)
- _TCP back-pressure_

#### [[⬆]](#toc) <a name='os'>Operating system:</a>

- What is [_memory mapped_](https://en.wikipedia.org/wiki/Memory-mapped_file) file and its benefits?
- _Interprocess communication_ methods. (Pipes, Events, Mailboxes/Ports (can be implemented by using shared memory and semaphores), Direct Message Passing).
- [_Virtual memory_](https://en.wikipedia.org/wiki/Virtual_memory) organization.
- _Process scheduler_.

#### [[⬆]](#toc) <a name='functional-programming'>Functional programming:</a>

- [_Referential transparency_](https://en.wikipedia.org/wiki/Referential_transparency)
- What is [_Monad_](<https://en.wikipedia.org/wiki/Monad_(functional_programming)>)?

#### [[⬆]](#toc) <a name='reactive-programming'>Reactive programming:</a>

- [_The Reactive Manifesto_](http://www.reactivemanifesto.org) (responsive, resilient, elastic, message driven)
- [Reactive extensions](http://reactivex.io)
- What is _asynchronous_ and _non-blocking_? [link](https://www.linkedin.com/pulse/java-servlets-asynchronous-non-blocking-aliaksandr-liakh)

#### [[⬆]](#toc) <a name='git'>Git:</a>

- _Git_ workflow? (Master: production-ready state; Develop: latest delivered development changes for the next release; Feature Branches; Release Branches; Hotfixes) ![Git workflow](http://nvie.com/img/git-model@2x.png "Git workflow") http://nvie.com/posts/a-successful-git-branching-model/
- What is a rebase?

#### [[⬆]](#toc) <a name='devOps'>DevOps:</a>

- What is _Blue-green Deployment_, _Canary release_, _A/B testing_? [link](https://www.javacodegeeks.com/2016/02/blue-green-deployment.html)
- What is _Docker_?

#### [[⬆]](#toc) <a name='agile'>Agile:</a>

- What is Agile? (http://agilemanifesto.org/principles.html)
  - Individuals and interactions over Processes and tools
  - Working software over Comprehensive documentation
  - Customer collaboration over Contract negotiation
  - Responding to change over Following a plan
- What is Scrum? (Roles: product owner, development team, scrum master. Events: sprint)
- What are the differences between Scrum and Waterfall? ( http://www.leanagiletraining.com/agile/waterfall-versus-scrum-how-do-they-compare/)
- What is XP? ()
- What is Kanban?
- What is Lean development?

#### [[⬆]](#toc) <a name='other'>Other:</a>

- How to find memory leak. (Memory snapshot diff).
- Profiling: sampling and instrumentation.
- Regular expressions. (Examples)
- What are your goals to work in our company? (3 categories: professional, financial, social)
- What is _virtualization_?
- What is total/partial order?
- How to work with legacy code? (http://programmers.stackexchange.com/a/122024)

#### [[⬆]](#toc) <a name='big-data'>Big Data:</a>

- [_Lambda architecture_](https://en.wikipedia.org/wiki/Lambda_architecture)
- [_HyperLogLog_](https://en.wikipedia.org/wiki/HyperLogLog)
- [_Event sourcing_](http://microservices.io/patterns/data/event-sourcing.html)

#### [[⬆]](#toc) <a name='image-processing'>Image processing:</a>

#### [[⬆]](#toc) <a name='cryptography'>Cryptography:</a>

- [_Public-key cryptography_](https://en.wikipedia.org/wiki/Public-key_cryptography)
- [_Public key certificate_](https://en.wikipedia.org/wiki/Public_key_certificate)
- [_Blockchain_](https://en.wikipedia.org/wiki/Blockchain)
- [_Proof-of-work system_](https://en.wikipedia.org/wiki/Proof-of-work_system)
- [_Secret sharing_](https://en.wikipedia.org/wiki/Secret_sharing)
- [_RSA_](<https://en.wikipedia.org/wiki/RSA_(cryptosystem)>)

```
select 2 primes: p,q
n = p*q
phi(n) = (p-1)*(q-1)
select 1<e<phi(n), gcd(e,phi(n))=1
d=e^-1 mod phi(n)
(e,n) - public key
(d,n) - private key
c = m^e mod n
m = c^d mod n = m^(e*d) mod n = m^(e*d mod phi(n)) mod n = m
```

#### [[⬆]](#toc) <a name='security'>Security:</a>

- What is _OpenID and OAuth2.0 and OpenID Connect_?
- Four main actors in an OAuth system (clients, resource owners, authorization servers, and protected resources)
- What is _access_token, refresh_token, SAML token, JWT token_?
- _Sticky session vs Session Replication_.
- What is hash [_salt_](<https://en.wikipedia.org/wiki/Salt_(cryptography)>)?
- What is _Federated Authentication_ ?
- What is _CSP_ and _SRI hash_ ?
- What is _Clickjacking_ and _Cursorjacking_ ? How to prevent it ?
