#### Continue Learning Notes - 5

######  Continue: Thursday 12th July
+ *How the web works* lesson explains how browsers connect to a server to retrieve web pages. Describes the role of domains, IPs, DNS(Domain Name System) and host servers. What is the headers and body requests and response cycle.

>* to check the IP of a website, open the terminal `ping www.facebook.com` and it will print the IP address. To quite press `ctrl+c`. I can then take that number and drop it in the browser web address and it will take me to facebook.
>* Humans can't remember all the IP addresses out there and that is why the DNS is extremely useful. It searches for the IP address and send it back to us.
>* To check your own IP address type `curl ifconfig.me` in terminal.
>* After testing `curl ifconfig.me` it is very slow and I researched if there is an alternative and `curl v4.ifconfig.co` instantly prints your IP.
>* Now we have the IP address for the website we need to access. Our browser connects to the host server and asks for permission to access content. This is called *Request*.
>* The way our browser asks for content is to provide an *HTTP header* in the request. This header is text content that contains information about our browser among other things.
>>* The HTTP protocol supports different request methods such as GET, PUT, PATCH, POST, and DELETE. In our www.facebook.com case our browser made a GET request meaning we simply want to get back some content and we are not posting or providing any content ourselves.
>>* Servers use status codes defined as a three digit number. This number determines the state of the request and gives insight into the success or failure of your request. The most common code you see when browsing the web is 200 meaning your request was successful.
>>* Request Headers which includes our User-Agent details. This gives the server information about our operating system and our browser.
>* If the server accepts your request it will send back a response. The response comes in the form of another header and a body.
>* Response body shows the HTML content that was sent back to our browser. The response body comes in form of HTML, CSS, or JavaScript code.
>* When this content is received by our browser, it begins to render the webpage content from this code.

Few *__protocols__* to know about:
>* Hypertext transfer protocol => HTTP
>* File transfer protocol => FTP

Two of the most important protocols:
>* Transmission control protocol => TCP
>* Internet protocol => IP

>* Internet service provider => ISP.
>>* The ISP routes the request to a server further up the chain on the Internet. Eventually, the request will hit a domain name server (DNS).
>>* This server will look for a match for the domain name you've typed in. If it finds a match, it will direct your request to the proper server's IP address. If it doesn't find a match, it will send the request further up the chain to a server that has more information.
>>* The request will eventually come to our Web server. Our server will respond by sending the requested file in a series of packets.
>>* Packets are parts of a file that range between 1,000 and 1,500 bytes. Packets have headers and footers that tell computers what's in the packet and how the information fits with other packets to create an entire file.
>>* Each packet travels back up the network and down to your computer.

+ Local VS Remote
>* Local or client-side refers to your computer.
>* Remote or server-side refers to a computer that is somewhere else in the world. In the case of the web this is typically a web server.

+ Front-End VS Back-End
>* Front-end development refers to writing the code that is interpreted by the browser locally (client-side). HTML, CSS, and JavaScript are front-end languages.
>* Back-end development refers to any programming language running on the remote server. Ruby, PHP, Node, Python, Java, ASP.NET, as well as database query languages like SQL are common programming languages that run server-side.

__Summary:__
>* DNS servers associate a domain name with a particular IP address.
>* IP addresses define the unique location of a computer on the internet.
>* The communication between your browser and servers is done through the request and response cycle, which is made up of headers and a response body made up of HTML, CSS, or JavaScript.

+ Also, I worked on *__HTML Fundamentals__* and I create a website along with the instructor. Next lesson contains lots of HTML resources and I want to check them.
>* HTML Language Code Reference, ISO Language codes. Check it on https://www.w3schools.com/tags/ref_language_codes.asp

######  Saturday 14th July
+ Today I worked on *__HTML Album Cover__* and the rest of this section *__Front-End HTML Fundamentals__*. Next section in *__Intro to HTML/CSS__* is *__Front-End CSS Introduction__*.

+ I learned about a new tag `<span></span>` plus previously `<img>`, `<h1></h1>` to `<h6></h6>`, `<p></p>` and `<a></a>`. All of the previous tags have an opening and closing tags except `<img>` is a self closing tag. I also learned about attributes where we can add them in the opening tag to provide more information about the tag.
