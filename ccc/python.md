---
layout: kab
title: Python
group: ccc
---
### Python

#### Script for on-demand, throw-away https server
```
# taken from http://www.piware.de/2011/01/creating-an-https-server-in-python/
# and https://gist.github.com/dergachev/7028596
# generate server.pem with the following command:
#    openssl req -new -x509 -keyout server.pem -out server.pem -days 365 -nodes
# run as follows:
#    python yourscriptname.py
# then in your browser, visit:
#    https://localhost:4443 -or- https://hostipaddress:4443

import BaseHTTPServer, SimpleHTTPServer
import ssl

httpd = BaseHTTPServer.HTTPServer(('', 4443), SimpleHTTPServer.SimpleHTTPRequestHandler)
httpd.socket = ssl.wrap_socket (httpd.socket, certfile='./server.pem', server_side=True)
httpd.serve_forever()
```
<br/>
<br/>
<br/>
