# Adding-HTTP-Security-Headers-Using-Lambda-Edge
Adding HTTP Security Headers Using Lambda@Edge and Amazon CloudFront

***Description:***

Response headers are added to improve the security and privacy of both viewers and content providers. Security headers are a group of headers in the HTTP response from a server that tell your browser how to behave when handling your site’s content.Adding security response headers is often achievable by modifications to your application configuration. Here we will achieve the same result when you have an application that can’t be modified at the origin (e.g., a web site hosted in Amazon S3).

***Lambda@Edge*** provides the ability to execute a Lambda function at an Amazon CloudFront Edge Location. You can run a Lambda@Edge function in response to four different CloudFront events.

Step 1: Create a lambda function and reate a new role from policy template *Basic Edge Lambda permissions*. Select runtime as Node.js 12.x

Step 2: Add trigger to the lambda function. Select the distribution name and add cloudfront event as ***Origin Response***

Step 3: Add code in the code section.

Strict Transport Security: informs browsers that the site should only be accessed using HTTPS, and that any future attempts to access it using HTTP should automatically be converted to HTTPS.

Content-Security-Policy: Used  to enhance the security of the document (or web page). 

X-Content-Type-Options: is a marker used by the server to indicate that the MIME types advertised in the Content-Type headers should be followed and not be changed. The header allows you to avoid MIME type sniffing by saying that the MIME types are deliberately configured.

X-Frame-Options : sed to indicate whether or not a browser should be allowed to render a page in a <frame> , <iframe> , <embed> or <object> . Sites can use this to avoid click-jacking attacks, by ensuring that their content is not embedded into other sites.
 
X-XSS-Protection: is a feature of Internet Explorer, Chrome and Safari that stops pages from loading when they detect reflected cross-site scripting (XSS) attacks
 
Referrer-Policy: is a security header that can (and should) be included on communication from your website's server to a client. The Referrer-Policy tells the web-browser how to handle referrer information that is sent to websites when a user clicks a link that leads to another page or website.
 
 
Step 4: The status of my distribution changes to In Progress for the duration of the replication (typically 5 to 8 minutes)

  ![image](https://user-images.githubusercontent.com/59678465/169502653-e3d882fd-3fb0-48c5-9190-5e5010b9da38.png)
  
  
  
  
 Referred: https://aws.amazon.com/blogs/networking-and-content-delivery/adding-http-security-headers-using-lambdaedge-and-amazon-cloudfront/
