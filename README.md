# Comparative Summary of Web Infrastructures

## Exercise 0 – Simple Web Stack
- Single server hosting web, application, and database (LAMP-like stack).  
- User accesses the website via DNS pointing to the server IP.  
- All components on one machine.  
- **Issues:** Single point of failure, downtime during maintenance, cannot scale for high traffic.

## Exercise 1 – Distributed Web Infrastructure
- Three servers: 2 app servers + 1 database (Primary + Replica).  
- Load balancer (HAproxy) distributes requests between app servers.  
- Primary handles writes, Replica handles reads.  
- **Benefits:** Redundancy, basic scalability, better availability.  
- **Issues:** SPOF on load balancer and primary database, no monitoring or security, SSL not included.

## Exercise 2 – Secured and Monitored Web Infrastructure
- Three servers with firewalls, monitoring clients, and HTTPS.  
- SSL certificate encrypts traffic.  
- Monitoring tools collect metrics and logs (CPU, memory, requests, errors).  
- **Benefits:** Increased security, encrypted traffic, observability.  
- **Issues:** Terminating SSL at the load balancer exposes internal traffic, single primary database is still a SPOF, same-component servers may waste resources.

## Exercise 3 – Scale Up
- Split architecture: dedicated servers for web, application, and database.  
- Load balancer cluster (HAproxy) for high availability.  
- Web servers handle static content, application servers handle dynamic logic, database handles writes/replication.  
- **Benefits:** Improved scalability, isolation of services, high availability.  
- Design supports horizontal scaling, better resource management, and easier maintenance.

## Overall Evolution
- From a **single-server monolith** (Exercise 0) → **distributed architecture** with load balancing and replication (Exercise 1) → **secured and monitored stack** (Exercise 2) → **fully split and scalable architecture** (Exercise 3).  
- Each step improves **availability, security, observability, and scalability**.
