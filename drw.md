
## Self Intro
my name is April. I am a full stack software engineer. Before my career transition, I used to be a commercial director and I shot videos for tech products so I was like, instead of promoting them, why not build them myself. My boyfriend works as a senior software engineer at Facebook, and sometimes I would ask him for some programming puzzles and solve them on napkins. That’s how my interest got started.
After taking a coding bootcamp and working on a lot of smaller projects, I started building more and more real-world apps. So I worked for a startup as an intern for their mobile app Blismo which serves local businesses, and on the side I worked with 2 other engineers on a website called pointer.ai. Later on I founded my own startup so I can give some branding to the two apps I invented, built and launched. 


## Why this school?

## Thread vs Process

- **Thread** is the smallest execution unit of executionfor cpu. For example a program want to do different things, and c
PU cdoesnt have to wait for one task to finish while it's asking for resource etc. so the cpu can just go on and execute the next thread. yes. 

actually i once was working on the ppointer.ai project, i had to generate two optimal learning plans for the user. and this is very time costly, so i used the multiprocessing module in python to generate two paths simula . so i can save half the time. 

there could be race conditions if we are accessing the same resource. at

- **Process** is the program which is actively running, including its threads
- **Program** is a set of instructions, represented by code that can executed plus its data


i have several interviews but nothing final stage 



whats; your daily schedule look like


## what is deadlock?
Deadlock is a situation where a set of processes are blocked because each process is holding a resource and waiting for another resource acquired by some other process. ... Similar situation occurs in operating systems when there are two or more processes hold some resources and wait for resources held by other(s).

so basically i need to remove any of these deadlock conditions / usually we focus on circular wait issues to resolve the deadlock. 

basically circular wait means A waits for B, and B waits for A. I think most algorithms focus on preventing this particular issue


maybe we can use id 

## asynchronous vs synchronous
Synchronous basically means that you can only execute one thing at a time. Asynchronous means that you can execute multiple things at a time and you don’t have to wait for the current task in order to move on to next one.

## what is a race condition?
A race condition occurs when two or more threads can access shared data and they try to change it at the same time. Because the thread scheduling algorithm can swap between threads at any time, you don’t know the order in which the threads will attempt to access the shared data. 


Therefore, the result of the change in data is dependent on the thread scheduling algorithm, i.e. both threads are “racing” to access/change the data.
Problems often occur when one thread does a “check-then-act” (e.g. “check” if the value is X, then “act” to do something that depends on the value being X) and another thread does something to the value in between the “check” and the “act”. E.g:
if (x == 5) // The “Check”
{
   y = x * 2; // The “Act”
   // If another thread changed x in between “if (x == 5)” and “y = x * 2" above,
   // y will not be equal to 10.
}
The point being, y could be 10, or it could be anything, depending on whether another thread changed x in between the check and act. You have no real way of knowing.
In order to prevent race conditions from occurring, you would typically put a lock around the shared data to ensure only one thread can access the data at a time. This would mean something like this:
// Obtain lock for x
if (x == 5)
{
   y = x * 2; // Now, nothing can change x until the lock is released.
              // Therefore y = 10
}
// release lock for x

it can be just instance variable on the resource. for example it's a object and then i have a boolean state indicate locked

i think as soon as we start updating the resource , we should change the value of that locked state. to prevent such situation. 
maybe we can update it ahead of time, and a scheduler can put a lock even before we start accessing the locked state.

##  favorite data strucuture and why?
Tree, because it's simple enough to understand but also can be very powerful when being extended. For example, it can be used to store dictionary and support quick search

## how would u implement ur favorite data strucuture
I would have a Node class to represent that tree node, and 


>## database ACID
 ACID is a set of properties that you would like to apply when modifying a database.
- Atomicity
- Consistency
- Isolation
- Durability
A transaction is a set of related changes which is used to achieve some of the ACID properties. Transactions are tools to achieve the ACID properties.
Atomicity means that you can guarantee that all of a transaction happens, or none of it does; you can do complex operations as one single unit, all or nothing, and a crash, power failure, error, or anything else won’t allow you to be in a state in which only some of the related changes have happened.
Consistency means that you guarantee that your data will be consistent; none of the constraints you have on related data will ever be violated.
Isolation means that one transaction cannot read data from another transaction that is not yet completed. If two transactions are executing concurrently, each one will see the world as if they were executing sequentially, and if one needs to read data that is written by another, it will have to wait until the other is finished.
Durability means that once a transaction is complete, it is guaranteed that all of the changes have been recorded to a durable medium (such as a hard disk), and the fact that the transaction has been completed is likewise recorded.
So, transactions are a mechanism for guaranteeing these properties; they are a way of grouping related actions together such that as a whole, a group of operations can be atomic, produce consistent results, be isolated from other operations, and be durably recorded.
## 2019(10-12月) 码农类General 硕士 实习@DRW - 网上海投 - 技术电面  | Other | fresh grad应届毕业生
 来吐槽一下一个神奇的公司，DRW。 广发oa，看到地里很多小伙伴都做了。意外的收到了电面，上周四面的，没有做题，就是聊简历聊得非常非常细，确保上面每个project你都做了，然后问了非常基础的data structure和OOD。小哥很nice的给我介绍了半天他们的业务，感觉很有passion。最后说很快会有结果，问我有没有别的deadline什么的。周三的时候我发了封邮件给recruiter问问情况，今天给我回复说，这个position on hold了，如果reopen再通知我，也不知道是真的还是给我委婉拒了, move on。
Sherlinhhh 发表于 2020/03/11 11:13:09
请问基础的data structure 和OOD是什么呀
> override，overload，hashmap，array和linkedlist区别?
Method overloading deals with the notion of having two or more methods in the same class with the same name but different arguments.
Method overriding means having two methods with the same arguments, but different implementations. One of them would exist in the parent class, while another will be in the derived, or child class. The @Override annotation, while not required, can be helpful to enforce proper overriding of a method at compile time.
- array : An array is used to store a collection of data, but it is often more useful to think of an array as a collection of variables of the same type.
- hashmap : HashMap is a Map based collection class that is used for storing Key & value pairs, it is denoted as HashMap<Key, Value> or HashMap<K, V>. ... It is not an ordered collection which means it does not return the keys and values in the same order in which they have been inserted into the HashMap.
- linked list : A linked list is a common data structure made of a chain of nodes in which each node contains a value and a pointer to the next node in the chain. The head pointer points to the first node, and the last element of the list points to null.
> Differences between Array and Vector
- Vector is better for frequent insertion and deletion whereas Arrays are much better suited for frequent access of elements scenario. Vector occupies much more memory in exchange for the ability to manage storage and grow dynamically whereas Arrays are memory efficient data structure.
### 2019(1-3月) 码农类General 硕士 全职@DRW - 网上海投 - 技术电面  | Fail/Rej | fresh grad应届毕业生
以下内容需要积分高于 100 您已经可以浏览
是 Trading System Developer的職位
先問履歷的上的問題、過去工作經驗
接著問OS及C++相關的問題 單純問答題
> Heap、Stack ?
- An abstract data type is defined by its behavior (semantics) from the point of view of a user, of the data, specifically in terms of possible values, possible operations on data of this type, and the behavior of these operations.
時不時會問操作時間複雜度
解釋 Hashmap如何實現
最後寫代碼考用位運算判斷二的倍數
麻煩同學加米 很多帖看不了 感謝！
> hashing function is (cityhash, CRC32, Murmurhash(ruby used))
> cryptographic: blowfish...)
- must be deterministic
- uniform distributed
- one way function (highly sensetive) (no way back)
- Disperated

#### [[⬆]](#toc) <a name='architecture'>Architecture:</a>

- **Design principles**

  - DRY: Do not Repeat Yourself, write reusable code
  - KISS: Keep It Simple, Stupid
  - Separation of Concerns: Separate program into different sections(folder / file) for different purpose

    - Why?
      - Easier to add new feature
      - Easier to optimize
      - Easier to test
      - Fixing and debugging are easier because each piece are independent

  - Single source of truth: Structure data models so that every data is only kept at once place and any usage of that data should be by reference only.

- **REST**(Representational state transfer) Every URI refers to a resource, and through the verbs GET, POST, PUT, DELETE, the client can operate on the resource on the server
- **RPC** is usually used for data transmission between service and service. And usually each RPC Url corresponds to a function, instead of a resource. It's similar to calling a function remotely
- **Microservices** are a style of software architecture that divide the system into small and independent services that collaborate with each other. (for example you have a Python program handles machine learning, but Ruby on Rails program serves as webserver, and they communicate with each other using, say RPC)

  - Pros of _microservices_:
    - The services are easy to replace;
    - Services can be implemented using different programming languages, databases, hardware and software environment, depending on what fits best

- **Idempotent operation** Idempotent means no matter how many times we run the operation, the result will be the same. PUT and DELETE http methods are idempotent for example. And say, we have an API for sending payment, then it should take a signature, otherwise the payment could be retried and sent multiple times.

- Why do you need **Web Server**? Web server is used to serve the static files of the website, such as HTML, JavaScript and CSS so the user can load the UI for the website

- **Inheritance vs Composition**

  - Inheritance means some type belongs to another more generic type, for example, Apple is a fruit. It's called "is-a" relationship
  - Composition means a class can have many parts of code, and those parts can be reused in other classes. So it's more of a "has-a" relationship. Like "Bird has the fly functionality and so does plane"
  - Usually we prefer composition over inheritance, because the child class wont be have to tightly coupled with the parent class, and also helps separation of concerns. Most programming languages also dont support multiple inheritance, and it's very confusing when used.

- Advantages of using **Modules**.
  - Make the code reusable
  - Decouple the code into independent pieces so different places can mix and use them
  - Also it uses namespace so it can provide similar but different functionality under different namespace ( `ModuleA::print` vs `ModuleB::print` )

#### [[⬆]](#toc) <a name='concurrency'>Concurrency:</a>

- **Pre-emptive** Scheduler switch back and forth between different sequence of instructions (threads)
- **Scheduler** Scheduler is a software component that controls the order of threads that get into the CPU to be executed. Scheduler will manage the priority for different threads and assign it to the CPU.
- **Thread vs Process vs Program**
  - **Thread** is the smallest execution unit of execution
  - **Process** is the program which is actively running, including its threads
  - **Program** is a set of instructions, represented by code that can executed plus its data
- **Multi-threading**

```
A CPU is giving the illusion that it's doing multiple comuptations at the same time. 
It does that by spending a bit of time on each computation. 
And thread is the execution context for each computation. So many tasks can share te same CPU. 
(e.g. Word will have one thread for keyboard input, one thread for rendering, another for saving files etc)
```

- **Multiprocessing vs Multithreading**

#### [[⬆]](#toc) <a name='web'>WEB:</a>

- [_MVC_](https://open.appacademy.io/learn/swe-in-person/rails/diagram-of-rails)
- [_API_](https://open.appacademy.io/learn/swe-in-person/rails/what-is-an-api-)
- What happens when you type in a URL in browser? [_Answer_](https://open.appacademy.io/learn/swe-in-person/career-quest/http-request-question)
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

#### [[⬆]](#toc) <a name='general'>General Questions:</a>

- [_Polymorphism_](<https://en.wikipedia.org/wiki/Polymorphism_(computer_science)>) (Variable of type Shape could refer to an object of type Square, Circle... Ability of a function to handle objects of many types)
- [_Encapsulation_](<https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)>) (Packing of data and functions into a single component)
- [_Virtual function_](https://en.wikipedia.org/wiki/Virtual_function) (Overridable function)
- [_Virtual method table_](https://en.wikipedia.org/wiki/Virtual_method_table)
- [_Dynamic binding_](https://en.wikipedia.org/wiki/Late_binding) (Actual method implementation invoked is determined at run time based on the class of the object, not the type of the variable or expression)
- How does [_garbage collector_](<https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)>) work? (Mark and sweep: mark: traverse object graph starting from root objects, sweep: garbage collect unmarked objects. Optimizations: young/old generations, incremental mark and sweep)
- [_Tail recursion_](https://en.wikipedia.org/wiki/Tail_call) (A tail call is a subroutine call performed as the final action of a procedure)
- [_Semantic versioning_](http://semver.org)

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
