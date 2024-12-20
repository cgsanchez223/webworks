1. What is HTTP?
Hyper Text Transfer Protocol - transfers data between server and client

2. What is URL?
Uniform Resource Locator - an address for websites

3. What is a DNS?
Domain Name System - converts URLs to IP addresses

4. What is a query string?
Allows you to give instructions to the website. Allows you to pass key-value pairs into the URL.

5. List two HTTP Verbs and their use cases:
GET - Entering URL in browser, clicking links, and form submission. Gets data from server.
POST - Sends data to sever. Arguments sent as body of request. Change data.

6. What is an HTTP request?
A request from a client to a server which follows the HTTP protocol. Such as using the search bar on a website.

7. What is an HTTP response?
A response from a server to a client that did the HTTP protocol. Gives back results from a search.

8. What is an HTTP header? Give examples
In VSCode when coding using HTML, the header contains information about the parameters of the page that is usually not visible. The visible portion is the title which appears on the tab of the page.
Types of request headers are host, user-agent, cookies, and cache-control. Response headers are content-type, last-modified, set-cookie, and cache-control.

9. What are the processes that happen when you type “http://somesite.com/some/page.html” into a browser?
The DNS converts the URL into a IP address. The IP address receives a request for header information. This can include cookies, cache, user name info and host info. The server will then send a response code to allow or deny access. The browser makes a DOM file and interprets HTML, images, CSS or other languages. The browser sends request for each resource and receives back responses for each of them.

______________________________________________________________________________
Part 2:
1. Using curl, make a GET request to the icanhazdadjoke.com API to find all jokes involving the word “pirate”

$ curl -H "Accept: application/json" https://icanhazdadjoke.com/search?term=pirate
{"current_page":1,"limit":20,"next_page":1,"previous_page":1,"results":[{"id":"SvzIBAQS0Dd","joke":"What did the pirate say on his 80th birthday? Aye Matey!"},{"id":"QuscibaMClb","joke":"What does a pirate pay for his corn? A buccaneer!"},{"id":"2gii3LeN7Ed","joke":"Why couldn't the kid see the pirate movie? Because it was rated arrr!"},{"id":"SnOf2gqjiqc","joke":"Why are pirates called pirates? Because they arrr!"},{"id":"exXSCtkOKe","joke":"Why do pirates not know the alphabet? They always get stuck at \"C\"."}],"search_term":"pirate","status":200,"total_jokes":5,"total_pages":1}



2. Use dig to find what the IP address is for icanhazdadjoke.com
172.22.192.1#53(172.22.192.1)
104.21.66.15
172.67.198.173
(I was not sure which one was the IP address)



3. Make a simple web page and serve it using python3 -m http.server. Visit the page in a browser.

(not sure how to provide the answer here. I used the index.html in the folder).

Part 4 and 5
I am not sure how I was supposed to post these. Here is my GET request

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello Test</title>
</head>
<body>
    <p>Welcome to My Page</p>

    <form action="" id="movieForm">
        <label for="title">Movie Title:</label>
        <input type="text" name="title" id="movieTitle" placeholder="Movie Title">
        <label for="rating">Movie Rating:</label>
        <input type="number" name="rating" id="movieRating" placeholder="Rating here. 0-10"><br>
        <span id="message">&nbsp;</span><br><br> <!--non-breaking space -->
        <button class="formbutton" id="add">Add Movie</button><br>
    </form>
<!-- Code injected by live-server -->
<script>
	// <![CDATA[  <-- For SVG support
	if ('WebSocket' in window) {
		(function () {
			function refreshCSS() {
				var sheets = [].slice.call(document.getElementsByTagName("link"));
				var head = document.getElementsByTagName("head")[0];
				for (var i = 0; i < sheets.length; ++i) {
					var elem = sheets[i];
					var parent = elem.parentElement || head;
					parent.removeChild(elem);
					var rel = elem.rel;
					if (elem.href && typeof rel != "string" || rel.length == 0 || rel.toLowerCase() == "stylesheet") {
						var url = elem.href.replace(/(&|\?)_cacheOverride=\d+/, '');
						elem.href = url + (url.indexOf('?') >= 0 ? '&' : '?') + '_cacheOverride=' + (new Date().valueOf());
					}
					parent.appendChild(elem);
				}
			}
			var protocol = window.location.protocol === 'http:' ? 'ws://' : 'wss://';
			var address = protocol + window.location.host + window.location.pathname + '/ws';
			var socket = new WebSocket(address);
			socket.onmessage = function (msg) {
				if (msg.data == 'reload') window.location.reload();
				else if (msg.data == 'refreshcss') refreshCSS();
			};
			if (sessionStorage && !sessionStorage.getItem('IsThisFirstTime_Log_From_LiveServer')) {
				console.log('Live reload enabled.');
				sessionStorage.setItem('IsThisFirstTime_Log_From_LiveServer', true);
			}
		})();
	}
	else {
		console.error('Upgrade your browser. This Browser is NOT supported WebSocket for Live-Reloading.');
	}
	// ]]>
</script>
</body>
</html>