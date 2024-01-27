Asynchronism

[Overview](https://nerohoop.gitbooks.io/system-design/content/system-design-and-scalability/asynchronism.html)

Back Pressure: 

Back pressure, in the context you've described, relates to a concept in computer science, particularly in systems design and software engineering. It's a flow control mechanism used in distributed systems, especially when dealing with asynchronous data streams or in microservices architectures. The idea is to prevent a system from being overwhelmed by too much data or too many requests.

Here's how it works:

Queue Size Management: A system (like a server) processes requests or data in a queue. Back pressure helps by limiting the size of this queue. This limitation is important because it ensures that the system doesn't take on more work than it can handle, which can lead to slowdowns or crashes.


When the queue reaches its capacity, clients will receive either a **"server busy" message or an HTTP 503 status code,** indicating that they should attempt their request at a later time.


Throughput and Response Times: By maintaining a manageable queue size, back pressure ensures that the system can process requests at a high throughput rate. This means requests are handled efficiently, leading to good response times for those requests that are being processed.


Handling Overload: When the queue is full, new incoming requests are given a 'server busy' response, often indicated by a HTTP 503 status code. This tells the client that the server is currently unable to handle the request due to overload but that the request may be attempted again later.


Client Strategy: Clients receiving a server busy response can employ strategies like 'exponential backoff'. This means they will retry the request after a delay, with the delay period increasing exponentially with each retry. This approach reduces the chance of continuously overwhelming the server and allows the system to recover.
