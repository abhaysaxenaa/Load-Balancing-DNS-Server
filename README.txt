Name: Malav Doshi
Netid: 

Name: Abhay Saxena
Netid: ans192

1. We handled the TS querying system by having two lists in LS, corresponding to the hostnames of each TS. When LS receives a new query from the Client, it first checks if that hostname exists in either of the TS lists (used the hash() function). If it does, LS requests for the specific IP address from that respective TS. If the hostname does not exist in either of the TS lists, LS arbitrarily sends the hostname to one of the TS servers (using an alternating indicator variable). From the moment LS sends the request to the TS, there is a timeout set (about 3 seconds) and if LS does not get back a response, potentially due to the TS dropping the connection, it sends the hostname to the other TS. If neither of the TS's respond to the LS within the specified timeout, LS sends a response back to the Client saying "hostname - Error:HOST NOT FOUND".

2. There are no known issues or bugs in the code. The code is bulletproof, made to be as intuitive as possible.

3. A few problems faced included: Getting the correct IP addresses for when there are 10+ hostnames provided (as it was an unexpected bug from the previous project). Another problem was how the program proceeded when one of the TS servers quit due to an error. These issues were successfully fixed.

4. This final project was a great learning experience, as we learnt how a Load-Balancing Server truly works, and how making it resilient to errors such as killing TS processes, avoiding redundant requests to the main Google and Cloudfare servers, as well as handling timeouts was a fun and inciteful experience.
