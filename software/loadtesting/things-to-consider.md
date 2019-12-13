This document provides a check list to consider when performing load testing or performance enhancements on back-end systems.


Check list for servers
Consider the following for each server in the architecture:

Is CPU 100% Utilized during load testing?

Is memory 100% Utilized during load testing?

 


Check list for the database server ( In case of PostgreSQL)
Consider the following:

is the max_connection > users?

i.e in case the number of concurrent users is 300, can the database have 300 connection open at the same time?

Noting that this is not a rigid rule, for the following reasons:

because some applications open multiple threads to be able to serve only one request

and in this case, X number of connections will be needed for each user, then 300 * X connections will be needed to the database server.

and in some other cases, the application can respond in less than 1 second for the same request

and in this case the number of connections to the database can be less than 300


Check list for the database connection pool
Consider the following:

Since each database connection pool has min and max number of connections configuration

is the min number of connection > users?

Always set max number of connections == min when doing the load testing, to be able to let the load testing results be configurable.

 


Check list for the application server thread pool
Consider the following:

Since each application server has a thread pool for serving requests, and has min and max number of threads configuration

is the min number of connection > users?

Always set max number of connections == min when doing the load testing, to be able to let the load testing results be configurable.

 


Check list for the Hardware specifications for servers
Consider the following:

is hardware specifications same as requested or not? and in terms of the following

CPU Cores

RAM Available

Hard disk storage and speed (HDD, Standard SSD or Premium SSD)

 


Check list for the Hardware specifications for the load testing Machine
Consider the following:

is hardware specifications same as requested or not? and in terms of the following

CPU Cores

RAM Available

Hard disk storage and speed (HDD, Standard SSD or Premium SSD)

is CPU 100% utilized during load testing?

is memory utilization 100% during load testing?
