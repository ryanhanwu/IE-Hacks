# IE Hacks
## CSS 
**Example CSS statement:**

``` 
#div {
   color: black;
}
```

#### Attribute Hacks

|                              |IE 6 |IE 7 |IE 8 |IE 9 |IE 10|
|:-----------------------------|:---:|:---:|:---:|:---:|:---:|
| ```_```color:                | V   |     |     |     |     |
| ```*```color:                | V   |  V  |     |     |     |
| ```#```color:                | V   |  V  |     |     |     |
| ```+```color:                | V   |  V  |     |     |     |
| color```/**/```:             |     |  V  |  V  |  V  |     |
| black```\9```;               | V   |  V  |  V  |  V  |     |
| color```/*\**/```: black```\9```;   |     |  V  |  V  |     |     |
| black```\0/```;              |     |     |  V  |  V  |     |


#### Selector Hacks

|                                |IE 6 |IE 7 |IE 8 |IE 9 |IE 10|
|:-------------------------------|:---:|:---:|:---:|:---:|:---:|
| ```* html``` #div:             | V   |     |     |     |     |
| ```html*``` #div:              | V   |  V  |     |     |     |
| ```*+html``` #div:             |     |  V  |     |     |     |
| ```*:first-child+html``` #div: |     |  V  |     |     |     |
| ```html>body``` #div           |     |  V  |     |     |     |
| ```html>/**/body``` #div       |     |     |  V  |     |     |
| ```html:root``` #div       |     |     |  V  |     |     |
| ```:root``` #div { color: black```\9```;}|     |    |    |  V  |     |

#### Media Hacks
|                                |IE 6 |IE 7 |IE 8 |IE 9 |IE 10|
|:-------------------------------|:---:|:---:|:---:|:---:|:---:|
| ```@media screen\9``` { … }    | V   |  V  |     |     |     |
| ```@media \0screen\,screen\9``` { … }  | V   |  V  | V   |     |     |
| ```@media \0screen``` { … }    |     |     |  V  |     |     |
| ```@media screen\0``` { … }    |     |     |  V  |  V  |     |

### Conditional Comments

#### IE : 6 - 9
* Follow this article : [QuirksMode](http://www.quirksmode.org/css/condcom.html)


#### IE 10
* [Obsolete features in Internet Explorer 10](http://msdn.microsoft.com/en-us/library/ie/hh801218(v=vs.85\).aspx)

* **Update 2012/12/07** : [IE 10 CSS Hack](http://www.impressivewebs.com/ie10-css-hacks/)

## DocType
#### Meta Tag

```
<meta http-equiv="X-UA-Compatible" content="IE=edge" >

```

| X-UA-Compatible value | Document modes |
|:----------------------:|:--------------:|
| IE=5                  | Quirks mode    |
| IE=7                  | IE7 mode |
| IE=8                  | IE8 mode |
| IE=9                  | IE9 mode |
| IE=10                 | IE10 mode |
| **IE=edge**           | The highest supported document mode of the browser |
| IE=EmulateIE7         | IE7 mode <br> (if a valid <!DOCTYPE> declaration is present) <br>Quirks mode (otherwise) |
| IE=EmulateIE8         | IE8 mode <br> (if a valid <!DOCTYPE> declaration is present) <br>Quirks mode (otherwise) |
| IE=EmulateIE9         | IE9 mode <br> (if a valid <!DOCTYPE> declaration is present) <br>Quirks mode (otherwise) |
| IE=EmulateIE10        | IE10 mode <br> (if a valid <!DOCTYPE> declaration is present) <br>Quirks mode (otherwise) |

#### Behind the scene

* [How IE 10 Determine Document Mode](imgs/DocMode-IE10.png)
* [How IE 9 Determine Document Mode](imgs/DocMode-IE9.png)
* [How IE 8 Determine Document Mode](imgs/DocMode-IE8.png)
* [How IE 7 Determine Document Mode](imgs/DocMode-IE7.png)

## Useful Development Tools
* [IE Tester](http://www.my-debugbar.com/wiki/IETester/HomePage)
* [IE Collection](http://finalbuilds.com/iecollection.htm)
* [Browser Shots](http://browsershots.org/)

## Refernces
* https://gist.github.com/983116
* http://www.impressivewebs.com/ie10-css-hacks/
* http://www.webdevout.net/css-hacks
* http://www.microsoft.com/taiwan/WebsiteSpark/webworld/201112/csshack.htm
* http://blogs.msdn.com/b/ie/archive/2005/10/12/480242.aspx
* http://msdn.microsoft.com/en-us/library/ie/ms535242(v=vs.85).aspx
* http://msdn.microsoft.com/en-us/library/ff955275(v=vs.85).aspx


#### TODO
http://blog.vervestudios.co/blog/post/2011/05/13/IE9-Only-CSS-Hack.aspx


<a href="https://github.com/you"><img style="position: absolute; top: 0; left: 0; border: 0;" src="https://s3.amazonaws.com/github/ribbons/forkme_left_red_aa0000.png" alt="Fork me on GitHub"></a>