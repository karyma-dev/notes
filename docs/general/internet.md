# Internet

A technical infrastructure which allows billions of computers to be connected all together. Web servers, email, IRC(Internet Relay Chat) are services built on top of the internet

### How does it work?

- Your computer is connected to a modem via wired or wireless
  - The modem connects your network of computers to the telephone infrastructure
- Modem is connected to an ISP(Internet Service Provider)
  - ISP is a company that manages some special routers that are all linked together and can also access other ISP's routers
  - Any computer linked to a network has a unique address called IP(Internet Provider) address
  - Domain names are alias for IP addresses

### Intranet vs Extranets

- Intranet
  - Private networks that are restricted to members of a particular organization
- Extranet
  - Similar to intranet but opens all or part of a private network to allow sharing and collaboration with other organizations
  - Typically used to safely and securely share information with clients and stakeholders

## Web

- Computers connected to the web are called clients and servers
- Clients are typically web user's internet-connected devices and web-accessing software, other servers may be clients as well
- Servers are computers that store webpages, sites, or apps.
  - When a client access a webpage, a copy of the webpage is downloaded from the server onto the client machine to be displayed in the user's web browser.
- TCP(Transmission Control Protocol) and IP(Internet Protocol) are communication protocols that define how data should travel across the internet
- DNS(Domain Name Servers) are like an address book for websites
- HTTP(Hypertext Transfer Protocol) is an application protocol that defines a language for clients and servers to speak to each other

### What happens when you enter a website

- Browser goes into DNS servers and finds the ip address
- Browser sends an HTTP request to the server, data is sent across the internet connection using TCP/IP
- If server approves of request, the server sends a response code and data in a series of chunks called data packets
- Browser assembles these data packets into a complete webpage and displays it
- HTML > DOM > CSS > JAVASCRIPT, order of which things get parsed

### Difference between webpage, website, web server and search engine

- Webpage
  - A document which can be displayed in a web browser such as Firefox, Google Chrome, Opera, Microsoft Internet Explorer or Edge, or Apple's Safari
- Website
  - A collection of web pages which are grouped together and usually connected together in various ways.
- Web Server
  - A computer that hosts a website on the Internet
  - May contain multiple websites
- Search Engine
  - A web service that helps you find other web pages and are normally accessed through a web browser
