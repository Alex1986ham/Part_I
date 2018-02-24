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

read more abou json: http://www.json.org
