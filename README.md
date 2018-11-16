1. Clone the repo.
2. cd into it.
3. Run npm i <node version 8.11.4 and above>

4. npm start to start the application - default port is 8087

http://localhost:8087/top/10  to get the words 

5. commit 51d1a2e4a16cc9011fa5a81e432154f2a2b8d5d0 - calls dict API sequentially, has bad performance due to waiting avg response 10 sec for 10 words

6. Latest commit uses parallel calls. tested till
  15 top elements. Response time is constant 2 secs
  100 top elements . Response time is under 3 secs
  200 top elements . Response time is under 3 secs
  
7. File read and processing time is under 800ms, most expensive part is still the network call.
  
TBD  - test cases, handle file as stream if too big in memory impact, more error handling
