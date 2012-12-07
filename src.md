# IE Hacks
<a href="https://twitter.com/share" class="twitter-share-button" data-via="flyworld" data-hashtags="ie">Tweet</a>
<script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0];if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src="//platform.twitter.com/widgets.js";fjs.parentNode.insertBefore(js,fjs);}}(document,"script","twitter-wjs");</script>

<iframe src="//www.facebook.com/plugins/like.php?href=http%3A%2F%2Fflyworld.github.com%2FIE-Hacks%2F&amp;send=false&amp;layout=standard&amp;width=450&amp;show_faces=true&amp;font&amp;colorscheme=light&amp;action=like&amp;height=80&amp;appId=529609970383823" scrolling="no" frameborder="0" style="border:none; overflow:hidden; width:450px; height:80px;" allowTransparency="true"></iframe>

## CSS 
**Example CSS statement:**

``` 
#div {
   color: black;
}
```

#### Attribute Hacks

|                                    |IE 6 |IE 7 |IE 8 |IE 9 |IE 10| Test |
|:-----------------------------------|:---:|:---:|:---:|:---:|:---:|:----:|
| ```_```color:                      | V   |     |     |     |     |
| ```*```color:                      | V   |  V  |     |     |     |
| ```#```color:                      | V   |  V  |     |     |     |
| ```+```color:                      | V   |  V  |     |     |     |
| color```/*\**/```: black```\9```;  |     |  V  |  V  |  V  |  V  | [Link](http://jsfiddle.net/theryanwu/nJsnL/3/) |
| black```\0/```;                    |     |     |  V  |  V  |  V  | [Link](http://jsfiddle.net/theryanwu/nJsnL/3/) |
| black```\9```;                     | V   |  V  |  V  |  V  |  V  | [Link](http://jsfiddle.net/theryanwu/Emhha/4/) |


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
| ```:root``` #div { color: black```\0```;}|     |    |    |  V  |  V  |

#### Media Hacks
|                                |IE 6 |IE 7 |IE 8 |IE 9 |IE 10| Test |
|:-------------------------------|:---:|:---:|:---:|:---:|:---:|      |
| @media screen```\9``` { … }    | V   |  V  |     |     |     | [Link]([Link](http://jsfiddle.net/theryanwu/QTZkV/3/)  |
| @media ```\0```screen```\```,screen```\9``` { … }  | V   |  V  | V  |     |     |  [Link](http://jsfiddle.net/theryanwu/QTZkV/3/)|
| @media ```\0```screen { … }    |     |     |  V  |     |     | [Link](http://jsfiddle.net/theryanwu/HWrUV/7/)|
| @media screen```\0``` { … }    |     |     |  V  |  V  |  V  | [Link](http://jsfiddle.net/theryanwu/HWrUV/7/) |
| @media screen and (min-width:0```\0```) { … } | | |  | V | V | [Link](http://jsfiddle.net/theryanwu/HWrUV/7/) |
| @media screen and ```(-ms-high-contrast: active), (-ms-high-contrast: none)``` { … } | | | |  | V | [Link](http://jsfiddle.net/theryanwu/BwzRR/)


### Conditional Comments

#### IE : 6 - 9
* Follow this article : [QuirksMode](http://www.quirksmode.org/css/condcom.html)


#### Deprecated in IE 10
* [Obsolete features in Internet Explorer 10](http://msdn.microsoft.com/en-us/library/ie/hh801218(v=vs.85\).aspx)

##### Work Around

**JavaScript**

```
 <!--[if !IE]><!-->
 <script>
 	if (/*@cc_on!@*/false) {
 		document.documentElement.className+=' ie10';
 	}
 </script>
 <!--<![endif]-->

```

**CSS**

```
.ie10 .example {
   /* IE10-only styles go here */
}
```

* Test IE 10 on [JS Fiddle](http://jsfiddle.net/theryanwu/UE6xd/)


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
* [JS Bin](http://jsbin.com/)
* [JS Fiddle](http://jsfiddle.net/)
* [IE Tester](http://www.my-debugbar.com/wiki/IETester/HomePage)
* [IE Collection](http://finalbuilds.com/iecollection.htm)
* [Browser Shots](http://browsershots.org/)

## Refernces
* **Update 2012/12/07** : [IE 10 CSS Hack](http://www.impressivewebs.com/ie10-css-hacks/)
* http://blog.vervestudios.co/blog/post/2011/05/13/IE9-Only-CSS-Hack.aspx
* https://gist.github.com/983116
* http://www.impressivewebs.com/ie10-css-hacks/
* http://www.webdevout.net/css-hacks
* http://www.microsoft.com/taiwan/WebsiteSpark/webworld/201112/csshack.htm
* http://blogs.msdn.com/b/ie/archive/2005/10/12/480242.aspx
* http://msdn.microsoft.com/en-us/library/ie/ms535242(v=vs.85).aspx
* http://msdn.microsoft.com/en-us/library/ff955275(v=vs.85).aspx


<a href="https://github.com/flyworld/IE-Hacks/tree/gh-pages"><img style="position: absolute; top: 0; left: 0; border: 0;" src="https://s3.amazonaws.com/github/ribbons/forkme_left_red_aa0000.png" alt="Fork me on GitHub"></a>