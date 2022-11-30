### **Phase 1**: _"I'd like to Teach the World to `Ping`"_

You have been provided a list of network assets belonging to RockStar Corp. Use `fping` to ping the network assets for only the Hollywood office.

```
Hollywood Rockstar Corp server list:
15.199.95.91/28 Hollywood Database server
15.199.94.91/28 Hollywood Web Servers
11.199.158.91/28 Hollywood Web Servers
167.172.144.11/32 Hollywood Application Servers
11.199.141.91/28 Hollywood Application Servers
```

  - Determine the IPs for the Hollywood office and run `fping` against the IP ranges in order to determine which IP is accepting     connections.

  - RockStar Corp doesn't want any of their servers, even if they are up, indicating that they are accepting connections.
     - Use `fping <IP Address>` and ignore any results that say "Request timed out".
     - If any of the IP addresses send back a Reply, enter Ctrl+C to stop sending requests.

    ```
    Command used: 
   
    fping 15.199.95.91 15.199.94.91 11.199.158.91 167.172.144.11 11.199.141.91. 

    Results:
    167.172.144.11 is alive
    15.199.95.91 is unreachable
    15.199.94.91 is unreachable
    11.199.158.91 is unreachable
    11.199.141.91 is unreachable
    
    Findings:
    The IP address 167.172.144.11/32 is a vulnerability to the Rockstar Corp because it is responding.  
    The following four 15.199.95.91, 15.199.94.91, 11.199.158.91, 11.199.141.91 are unreachable and 
    do not pose a risk for the Hollywood office.

    OSI Layer:
    This occurred on layer #3 of the OSI model which is the network layer that uses IP addresses. 

    ```
