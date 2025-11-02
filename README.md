This javscript code can interpret the _DX World Award_ status page from your logbook on qrz.com (copyright by its respective owner, whom I'm not affiliated with). It then pops up a window containing a regular expression that you can use on the real time log produced by WSJT-X (again, copyright by its owner whom I'm not affiliated with) as such ``tail -f ALL.TXT | grep --color -P '{the regex}'`` (or, even better, if you save the regex in a file: ``tail -f ALL.TXT | grep --color -P -f {filename}``).

# Running
Read my code, confirm that I'm not loading further code or posting your information to a malicious domain of mine, open the DX World Award status (you should see the country list) *then* in the browser console run
```javascript
var script = document.createElement('script'); script.type = 'text/javascript'; script.src = 'https://danielegozzi.github.io/qrz-com-awards/100-countries.js'; document.head.appendChild(script);
```

You aren't pasting javascript from strangers in your browser console, aren't you?

# Development
Run a webserver in a working copy directory
```console
$ python3 -m http.server 8080
```

Meditate on my warning in the _Running_ paragraph, then in the browser console run
```javascript
var script = document.createElement('script'); script.type = 'text/javascript'; script.src = 'http://localhost:8080/100-countries.js?qs=foo'; document.head.appendChild(script);
```
