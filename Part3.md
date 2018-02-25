# Servers & Clients

- HTTP: hypertext transfer protocol
- URI Uniform Resource Identifieer (is more precise than URL)
- URL Uniform Resource Locator
- DNS Domain Name Service (maintained by Internet Service Providers (ISPs) and other network users - to look up hostnames and get bac 
get back IP addresses.
- host www.google.com (to look up IP address of the server)
- nslookup could also be used as host
- nslookup localhost (to look up your own IP)
- 443 is the default port of a server

from http.server import HTTPServer, BaseHTTPRequestHandler


class EchoHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        # First, send a 200 OK response.
        self.send_response(200)

        # Then send headers.
        self.send_header('Content-type', 'text/plain; charset=utf-8')
        self.end_headers()

        # Now, write the response body.
        self.wfile.write(self.path[1:].encode())

if __name__ == '__main__':
    server_address = ('', 8000)  # Serve on all addresses, port 8000.
    httpd = HTTPServer(server_address, EchoHandler)
    httpd.serve_forever()



>>> from urllib.parse import urlparse, parse_qs
>>> address = 'https://www.google.com/search?q=gray+squirrel&tbm=isch'
>>> parts = urlparse(address)
>>> print(parts)
ParseResult(scheme='https', netloc='www.google.com', path='/search', params='', query='q=gray+squirrel&tbm=isch', fragment='')
>>> print(parts.query)
q=gray+squirrel&tbm=isch
>>> query = parse_qs(parts.query)
>>> query
{'q': ['gray squirrel'], 'tbm': ['isch']}


Idempotence
Vocabulary word of the day: idempotent. An action is idempotent if doing it twice (or more) produces the same result as doing it once. "Show me the search results for 'polar bear'" is an idempotent action, because doing it a second time just shows you the same results. "Add a polar bear to my shopping cart" is not, because if you do it twice, you end up with two polar bears.


## JSON

read more about json: http://www.json.org

## HTTP Cache

read more http cache: https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching

## Cookies

read more: https://docs.python.org/3/library/http.cookies.html

## HTTPS

SSL (Secure Sockets Layer) old version for encoding http trafic
TSL (Transport Layer Security) new version for encoding http trafic

certificate authority (CA) acts like a Notar and gives a certification to the server and says that this server is who he is

## How does TLS assure integrity?

Every request and response sent over a TLS connection is sent with a message authentication code (MAC) that the other end of the connection can verify to make sure that the message hasn't been altered or damaged in transit.

Resources
Here are some handy resources for learning more about HTTP:

Mozilla Developer Network's HTTP index page contains a variety of tutorial and reference materials on every aspect of HTTP.
The standards documents for HTTP/1.1 start at RFC 7230. The language of Internet standards tends to be a little difficult, but these are the official description of how it's supposed to work.
The standards documents for HTTP/2 are at https://http2.github.io/.
If you already run your own web site, Let's Encrypt is a great site to learn about HTTPS in a hands-on way, by creating your own HTTPS certificates and installing them on your site.
HTTP Spy is a neat little Chrome extension that will show you the headers and request information for every request your browser makes.
