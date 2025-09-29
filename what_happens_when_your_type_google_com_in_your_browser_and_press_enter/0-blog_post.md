# What happens when you search ```www.google.com```  and press Enter

The thing we do every day, open a browser, type a URL, and press Enter. And yet, have you ever wondered what the behind the scenes are when you go to a website on google? The small amount of time it takes for this complex chain of events to work. Traveling across networks, servers and sstems just to deliver the page to your screen.

# DNS lookup
The very first thing  your browser needs to do is where ```www.google.com``` actually exists on the internet. Computers communicate using numerical IP addresses which are not human-readable domain names. This is where the Domain Name System (DNS) makes its debut, acting like the internet's phonebook.

- The browser checks if it knows the IP address
- if it doesn't, it asks the operating system
- If the computer doesn't know it sends a request to DNS server
- The DNS server looks it up and returns Google's IP address.

# TCP and connection
Now with Google's IP address, the browser wants to talk to Google's server using TCP/IP

TCP (Transmission Control Protocol) handles the connection. It makes sure everything is delivered reliably and in order, This actually happens through a process called the TCP three-way handshake. 

1. **Synchronize**: Computer says "Hi"
2. **Synchronize-Acknowledge**:  Google responds "Hi, got your message"
3. **Acknowledge**: You confirm

# Firewall Check 
Before the request makes it to the Google servers it will need to pass many firewalls.


- Your own computer or network may have a firewall that checks outgoing traffic.

- Google’s data centers definitely have firewalls that look at incoming requests to block anything suspicious, like hacking attempts or spamming bots.


# HTTPS and SSL 
You typed ```https://``` in your browser which sets a secure and encrypted connection with Google using SSL/TLS.

- Browser and Google exchange information to agree on how to encrypt the data 
- Google sends its SSL certificate which your browser checks to make sure is real.
- They create a shared encryption key so all communication is private and secure.

# Load-balancer 
Now your secure request reaches Google but doesn't go straight to a server, instead it meets a load-balancer first.

Google has thousands of servers or more and the load-balancer's job is to figure out which of the servers should handle your requests. It looks for things like 

- How busy each server is 
- Your location to reduce loading time
- Server health

# Web server

The server that gets your request runs a web server like Ngix or Google's own system, the web server is the piece that handles HTTP requests.


# Application server
Now we reach the back end, this is where the logic lives.

The application handles things like:
- Processing your search
- Figuring what kind of results to show
- Talking to other internal services

# Database
The app server might need to look up data such as recent search trends, previous serches, if you're logged in. This is where database comes in.

The app server queries the database, grabs the information it needs and builds the response.

# Response
Once everything is ready the data flows back:
- From the app server 
- To the web server
- Through the load balancer
- Over the HTTPS
- And finally back to your browser

The browser renders the page, displays the familiar Google logo, a seach box and perhaps some personalized elenents.

All of this happens in less than a second.

# Epilogue
 The next time you find yourself typing ```https://www.google.com``` i hope you remember that your request just traveled across the internet, hit multiple layers of security and logic, talked to several powerful systems and the came back in a literal blink of an eye.

