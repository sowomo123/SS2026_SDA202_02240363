# ###1. Problem Statement
- The main problem in here is URL shortening system such as TinyURL , the goal for them is to convert the long URL into short URL , manageable links and ensure that users can be redirected back to the original URL when needed.

### my understanding 
This problem is related more with designing a large-scale distrubution system that meets the requirments of the actual practice, Discarding the correctness of the code, it focus more on how the system runs or face when the millions of users are using it at the same time. To accomplish this the system give out the equal to to many server to prevent this situsation where one server is overwhelmed.
Caching techniques is use to store the large number of data and to ensure the system is capable of responding as fast as posible without any failuer 

### 2. Analysis of the Author’s Solutions

#### 1. High-Level Design

According to the author, in high-level design which includes the use of REST APIs, a POST request, a GET request, HTTP status codes, etc. The status codes include 301, which is a permanent redirect, and 302, which is a temporary redirect.

#### 2. Back of the Envelope Estimation

According to the author, the system will handle can handle about 100 million URLs per day. In a span of 10 years, this will result in a total around 365 billion records where the system  need around 365 TB of storage space.

#### 3. Data Storage Design
used  a relational database which store the  unique ID, the short URL, and the long URL, it helps in organizing and fetching data efficiently.

#### 4. URL Shortening Flow
first the  system does is to check if the given long URL already exists or not. If it is not there  it will generate a unique ID. This unique ID will be changed  into Base62 to create a short URL that is user-friendly. Then it will be stored.

#### 5. URL Redirecting Flow

In the process of URL redirecting, the system will first check the cache to obtain the long URL in a timely fashion. Then, if the information is not found in the cache, the system will access the database. The load balancer is utilized to distribute the requests to the multiple servers to achieve better performance, scalability, and reliability of the system.

### Review of the Analysis (Short)

The chapter provides guidance on designing a URL shortener system in an easy-to-understand manner. It demonstrates how to shorten URLs as well as handle huge amounts of traffic efficiently

The solutions, such as using APIs, Base62 encoding, caching, and databases, are feasible and applicable. However, some sections on Bloom filters and ID generation are not well described, which makes them confusing

The chapter provides a good understanding of system design, but some topics are advanced, requiring further learning.

### My Confusions
i was not able to understand the concept of databse choice.



### Topics for Further Exploration
- NoSQL databases (MongoDB, Cassandra)
- Database sharding techniques

### Brief Summary of Critical Analysis
The chapter provides a simple yet practical guide to how to design a URL shortener. It covers important concepts such as API design, hashing, scalability, and caching in a simple yet easy-to-understand manner. The use of Base62 encoding and caching provides a practical example of how the system is used.
# ###1. Problem Statement
- The main problem in here is URL shortening system such as TinyURL , the goal for them is to convert the long URL into short URL , manageable links and ensure that users can be redirected back to the original URL when needed.

### my understanding 
This problem is related more with designing a large-scale distrubution system that meets the requirments of the actual practice, Discarding the correctness of the code, it focus more on how the system runs or face when the millions of users are using it at the same time. To accomplish this the system give out the equal to to many server to prevent this situsation where one server is overwhelmed.
Caching techniques is use to store the large number of data and to ensure the system is capable of responding as fast as posible without any failuer 

### 2. Analysis of the Author’s Solutions

#### 1. High-Level Design

According to the author, in high-level design which includes the use of REST APIs, a POST request, a GET request, HTTP status codes, etc. The status codes include 301, which is a permanent redirect, and 302, which is a temporary redirect.

#### 2. Back of the Envelope Estimation

According to the author, the system will handle can handle about 100 million URLs per day. In a span of 10 years, this will result in a total around 365 billion records where the system  need around 365 TB of storage space.

#### 3. Data Storage Design
used  a relational database which store the  unique ID, the short URL, and the long URL, it helps in organizing and fetching data efficiently.

#### 4. URL Shortening Flow
first the  system does is to check if the given long URL already exists or not. If it is not there  it will generate a unique ID. This unique ID will be changed  into Base62 to create a short URL that is user-friendly. Then it will be stored.

#### 5. URL Redirecting Flow

In the process of URL redirecting, the system will first check the cache to obtain the long URL in a timely fashion. Then, if the information is not found in the cache, the system will access the database. The load balancer is utilized to distribute the requests to the multiple servers to achieve better performance, scalability, and reliability of the system.

### Review of the Analysis (Short)

The chapter provides guidance on designing a URL shortener system in an easy-to-understand manner. It demonstrates how to shorten URLs as well as handle huge amounts of traffic efficiently

The solutions, such as using APIs, Base62 encoding, caching, and databases, are feasible and applicable. However, some sections on Bloom filters and ID generation are not well described, which makes them confusing

The chapter provides a good understanding of system design, but some topics are advanced, requiring further learning.

### My Confusions
i was not able to understand the concept of databse choice.



### Topics for Further Exploration
- NoSQL databases (MongoDB, Cassandra)
- Database sharding techniques

### Brief Summary of Critical Analysis
The chapter provides a simple yet practical guide to how to design a URL shortener. It covers important concepts such as API design, hashing, scalability, and caching in a simple yet easy-to-understand manner. The use of Base62 encoding and caching provides a practical example of how the system is used.