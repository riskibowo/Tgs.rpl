# Tgs.
```
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE html>
<html b:css='false' b:defaultwidgetversion='2' b:layoutsVersion='3' b:responsive='true' b:templateVersion='1.0.0' expr:class='data:blog.languageDirection' expr:dir='data:blog.languageDirection' xmlns='http://www.w3.org/1999/xhtml' xmlns:b='http://www.google.com/2005/gml/b' xmlns:data='http://www.google.com/2005/gml/data' xmlns:expr='http://www.google.com/2005/gml/expr'>
 
<head>

  <b:if cond='data:view.isMultipleItems'>
    <b:if cond='data:view.isHomepage'>
      <!--[ Homepage title ]-->
      <title><data:blog.title.escaped/></title>
      <b:elseif cond='data:view.search.query'/>
      <!--[ Search title ]-->
      <title><data:messages.search/>: <data:view.search.query/></title>
      <b:elseif cond='data:view.search.label'/>
      <!--[ Label title ]-->
      <title><data:blog.pageName.escaped/> - <data:blog.title.escaped/></title>
      <b:elseif cond='data:view.isArchive'/>
      <!--[ Archive title ]-->
      <title>Blog archive in: <data:blog.pageName.escaped/></title>
      <b:else/>
      <title>Blog: <data:blog.title.escaped/></title>
    </b:if>
    <b:elseif cond='data:view.isError'/>
    <!--[ Error title ]-->
    <title>Error 404: Not Found</title>
    <b:else/>
    <!--[ SingleItem title ]-->
    <title><data:blog.pageName.escaped/> - <data:blog.title.escaped/></title>
  </b:if>
  
  <!--[ Meta for browser ]-->
  <meta charset='UTF-8'/>
  <meta content='IE=edge' http-equiv='X-UA-Compatible'/>
  <meta content='max-image-preview:large' name='robots'/>

  <!-- Link Canonical -->
  <link expr:href='data:blog.url.canonical' rel='canonical'/>
  <!--<b:if cond='data:view.url == data:view.url params { amp: &quot;1&quot; }'>
    <link expr:href='data:view.url' rel='alternate'/>
    <b:else/>
    <link expr:href='data:view.url + &quot;?m=1&quot;' rel='alternate'/>
    <link expr:href='data:view.url params { amp: &quot;1&quot; }' rel='amphtml'/>
  </b:if>-->

  <b:if cond='!data:view.isError'>
    <!--[ Browser data, description and keyword ]-->
    <b:if cond='data:blog.metaDescription'>
      <meta expr:content='data:blog.metaDescription.escaped' name='description'/>
      <b:elseif cond='data:view.isSingleItem'/>
      <meta expr:content='data:post.snippet.escaped snippet { length: 147, links: false, linebreaks: false, ellipsis: false }' name='description'/>
      <b:else/>
      <meta expr:content='data:blog.pageName.escaped ? data:blog.pageName.escaped : data:blog.title' name='description'/>
    </b:if>
    <meta expr:content='data:blog.title.escaped + &quot;, &quot; + data:blog.pageName.escaped + &quot;, Keyword_1, Keyword_2, Keyword_3 &quot;' name='keywords'/>
    <b:tag cond='data:view.isPost' expr:href='resizeImage(data:blog.postImageUrl, 0)' name='link' rel='image_src'/>
  
    <!--[ Generator and rrs ]-->
    <meta content='blogger' name='generator'/>
    <link expr:href='data:blog.homepageUrl.canonical + &quot;feeds/posts/default&quot;' expr:title='data:blog.title + &quot; » Atom&quot;' rel='alternate' type='application/atom+xml'/>
    <link expr:href='data:blog.homepageUrl.canonical + &quot;feeds/posts/default?alt=rss&quot;' expr:title='data:blog.title + &quot; » Feed&quot;' rel='alternate' type='application/rss+xml'/>
    <link expr:href='data:blog.homepageUrl.canonical + &quot;feeds/comments/default?alt=rss&quot;' expr:title='data:blog.title + &quot; » Comments Feed&quot;' rel='alternate' type='application/rss+xml'/>
  
    <!--[ Theme Color ]-->
    <meta expr:content='data:skin.vars.themeColor' name='theme-color'/>
    <meta expr:content='data:skin.vars.themeColor' name='msapplication-navbutton-color'/>
    <meta expr:content='data:skin.vars.themeColor' name='apple-mobile-web-app-status-bar-style'/>
    <meta expr:content='yes' name='apple-mobile-web-app-capable'/>
  
    <!--[ Favicon ]-->
    <link expr:href='data:blog.blogspotFaviconUrl' rel='apple-touch-icon' sizes='120x120'/>
    <link expr:href='data:blog.blogspotFaviconUrl' rel='apple-touch-icon' sizes='152x152'/>
    <link expr:href='data:blog.blogspotFaviconUrl' rel='icon' type='image/x-icon'/>
    <link expr:href='data:blog.blogspotFaviconUrl' rel='shortcut icon' type='image/x-icon'/>
    
    <!--[ Open graph ]-->
    <meta expr:content='data:blog.pageName.escaped ? data:blog.pageName.escaped : data:blog.title.escaped' property='og:title'/>
    <meta expr:content='data:blog.canonicalUrl' property='og:url'/>
    <meta expr:content='data:blog.title.escaped' property='og:site_name'/>
    <b:if cond='data:view.isMultipleItems'>
      <meta content='website' property='og:type'/>
      <b:if cond='data:blog.metaDescription'>
        <meta expr:content='data:blog.metaDescription.escaped' property='og:description'/>         
        <b:else/>
        <meta expr:content='data:blog.pageName.escaped ? data:blog.pageName.escaped : data:blog.title' property='og:description'/>
      </b:if>
      <b:else/>
      <meta content='article' property='og:type'/>
      <b:if cond='data:blog.metaDescription'>
        <meta expr:content='data:blog.metaDescription.escaped' property='og:description'/>            
        <b:else/>
        <meta expr:content='data:post.snippet.escaped snippet { length: 147, links: false, linebreaks: false, ellipsis: false }' property='og:description'/>
      </b:if>
    </b:if>
    <meta expr:content='data:blog.pageName.escaped ? data:blog.pageName.escaped : data:blog.title.escaped' property='og:image:alt'/>
    <b:if cond='data:blog.postImageUrl'>
      <meta expr:content='resizeImage(data:blog.postImageUrl, 0)' property='og:image'/>
      <b:else/>
      <meta content='Add_your_image_url_here' property='og:image'/>
    </b:if>
    
    <!--[ Twitter Card ]-->
    <meta expr:content='data:blog.pageName.escaped ? data:blog.pageName.escaped : data:blog.title.escaped' name='twitter:title'/>
    <meta expr:content='data:blog.canonicalUrl' name='twitter:url'/>
    <b:if cond='data:view.isMultipleItems'>
      <b:if cond='data:blog.metaDescription'>
        <meta expr:content='data:blog.metaDescription.escaped' name='twitter:description'/>         
        <b:else/>
        <meta expr:content='data:blog.pageName.escaped ? data:blog.pageName.escaped : data:blog.title' name='twitter:description'/>
      </b:if>
      <b:else/>
      <b:if cond='data:blog.metaDescription'>
        <meta expr:content='data:blog.metaDescription.escaped' name='twitter:description'/>            
        <b:else/>
        <meta expr:content='data:post.snippet.escaped snippet { length: 147, links: false, linebreaks: false, ellipsis: false }' name='twitter:description'/>
      </b:if>
    </b:if>
    <meta content='summary_large_image' name='twitter:card'/>
    <meta expr:content='data:blog.pageName.escaped ? data:blog.pageName.escaped : data:blog.title.escaped' name='twitter:image:alt'/>
    <b:if cond='data:blog.postImageUrl'>
      <meta expr:content='resizeImage(data:blog.postImageUrl, 0)' name='twitter:image:src'/>
      <b:else/>
      <meta content='Add_your_image_url_here' name='twitter:image:src'/>
    </b:if>  
  
    <!-- Site Verification -->
<meta content='Google-verification-tag' name='google-site-verification'/>
<meta content='Bing-verfication-tag' name='msvalidate.01'/>
    
  </b:if> 
  
<meta content='width=device-width, initial-scale=1, minimum-scale=1, maximum-scale=1' name='viewport'/>

<link href='https://fonts.googleapis.com/css?family=Open+Sans:400,600,700&amp;display=swap' rel='stylesheet'/>

<script src='http://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js' type='text/javascript'/>

<link href='https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css' rel='stylesheet'/>

<b:if cond='data:blog.pageType != &quot;error_page&quot;'>
<script type='application/ld+json'>{ &quot;@context&quot;: &quot;http://schema.org&quot;, &quot;@type&quot;: &quot;WebSite&quot;, &quot;@id&quot;: &quot;#website&quot;, &quot;url&quot;: &quot;<data:blog.homepageUrl/>&quot;, &quot;potentialAction&quot;: { &quot;@type&quot;: &quot;SearchAction&quot;, &quot;target&quot;: &quot;<data:blog.homepageUrl/>search?q={search_term}&quot;, &quot;query-input&quot;: &quot;required name=search_term&quot; } }</script>
</b:if>

<b:skin version='1.3.0'><![CDATA[/*
---*****************************

Name:  SOUQStore (No Checkout page)
Demo : souqstore-bloggertheme9.blogspot.com
Type : Demo
Designer : Nikz Naveed
Website : www.bloggertheme9.com 

********************************/
/*

<Group description="Color selection">
<Variable name="mn.color" description="main colors" type="color" default="#7d4998" value="#7d4998"/>
</Group>

<Group description="Header colors, background and height">
<Variable name="header.height" description="Header height" type="length" max="80px" default="100px" value="100px"/>
<Variable name="header.heightM" description="Header height(mobile)" type="length" max="80px" default="60px" value="60px"/>
<Variable name="header.text" description="Header text colors" type="color" default="#08102b" value="#08102b"/>
<Variable name="header.bgColor" description="Header background color" type="color" default="#fff" value="#ffffff"/>
</Group>

*/
/* Variable color */
:root{
--mainC: $(mn.color);

--headerC: $(header.text) ;
--headerB: $(header.bgColor) ;
--headerH: $(header.height) ;
--headerHm: $(header.heightM) ;
}

@font-face{font-family:'Droid Arabic Kufi'; font-style: normal; font-weight: 400; src: url(//fonts.gstatic.com/ea/droidarabickufi/v6/DroidKufi-Regular.eot); src: url(//fonts.gstatic.com/ea/droidarabickufi/v6/DroidKufi-Regular.eot?#iefix) format('embedded-opentype'), url(//fonts.gstatic.com/ea/droidarabickufi/v6/DroidKufi-Regular.woff2) format('woff2'), url(//fonts.gstatic.com/ea/droidarabickufi/v6/DroidKufi-Regular.woff) format('woff'),        url(//fonts.gstatic.com/ea/droidarabickufi/v6/DroidKufi-Regular.ttf) format('truetype');} @font-face {font-family:'Droid Arabic Kufi'; font-style: normal; font-weight: 700; src: url(//fonts.gstatic.com/ea/droidarabickufi/v6/DroidKufi-Bold.eot); src: url(//fonts.gstatic.com/ea/droidarabickufi/v6/DroidKufi-Bold.eot?#iefix) format('embedded-opentype'),  url(//fonts.gstatic.com/ea/droidarabickufi/v6/DroidKufi-Bold.woff2) format('woff2'),     url(//fonts.gstatic.com/ea/droidarabickufi/v6/DroidKufi-Bold.woff) format('woff'),  url(//fonts.gstatic.com/ea/droidarabickufi/v6/DroidKufi-Bold.ttf) format('truetype');}

/* New interface B - ver 3
----------------------------------------------- */

html, body, div, span, applet, object, iframe, h1, h2, h3, h4, h5, h6, p, blockquote, pre, a, abbr, acronym, address, big, cite, code,
del, dfn, em, font, img, ins, kbd, q, s, samp, small, strike, strong, sub, sup, tt, var, dl, dt, dd, ol, ul, li, fieldset, form, label, legend, table, caption, tbody, tfoot, thead, tr, th, td, figure { margin: 0; padding: 0;}
article,aside,details,figcaption,figure,footer,header,hgroup,menu,nav,section {display:block;}
ins{text-decoration:underline}
del{text-decoration:line-through}

*, *:before, *:after, html {-moz-box-sizing: border-box; -webkit-box-sizing: border-box; box-sizing: border-box;}

caption {background: #eee; text-align:center; padding: 4px 10px 4px}
dl {margin: 0 0 20px 0}
dl dt {font-weight: bold}
dd {margin-left: 20px}
pre {margin: 20px 0; white-space: pre}
pre, code, tt {font: 13px 'andale mono', 'lucida console', monospace; line-height: 18px}

sup{ vertical-align: super; font-size:smaller; }
code{ font-family: 'Courier New', Courier, monospace; font-size:12px; color:#272727; }
a img{border: none;}
ul ul, ol ol { padding: 0; }

ol, ul { padding: 0px;  margin: 0; }
ol li { list-style-type: none;  padding:0;  }
ul li { list-style-type: none;  padding: 0;  }

/* Theme color change
----------------------------------------------- */
a,a:hover,.post-title a:hover, .sidebar-wrapper a:hover,#related-article h4 a:hover, .sidebar-wrapper a:hover, .cart-description .item-quantity, .cart-description .item-total, .fourthing i, .footer-credits a:hover, .PopularPosts .post-title a:hover{color:var(--mainC);}
.no-posts-message,.share-buttons li .sharing-platform-button:focus, .share-buttons li .sharing-platform-button:hover,.post-filter-message,#blog-pager a, .showpagePoint, .search-submit-container button, .cart-description .item-decrement a:hover,.cart-description .item-increment a:hover, .cart-details, .cart-description .simpleCart_checkout, .menu-bg{background-color:var(--mainC);}

h1, h2, h3, h4, h5, h6 {color: #555; font-family:'Open Sans',sans-serif; font-weight:600; margin:0; line-height:1.6em; }
h1{font-size:1.6rem} h2{font-size:1.4rem} h3{font-size:1.3rem} h4{font-size:1.2rem} h5{font-size:1.1rem} h6{font-size:1rem}
.post-body h1, .post-body h2, .post-body h3, .post-body h4, .post-body h5, .post-body h6{line-height:1.5em; margin:1.5em 0 18px;}

.Rtl h1,.Rtl h2,.Rtl h3,.Rtl h4,.Rtl h5,.Rtl h6 {font-family: 'Droid Arabic Kufi', 'Open Sans', sans-serif; }

img{max-width:100%;}

a{ color: ; outline:none; text-decoration: none; }
a:hover { color: ; transition:opacity .4s;}
body {background-color: #fff; color:#666; font:14px/1.7em 'Open Sans',sans-serif; letter-spacing:.1px; overflow-wrap: break-word; word-break: break-word; word-wrap: break-word; margin:0; padding:0;} 

.ct-wrapper {padding:0px 0px 0; position:relative; margin: 0px auto;}
.outer-wrapper {margin:0; position: relative;}
.main-wrapper{background:#fff; float:left; overflow:hidden; width:calc(100% - 285px); word-wrap:break-word; padding:0 0px; margin:0 0 20px;}
.sidebar-wrapper{float:right; overflow:hidden; width:260px; word-wrap:break-word; padding:0 0px; margin:0;}
.contained {margin: 0 auto; padding: 0 20px; position: relative; clear:both; max-width:1190px;}

.ct-wrapper, .crossy, .post, .sidebar-wrapper{overflow:hidden;}

#header{margin:0px 0 0; float:left; min-width:260px;}
#header h1, #header h2 {font-size: 27px; margin: 0; padding: 0; font-weight:600; line-height:36px; text-overflow: ellipsis; white-space: nowrap;}
#header h1 a, #header h2 a{}
#header h1 a:hover, #header h2 a:hover{opacity:.8;}
.header-logo img{max-width:100%; max-height:45px; margin:0;}
.Header p {display:none; color: #fff; font-weight:300; font-size:14.7px; line-height:1.7; margin: 6px 0 0; padding: 0;}
.header-wrapper{padding:16px 0; float: left; width: 100%;}

.PopularPosts .popular-posts-snippet, .Header p{font-family:Merriweather,Georgia,serif; font-style:italic;}

.hidden, .theme-options {display: none;}
.barred-widgets, .hidden-widgets{display: none; visibility: hidden;}
.invisible {visibility: hidden;}

.top{margin-top:30px;}

.color{background-image: -webkit-gradient(linear,right top,left top,from(#CD4033),to(#FFB100)); background-image: linear-gradient(to left,#CD4033,#FFB100);}

.clear { clear: both;}

.main-heading {position: absolute; clip: rect(1px,1px,1px,1px); padding: 0; border: 0; height: 1px; width: 1px; overflow: hidden;}
.blogger-logo, .svg-icon-24.blogger-logo {fill: #ff9800; opacity: 1;}

.item-control {display: none;}

.BLOG_mobile_video_class {display: none;}
.bg-photo {background-attachment: scroll !important;}

.tred{background:#F4F4F4; float:left; width:100%; padding:6px 0; font-size:13.4px;}

.socal, .slogy{float:left; }
.socal a{background:#ddd; display:block; float:left; width:34px; height:34px; line-height:34px; overflow:hidden; color: #fff !important; text-align:center; margin:0 4px 6px; font-size:15px; border-radius: 2px;}

.socal a.fb-ic{background:#3B5998; color:#fff;}
.socal a.tw-ic{background:#19BFE5; color:#fff;}
.socal a.ig-ic{background:linear-gradient(15deg,#ffb13d,#dd277b,#4d5ed4); color:#fff;}
.socal a.yt-ic{background:#ca2127; color:#fff;}
.socal a.rs-ic{background:#0077b5; color:#fff;}

.apploads{margin:14px 0 0; float:left; width:100%; }
.apploads a {background-color: #5d5d5d; display: inline-block; border-radius: 4px; padding: 6px 10px; margin:0 4px 6px; font-size: 15px; color:#fff !important; font-family: 'Open Sans',sans-serif;}
.apploads a i{}
.apploads a:hover, .socal a:hover{opacity:.8; }

.cates {display: block; float:right; }
.cates li {display: inline-block; border-left:2px solid #e1e1e1; }
.cates li a {color: #666; padding:0 12px; }
.cates li a:hover {color:#333;}
.cates li:first-child {border:none;}
.cates i{font-size:19px; margin:0 3px 0 0px;}

a.menu-btn { display: none; color: #fff; background-color: #333; padding: 18px 15px 18px 55px; font-size: 15px; font-weight: 600; position:relative; }
.menu-bg {background-color:; float: left; width: 100%;}
.menu { float: left; margin: 0 -10px; -webkit-transition: all 0.3s ease; -moz-transition: all 0.3s ease; -ms-transition: all 0.3s ease; transition: all 0.3s ease; }
.menu ul {padding: 0px; margin: 0px; list-style: none; position: relative; }
.menu > li > ul.sub-menu {min-width: 10em; padding: 4px 0;  background-color: #f4f4f4; border: 1px solid #CCC; }
.menu ul li {z-index: 10; position:relative;}
ul.megamenu > li { display: inline-block; }
.menu ul li > a { display: block; color: #fff; font-size: 15px; padding:0px 20px; line-height:50px;}

.menub ul ul {display:none;position: absolute; top:100%; min-width: 0px; background-color: #fff; box-shadow: 0 5px 8px rgba(0, 0, 0, 0.25); z-index:9; visibility: hidden; opacity: 0; transform: translate(0,25px); transition: all 0.2s ease-out;}
.menug ul li:hover > ul {visibility: visible; opacity: 1; transform: translate(0,0);}

.menu ul li > ul{display:none;}
.menu ul li a:hover > ul {display:block;}
 
.megamenuid li div.megasubmenu{background:#F8F8F8; position:absolute; width:870px; left:0; top:100%; overflow:hidden; min-height:0px; visibility:hidden; opacity:0; color:#888; 
-moz-transform:translate(0,30px); -webkit-transform:translate(0,30px); -o-transform:translate(0,30px); transform:translate(0,30px);
transform-origin:50% 0; box-shadow:0 10px 7px -7px rgba(0,0,0,0.1); transition:all 0.3s ease-in-out; }
.megamenuid li:hover div.megasubmenu{visibility:visible; opacity:1; -moz-transform:translate(0,0); -webkit-transform:translate(0,0); -o-transform:translate(0,0); transform:translate(0,0); }

.leftmenulist{float:left; background: #f4f4f4; border-right: 1px solid #e4e4e4; min-height: 222px; width:168px; }
.leftmenulist li a {display: block; transition: all 0.3s ease-in-out;}

.rightmenulist{display: flex; flex-wrap: wrap; margin-left: -12px; margin-right: -12px;}
.rightmenulist li{-moz-box-flex: 0; float:left; width: calc(100% / 4); padding:14px 12px;}
.rightmenulist li a {font-weight: 600; font-size: 14px; }
.thumb-container{width:100%; overflow: hidden; display: block; height: 194px;}
.thumb-container img{width:100%; height:142px; border:1px solid #eee;}

.menu ul ul > li { position: relative; }
.menu ul ul ul { position: absolute; left: 100%; top:0; }
.menu ul ul > li a {color:#555; }
.menu ul ul > li a:hover {color: #222; }
.menu ul li a:hover{color: #fff;}

.with-ul:after {border-color: #ddd transparent transparent; border-image: none; border-style: solid; border-width: 4px; content: ""; position: absolute; top: 50%; right:5px;}

ul.megamenuid .loading-icon{background:url('http://2.bp.blogspot.com/-N9HNU11nhiA/Va-NLcGF0lI/AAAAAAAALW4/HzSlCK7PGeY/s1600/wait.gif') no-repeat scroll 0 0 transparent;width:22px;height:22px;position:absolute;top:50%;margin-top:-11px;right:5
px}
ul.megamenuid .menu-icon{border-bottom:4px solid transparent;border-top:4px solid transparent;border-left:4px solid #777;display:block;height:0;margin-top:-4px;position:absolute;right:11px;top:50%;width:0}

#megamenuid h5{font-size:16px;margin-top:70px;text-align:center}
#megamenuid h5:before{content:"";position:absolute;top:50px;left:50%;width:5px;height:2px;margin-left:-4px;border-left:2px solid black;border-right:2px solid black}
#megamenuid h5:after{content:"";position:absolute;top:55px;left:50%;width:10px;height:5px;margin-left:-7px;border-top:2px solid black;border-left:2px solid black;border-right:2px solid black;border-radius:8px 8px 0px 0px}

.hamburger {float: left; width: 20px; height: 20px; position: absolute; left: 25px; top: 28px;}
.hamburger > div {position: relative; width: 100%; height: 3px; background: #fff; align-items: center; justify-content: center; transition: all 0.4s ease;}
.hamburger > div::before,.hamburger > div::after {content: ''; position: absolute; z-index: 1; top: -8px; width: 100%; height: 3px; background: inherit;}
.hamburger > div::after {top: 8px;}

.peekar form{position:relative; width:100%; float:left; margin:0px 0; border:6px solid #ddd; background-color:#fff; }
.peekar input{float:left; height:36px; text-indent:7px; width:100%; color:#888; border:0; }
.peekar input:focus{outline: none !important;}
.peekar button{border: 0; position:absolute; background-color:transparent; right:4px; top:6px; cursor: pointer; color:#aaa; font-size:18px; }
.peekar button:hover{}

.base1{background-color: #354058; height:60px; float: left; width: 100%;}
.base2{background-color: #ddd; float: left; width: 100%;}
.white{background:#E9EFF9; float: left; width: 100%;}
.sidebar-wrapper .widget{overflow:hidden; clear: both; margin-bottom: 25px;}
.sidebar-wrapper li{border-bottom: 1px solid #ddd; margin: 0; padding: 7px 0 7px 7px; text-transform: capitalize;}
.sidebar-wrapper li:last-child, .footer li:last-child{border-bottom:none !important;}
.footer li:first-child, .PopularPosts ul li:first-child{padding-top:2px !important;}
.sidebar-wrapper h3{margin: 0 0 10px; padding: 0;font-size:1.1rem;}
.sidebar-wrapper a:hover{}

.post-body ol,.post-body ul { padding: 10px 0 20px;  margin: 0 0 0 25px;  text-align: left;  }
.post-body ol li { list-style-type: decimal;  padding:0 0 5px;  }
.post-body ul li { list-style-type: square;  padding: 0 0 5px;  }
.post-body img{max-width:100%; height:auto;}

.post-body iframe {max-width: 100%;}
.post-body a[imageanchor="1"] {display: inline-block;}
.post-body{margin:0 0 20px;}

.bow {display: flex; flex-wrap: wrap; margin-left: -12px; margin-right: -12px;}
.half, .brox, .vert-ad{-moz-box-flex: 0; width: calc(100% / 2); padding-left: 12px; padding-right: 12px;}
.third,.delate, .banner3, .fourthing {-moz-box-flex: 0; width: calc(100% / 3); padding-left: 12px; padding-right: 12px;}
.quart {-moz-box-flex: 0; width: calc(100% / 4); padding-left: 12px; padding-right: 12px;}
.fifth, .related-posts li {-moz-box-flex: 0; width: calc(100% / 5); padding-left: 12px; padding-right: 12px;}
.producting li {-moz-box-flex: 0; width: calc(100% / 6); padding-left: 12px; padding-right: 12px;}
.post-header{margin:5px 0; font-weight:500; font-size:14px; color:#a1a1a1;}

.soothing, a, .seemcard a, .cart-buttons a{transition: all .5s ease-out; -webkit-transition: all .5s ease-out; -moz-transition: all .5s ease-out; -ms-transition: all .5s ease-out; -o-transition: all .5s ease-out;}

.byline {margin-right: 1em;}
.byline:last-child {margin-right: 0;}

.byline.reactions iframe {height: 20px;}

.no-posts-message {line-height: 40px; text-align: center; margin: 10px 0; background-color:; color:#fff;}

.crossy .widget-content{text-align:center; float:left; margin:20px 0 0; width:100%;}

.fn:before{font-family:fontawesome; content:"\f007"; font-style:normal; color:#777; float: left; margin: 0 6px 0 0;}
.publisheds:before{font-family:fontawesome; content:"\f133"; font-style:normal; color:#777; margin: 0 3px 0 0;}


.feet-icons{margin: 0 0 0px;}
.feet-icons span{float:left; font-size:13px; }
.feet-icons a{float:left; width:28px; height:30px; line-height:25px; overflow:hidden; text-align:center; }
.feet-icons a i{font-size:15px; color:rgba(0,0,0,.6);}
.feet-icons a:hover{opacity:.8; }

a.face-ico i{color:#3B5998;}
a.twi-ico i{color:#19BFE5;}
a.pint-ico i{color:#ca2127;}
a.bitz-ico i{color:#23A215;}
a.link-ico i{color:#0077b5;}

.title-secondary{width: 99%; color: #888888; background: url(//2.bp.blogspot.com/-5feHh8DpM_k/U88bANmcxnI/AAAAAAAAB40/69FQdxpYqb0/s1600/title_pat.png) center left repeat-x;
padding-left: 2%; clear: both; height: 63px; font-size: 14px; line-height: 63px; font-weight:600; overflow: hidden; white-space: nowrap; text-overflow: ellipsis}
.post-author, .post-date{background: #fff; margin-right: 10px; padding: 7px; }

.title-secondary img {background:#fff; vertical-align: middle; padding:6px; float: left; width: 50px; height: 50px; margin: 4px 8px 0 0; border-radius: 50%;}

.producting{color:#fff;}
.producting li{float:left; position:relative; margin:0 0 10px;}
.producting h3{background: #fff; top: -9px; padding-right: 1.2%; margin: 0 0 25px; position: absolute; font-size:1rem;}
.producting .product_off {right:22px; }
.producting em{margin: 3px 0 14px; float: left; height: 12px; width: 100%; position: relative; font-style:unset;
background-image: -webkit-repeating-linear-gradient(135deg, #eaeaea, #eaeaea 1px, transparent 2px, transparent 2px, #eaeaea, #eaeaea 3px);
background-image: -moz-repeating-linear-gradient(135deg, #eaeaea, #eaeaea 1px, transparent 2px, transparent 2px, #eaeaea, #eaeaea 3px);
background-image: -o-repeating-linear-gradient(135deg, #eaeaea, #eaeaea 1px, transparent 2px, transparent 2px, #eaeaea, #eaeaea 3px);
background-image: repeating-linear-gradient(135deg, #eaeaea, #eaeaea 1px, transparent 2px, transparent 2px, #eaeaea, #eaeaea 3px);
-webkit-background-size: 4px 4px; -moz-background-size: 4px 4px; background-size: 4px 4px; }

.product-header{position:relative; width:100%; background-color:#f8f8f8; overflow:hidden; border:1px solid #eee; padding:15px; margin:0 0 20px; }
.col-left{position:relative; float:left; width:300px; }
.col-left .post-image-wrap{position:relative; margin:0; width:100%; height:auto; }
.col-right{position:relative; float:right; width:calc(100% - 315px)}
.col-left .post-thumb:hover{transform: scale(1); -ms-transform: scale(1); -webkit-transform: scale(1);}

.tier-price{margin:0 0 14px; color:#23A215; font-size: 24px; font-weight:600; }

.reviews{margin:0 0 14px;}
.reviews i{color: #ddd; }
.reviews .checked {color: #FFD700;}

.seemcard{display:flex; margin:0 0 20px}
.seemcard a{display:flex;align-items:center;justify-content:center;height:36px;background-color:var(--mainC); font-size:14px; color:#fff; padding:0px 15px; margin:0px 10px 0 0; border-radius:3px; }
.seemcard a.cart-payment{background-color:#4d4d4d;}
.seemcard a:hover{opacity:.9;}
.seemcard i{font-size:16px;}

.seemcard .item_add, .seemcard .disab-cart{flex:1;}
.ccrt{margin-left:4px;}

.product-size{margin:0 0 8px;}
.product-size select{margin:0 0 0 6px; outline:none;cursor:pointer;border: 1px solid #bbb; padding: 4px 4px; width: 140px; }

.add-to-wishlist{ text-align: center; cursor:pointer; }
.shopping-msg{margin: -6px 0 6px; }
.shopping-msg a{font-weight:600; }
.shopping-msg i, .wishlist-title a:hover{color:var(--mainC);}
.remove-from-wishlist{font-size: 13px; cursor: pointer;}
.wishlist-title a, .remove-from-wishlist:hover{color:#555;}
.empty-wishlist{margin:0 0 0 12px;}

.product_off{position:absolute; top:10px; right:10px; height:24px; background-color:#F2616E; font-size:11px; color:#fff; font-weight:600; text-align:center; line-height:24px; z-index:2; padding:0 8px;  letter-spacing:.5px; }
.index-post .product_off,.FeaturedPost .product_off,.product-header .product_off{visibility:hidden;opacity:0;transition:all .17s ease}
.index-post .product_off.show,.FeaturedPost .product_off.show,.product-header .product_off.show{visibility:visible;opacity:1}

.post-thumb {display: block; position: relative; width: 100%; height: 100%; z-index: 1; transition: transform 1s; margin: 0 auto;}
.post-image-wrap{position:relative; margin: 0 0 8px; width: 100%; height: auto; overflow: hidden; border:1px solid #eee;}

.post-thumb:hover {transform: scale(1.2); -ms-transform: scale(1.2); -webkit-transform: scale(1.2);}

[class*=mk-inline] {
    display: block;
    position: relative;
    max-width: 100%;
    vertical-align: middle;
    -webkit-backface-visibility: hidden;
}

.mk-input, .mk-select, .mk-textarea {
    max-width: 100%;
    width: 100%;
    border: 0 none;
    padding: 10px 15px;
    background: #fff;
    color: #666;
    border-radius: 4px;
    font-size: .875rem;
    font-weight: 300;
    box-shadow: 0 5px 10px rgb(0 0 0 / 15%);
    transition: .3s ease-in-out;
    transition-property: color,background-color,border,box-shadow;
}

.mk-button {
    margin: 0;
    border: none;
    overflow: visible;
    font: inherit;
    color: inherit;
    text-transform: none;
    display: inline-block;
    border-radius: 500px;
    font-weight: 300;
    padding: 0 30px;
    vertical-align: middle;
    font-size: .875rem;
    line-height: 38px;
    text-align: center;
    text-decoration: none;
    box-shadow: 0 5px 10px rgb(0 0 0 / 15%);
    text-transform: uppercase;
    transition: .3s ease-in-out;
    transition-property: color,background-color,border-color,box-shadow;
}

.mt-ad{min-height:70px;display:flex;align-items:center;justify-content:center;font-size:13px;color:#989b9f;border:1px solid #e6e6e6;border-radius:3px} .mt-ad::before{content:attr(data-text)}
.dropCap{float:left;margin:2px 8px 0 0; font-size:55px;line-height:45px;opacity:.8}
blockquote, .cmC i[rel=quote]{position:relative;font-size:.97rem; opacity:.8;line-height:1.6em;margin-left:0;margin-right:0;padding:5px 20px;border-left:2px solid #e6e6e6;} 
blockquote, details.sp{font-size:.93rem; padding:25px 25px 25px 45px; margin:1em 0; border:1px solid #989b9f;border-left:0;border-right:0;line-height:1.7em} 
blockquote::before{content:'\201D';position:absolute;top:10px;left:0; font-size:60px;line-height:normal;opacity:.5} 
details.sp{padding:20px 15px} details.sp summary{display:flex;justify-content:space-between;align-items:baseline} details.sp summary::after{content:attr(data-show);font-size:12px; opacity:.7;cursor:pointer} details.sp[open] summary::after{content:attr(data-hide)} details.toc a{color:#204ecf;}details.toc a:hover{text-decoration:underline} details.toc ol, details.toc ul{padding:0 20px; list-style-type:decimal;margin:0 !important;font-size:14px;} details.toc li ol, details.toc li ul{margin:5px 0 10px; list-style-type:lower-alpha} 
details.toc li, details.toc li{padding:0 !important;}
table{margin:0 auto; font-size:14px;font-family:'Noto Sans', sans-serif;} table:not(.tr-caption-container){min-width:90%;border:1px solid #e6e6e6;border-radius:3px;overflow:hidden} table:not(.tr-caption-container) td{padding:16px} table:not(.tr-caption-container) tr:not(:last-child) td{border-bottom:1px solid #e6e6e6;} table:not(.tr-caption-container) tr:nth-child(2n+1) td{background:rgba(0,0,0,.01)} table th{padding:16px; text-align:inherit; border-bottom:1px solid #e6e6e6;} .table{display:block; overflow-y:hidden;overflow-x:auto;scroll-behavior:smooth}
.note{position:relative;padding:16px 20px 16px 50px; background:#e1f5fe;color:#3c4043; font-size:.85rem;font-family:'Noto Sans', sans-serif;;line-height:1.6em;border-radius:10px;overflow:hidden} .note::before{content:'';width:60px;height:60px;background:#81b4dc;display:block;border-radius:50%;position:absolute;top:-12px;left:-12px;opacity:.1} .note::after{content:'\002A';position:absolute;left:18px;top:16px; font-size:20px; min-width:15px;text-align:center} .note.wr{background:#ffdfdf;color:#48525c} .note.wr::before{background:#e65151} .note.wr::after{content:'\0021'}
.post-body p{margin:1.6em 0;} .showH{font-size:.93rem;font-family:'Noto Sans', sans-serif;;line-height:1.7em} details.ac{padding: 18px 0; border-bottom: 1px solid #e6e6e6;} details.ac summary{font-weight:700; display:flex;align-items:baseline; transition:all .1s ease;} details.ac summary::before{content:'\203A'; flex:0 0 25px;display:flex;align-items:center;justify-content:flex-start;padding:0 5px; font-weight:400;font-size:1.33rem;color:inherit} details.ac[open] summary{color:#1C74E9;} details.ac:not(.alt)[open] summary::before{transform:rotate(90deg);padding:0 0 0 5px;justify-content:center} details.ac.alt summary::before{content:'\002B'; padding:0 2px} details.ac.alt[open] summary::before{content:'\2212'} details.ac .aC{padding:0 18px;opacity:.9}
.pre{background:#f4f4f4;color:#2f3337; direction: ltr} .pre:not(.tb){position:relative;border-radius:3px;overflow:hidden;margin:1.7em auto;font-family:'Fira Mono', monospace;} .pre pre{margin:0;color:inherit;background:inherit} .pre:not(.tb)::before, .cmC i[rel=pre]::before{content:'</>';display:flex;justify-content:flex-end;position:absolute;right:0;top:0;width:100%;background:inherit;color:#656e77;font-size:10px;padding:0 10px;z-index:2;line-height:30px} .pre:not(.tb).html::before{content:'.html'} .pre:not(.tb).css::before{content:'.css'} .pre:not(.tb).js::before{content:'.js'} pre, .cmC i[rel=pre]{display:block;position:relative;font-family:'Fira Mono', monospace;;font-size:13px;line-height:1.6em;border-radius:3px;background:#f4f4f4;color:#2f3337;padding:30px 20px 20px;margin:1.7em auto; -moz-tab-size:2;tab-size:2;-webkit-hyphens:none;-moz-hyphens:none;-ms-hyphens:none;hyphens:none; overflow:auto;direction:ltr;white-space:pre} pre i{color:#015692;font-style:normal} pre i.block{color:#fff;background:#015692;} pre i.green{color:#54790d;} pre i.gray{color:#656e77;} pre i.red{color:#b75501;} pre i.blue{color:#015692;} code{display:inline;padding:5px;font-size:14px;border-radius:3px;line-height:inherit;color:#2f3337;background:#f2f3f5;font-family:'Fira Mono', monospace;} .pre.tb{border-radius:5px} .pre.tb pre{margin:0;background:inherit} .pre.tb .preH{font-size:13px;border-color:rgba(0,0,0,.05);margin:0} .pre.tb .preH >*{padding:13px 20px} .pre.tb .preH::after{content:'</>';font-size:10px;font-family:'Fira Mono', monospace;;color:#656e77;padding:15px;margin-left:auto} .pre.tb >:not(.preH){display:none} input[id*="1"]:checked ~ div[class*="C-1"], input[id*="2"]:checked ~ div[class*="C-2"], input[id*="3"]:checked ~ div[class*="C-3"], input[id*="4"]:checked ~ div[class*="C-4"]{display:block} 
.tbHd{display:flex; border-bottom:1px solid #e6e6e6;margin-bottom:30px;font-size:14px;font-family:'Noto Sans', sans-serif;;line-height:1.6em; overflow-x:hidden;overflow-y:hidden;scroll-behavior:smooth;scroll-snap-type:x mandatory; -ms-overflow-style:none;-webkit-overflow-scrolling:touch} .tbHd >*{padding:12px 15px; border-bottom:1px solid transparent; transition:all .1s ease;;opacity:.6;white-space:nowrap; scroll-snap-align:start} .tbHd >*::before{content:attr(data-text)} .tbCn >*{display:none;width:100%} .tbCn >* p:first-child{margin-top:0} input[id*="1"]:checked ~ .tbHd label[for*="1"], input[id*="2"]:checked ~ .tbHd label[for*="2"], input[id*="3"]:checked ~ .tbHd label[for*="3"], input[id*="4"]:checked ~ .tbHd label[for*="4"]{border-color:#1C74E9;opacity:1} input[id*="1"]:checked ~ .tbCn div[class*="Text-1"], input[id*="2"]:checked ~ .tbCn div[class*="Text-2"], input[id*="3"]:checked ~ .tbCn div[class*="Text-3"], input[id*="4"]:checked ~ .tbCn div[class*="Text-4"]{display:block} .tbHd.stick{position:-webkit-sticky;position:sticky;top:60px;background:#1C74E9;}
.extL::after{content:''; width:14px;height:14px; display:inline-block;margin:0 5px; background: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='%23989b9f' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'><path d='M13 11L21.2 2.80005'/><path d='M22 6.8V2H17.2'/><path d='M11 2H9C4 2 2 4 2 9V15C2 20 4 22 9 22H15C20 22 22 20 22 15V13'/></svg>") center / 14px no-repeat}
.button{display:inline-flex;align-items:center; margin:10px 0;padding:12px 15px;outline:0;border:0; border-radius:3px;line-height:20px; color:#fffdfc; background:#1C74E9; font-size:15px;font-family:'Noto Sans', sans-serif;; white-space:nowrap;overflow:hidden;max-width:320px; transition:all .3s ease;} .button.ln{color:inherit;background:transparent; border:1px solid #767676;} .button.ln:hover, .zbutton.ln:hover{border-color:#1C74E9;box-shadow:0 0 0 1px #1C74E9 inset} .btnF{display:flex;justify-content:center; margin:10px 0;width:calc(100% + 12px);left:-6px;right:-6px;position:relative} .btnF >*{margin:0 6px} .dlBox{max-width:500px;background:#f1f1f0;border-radius:10px;padding:12px;margin:1.7em 0; display:flex;align-items:center; font-size:14px} .dlBox .fT{flex-shrink:0;display:flex;align-items:center;justify-content:center; width:45px;height:45px; padding:10px; background:rgba(0,0,0,.1);border-radius:5px} .dlBox .fT::before{content:attr(data-text);opacity:.7} .dlBox a{flex-shrink:0;margin:0;padding:10px 12px;border-radius:5px;font-size:13px} .dlBox a::after{content:attr(aria-label)} .dlBox .fN{flex-grow:1; width:calc(100% - 200px);padding:0 15px} .dlBox .fN >*{display:block;white-space:nowrap;overflow:hidden;text-overflow:ellipsis} .dlBox .fS{line-height:16px;font-size:12px;opacity:.8} /* Icon btn */ .icon{flex-shrink:0;display:inline-flex} .icon::before{content:'';width:18px;height:18px;background-size:18px;background-repeat:no-repeat;background-position:center} .icon::after{content:'';padding:0 6px} .icon.dl::before, .drK .button.ln .icon.dl::before, .drK .zbutton.ln .icon.dl::before{background-image:url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='%23fefefe' stroke-linecap='round' stroke-linejoin='round' stroke-width='1.5'><polyline points='8 17 12 21 16 17'/><line x1='12' y1='12' x2='12' y2='21'/><path d='M20.88 18.09A5 5 0 0 0 18 9h-1.26A8 8 0 1 0 3 16.29'/></svg>")} .icon.demo::before{background-image:url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='%23fefefe' stroke-linecap='round' stroke-linejoin='round' stroke-width='1.5'><path d='M7.39999 6.32003L15.89 3.49003C19.7 2.22003 21.77 4.30003 20.51 8.11003L17.68 16.6C15.78 22.31 12.66 22.31 10.76 16.6L9.91999 14.08L7.39999 13.24C1.68999 11.34 1.68999 8.23003 7.39999 6.32003Z'/><path d='M10.11 13.6501L13.69 10.0601'/></svg>")} .button.ln .icon.dl::before, .zbutton.ln .icon.dl::before{background-image:url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='%2308102b' stroke-linecap='round' stroke-linejoin='round' stroke-width='1.5'><polyline points='8 17 12 21 16 17'/><line x1='12' y1='12' x2='12' y2='21'/><path d='M20.88 18.09A5 5 0 0 0 18 9h-1.26A8 8 0 1 0 3 16.29'/></svg>")}a:hover.button{opacity:.8;color:#fff;} a:hover.button.ln{color:#555;}
.videoYt{position:relative;padding-bottom:56.25%; overflow:hidden;border-radius:5px} .videoYt iframe{position:absolute;width:100%;height:100%;left:0;right:0} .lazyYt{background:#f4f4f4;position:relative;overflow:hidden;padding-top:56.25%;border-radius:5px} .lazyYt img{width:100%;top:-16.84%;left:0;opacity:.95} .lazyYt img, .lazyYt iframe, .lazyYt .play{position:absolute} .lazyYt iframe{width:100%;height:100%;bottom:0;right:0} .lazyYt .play{top:50%;left:50%; transform:translate3d(-50%,-50%,0); transition:all .5s ease;display:block;width:70px;height:70px;z-index:1} .lazyYt .play svg{width:inherit;height:inherit; background:#fff; fill:none;stroke-width:8} .lazyYt .play .c{stroke:rgba(255,255,255,.85);stroke-dasharray:650;stroke-dashoffset:650; transition:all .4s ease-in-out; opacity:.3} .lazyYt .play .t{stroke:#FF0000; opacity:.7; stroke-dasharray:240;stroke-dashoffset:480; transition:all .6s ease-in-out; transform:translateY(0)} .lazyYt .play:hover .t{animation:nudge .6s ease-in-out;-webkit-animation:nudge .6s ease-in-out} .lazyYt .play:hover .t, .lazyYt .play:hover .c{stroke-dashoffset:0; opacity:.7;stroke:#FF0000} .nAmp .lazyYt{display:none} .lazyYt svg{position: relative; right: 0px; background-color: rgba(255, 54, 112, 0.11); border-radius: 50% !important; animation: pulse-border-pink 1.5s linear infinite; }

.dab{margin:20px 0 0px;}

.vert-ad{margin:0 0 30px;position:relative;}
.vert-space{background:#F5F5F5;border-radius:2px;padding:0 30px;width:100%;height:200px;display:flex;align-items:center;overflow:hidden;}
.vert-left{}.vert-left span{font-size:0.75rem;margin-top:10px;font-weight:500;text-transform:uppercase;letter-spacing:.8px;color:#1C74E9;}
.vert-space img{width:auto;height:170px;}
.img-ad{display:flex;justify-content:flex-end;flex:1;}.vert-left p{font-size:0.85rem;letter-spacing:.7px;}
.ad-btn{font-size:0.9rem;display:block;margin:10px 0 0;text-align:center;width:120px;padding:6px 20px;background-color:#1C74E9;color:#fff;border-radius:3.4375rem;}

.gap{margin:20px 0 0; }
.fourthing {margin:20px 0 0px; position:relative; }
.fourthing i{position:absolute; left:10px; top:2px; font-size:26px; width:55px; height:55px; line-height:55px; background:#eee; text-align:center; border-radius:50%; }
.ico-fourth {float:left; padding-left:67px;} 
.fourthing h3{font-size:1.1rem; margin:0 0 2px;}
.fourthing p{}

.vert-space img,.ad-space img{transition: transform 1s;}
.vert-space:hover img,.ad-space:hover img {transform: scale(1.2); -ms-transform: scale(1.2); -webkit-transform: scale(1.2);}

.ad-space{background:#EDEEF0; border-radius:2px; width:280px; height:600px; padding-top:30%;}
.ad-space span, .ad-space a, .ad-space img{display:block; text-align:center;}
.ad-space .img-ad{position: relative; width: 218px; margin: auto; }
.ad-space em{position:absolute; width: 85px; font-size: 22px; font-style: unset; font-weight: 600; border-radius: 50%; right: 0; padding: 13px 0; top: -10%; text-align: center; height: 85px; background: var(--mainC); color: #fff; line-height:29px;}
.ad-space em div{}
.text-ad{font-size: 14px; color: #888; margin-top:12%;}
.title-ad{font-size: 24px; font-weight: 600; color: #222; }
.btn-ad{background:var(--mainC); color: #fff; padding: 6px 0; font-size: 16px; border-radius: 4px; width: 148px; margin: 10px auto 0; }
a.btn-ad{color:#fff !important; }

.my-comments {background: #FAFAFA; float:left; width:100%; margin: 0 0 25px; }
.my-comments h5 {margin: 0 0 4px; }
#comments .comment-form h5{float:left;width:100%;}
#commentsHolder{border:1px solid #ddd; }
.comment-form iframe{margin:0 0 10px;}
body.item-view #comments .comment-form h4 {position: absolute; clip: rect(1px,1px,1px,1px); padding: 0; border: 0; height: 1px; width: 1px; overflow: hidden;}
#comment-holder .continue {display: none;}
#comments .comment-thread ol {margin: 0; padding-left: 0;}
#comments .comment-thread ol {padding-left: 0;}
#comments .comment-thread .comment-replies, #comments .comment .comment-replybox-single {margin-left: 60px;}
#comments .comment-thread .thread-count {display: none;}
#comments .comment {position: relative;}
.comments-content{float:left; width:100%; }
#comments .comment .comment {padding-bottom: 8px;}
.comment .avatar-image-container {position: absolute;}
.comment .avatar-image-container img {border-radius: 50%;}
.avatar-image-container svg, .comment .avatar-image-container .avatar-icon {border-radius: 50%; border: solid 1px #999; box-sizing: border-box; fill: #999; height: 35px; margin: 0; padding: 7px; width: 35px;}
.comment .comment-block {background: #fff; border: 1px solid #ddd; border-radius: 4px; margin: 0 0 25px 48px; padding: 12px 16px;}
.deleted-comment {background: #eee; border-radius: 3px; color: #999; font-size: 13px; padding: 10px;}
#comments .comment-author-header-wrapper {margin-left: 40px;}
#comments .comment .thread-expanded .comment-block {padding-bottom: 20px;}
.user a {color: #666; font-size: 15px; text-decoration: none;}
.comments .comments-content .user {font-style: normal;font-weight: bold;}
#comments .comment .comment-actions a{background: #fdfdfd; border: 1px solid #ccc; border-radius: 2px; color: #999; display: inline-block; font-size: 10.6px; height: 18px; line-height: 19px; margin: 0 6px 0 0; text-align: center; width: 36px;}
.comment-actions .item-control a {position: absolute; right: 5px; top: 10%;}
#comments .comment .comment-actions>* {margin-right: 8px;}
#comments .comment .comment-header .datetime {display: inline-block;}
#comments .comment .comment-header .datetime { margin-left: 8px;}
.datetime a {color: #666; font-size: 11px; font-weight: 400; opacity: 0.9; padding: 1px 6px; text-align: center; text-transform: none;}
#comments .comment .comment-header, #comments .comment .comment-footer .comment-timestamp a {color: rgba(0,0,0,0.54);}
.comments .comments-content .comment-content {color: #666; font-size: 14px; line-height: 1.6em; margin: 0; overflow-wrap: break-word; text-align: justify; padding: 12px 0; word-break: break-word; position: relative; transition: all 0.3s ease-out 0s;}
.comment-body {margin-bottom: 12px;}
#comments.embed[data-num-comments="0"] {}
#comments.embed[data-num-comments="0"] #comment-post-message, #comments.embed[data-num-comments="0"] div.comment-form>p, #comments.embed[data-num-comments="0"] p.comment-footer {display: none;}
#comment-editor-src {display: none;}
.comments .comments-content .loadmore.loaded {max-height: 0; opacity: 0; overflow: hidden;}

.svg-icon-24, .svg-icon-24-button {cursor: pointer; height: 24px; width: 24px; min-width: 24px;}

.snippet-container {margin: 0; position: relative; overflow: hidden;}
.snippet-fade {bottom: 0; box-sizing: border-box; position: absolute; width: 96px;}
.snippet-fade {right: 0;}
.snippet-fade:after {content: '\2026';}
.snippet-fade:after {float: right;}

.rating {border:none; float:left; margin: 0 0 10px;}
.rating > input { display: none; } 
.rating > label:before {margin: 0 5px 0 0; font-size: 1.13em; font-family: FontAwesome; display: inline-block; content: "\f005"; }
.rating > .half:before {content: "\f089"; position: absolute; }
.rating > label {color: #ddd; float: right; }
.rating > input:checked ~ label, .rating:not(:checked) > label:hover, .rating:not(:checked) > label:hover ~ label { color: #FFD700;  } 
.rating > input:checked + label:hover, .rating > input:checked ~ label:hover, .rating > label:hover ~ input:checked ~ label, .rating > input:checked ~ label:hover ~ label { color: #FFED85;  } 

.share-buttons .svg-icon-24, .centered-bottom .share-buttons .svg-icon-24 {fill: #fff;}
.sharing-open.touch-icon-button:focus .touch-icon, .sharing-open.touch-icon-button:active .touch-icon {background-color: transparent;}
.share-buttons {background: #444; color: #fff; border-radius: 2px; box-shadow: 0 2px 2px 0 rgba(0,0,0,.14) , 0 3px 1px -2px rgba(0,0,0,.2) , 0 1px 5px 0 rgba(0,0,0,.12); color: #fff; margin: 0; position: absolute; top: -11px; min-width: 160px; z-index: 101;}
.share-buttons.hidden {display: none;}
.sharing-button {background: transparent; border: none; margin:14px 0; outline: none; padding: 0; cursor: pointer;}
.share-buttons li {margin: 0; height: 38px;}
.share-buttons li:last-child {margin-bottom: 0;}
.share-buttons li .sharing-platform-button {box-sizing: border-box; cursor: pointer; display: block; height: 100%; margin-bottom: 0; padding: 0 14px; position: relative; width: 100%;}
.share-buttons li .sharing-platform-button:focus, .share-buttons li .sharing-platform-button:hover {background-color:; outline: none;}
.share-buttons li svg[class^="sharing-"], .share-buttons li svg[class*=" sharing-"] { position: absolute; top: 7px;}
.share-buttons li span.sharing-platform-button, .share-buttons li span.sharing-platform-button {position: relative; top: 0;}
.share-buttons li .platform-sharing-text {display: block; font-size: 16px; line-height: 38px; white-space: nowrap;}
.share-buttons li .platform-sharing-text {margin-left: 40px;}

.ContactForm .mk-button{position:relative; background-color:var(--mainC); color:#fff; }  
.ContactForm .mk-button input{background:transparent;border:0;border-radius:100px;cursor:pointer;top:0;left:0;bottom:0;right:0;width:100%;height:100%;opacity:0;position:absolute;padding:0;margin:0;line-height:0;font-size:0}
.ContactForm p{margin:0;overflow:hidden}
.ContactForm .contact-form-message-box{text-align:center;max-width:100%;width:100%}
.ContactForm p.contact-form-error-message-with-border,.ContactForm p.contact-form-success-message-with-border{line-height:20px;padding:5px 12px;border:0;border-radius:2px;background-color:#dedede;display:block;color:rgba(0,0,0,.87);position:relative;margin-top:14px;font-size:12px;font-weight:300}
.ContactForm p.contact-form-error-message-with-border{padding-right:42px}
.contact-form-error-message-with-border:before,.contact-form-error-message-with-border img{content:'';height:22px;width:23px;line-height:22px;position:absolute;top:4px;right:5px;z-index:1;background:#777;border-radius:100%}
.contact-form-error-message-with-border img{opacity:0;cursor:pointer;z-index:10}
.contact-form-error-message-with-border:after{content:'+';height:22px;line-height:22px;width:22px;position:absolute;top:5px;right:5px;z-index:2;color:#dedede;font-size:26px;text-align:center;-webkit-transform:rotate(-45deg);-ms-transform:rotate(-45deg);-o-transform:rotate(-45deg);transform:rotate(-45deg)}
.ContactForm p.contact-form-success-message-with-border{background:#83B641;color:#fff;border-radius:100px}
.contact-form-widget{background-color:#FBFBFB; border:1px solid #f7eeee; padding: 22px 22px; max-width:650px;}

.post .thumb {float: left; height: 20%; width: 20%;}

.bot-twenty{margin-bottom:20px; }
.blog-pager {text-align: center;}

.post-title{font-size: 22px; line-height: 28px; font-weight:600; margin:0 0 14px; }
.sidebar-wrapper a, .post-title a{color:#555;}
.sidebar-wrapper a:hover {}

.related-posts li{margin: 0 0 18px;}
.related-item h2{font-size:13.5px; line-height: 22px; font-weight:600; margin: 0 0 2px; }
.related-item .meta-price{font-weight:600; color:#23A215; font-size:15px; }

.post-snippet .snippet-fade {bottom: 0; position: absolute;}
.post-snippet{margin:12px 0 0;}

.post-filter-message {background-color:; width:100%; color: #fff; font-size:15.5px; letter-spacing:.9px; margin:0px 0 25px; padding: 12px 16px;}
.post-filter-message a {color: #fff; cursor: pointer; padding-left: 30px; white-space: nowrap;}
.post-filter-message .search-label, .post-filter-message .search-query {font-style: italic; quotes: "\201c" "\201d" "\2018" "\2019";}
.post-filter-message .search-label:before, .post-filter-message .search-query:before {content: open-quote;}
.post-filter-message .search-label:after, .post-filter-message .search-query:after {content: close-quote;}
.post-filter-message .show-more{float:right;}

.error-home{color: #111111; padding: 10px 0 20px;}
.error-home h3{font-size: 26px; line-height: 1; margin: 0 0 16px; padding:16px 0; border-bottom:1px solid #ccc;}
.error-home h4, .error-home p{font-size:17px; line-height: 1; font-weight:400; }
.error-home h4{margin:0 0 25px;}
.error-home p{margin:0 0 18px; }
.error-home a{border: 1px solid #999; background:#f1f1f1; opacity:.8; padding: 8px 12px; color:#666; font-size: 15px; font-weight:600; display:inline-block; border-radius:4px;}
.error-home a:hover{opacity:1;}

.post-labels{width:100%; margin:0 0 20px; float:left; }
.post-labels span, .post-labels a {height: 22px; font-size: 13px; line-height: 22px; font-weight: 400; margin: 0; }
.post-labels a {margin: 0 0 0px; color:#777; display:inline-block; transition: all .17s ease;}
.post-labels span, .feet-icons span{color:#444; }
.post-labels span{float:left; margin-right:4px;}

.post-labels a::after {content: ", "; }
.post-labels a:last-child::after {content: ""; }

body.feed-view .byline.post-labels a, body.feed-view .labels-more a {background-color: #ffffff; box-shadow: 0 0 2px 0 rgba(0, 0, 0, 0.18);  opacity: 0.9;}
.post .labels-container a {display: inline-block; max-width: calc(100% - 16px); overflow-x: hidden; text-overflow: ellipsis; vertical-align: top; white-space: nowrap;}
.post .labels-outer-container {margin: 0 -4px; position: absolute; top: 12px; transition: opacity 0.2s ease 0s; width: calc(100% - 2 * 16px);}

#blog-pager {float:left; width:100%; margin:0 0 20px;}
#blog-pager a {color: #fff; background: ; cursor: pointer; text-transform: uppercase;}

.PopularPosts .post{overflow:hidden;margin:20px 0 0}
.PopularPosts .post:first-child{padding:0;margin:0;border:0}
.PopularPosts .post-image-link{position:relative;width:80px; float:left;overflow:hidden;display:block;vertical-align:middle; border:1px solid #eee; margin:0 12px 0 0}

.PopularPosts .post-thumb {display: block; position: relative; width: 100%; height: 100%; object-fit: cover; z-index: 1;}
.PopularPosts .post-info{overflow:hidden}
.PopularPosts .post-title{font-size:15px; line-height:21px; font-weight:600; margin:0 0 5px; }
.PopularPosts .post-title a{display:block; transition:color .17s}
.PopularPosts .post-title a:hover{}
.PopularPosts .post-date{font-size:13px;}

.whatsend{}
a.whatsend{background: #2BD34B !important;}
.whatsend svg{fill: #fff; width: 20px; height: 36px;}

.snipter{float:left; max-height: calc(21px * 6); overflow: hidden; }

.topper{display: flex;}
.topper li{list-style:none;}
.tableft{}
.tabmid{flex-grow: 1;}
.tabright{}

.search {float: left; margin: 0 20px;}
.search h3{display:none;}
.search-submit-container button {border: 0 none; font-family:'Open Sans',sans-serif; color: #fff; letter-spacing: .6px; cursor: pointer; font-size: 14px; margin: 1px 0 0 -72px; padding:12px 13px; position: absolute; overflow: hidden; border-radius:0px 5px 5px 0px;}
.search-input input {border:2px solid #e6e6e6; padding:5px 5px; height:45px; text-indent:3px; border-radius:5px; width:550px; float:left; font-size:15px;  }
.search-input input::placeholder {color:#7e7e7e; font-family:'Open Sans',sans-serif; }
.search-input{padding:0 10px; margin:0 0;}
.search-submit-container button:hover{opacity:.9;}

.menu-page {float:right; }
.menu-page li{float:left; }
.menu-page a:hover{opacity:.9;}
a.cart-details:hover{color:#fff;}

.showpageNum a, .showpage a, .showpagePoint {cursor: pointer; font-size: 13.4px; font-weight: 500; padding: 6px 12px; display: inline-block; border-radius:4px; transition:all .5s ease-out}
.showpageNum a:hover, .showpage a:hover, .showpagePoint {opacity:.8; color:#fff;  }
.showpageOf {display:none; margin-right:30px; margin-left:8px; }
.showpagePoint, .showpage a, .showpageNum a { margin: 0 3px 0; }

.breadcrumbs{color:#b8b8b8; margin:0 0 6px; overflow:hidden; white-space:nowrap; text-overflow:ellipsis;}
.breadcrumbs a{color:#b8b8b8; margin:0 0; line-height:normal; font-size:14px; }
.breadcrumbs .breadhome a{margin:0 5px 0 0}
.breadlabel a{}
.breadlabel:before { content: "/"; padding-right: 3px; color: #d2d2d2;}
.breadlabel:first-child:before { content: ""; padding-right: 0; }
.breadcrumbs a:hover{}

.post-wrapper {position: relative;}

body.feed-view .post-wrapper .snippet-thumbnail {display: block; background-position: center; background-size: cover; width: 100%;}

#related-article{display: block; margin: 2px 0 16px; float: left; width: 100%;}
#related-article ul {}
#related-article ul li{margin:0 0px 16px; }
#related-article h4 a{margin:8px 0 0; color:#606060; font-size:16px; line-height:22px; font-weight:400; display:block; transition:all .3s;}
#related-article h4 a:hover{color:;}
#related-article img{transition:all .3s ease-out; border: 1px solid #ddd; width: 99%; height:100%;}
.bimb {height: 135px; position: relative;}
#related-article h5 {font-size: 16px; text-transform: uppercase; line-height:26px; margin: 0 0 25px; padding-bottom: 15px; font-weight: 700; letter-spacing: 1px; text-align: center; position: relative;}
#related-article h5:after {content: ''; position: absolute; width: 4px; height: 4px; background: #aaa; border-radius: 50%; bottom: 0; left: 47%; box-shadow: 1em 0 0 0 #aaa,2em 0 0 0 #aaa;}

#related-article img:hover{opacity:0.7; }

.bukshan img{height:100%; width: 100%; }
.bukshan{width:315px; height:198px; margin:0 4% 12px 0; float:left; transition:all 0.3s ease-out 0s;}

#footer {padding:20px 0 0; overflow:hidden; z-index:10; position:relative;}
#footer h3 { margin:0 0 18px; font-size: 18px;}

.footer-wrapper{margin:0 -10px; border-top:1px solid #ddd; border-bottom:1px solid #ddd; padding: 18px 0px; overflow:hidden; }
.footer{width: calc(100% / 4); box-sizing: border-box; float:left; padding: 0 10px;} 
.footer .widget{ clear: both; margin: 0px 0px 20px; }
.footer li {border-bottom: 1px solid #ddd; list-style: none; margin: 0 !important; padding: 8px 8px !important; text-transform: capitalize;}
.footer a { color:#666; }
.footer a:hover, .footer-credits a, .med-lab a:hover{color:var(--mainC);}

.logo-footer img{max-height:50px;}

.footer-credits {margin:0 -10px; border-top:1px solid #ddd; z-index:10; position:relative; padding:18px 10px; text-transform:uppercase; font-size:12.4px;}
.img-payments{float:right; }
.bukshan:hover, .PopularPosts .item-thumbnail img:hover, .brick li img:hover{opacity:.6;}

.footer-credits a{color:#3f3f3f; font-weight:600; }

.post-body h2.ddtl{font-size:30px;margin: 0 0 10px;}

.dlab{padding:20px 0 10px; float:left; width:100%; }
.med-lab{margin:0 0 14px; float:left; width:100%; }
.med-lab h3{font-size: 14px; display: inline-block; color:#444; margin-bottom: 0; padding-right: 5px; float:left; }
.med-lab .widget-content li{display: inline-block; padding: 0 10px; float:left; position:relative; }
.med-lab .widget-content li:after{position: absolute; top: 50%; transform: translateY(-50%); right: 0; height: 12px; width: 1px; content: ""; background-color: #666;}
.med-lab .widget-content li:last-child:after{height: 0px; width: 0px; }
.med-lab a{color:#666;}

.item_add,.disab-cart{position:relative;}
.seemcard .disab-cart{cursor:alias;background-color:#363B3F;}
.seemcard .item_add:before{content:'';width:22px;height:22px;margin-right:4px;
background:rgba(0,0,0,0) url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 64 64' fill='%23fff'><path d='M60.53,18.71A2,2,0,0,0,59,18H48.85A15,15,0,0,0,34,5H30A15,15,0,0,0,15.15,18H5a2,2,0,0,0-1.53.71A2,2,0,0,0,3,20.35l5.33,30.3A6.51,6.51,0,0,0,14.77,56H49.23a6.51,6.51,0,0,0,6.41-5.36L61,20.35A2,2,0,0,0,60.53,18.71ZM30,9h4a11,11,0,0,1,10.81,9H19.19A11,11,0,0,1,30,9ZM51.71,49.94A2.52,2.52,0,0,1,49.23,52H14.77a2.5,2.5,0,0,1-2.47-2L7.38,22H56.62Z'/></svg>") center / 22px no-repeat; }
.seemcard .disab-cart:before{content:'';width:22px;height:22px;margin-right:4px;
background:rgba(0,0,0,0) url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 512 512' fill='%23fff'><polygon points='437.3,30 202.7,339.3 64,200.7 0,264.7 213.3,478 512,94'/></svg>") center / 18px no-repeat; }
.Rtl .item_add:before,.Rtl .disab-cart:before{margin-right:0px;margin-left:4px;}

.whts-btn {position:fixed; bottom:14px; right:16px; z-index:10; -webkit-transition: all 0.5s ease 0s; transition: all 0.5s ease 0s; border:0; box-shadow:rgb(0 0 0 / 40%) 2px 2px 6px;
border-radius: 50%; display: flex; -webkit-box-pack: center; justify-content: center; -webkit-box-align: center; align-items: center; cursor: pointer; user-select: none; outline: transparent; background-color: rgb(79, 206, 93); width: 58px; height: 58px;}
.whts-btn svg{width:30px; height:30px; fill:#fff;}
.whts-btn:hover{box-shadow:rgb(0 0 0 / 70%) 2px 2px 11px; }

.view-art{ }
.view-art a{font-size:17px; display:block; font-weight: 600; margin: 8px 10px 0 0px; }

.p-cart{display:flex;align-items:center;justify-content:space-between;}
.p-cart a{float:right;border-radius:4px;width:28px;height:26px;background:#555;align-items:center;justify-content:center;}

.p-cart .item_add, .p-cart .disab-cart{display:flex;}
.p-cart .disab-cart{cursor:alias;}
.p-cart .item_add:before{content:'';width:22px;height:22px;
background:rgba(0,0,0,0) url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%23fff'><path d='M21.822 7.431A1 1 0 0 0 21 7H7.333L6.179 4.23A1.994 1.994 0 0 0 4.333 3H2v2h2.333l4.744 11.385A1 1 0 0 0 10 17h8c.417 0 .79-.259.937-.648l3-8a1 1 0 0 0-.115-.921z'/><circle cx='10.5' cy='19.5' r='1.5'/><circle cx='17.5' cy='19.5' r='1.5'/></svg>") center / 25px no-repeat; }

.p-cart .disab-cart:before{content:'';width:24px;height:24px;
background:rgba(0,0,0,0) url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%23fff'><path d='M11.9584 4.25H12.0416C13.4108 4.24999 14.4957 4.24999 15.3621 4.33812C16.2497 4.42841 16.9907 4.61739 17.639 5.05052C18.1576 5.39707 18.6029 5.84239 18.9495 6.36104C19.3826 7.00926 19.5716 7.7503 19.6619 8.63794C19.75 9.5043 19.75 10.5892 19.75 11.9584V12.0416C19.75 13.4108 19.75 14.4957 19.6619 15.3621C19.5716 16.2497 19.3826 16.9907 18.9495 17.639C18.6029 18.1576 18.1576 18.6029 17.639 18.9495C16.9907 19.3826 16.2497 19.5716 15.3621 19.6619C14.4957 19.75 13.4108 19.75 12.0416 19.75H11.9584C10.5892 19.75 9.5043 19.75 8.63794 19.6619C7.7503 19.5716 7.00926 19.3826 6.36104 18.9495C5.84239 18.6029 5.39707 18.1576 5.05052 17.639C4.61739 16.9907 4.42841 16.2497 4.33812 15.3621C4.24999 14.4957 4.24999 13.4108 4.25 12.0416V11.9584C4.24999 10.5892 4.24999 9.5043 4.33812 8.63794C4.42841 7.7503 4.61739 7.00926 5.05052 6.36104C5.39707 5.84239 5.84239 5.39707 6.36104 5.05052C7.00926 4.61739 7.7503 4.42841 8.63794 4.33812C9.5043 4.24999 10.5892 4.24999 11.9584 4.25ZM16.0083 10.0515C16.3129 9.77078 16.3322 9.29631 16.0515 8.99172C15.7708 8.68714 15.2963 8.66779 14.9917 8.9485L11.1317 12.506L9.51928 10.9588C9.2204 10.6721 8.74563 10.6819 8.45884 10.9807C8.17205 11.2796 8.18185 11.7544 8.48073 12.0412L10.602 14.0767C10.888 14.3511 11.3382 14.3556 11.6296 14.087L16.0083 10.0515Z'/></svg>") center / 30px no-repeat; }

.my-cart{position:relative;float:right;height:34px;z-index:100;margin:0}
.cart-details{color: #fff; height: 42px; width: 42px; display: block; cursor: pointer; text-align: center; background:; line-height: 40px; font-size:20px;}
.my-cart .simpleCart_quantity{width: 20px; height: 20px; background-color: #4d4d4d; font-size: 12px; color: #ffffff; line-height: 20px;  top: -7px; font-weight:700; border-radius: 50%; position: absolute;}
.cart-description{position:absolute;right:0;top:42px;width:270px;background-color:#fff;padding:15px; border:1px solid #eee; visibility:hidden; opacity:0; -webkit-transform: translateY(40px); transform: translateY(40px); -webkit-transition: all 0.5s ease 0s; transition: all 0.5s ease 0s; box-shadow:0px 3px 6px rgba(0,0,0,0.2);}
.my-cart:hover .cart-description{visibility:visible;opacity:1; -webkit-transform: translateY(0px);transform: translateY(0px);}
.cart-description .headerRow{display:none}
.cart-description .itemRow{position:relative;display:block;overflow:hidden;background-color:#fff;padding:0 20px 15px 0;margin:0 0 15px;border-bottom:1px solid rgba(0,0,0,0.1)}
.cart-description .itemRow:last-child{margin:0 0 10px}
.cart-description .item-thumb{float:left;width:70px;margin-right:10px}
.cart-description .item-thumb img{width:100%;vertical-align:middle;object-fit:cover}
.cart-description .item-name{display:block;font-size:14px; line-height:20px;}
.cart-description .item-price{font-size:13px;color:#aaa;margin:0 0 10px}
.cart-description .item-decrement,.cart-description .item-increment{width:16px;float:left;text-align:center}
.cart-description .item-decrement,.cart-description .item-quantity{float:left;margin-right:5px}
.cart-description .item-decrement a,.cart-description .item-increment a{padding:1px 4px; background-color:#ddd;font-size:12px;color:#fff;text-align:center;transition:background .17s ease}
.cart-description .item-decrement a:hover,.cart-description .item-increment a:hover{}
.cart-description .item-quantity{margin:0 10px 0 5px}
.cart-description .item-total{margin:0}

.cart-description{font-weight:600;}
.cart-description .item-quantity, .cart-description .item-total{font-size:14px; }
.item-decrement a:hover, .item-increment a:hover{background-color:var(--mainC);}

.cart-description .item-increment{margin-right:5px}
.cart-description .item-remove{position:absolute;top:0;right:0}
.cart-description .item-remove a{ font-size:19px; color: #666; }
.cart-description .item-remove a:hover{}
.cart-buttons{text-align:center;display:block;clear:both}
.cart-description .simpleCart_empty,.cart-description .simpleCart_checkout{float:left; width:calc(50% - 5px); display:block; background-color:; font-size:13.2px; color:#fff; border-radius:2px; white-space:nowrap; padding:6px 0; margin:10px 0 0; }
.cart-description .simpleCart_empty{background-color:#4d4d4d;}
.cart-description .simpleCart_checkout{float:right}
.cart-description .simpleCart_empty:hover,.cart-description .simpleCart_checkout:hover{opacity:.8;}
.cart-description .simpleCart_empty:before,.cart-description .simpleCart_checkout:before{}
.cart-description .simpleCart_checkout:before{}

.my-shopping .headerRow{display:none;}
.cart-review-wrap .itemRow{}
.cart-review-wrap .itemRow div{ }
.my-shopping h2{font-size:22px; color:#4d4d4d; margin:0 0 18px;}
.cart-review-wrap{ font-weight:600; }
.cart-review-wrap .itemRow{position:relative; float:left; width:100%; margin:0 0 20px; overflow:hidden; border:1px solid #e0e0e0; color:#555; padding:12px}

.cart-review-wrap .item-thumb{float:left;width:120px; margin-right:12px}
.cart-review-wrap .item-thumb img{width:100%;vertical-align:middle; }
.cart-review-wrap .item-name{display:block;font-size:18px; line-height:24px; }
.cart-review-wrap .item-price{font-size:15px; margin:0 0 5px; }
.cart-review-wrap .item-decrement, .cart-review-wrap .item-increment{width:16px;float:left;text-align:center}
.cart-review-wrap .item-decrement,.cart-review-wrap .item-quantity,.cart-review-wrap .item-increment{float:left;margin-right:5px}
.cart-review-wrap .item-decrement a,.cart-review-wrap .item-increment a{padding:1px 4px; background-color:#ddd;font-size:12px;color:#fff;text-align:center;transition:background .17s ease}
.cart-review-wrap .item-decrement a:hover,.cart-review-wrap .item-increment a:hover{background:var(--mainC);}
.cart-review-wrap .item-quantity{margin:0 10px 0 5px}
.cart-review-wrap .item-total{margin:0}
.cart-review-wrap .item-remove{position:absolute;top:14px;right:14px; }
.cart-review-wrap .item-remove a{ font-size:19px; color: #666; }
.cart-review-wrap .item-remove a:hover{color:#444;}
.cart-review-wrap .simpleCart_items{}

.cart-review-wrap .cart-bot-element{width: 300px; border: 1px solid #ddd; padding: 16px; float: right; margin: 0px 0 10px;}
.cart-bot-element h4{margin:0 0 6px;}
.cart-review-wrap .cart-amount{ }
.cart-review-wrap .cart-subtotal{font-size: 16px; font-weight: 600; border-bottom: 1px solid #ddd; margin: 0 0px 16px 0; padding: 0 0 6px;}
.my-total{font-size: 16px; font-weight: 600; border-top: 1px solid #ddd; margin: 16px 0px 0px 0; padding: 6px 0 0px;}
.cart-review-wrap .simpleCart_total{float:right; color:var(--mainC); }
.cart-review-wrap .simpleCart_checkout{background-color:#4d4d4d; margin:12px 0 0; padding:8px 12px; border-radius:2px; font-size:14px; color:#fff; font-weight:600; float:right;}
.cart-review-wrap .simpleCart_checkout:hover{background-color:var(--mainC)}
.checkout-bill{border:none; cursor: pointer; background: none; color: #fff; font-size: 14px; font-weight: 600; font-family: 'Open Sans',sans-serif;}

.form-bret .contact-form-name, .form-bret .contact-form-email{width:300px; display:block; padding:8px 8px; margin:0 0 14px; border:2px solid #ddd; border-radius:4px;}
.form-bret .contact-form-email-message{border:2px solid #ddd; width:75%; display:block; padding:8px 8px; margin:0 0 16px; border-radius:4px; }
.form-bret label{margin:0 0 2px; display:block; color:#555; }
.form-bret abbr{ text-decoration: none; color:#E01020; }
.form-bret .contact-form-name, .form-bret .contact-form-email, .form-bret .contact-form-email-message{color: #777; }

.slider{margin:25px 0;}

.slider, .slider > div {display: block; width: 100%; height: 372px; position: relative; overflow: hidden;
-moz-transition: transform .4s; -o-transition: transform .4s; -webkit-transition: transform .4s; transition: transform .4s;}
.slider > div img{width:100%; height:100%;}
.slider > div {position: absolute;}
.slider > i {position: absolute; font-size: 50px; margin: 10px; top: 38%; transition: .3s; width: 22px; padding: 12px 8px; background: #2a2a2a; opacity:.7; cursor: pointer; line-height: 0; box-sizing: content-box; border-radius: 3px; z-index: 4;}
.slider > i svg {fill:#fff;}
.slider > i:hover {opacity:.9; transform: translateX(-2px);}
.slider > i.right:hover {transform: translateX(2px);}
.slider > i.right:active, .slider > i.left:active {transform: translateY(1px);}

.slider > .left {left: 0px;}
.slider > .right {right: 0px;}
.slider > ul {position: absolute; bottom: 10px; left: 50%; z-index: 4; padding: 0; margin: 0; transform: translateX(-50%);}

.slider > ul > li {padding: 7px; width: 18px; height: 18px; border-radius: 50%; position:relative; float: left; margin: 10px 10px 10px; cursor: pointer;
-webkit-border-radius: 50%; -moz-border-radius: 50%; border-radius: 50%;
-webkit-box-shadow: 0 0 0 2px #fff; -moz-box-shadow: 0 0 0 2px #fff; box-shadow: 0 0 0 2px #fff;
-moz-transition: .3s; -o-transition: .3s; -webkit-transition: .3s; transition: .3s;}

.slider > ul > .showli {background-color: #fff; 
-webkit-box-shadow: 0 0 0 3px rgba(255,255,255,0.3); -moz-box-shadow: 0 0 0 3px rgba(255,255,255,0.3); 
box-shadow: 0 0 0 3px rgba(255,255,255,0.3);
-moz-animation: boing .5s forwards; -o-animation: boing .5s forwards; -webkit-animation: boing .5s forwards;
animation: boing .5s forwards;}

.slider > ul > li:hover {background-color: #fff;}

.slider > ul > .showli:after, .slider > ul > li:hover:after{position: absolute; content:''; top: 0; left: 0; width: 100%; height: 100%; background-color: var(--mainC); -webkit-transition: all 0.3s; -moz-transition: all 0.3s; -ms-transition: all 0.3s; -o-transition: all 0.3s; transition: all 0.3s; -webkit-border-radius: 50%; -moz-border-radius: 50%; border-radius: 50%; -webkit-transform:scale(0.4); -moz-transform:scale(0.4); -o-transform:scale(0.4); transform:scale(0.4);}

.slider > .show {z-index: 1;}
.hideDots > ul {display: none;}
.arrows{z-index:2; position:absolute;}
.showArrows > .left {left: 0;}
.showArrows > .right {right: 0;}

@keyframes boing {
0% {transform: scale(1.2);}
40% {transform: scale(.6);}
60% {transform: scale(1.2);}
80% {transform: scale(.8);}
100% {transform: scale(1);}
}

.js-tabs .tabs {position:relative;  }

.tabs a{border-bottom: 1px solid #d3ced2; font-size:16px; font-weight:600; color:#777; padding:4px 8px; overflow: hidden; }
.js-tabs a.active {cursor: default; border-bottom: 1px solid var(--mainC); color:var(--mainC);}

.js-tabs .panel {display: none;}
.js-tabs .panel.active {display: block;}

.js-tabs .panels {padding:20px 0 0;}

.successbox .orderdetails {background-color: var(--mainC); }
.successbox ._order th {background: var(--mainC) !important; border-color:#ccc !important; }
.successbox ._order th, .infoorder th, .orderdetails th {border: 1px solid #ccc; background: #f5f8f9; }
.successbox .orderdetail .ticlehead, .successbox .infoorder .ticlehead {border-left: 3px solid var(--mainC); }
.successbox .ticlehead b{ }
.successbox p.thanks .namesuccess {color: var(--mainC); }
.successbox p.thanks .namesuccess:after {background-color: var(--mainC); }
.orderdetail{margin:0 0 25px; }
#-checkout-method em{font-style:normal; }

.banner3,.fourthing{margin:0 0 20px;}
.PopularPosts .meta-price{font-weight:700; color:#23A215; font-size:15px; height:30px; line-height:30px; }

/* --- Remove to reduce CSS size or if you aren&#39;t using RTL --- */
/* RTL Mode */.Rtl .search-input input, .Rtl .menu, .Rtl .slogy, .Rtl .footer, .Rtl .apploads, .Rtl .socal a, .Rtl .socal, .Rtl .contact-form-button.customform-ok, .Rtl .med-lab h3, .Rtl .feet-icons span, .Rtl .feet-icons a, .Rtl .col-left, .Rtl .med-lab .widget-content li, .Rtl .main-wrapper, .Rtl .seemcard a, .Rtl .menu-page li, .Rtl .cart-description .simpleCart_empty, .Rtl .leftmenulist{float:right; }.Rtl .search-submit-container button{border-radius:5px 0px 0px 5px; } .Rtl .cates, .Rtl .img-payments, .Rtl .sidebar-wrapper, .Rtl .cart-description .simpleCart_checkout, .Rtl .col-right, .Rtl .item_add, .Rtl .contact-form-button, .Rtl .contact-form-button.disabled:hover{float:left; } .Rtl .cates li{border-right:2px solid #e1e1e1; border-left:0; } .Rtl .cates i {margin: 0 0 0 3px; } .Rtl .ico-fourth{padding-left: 0px; padding-right: 67px; } .Rtl .fourthing i {right:10px;} .Rtl .with-ul:after {left: 5px; right:unset; } .Rtl .logo-footer .widget-title {padding-left: 0px; padding-right:50px; } .Rtl .producting h3 {padding-left: 1.2%; padding-right: 0;} .Rtl .megamenuid li div.megasubmenu{left:unset; right:0;} .Rtl .PopularPosts .post-image-link {float: right; margin: 0 0 0 12px;} .Rtl .view-art a {margin: 8px 0 0 10px; } .Rtl ul.megamenuid .menu-icon {border-right: 4px solid #777; border-left:unset; } .Rtl .product_off {left: 10px; right:unset; } .Rtl .seemcard a{margin:0px 0px 0 10px;} .Rtl .producting .product_off {left: 22px; right:unset; } .Rtl .post-labels span {float: right; margin-right: 0px; margin-left:4px; } .Rtl .post-body ol, .Rtl .post-body ul{text-align:right;} .Rtl .widget .post-body .checkout-options ul li label img{margin-right: 10px; margin-left: 0px;} .Rtl .uk-checkout-wrap .item-remove{left:14px; right:unset; } .Rtl .uk-checkout-wrap .item-decrement, .Rtl .uk-checkout-wrap .item-quantity, .Rtl .uk-checkout-wrap .item-increment {float: right; margin-right: 0px; margin-left:5px; } .Rtl .uk-checkout-wrap .item-thumb {float: right; margin-left: 12px; margin-right:0;} .Rtl .med-lab .widget-content li:after{left:0; right:unset; } .Rtl .peekar button{left:4px; right:unset; } .Rtl .hamburger{left:20px; right:unset; } .Rtl td,.Rtl th,.Rtl .successbox ._order table,.Rtl .infoorder table,.Rtl .orderdetails table{text-align:right; } body.Rtl{background-color: #fff; color:#666; font:14px/1.8 'Droid Arabic Kufi', 'Open Sans', sans-serif; letter-spacing:0px;}
.Rtl .cart-description, .Rtl ul.megamenuid .menu-icon, .Rtl .successbox p.thanks .print {right: unset; left:0;}
/* --- End --- */

@media screen and (-webkit-min-device-pixel-ratio:0) {

}


@media (max-width: 1140px) {
.slider, .slider > div{height:300px;}
.ccrt{display:none;}

}

@media (max-width: 1080px) {
.slider, .slider > div{height:290px;}

}

@media (max-width: 1030px) {
.contained {padding: ;}
.main-wrapper{width:calc(100% - 275px);}
.search-input input{width:100%; }
.sidebar-wrapper{}
.bukshan{width:230px; height:160px; margin:6px 3% 12px 0;}
.slider > ul{display:none;}

.col-left{width:280px; }
.col-right{width:calc(100% - 295px)}

}

@media (max-width: 1000px) {
.main-wrapper{ }
.cart-review-wrap .item-name{width:260px;}
.producting li {width: calc(100% / 5);}
}


@media (max-width: 960px) {
.slider, .slider > div{height:280px; }
.banner3,.fourthing{width: calc(100% / 2);}
.main-wrapper {width:100%;}
.Rtl .menu-page{float:left; }
.Rtl #header{float:right; }
.sidebar-wrapper{float:unset;margin-left:auto;margin-right:auto;}
.ccrt{display:unset;}
}

@media (max-width: 900px) {
.vert-ad{width: calc(100% / 1);}
}

@media (max-width: 840px) {

a.menu-btn { display: block; }
.menu { clear: both; min-width: inherit; float: none; margin:0; background-color: #2E2E2E;}
.menu, ul.megamenu ul { overflow: hidden; max-height: 0; background-color: #2E2E2E; }
.megamenu li > ul.sub-menu { padding: 0px; border: none; }
.menu.active, ul.megamenu ul.active {max-height: 100%; width:100%;}
ul.megamenu li > a {line-height:50px; color:#ddd;}
.menu li, ul.megamenu > li { display: block; }
.menu li a {display: block; border-top: 1px solid #444; position: relative; }
.menub li.with-ul > a:after {content: '+'; position: absolute; top: 0; right: 0; display: block; font-size: 1.5em; padding: 0.55em 0.5em;}
.menub li.with-ul > a.active:after {content: "-";}
.menu ul ul li > a {line-height:38px;}
.menu ul ul > li a {padding:0px 0px 0px 26px; background:#555; color:#ddd;}
.Rtl .menu ul ul > li a{padding:0px 26px 0px 0px;}
.menu ul ul > li a:hover, .menu ul li > a:hover{color:#fff; }
.with-ul:after, ul.megamenuid .menu-icon, .cates li {border:0;}

.megamenuid li div.megasubmenu{position:unset; width:100%; box-shadow: none; visibility:visible; opacity:1; -moz-transform:translate(0,0); -webkit-transform:translate(0,0); -o-transform:translate(0,0); transform:translate(0,0); background:#2e2e2e; padding:0 25px; }
.leftmenulist {background: none; border-right: 0; min-height: 173px; width: 100%;}
.rightmenulist{float:left; display:none; }
ul.megamenuid .loading-icon{background:none;}

.peekar{ display: flex; display: block !important; height:48px; } .tabmid{display:none; }
}

@media (max-width: 840px) {
#header{margin:0;}
.cates li a{padding:0 8px 0 0px;}
.cart-review-wrap .item-name{width:280px;}
.footer,.producting li {width: calc(100% / 4);}

}

@media (max-width: 800px) {
.topper {display: block;}
.slider, .slider > div{height:220px; }
.slider > div img{height:auto;}
.footer {width: calc(100% / 3);}
.bulean:hover{right:-122px; }
}

@media (max-width: 750px) {
.regent {width:calc(100% / 1);}
.footer{width: calc(100% / 2);}
.hider{display:none !important;}
.form-bret .contact-form-email-message{width:100%; }
.ccrt{display:none;}
}

@media (max-width: 685px) {
.col-left{width:300px; margin:0 auto 16px; float:none;}
.col-right{width:100%; }
}

@media (max-width: 630px) {
.producting li {width: calc(100% / 3);}
.banner3,.fourthing{width: calc(100% / 1);}
.slider, .img-payments, .slogy {display:none;}
.cates{float:left; }

.cart-review-wrap .item-name{width:auto; }
.cart-review-wrap .item-price, .cart-review-wrap .item-decrement a, .cart-review-wrap .item-increment a, .cart-review-wrap .item-quantity, .cart-review-wrap .item-total{margin-top:8px;}
.cart-review-wrap .item-name{margin-top:0;}

}

@media (max-width: 603px) {
.related-posts li {width: calc(100% / 4);}

}

@media (max-width: 550px) {


}

@media (max-width: 500px) {
.footer, .delate {width: calc(100% / 1);}
.producting li {width: calc(100% / 2);}
.related-posts li {width: calc(100% / 3);}

.cart-review-wrap .item-remove a{top:40%; left:3px;}
.cart-review-wrap .item-thumb{margin:0 2% 0 0px; }
.cart-review-wrap .item-name{width:70%; }
.cart-review-wrap .item-price, .cart-review-wrap .item-total{width:24%;}
.cart-review-wrap .item-name{margin-bottom:0;}

}

@media (max-width: 400px) {
a.menu-btn {}
.hamburger{ }
.related-posts li {width: calc(100% / 2);}

.cart-review-wrap .item-price, .cart-review-wrap .item-decrement a, .cart-review-wrap .item-increment a, .cart-review-wrap .item-quantity{display:none; }
.cart-review-wrap .item-name{width:60%; }
.cart-review-wrap .cart-bot-element{width:100%;}

.add_product{display:none;}

}

@media (max-width: 340px) {
.contained {padding: 0 14px;}
.delate {width: calc(100% / 1);}
.hamburger{left:28px; }
.form-bret .contact-form-name, .form-bret .contact-form-email{width:100%; }

}

@media (max-width: 300px) {


}

@media (max-width: 260px) {
.contained {padding: 0 10px;}
#header{margin-left:0px;}
.bukshan{height:130px;}
.bhider{display:none !important;}

.cart-review-wrap .item-thumb{display:none;}
.cart-review-wrap .item-name, .cart-review-wrap .item-total{width:100%; padding-left:12px;}

.product-header{padding:0; border:0;}

}


]]></b:skin>
  
<style>
#ContactForm1{
    overflow:hidden;
    width:100%;
    padding:20px;
    background:#fff;
    margin:20px 0 2px;
    border:1px solid #e1e8ed;
    border-radius:3px;
    box-shadow:0 1px 0 0 rgba(0,0,0,0.02)
}
 .contact-form-widget{
    max-width:100%
}
 .contact-style{
    height:40px;
    line-height:30px;
    font-size:13px;
    font-family:inherit;
    box-shadow:none!important;
    outline:none;
    padding:5px 10px;
    margin:0 0 16px;
    border:1px solid #e1e8ed!important;
    border-radius:3px;
    box-sizing:border-box;
}
 .contact-style:hover{
    border-color:#c6c6c6!important
}
 .contact-style:focus{
    border-color:#1C74E9 !important
}
 .contact-style.error{
    border-color:red!important
}
.customform .contact-form-email-message{
    display:none!important
}
  
.address-flix{display:flex;}
.customform-address{flex:1;}
.customform-postal{width:25%;margin-left:20px;}
.formone{width:100%;display:grid;grid-template-columns:repeat(2,1fr);grid-gap:20px;}
  
 .contact-form-email-message,.customform-message{
    width:100%;
    max-width:100%;
    height:auto!important;
    min-height:100px;
    float:left
}
 .contact-form-button,.contact-form-button.disabled:hover{
    float:right;
    width:calc(200px - 5px);
    max-width:calc(200px - 5px);
    height:40px;
    font-family:inherit;
    font-size:15px;
    color:#fff;
    font-weight:500;
    cursor:pointer;
    background:#00b140!important;
    border:0!important;
    box-shadow:none!important;
    border-bottom:2px solid rgba(0,0,0,0.1)!important;
    border-radius:3px
}
 .contact-form-button.customform-ok{
    float:left;
    background:#2196F3!important
}
 .contact-form-button.disabled{
    opacity:.65;
    cursor: not-allowed!important;
}
 .contact-form-button:hover{
    background:$(main.color.bb.hover)!important
}
 .contact-form-button.customform-ok:hover{
    background:#00a03a!important
}
 .contact-form-error-message-with-border{
    float:left;
    width:100%;
    background:#fff;
    text-align:left;
    font-size:14px;
    color:#e74c3c;
    border:0;
    box-shadow:none;
    margin:10px 0 0
}
 .contact-form-success-message-with-border{
    float:left;
    width:100%;
    background:#fff;
    text-align:left;
    font-size:14px;
    color:#3c97ef;
    border:0;
    box-shadow:none;
    margin:10px 0 0
}
 .contact-form-cross{
    cursor:pointer;
    vertical-align:middle;
    margin:-3px 0 0 4px
}

.uk-checkout-wrap .itemRow{position:relative; float:left; background-color:#fff; border:1px solid #e0e0e0; width:100%; padding:14px; margin:0 0 15px; }
.uk-checkout-wrap .itemRow:last-child{margin:0 0 10px}
.uk-checkout-wrap .item-thumb{float:left;width:120px; margin-right:12px}
.uk-checkout-wrap .item-thumb img{width:100%;vertical-align:middle; }
.uk-checkout-wrap .item-name{display:block;font-size:18px; line-height:24px;}
.uk-checkout-wrap .item-price{font-size:15px; margin:0 0 5px; }
.uk-checkout-wrap .item-decrement, .uk-checkout-wrap .item-increment{width:16px;float:left;text-align:center}
.uk-checkout-wrap .item-decrement,.uk-checkout-wrap .item-quantity,.uk-checkout-wrap .item-increment{float:left;margin-right:5px}
.uk-checkout-wrap .item-decrement a,.uk-checkout-wrap .item-increment a{padding:1px 4px; background-color:#ddd;font-size:12px;color:#fff;text-align:center;transition:background .17s ease}
.uk-checkout-wrap .item-decrement a:hover,.uk-checkout-wrap .item-increment a:hover{background:var(--mainC);}
.uk-checkout-wrap .item-quantity{margin:0 10px 0 5px}
.uk-checkout-wrap .item-total{margin:0}
.uk-checkout-wrap .item-remove{position:absolute;top:14px;right:14px; }
.uk-checkout-wrap .item-remove a{ font-size:19px; color: #666; }
.uk-checkout-wrap{font-weight:600;}
.uk-checkout-wrap .item-size{margin:0 0 10px; }
.uk-checkout-wrap .item-quantity, .uk-checkout-wrap .item-total{font-size:14px; }
.uk-checkout-wrap .item-remove a, .uk-checkout-wrap .item-decrement a:hover,.uk-checkout-wrap .item-increment a:hover{background-color:;}

.successbox, .-bank-details, .-upi-details {display: none;}
  
._order {
margin-bottom: 20px;
}
.successbox p.thanks {
position: relative;
display: block;
font-size: 18px;
color: #111111;
line-height: 1.5em;
font-weight: 700;
margin: 10px 0 20px;
padding: 0 0 10px;
border-bottom: 1px solid #ebebeb;
}
.successbox p.thanks .namesuccess {
font-style: italic;
opacity:.8;
position: relative;
}
.successbox p.thanks .namesuccess:after {
position: absolute;
content: &#39;&#39;;
width: 100%;
opacity:.8;
height: 2px;
bottom: -2px;
left: 0;
margin: 0;
}
.successbox p.thanks .print {
position: absolute;
right: 0;
top: 0;
bottom: 0;
margin: auto;
height: 20px;
}
.successbox ._order table, .infoorder table, .orderdetails table {
display: table;
text-align: left;
border: 1px solid #aaa;
border-collapse: collapse;
width: 100%;
margin:0 0;
box-sizing:border-box;
}
.orderdetails table {
background: #f5f8f9;
}
.successbox ._order th, .infoorder th, .orderdetails th {
padding: 10px 20px;
width: 200px;
}
.successbox ._order th {
display: table-cell;
border-right: none !important;
color:#fff;
}
.successbox ._order td img {
max-height: 17px;
margin-left: 10px;
top: 3px;
}
.successbox ._order td, .infoorder td, .orderdetails td {
padding: 10px 20px;
border: 1px solid #ccc;
}
.successbox ._order td {
border: 1px solid #ccc;
}
.successbox .ticlehead {
font-size: 18px;
margin-bottom: 15px;
line-height: 1.6em;
color:#222;
margin-top: 0;
}
.successbox .orderdetail .ticlehead, .successbox .infoorder .ticlehead {
background: #f0f0f0;
padding: 10px 12px;
display: block;
vertical-align: middle;
margin: 10px 0;
font-size: 16px;
white-space: nowrap;
text-transform: capitalize;
letter-spacing: 1px;
position: relative;
font-weight: 600;
box-sizing: border-box;
}
.successbox .orderdetails {
width: 100%;
box-sizing: border-box;
padding: 4px;
background: var(--mainC);
}
.-upi-details {
background: #f6f8f9;
border: 1px solid #e1e5e7;
padding: 20px;
margin:0 0 30px;
box-sizing: border-box;
}
.-bank-details {
margin:0 0 30px;
box-sizing: border-box;
}
.-bank-details .infoorder, .-bank-details .infoorder th {
background: rgba(0, 141, 253, 0.11);
}
.-upi-details .infoorder ul {
padding: 0;
margin: 0;
overflow: hidden;
}
.-upi-details .infoorder ul li {
display: block;
width: 33.3333%;
box-sizing: border-box;
float: left;
padding: 15px;
}
.-upi-details .infoorder ul li:before {
display:none;
}
.-upi-details .infoorder ul li img {
max-width: 100%;
max-height: 100%;
}
.-upi-details .infoorder ul li span {
background: #34bd5c;
display: block;
text-align: center;
color: #fff;
padding: 6px 5px;
box-sizing: border-box;
font-weight: bold;
letter-spacing: 1px;
font-size: 18px;
}
.-upi-details .infoorder ul li.paytm-qr span {
background:#2DB45F;
}
.-upi-details .infoorder ul li.phonepe-qr span {
background:#E63B2F;
}
.-upi-details .infoorder ul li.gpay-qr span {
background:#01BAF2;
}
  
  .widget .post-body .checkout-options ul {
    padding: 14px 14px;
    margin-top: 10px;
    background: #fff;
    margin: 10px 0 20px;
    border: 1px solid #e0e0e0;
list-style:none;
box-sizing:border-box;
}
.widget .post-body .checkout-options ul li {
margin: 0 0 20px;
    padding: 0;
line-height: 35px;
list-style: none;
    list-style-type: none;
}
.widget .post-body .checkout-options ul li:before {
display:none;
}
.widget .post-body .checkout-options ul li label input {
     -webkit-appearance: checkbox;
     -moz-appearance: checkbox;
     appearance: checkbox;
}
.widget .post-body .checkout-options ul li label img {
    position: absolute;
    display: inline-block;
    text-align: left;
    margin-left: 10px;
}

  
 .errorWrap{
    color:#29313a;
    text-align:center;
    padding:120px 0 100px
}
 .errorWrap h3{
    font-size:160px;
    line-height:1;
    margin:0 0 30px
}
 .errorWrap h3 span{
    display:inline-block;
    vertical-align:top;
    font-size:140px
}
 .errorWrap h4{
    font-size:25px;
    margin:0 0 20px
}
 .errorWrap p{
    color:#656565;
    padding:0 0 50px
}
 .errorWrap a{
    display:-inline;
    background-color:#3c97ef;
    font-size:15px;
    color:#fff;
    font-weight:500;
    padding:10px 20px;
    border-radius:3px
}
 .errorWrap a:hover{
    background-color:#3688d7
}
 .queryEmpty{
    width:70%;
    margin:0 auto;
    text-align:center;
    padding:0 10px
}
 .queryEmpty span{
    background-color:#fff;
    display:block;
    font-size:14px;
    padding:15px 0;
    margin:40px 0 0;
    border:1px solid #e1e8ed;
    border-radius:3px;
    box-shadow:0 1px 0 0 rgba(0,0,0,0.02)
}
 .cod-but{
    display:none;
}
  
@media (max-width: 500px) {
.formone{grid-template-columns:repeat(1,1fr);grid-gap:0px;}
.customform-postal{width:160px;margin-left:0px;}
.address-flix{display:block;}
}
  
@media only screen and (max-width: 480px) {
.contact-form.customform .contact-form-name, .customform-phone, .customform-address, .customform-state, .contact-form.customform .contact-form-email, .customform-postal, .customform-city, .customform-country {width: 100%; max-width: 100%; float: none; }
.contact-form-button,.contact-form-button.disabled:hover{width:calc(48% - 5px); max-width:calc(48% - 5px);
}
  .widget .post-body .checkout-options ul li label img {
    position: static;
    margin: 5px 0 0;
    display: block;
}
.widget .post-body .checkout-options ul li {
    line-height: inherit;
}
.-upi-details .infoorder ul li {
    width: 100%;
    padding: 5px;
}
.successbox ._order table, .infoorder table, .orderdetails table {
    display: block;
}
.successbox ._order table tbody, .infoorder table tbody, .orderdetails table tbody {
    display: block;
}
.successbox ._order table tbody tr, .infoorder table tbody tr, .orderdetails table tbody tr {
    display: block;
}
.successbox ._order th, .orderdetails th, .infoorder th {
    display: block;
    width: 100%;
    box-sizing: border-box;
}
.successbox ._order td, .infoorder td, .orderdetails td {
    display: block;
    box-sizing: border-box;
    text-align: center;
}
}
@media only screen and (max-width: 340px) {
}
</style>
  
<b:if cond='data:view.isLayoutMode'>
<b:template-skin>
<![CDATA[
html,body#layout #outer-wrapper, body#layout .row{width:auto; padding:0; }
body#layout .bow, body#layout .outer-wrapper{margin:0; display: flex; flex-wrap:wrap;} 
body#layout{position:relative; width:980px; background-color:#f9f9f9; padding:95px 0px 0; margin:0; }
body#layout:before{content:'SouqStore by Bloggertheme9.com'; position:absolute; top:0; left:5px; right:5px; height:95px; font-size:18px; font-family:Roboto,sans-serif; color:#1f2024; line-height:95px;text-align:center; }
body#layout div.section{display:block; background-color:#f1f1f1 !important; margin:0 5px 20px !important; padding:16px 16px 18px !important; border-color:#e5e5e5; }
body#layout .section h4{font-size:14px; color:#1f2024; text-transform:uppercase; margin:0; }
body#layout .section h4:after{text-transform:initial; color:#656565; font-weight:400; }
body#layout .add_widget a{color:#3c97ef !important}
body#layout .widget-content{width:auto; max-width:none; max-height:none; margin:0; border:1px solid #e5e5e5; border-left:0; }
body#layout .locked-widget .widget-content{border-left:2px solid #3c97ef; }
body#layout .locked-widget .widget-content:hover{border-left-color:#00b140; }
body#layout .header-logo, body#layout .main-menu-wrap{width:40%}
body#layout #content-wrapper{padding:0; margin:0; }
body#layout .main-wrapper{width:66%; float:left;}
body#layout .sidebar-wrapper{width:34%; float:right; margin-top:16px;}
body#layout .section > h4:after{font-size:12px; }
body#layout .header-logo > h4:after{content:' - Recommended Height (34px)'; }
body#layout .main > h4:after{content:' - Default Blog Posts'; }
body#layout .med-lab > h4:after{content:' - Footer category label'; }
body#layout #footer1 > h4:after{content:' - Short description here'; }
body#layout #footer5 > h4:after{content:' - Social profile links'; }
body#layout .banner2{float:left; width:48%; margin:0; }
body#layout .footer,body#layout .med-lab{width:28%;display:inline-block !important;}
body#layout .theme-options{display:block; }
body#layout .vert-menu, body#layout .slider, body#layout #search_top, body#layout .cates, body#layout .menu-page, body#layout .menu, body#layout .tabmid{display: none;}
body#layout .footer{}
]]></b:template-skin>
</b:if>

<b:if cond='data:view.isMultipleItems'>
<style>
.post-title{font-size: 14px; line-height: 20px;}

.grid-view{display:flex; flex-wrap: wrap; margin-left: 0px; margin-right: 0px;}
.index-post{width:calc(100% / 4); padding:12px; margin:0 0 30px; border: 1px solid #eee; background: #f8f8f8;}

.meta-price{font-weight:700; color:#23A215; font-size:15px; height:30px; line-height:30px; }


@media (max-width: 620px) {
.index-post { width: calc(100% / 3);}

}


@media (max-width: 500px) {
.index-post{width:calc(100% / 2);}

}

@media (max-width: 340px) {


}

@media (max-width: 300px) {


}

@media (max-width: 260px) {


}

</style>
</b:if>

<b:if cond='data:blog.pageType == &quot;static_page&quot;'>
<style type='text/css'>
.post-title{margin:0 0 6px;}
.post-body{} 
</style>
</b:if>

<b:if cond='data:blog.url == data:blog.homepageUrl'>
<style type='text/css'>

@media (max-width: 840px) {

}

</style>
</b:if>

<b:if cond='data:blog.canonicalUrl == &quot;https://souqstore-bloggertheme9.blogspot.com/p/wishlist.html&quot;'>
<style type='text/css'>

.thumb-wishlist{overflow:hidden; float:left; width:100%; }
.shopping-thumb img{width:100%; height:auto; }
.wishlist-title{font-size:14px; line-height:20px; font-weight:600; margin:0 0 4px;}
.wishlist-page {display: flex; flex-wrap: wrap; margin-left: -12px; margin-right: -12px;}
.shopping-item {width: calc(100% / 4); padding-left: 12px; padding-right: 12px; margin: 0 0 25px;}
h1.post-title{display:none;}

@media (max-width: 650px) {
.shopping-item {width: calc(100% / 3);}

}

@media (max-width: 460px) {
.shopping-item {width: calc(100% / 2);}

}

@media (max-width: 240px) {
.shopping-item {width: 80%;}

}

</style>
</b:if>

<script type='text/javascript'>
//<![CDATA[
var monthFormat = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"],
    noThumbnail = "https://3.bp.blogspot.com/-zLt7J5ZUuJ8/Xq1wKD_SqyI/AAAAAAAABdE/7aQugbcCRN4aQNqRehD2_HqtZ5cuBTBYACLcBGAsYHQ/s1600/No_Image_Available.jpg",
    postPerPage = 16,
    paymentOption = "PayPal",
    paypalMail = "123@gmail.com",
    currencyOption = "USD",
    shippingOption = "10"

//]]>
</script>

<b:if cond='data:view.isHomepage'>
<script type='text/javascript'>
//<![CDATA[
(function($) {"use strict";
$.fn.sliderResponsive = function(settings) {
var set = $.extend( {slidePause: 4000, fadeSpeed: 800, autoPlay: "on", showArrows: "off", hideDots: "off"}, settings ); 
var $slider = $(this); var size = $slider.find("> div").length; var position = 0; var sliderIntervalID;
$slider.append("<ul></ul>"); $slider.find("> div").each(function(){$slider.find("> ul").append('<li></li>');});
$slider.find("div:first-of-type").addClass("show");
$slider.find("li:first-of-type").addClass("showli")
$slider.find("> div").not(".show").fadeOut();
if (set.autoPlay === "on") { startSlider();}
if (set.showArrows === "on") {$slider.addClass('showArrows'); }
if (set.hideDots === "on") {$slider.addClass('hideDots'); }
function startSlider() {sliderIntervalID = setInterval(function() {nextSlide();}, set.slidePause);}
$slider.mouseover(function() {if (set.autoPlay === "on") {clearInterval(sliderIntervalID);} });
$slider.mouseout(function() { if (set.autoPlay === "on") {startSlider(); } });
$slider.find("> .right").click(nextSlide)
$slider.find("> .left").click(prevSlide);
function nextSlide() {position = $slider.find(".show").index() + 1;
if (position > size - 1) position = 0; changeCarousel(position);}
function prevSlide() {position = $slider.find(".show").index() - 1;
if (position < 0) position = size - 1; changeCarousel(position);}
$slider.find(" > ul > li").click(function() {position = $(this).index(); changeCarousel($(this).index()); });
function changeCarousel() {$slider.find(".show").removeClass("show").fadeOut();
$slider .find("> div") .eq(position) .fadeIn(set.fadeSpeed) .addClass("show");
$slider.find("> ul").find(".showli").removeClass("showli");
$slider.find("> ul > li").eq(position).addClass("showli"); }
return $slider;};
})(jQuery);
$(document).ready(function() { $("#slider1").sliderResponsive({// Using default everything // slidePause: 5000, // fadeSpeed: 800,  // autoPlay: "on", // showArrows: "off", // hideDots: "off", // titleBarTop: "off" 
}); }); 
//]]>
</script>
</b:if>

<b:defaultmarkups>
  <b:defaultmarkup type='Common'>
      <!--[ Normal page condition ]-->
      <b:includable id='blogPost'>
        <style>/*<![CDATA[*/ .mainbar{flex-basis:100%} .sidebar{display:none; flex:0 0 530px;margin:50px auto 0} .sidebar::before{display:none} .sideIn{width:100%} .product-header{display:none;} /*]]>*/</style>
      </b:includable>
    <b:includable id='widget-title'>
      <b:if cond='data:defaultTitle or data:title'>
        <div class='widget-title'>
          <h3 class='title'>
            <data:title/>
          </h3>
        </div>
      </b:if>
    </b:includable>    
  </b:defaultmarkup>
  <b:defaultmarkup type='AdSense,Blog'>
   <b:includable id='defaultAdUnit'>
          <!-- Clear out style (need non-empty string) -->
          <b:with value='&quot;/* Done in css. */&quot;' var='style'>
            <b:include name='super.defaultAdUnit'/>
          </b:with>
   </b:includable>
  </b:defaultmarkup>
  <b:defaultmarkup type='PopularPosts'>
    <b:includable id='main' var='this'>
      <b:include name='widget-title'/>
      <div class='widget-content'>
        <b:loop values='data:posts' var='post'>
          <b:include data='post' name='postContent'/>
        </b:loop>
      </div>
    </b:includable>
    <b:includable id='postContent' var='post'>
      <div class='post'>
        <div class='post-content'>
          <a class='post-image-link' expr:href='data:post.url'>
            <b:if cond='data:post.featuredImage'>
              <img class='post-thumb' expr:alt='data:post.title' expr:src='data:post.featuredImage resizeImage 680'/>
              <b:else/>
              <img class='post-thumb' expr:alt='data:post.title' src='https://4.bp.blogspot.com/-O3EpVMWcoKw/WxY6-6I4--I/AAAAAAAAB2s/KzC0FqUQtkMdw7VzT6oOR_8vbZO6EJc-ACK4BGAYYCw/w680/nth.png'/>
            </b:if>
          </a>
          <div class='post-info'>
            <h2 class='post-title'>
              <a expr:href='data:post.url'><data:post.title/></a>
            </h2>
            <div class='title-secondary'>
              <span class='post-date published' expr:datetime='data:post.date.iso8601'><data:post.date/></span>
            </div>
          </div>
        </div>
      </div>
    </b:includable>
  </b:defaultmarkup>
  <b:defaultmarkup type='Header'>
    <b:includable id='main' var='this'>
      <div class='header-widget'>
        <b:include cond='data:imagePlacement in {&quot;REPLACE&quot;, &quot;BEFORE_DESCRIPTION&quot;}' name='image'/>
        <b:include cond='data:imagePlacement == &quot;BEHIND&quot;' name='title'/>
      </div>
    </b:includable>
    <b:includable id='image'>
      <a class='header-image-wrapper' expr:href='data:blog.homepageUrl'>
        <img expr:alt='data:blog.title.escaped' expr:data-height='data:height' expr:data-width='data:width' expr:src='data:image'/>
      </a>
    </b:includable>
  </b:defaultmarkup>
  <b:defaultmarkup type='FeaturedPost'>
    <b:includable id='main' var='this'>
      <b:include name='widget-title'/>
      <div class='widget-content'>
        <b:loop values='data:posts' var='post'>
          <b:include data='post' name='postContent'/>
        </b:loop>
      </div>
    </b:includable>
    <b:includable id='postContent' var='post'>
      <div class='post'>
        <div class='post-content'>
          <a class='post-image-link' expr:href='data:post.url'>
            <b:if cond='data:post.featuredImage'>
              <img class='post-thumb' expr:alt='data:post.title' expr:src='data:post.featuredImage resizeImage 680'/>
              <b:else/>
              <img class='post-thumb' expr:alt='data:post.title' src='https://4.bp.blogspot.com/-O3EpVMWcoKw/WxY6-6I4--I/AAAAAAAAB2s/KzC0FqUQtkMdw7VzT6oOR_8vbZO6EJc-ACK4BGAYYCw/w680/nth.png'/>
            </b:if>
            <span class='post-tag'><data:post.labels.last.name/></span>
          </a>
          <div class='post-info'>
            <h2 class='post-title'>
              <a expr:href='data:post.url'><data:post.title/></a>
            </h2>
            <div class='title-secondary'>
              <span class='post-date published' expr:datetime='data:post.date.iso8601'><data:post.date/></span>
            </div>
          </div>
        </div>
      </div>
    </b:includable>
  </b:defaultmarkup>
  <b:defaultmarkup type='Label'>
    <b:includable id='main' var='this'>
      <b:include name='widget-title'/>
      <b:include name='content'/>
    </b:includable>
    <b:includable id='content'>
      <div class='widget-content'>
        <b:class expr:name='data:this.display + &quot;-label&quot;'/>
        <b:include cond='data:this.display == &quot;list&quot;' name='list'/>
        <b:include cond='data:this.display == &quot;cloud&quot;' name='list'/>
      </div>
    </b:includable>
    <b:includable id='list'>
      <ul>
        <b:loop values='data:labels' var='label'>
          <li>
            <a class='label-name' expr:href='data:label.url'>
              <data:label.name/>
              <b:if cond='data:this.showFreqNumbers'>
                <span class='label-count'><data:label.count/></span>
              </b:if>
            </a>
          </li>
        </b:loop>
      </ul>
    </b:includable>
  </b:defaultmarkup>
  <b:defaultmarkup type='FollowByEmail'>
    <b:includable id='main' var='this'>
      <b:include name='content'/>
    </b:includable>
    <b:includable id='content'>
      <div class='widget-content'>
        <b:if cond='data:defaultTitle or data:title'>
          <h3 class='title'>
            <data:title/>
          </h3>
        </b:if>
        <span class='before-text'><data:skin.vars.followByEmail/></span>
        <div class='follow-by-email-inner'>
          <form action='https://feedburner.google.com/fb/a/mailverify' expr:onsubmit='&quot;window.open(\&quot;https://feedburner.google.com/fb/a/mailverify?uri=&quot; + data:feedPath + &quot;\&quot;, \&quot;popupwindow\&quot;, \&quot;scrollbars=yes,width=550,height=520\&quot;); return true&quot;' method='post' target='popupwindow'>
            <input autocomplete='off' class='follow-by-email-address' expr:placeholder='data:messages.emailAddress' name='email' type='email'/>
            <input class='follow-by-email-submit' expr:value='data:messages.subscribe' type='submit'/>
            <input expr:value='data:feedPath' name='uri' type='hidden'/>
            <input name='loc' type='hidden' value='en_US'/>
          </form>
        </div>
      </div>
    </b:includable>
  </b:defaultmarkup>
  <b:defaultmarkup type='BlogArchive'>
    <b:includable id='main' var='this'>
      <b:include name='widget-title'/>
      <b:include name='content'/>
    </b:includable>
    <b:includable id='content'>
      <div class='widget-content'>
        <div id='ArchiveList'>
          <div expr:id='data:widget.instanceId + &quot;_ArchiveList&quot;'>
            <b:include cond='data:this.style in {&quot;FLAT&quot;, &quot;MENU&quot;, &quot;HIERARCHY&quot;}' name='flat'/>
          </div>
        </div>
      </div>
    </b:includable>
    <b:includable id='flat'>
      <ul class='flat'>
        <b:loop values='data:data' var='i'>
          <li class='archivedate'>
            <a expr:href='data:i.url'>
              <data:i.name/><span class='post-count'><data:i.post-count/></span>
            </a>
          </li>
        </b:loop>
      </ul>
    </b:includable>
  </b:defaultmarkup>
</b:defaultmarkups>
 
    <b:if cond='data:blog.adsenseClientId and !data:widgets.AdSense.empty'>
      <script async='async' src='//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js'/>
    </b:if>

    <script async='async' src='//www.gstatic.com/external_hosted/clipboardjs/clipboard.min.js'/>

</head>
<body expr:class='data:blog.pageType'>

<div id='fb-root'/>
<script async='async' crossorigin='anonymous' defer='defer' src='https://connect.facebook.net/en_US/sdk.js#xfbml=1&amp;version=v5.0'/>

  <b:class cond='data:blog.languageDirection == &quot;rtl&quot;' name='Rtl'/>
  <b:class cond='data:view.isHomepage' name='home'/>
  <b:class cond='data:view.isPage' name='item'/>
  <b:class cond='data:view.isArchive' name='index'/>
  <b:class cond='data:view.isError' name='error404'/>
  
<!-- Theme Options -->
  <div class='theme-options'>
    <b:section class='jet-panel' id='jet-panel' maxwidgets='1' name='Theme Options' showaddelement='no'>
      <b:widget id='LinkList33' locked='true' title='Payment Options' type='LinkList' version='2' visible='true'>
        <b:widget-settings>
          <b:widget-setting name='link-3'>10</b:widget-setting>
          <b:widget-setting name='sorting'>NONE</b:widget-setting>
          <b:widget-setting name='text-1'>paymentOption</b:widget-setting>
          <b:widget-setting name='link-1'>PayPal</b:widget-setting>
          <b:widget-setting name='text-0'>paypalMail</b:widget-setting>
          <b:widget-setting name='link-2'>USD</b:widget-setting>
          <b:widget-setting name='text-3'>shippingOption</b:widget-setting>
          <b:widget-setting name='link-0'>123@gmail.com</b:widget-setting>
          <b:widget-setting name='text-2'>currencyOption</b:widget-setting>
        </b:widget-settings>
        <b:includable id='main'>
          <b:include name='content'/>
        </b:includable>
        <b:includable id='content'>
          &lt;script type=&#39;text/javascript&#39;&gt;
          //&lt;![CDATA[
          <b:loop values='data:links' var='link'>
            <b:if cond='data:link.name == &quot;paymentOption&quot;'>
              var paymentOption = &quot;<data:link.target/>&quot;;
            </b:if>
            <b:if cond='data:link.name == &quot;paypalMail&quot;'>
              var paypalMail = &quot;<data:link.target/>&quot;;
            </b:if>
            <b:if cond='data:link.name == &quot;currencyOption&quot;'>
              var currencyOption = &quot;<data:link.target/>&quot;;
            </b:if>
 <b:if cond='data:link.name == &quot;shippingOption&quot;'>
              var shippingOption = &quot;<data:link.target/>&quot;;
            </b:if>
          </b:loop>
          //]]&gt;
          &lt;/script&gt;
        </b:includable>
      </b:widget>
      <b:widget id='LinkList51' locked='true' title='Upi Options' type='LinkList' version='2' visible='true'>
        <b:widget-settings>
          <b:widget-setting name='sorting'>NONE</b:widget-setting>
          <b:widget-setting name='text-1'>Gpay</b:widget-setting>
          <b:widget-setting name='link-1'>https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgdAywsflkYP8fYlZLBFsN8K5Sa3sA3UHyfYQtkscma4-h20jaMYM3YvChVut-D2DKY8fqS8BgxMEKHOYGYRROTlEZ6RisHcMjOgMsZ_qGaN_55toHKWnjFyLKL2m7TJRMxvpBfoglAF9tmyc3-006ez-QAsSnXgswk-SEog3oO60PQTrfU8Gq2UmxCAg/s1600/G-pay.png</b:widget-setting>
          <b:widget-setting name='text-0'>Paytm</b:widget-setting>
          <b:widget-setting name='link-2'>https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh4HBQAnD4Vr1x7Q2eeaXI5udwIHwwbQ1d-3ORDI25ZLhC8RQ-IUl3g7tSQxYKrX41DLBzpNjfQ5SS4acbkW1_hxA8bUpce8O1PIvPimNNXPqa6-VDAst97t9NYVVFBE-yylUnJGYvIzvtX7Knv57TIu7BA3SeRuM-5VrybJsX7VZmobjirwn8k1y_yqw/s1600/phone-pe.png</b:widget-setting>
          <b:widget-setting name='link-0'>https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjnzSQCgEr_gJ8a4rac_93RMdG6JVWAw1-yejdI7m8HwXGdcWa4xNFrMqc-OcW_ftBTXfpXbdFNTDAnGU3u2BShNbIpdDcepi2F7NrDscIFf8YiizgwYPyBSE-Qg1iB-tQ_aWsaonfTIMtSVYKjHf-fl39z-l2AVMIfaHj8Gc8h5yF66-pM15uHe4_4Sg/s1600/Paytm.png</b:widget-setting>
          <b:widget-setting name='text-2'>PhonePe</b:widget-setting>
        </b:widget-settings>
        <b:includable id='main'>
  <b:include name='widget-title'/>
  <b:include name='content'/>
</b:includable>
        <b:includable id='content'>
 <div class='widget-content'>
   <ul>
     <b:loop values='data:links' var='link'>
       <li expr:class='data:link.name'><img expr:src='data:link.target'/><span><data:link.name/></span></li>
     </b:loop>
   </ul>
 </div>
</b:includable>
      </b:widget>
      <b:widget id='LinkList61' locked='true' title='Bank Details' type='LinkList' version='2' visible='true'>
        <b:widget-settings>
          <b:widget-setting name='link-3'>Bloggertheme9</b:widget-setting>
          <b:widget-setting name='sorting'>NONE</b:widget-setting>
          <b:widget-setting name='link-4'>SA3915000671546385470007</b:widget-setting>
          <b:widget-setting name='text-1'>Branch:</b:widget-setting>
          <b:widget-setting name='link-1'>Al Aziziyah</b:widget-setting>
          <b:widget-setting name='text-0'>Bank Name:</b:widget-setting>
          <b:widget-setting name='link-2'>ALBISARI</b:widget-setting>
          <b:widget-setting name='text-3'>Account:</b:widget-setting>
          <b:widget-setting name='link-0'>Bank Al Bilad</b:widget-setting>
          <b:widget-setting name='text-2'>Swift Code:</b:widget-setting>
          <b:widget-setting name='text-4'>Account number:</b:widget-setting>
        </b:widget-settings>
        <b:includable id='main'>
  <b:include name='widget-title'/>
  <b:include name='content'/>
</b:includable>
        <b:includable id='content'>
 <div class='widget-content'>
   <ul>
     <b:loop values='data:links' var='link'>
       <li><span class='details-first'><data:link.name/></span><span class='details-second'><data:link.target/></span></li>
     </b:loop>
   </ul>
 </div>
</b:includable>
      </b:widget>
    </b:section>
  </div>

  <div class='ct-wrapper'>

    
     <b:with value='data:widgets.AdSense any (w =&gt; w.sectionId == &quot;ads&quot;)' var='hasVerticalAds'>

          <b:class cond='data:hasVerticalAds' name='vertical-ads'/>

<div class='tred'>

<div class='contained'>
  
  
<div class='slogy'>

<!-- Welcome to Souq commerce -->

Welcome to Souq commerce Store !
  
</div>

<ul class='cates'>

<!-- Customize Top Menu Here -->

<li class='bhider'><a href=''><i class='fa fa-map-marker'/> Store Location</a></li>   

<li class='hider'><a href=''><i class='fa fa-headphones'/> Help Center</a></li>   

<li><a href=''><i class='fa fa-mobile'/> Download App</a></li>   

</ul>

</div>

</div>
<div class='clear'/>
       
<header class='header-wrapper' id='header' itemscope='itemscope' itemtype='https://schema.org/WPHeader' role='banner'>

<div class='contained'>

<div class='topper'>

   <b:section class='header-logo' id='header' name='Header' showaddelement='false'>
     <b:widget id='Header1' locked='true' title='Riskystore (Header)' type='Header' version='2' visible='true'>
       <b:widget-settings>
         <b:widget-setting name='displayUrl'>https://blogger.googleusercontent.com/img/a/AVvXsEiSTy8IaMbapQgNqVPCZnfIDy2olaF0mkYioRdh5qbECYaOGC7c_duuOjeMkMxScH0aQ0n1V1LzFlXAJo6i1yJuRHC4-g9NoROlqDWjjqCKcvLKy4ztbw4zjiWlsJPKpSWRZk_GpicsXwE-ma8vcUzLlWgp4xuA555uKaxBDhZH8RmY5hUUld8ieSuzIScb=s370</b:widget-setting>
         <b:widget-setting name='displayHeight'>90</b:widget-setting>
         <b:widget-setting name='sectionWidth'>150</b:widget-setting>
         <b:widget-setting name='useImage'>true</b:widget-setting>
         <b:widget-setting name='shrinkToFit'>false</b:widget-setting>
         <b:widget-setting name='imagePlacement'>REPLACE</b:widget-setting>
         <b:widget-setting name='displayWidth'>370</b:widget-setting>
       </b:widget-settings>
       <b:includable id='main' var='this'>
    <div class='header-widget'>
      <b:include cond='data:imagePlacement in {&quot;REPLACE&quot;, &quot;BEFORE_DESCRIPTION&quot;}' name='image'/>
      <b:include cond='data:imagePlacement not in {&quot;REPLACE&quot;, &quot;BEFORE_DESCRIPTION&quot;}' name='title'/>
      <b:include cond='data:imagePlacement != &quot;REPLACE&quot;' name='description'/>
    </div>
    <b:include cond='data:imagePlacement == &quot;BEHIND&quot;' name='behindImageStyle'/>
  </b:includable>
       <b:includable id='behindImageStyle'>
    <b:if cond='data:sourceUrl'>
      <b:include cond='data:this.image' data='{                    image: data:this.image,                    selector: &quot;.header-widget&quot;                  }' name='responsiveImageStyle'/>
      <style type='text/css'>
        .header-widget {
          background-position: <data:blog.locale.languageAlignment/>;
          background-repeat: no-repeat;
        }
      </style>
    </b:if>
  </b:includable>
       <b:includable id='description'>
          <!-- Don't show description on the item page -->
          <b:include cond='not data:view.isSingleItem' name='super.description'/>
        </b:includable>
       <b:includable id='image'>
      <a class='header-image-wrapper' expr:href='data:blog.homepageUrl'>
        <img expr:alt='data:blog.title.escaped' expr:data-height='data:height' expr:data-width='data:width' expr:src='data:image'/>
      </a>
          <!-- If we are replacing the title, force it to render anyway, and it'll be hidden in CSS. -->
        </b:includable>
       <b:includable id='title'>

<b:if cond='data:blog.pageType != &quot;item&quot;'>
<b:if cond='data:blog.pageType != &quot;static_page&quot;'>
    <h1>
      <b:tag expr:href='data:blog.homepageUrl' expr:title='data:blog.title' itemprop='url' name='a' rel='bookmark'>
        <span itemprop='headline'><data:title/></span>
      </b:tag>
    </h1>
<b:else/>
    <h2>
      <b:tag expr:href='data:blog.homepageUrl' expr:title='data:blog.title' itemprop='url' name='a' rel='bookmark'>
        <span itemprop='headline'><data:title/></span>
      </b:tag>
    </h2>
</b:if>
<b:else/>
    <h2>
      <b:tag expr:href='data:blog.homepageUrl' expr:title='data:blog.title' itemprop='url' name='a' rel='bookmark'>
        <span itemprop='headline'><data:title/></span>
      </b:tag>
    </h2>
</b:if>

        </b:includable>
     </b:widget>
   </b:section>

<li class='tabmid search'>
<b:section id='search_top' name='Search (Top)' showaddelement='false'>
  <b:widget id='BlogSearch1' locked='true' title='Search This Blog' type='BlogSearch' version='2' visible='true'>
    <b:includable id='main'>
<b:include name='content'/>
</b:includable>
    <b:includable id='content'>
<div class='widget-content' role='search'>
<b:include name='searchForm'/>
</div>
</b:includable>
    <b:includable id='searchForm'>
<form expr:action='data:blog.searchUrl'>
<b:attr cond='not data:view.isPreview' name='target' value='_top'/>
<b:include name='urlParamsAsFormInput'/>
<div class='search-input'>
<input aria-label='Search for Products' autocomplete='off' expr:value='data:view.isSearch ? data:view.search.query.escaped : &quot;&quot;' name='q' placeholder='Search for Products'/>
</div>
<b:include name='searchSubmit'/>
</form>
</b:includable>
    <b:includable id='searchSubmit'>
<b:if cond='data:widget.sectionId == &quot;search_top&quot;'>
<label class='search-submit-container'>
<button title='search' type='submit'>Search</button>
</label>
<b:else/>
<b:include name='super.searchSubmit'/>
</b:if>
</b:includable>
  </b:widget>
</b:section>
</li>

<ul class='menu-page'>

<!-- Top menu links -->

<li class='view-art'><a href='/p/wishlist.html'>My Wishlist</a></li>

          <li class='my-cart'>
            <a class='cart-details'><i class='fa fa-shopping-cart'/>
              <span class='simpleCart_quantity'>0</span>
            </a>
            <div class='cart-description'>
              <div class='simpleCart_items'/>
              <div class='cart-buttons-wrap'>
                <div class='cart-amount'><span class='cart-subtotal'>SUBTOTAL :</span><span class='simpleCart_total'/></div>
                <div class='cart-buttons'>
                  <a class='simpleCart_empty' href='javascript:;'><span>Empty cart</span></a><a class='simpleCart_checkout' href='/p/checkout.html'><span><i class='fa fa-credit-card'/> Checkout</span></a>
                </div>
              </div>
            </div>
          </li>

</ul>
</div><!-- topper -->

</div><!--Div Contained-->

            </header>
      <div class='clear'/>

<div class='menu-bg'>
<div class='contained'>
<div class='peekar' style='display:none;'>
<form action='/search' id='peekar'>
<input name='q' onblur='if (this.value == &quot;&quot;) {this.value = &quot;Search for Products&quot;;}' onfocus='if (this.value == &quot;Search for Products&quot;) {this.value = &quot;&quot;;}' type='text' value='Search for Products'/>
<button title='Search' type='submit'><span class='fa fa-search'/></button>
</form>
</div>
  
  <a class='menu-btn' href='#menu'> <div class='hamburger'><div/></div> Menu</a>
        
<b:section class='menu' id='menu' maxwidgets='1' showaddelement='no'>
  <b:widget id='HTML29' locked='true' title='Main Menu' type='HTML' version='2' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'>&lt;li&gt;&lt;a href=&#39;https://souqstore-bloggertheme9.blogspot.com/&#39;&gt;Home&lt;/a&gt;&lt;/li&gt;


&lt;li class=&#39;with-ul&#39;&gt;&lt;a href=&#39;#&#39;&gt;Fashion&lt;/a&gt;
&lt;ul&gt;
&lt;!-- Customize Mega Menu Here --&gt;

&lt;li&gt;&lt;a href=&#39;https://souqstore-bloggertheme9.blogspot.com/search/label/Men&#39;&gt;Men&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&#39;https://souqstore-bloggertheme9.blogspot.com/search/label/Women&#39;&gt;Women&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&#39;https://souqstore-bloggertheme9.blogspot.com/search/label/Gadgets&#39;&gt;Gadgets&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&#39;https://souqstore-bloggertheme9.blogspot.com/search/label/Furniture&#39;&gt;Furniture&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;/li&gt;

&lt;!-- Customize Navigation Menu Here --&gt;

&lt;li&gt;&lt;a href=&#39;https://souqstore-bloggertheme9.blogspot.com/2020/04/lamp-et-dolorum-fuga-extra-harum-nat.html&#39;&gt;Post right&lt;/a&gt;&lt;/li&gt;

&lt;li&gt;&lt;a href=&#39;https://souqstore-bloggertheme9.blogspot.com/2020/04/illo-inventore-veritatis-et-salvia.html&#39;&gt;Full Width&lt;/a&gt;&lt;/li&gt;

&lt;li&gt;&lt;a href=&#39;/2019/03/shortcodes-added-for-different-functions.html&#39;&gt;Shortcodes&lt;/a&gt;&lt;/li&gt;

&lt;li&gt;&lt;a href=&#39;https://souqstore-bloggertheme9.blogspot.com/?hl=ar&#39;&gt;RTL Mode&lt;/a&gt;&lt;/li&gt;</b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
<!--<b:include name='widget-title'/>-->
<div class='widget-content'>
<ul class='megamenu' id='megamenuid'>
  <data:content/>
</ul>
</div>
</b:includable>
  </b:widget>
</b:section>

</div>
</div>
<div class='clear'/>

<b:if cond='data:view.isHomepage'>
<!-- slider -->
<div class='contained'>
<b:section class='slider' id='slider1' name='Product Slider' showaddelement='no' version='3'>
  <b:widget id='Image10' locked='true' title='Slideshow 1' type='Image' version='3' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='displayUrl'>https://4.bp.blogspot.com/-5MORAWuKZRw/XqryORmehyI/AAAAAAAAACw/UUYNV-J7eGg3910DmKh4qtwSEFHmqThvgCLcBGAsYHQ/s150/slider1.jpg</b:widget-setting>
      <b:widget-setting name='displayHeight'>48</b:widget-setting>
      <b:widget-setting name='sectionWidth'>150</b:widget-setting>
      <b:widget-setting name='shrinkToFit'>false</b:widget-setting>
      <b:widget-setting name='displayWidth'>150</b:widget-setting>
      <b:widget-setting name='link'>/</b:widget-setting>
      <b:widget-setting name='caption'/>
    </b:widget-settings>
    <b:includable id='main'>
                    <b:include name='content'/>
                  </b:includable>
    <b:includable id='content'>
                    <figure>
                      <b:tag cond='data:link' expr:href='data:link' expr:title='data:title' name='a'>
                        <img expr:alt='data:title + &quot; - &quot; + data:caption' expr:src='resizeImage(data:sourceUrl, 1150, &quot;&quot;)' height='372' width='1150'/>
                      </b:tag>
                      <b:if cond='data:title AND data:caption'>
                        <figcaption style='display:none;'><data:title/> &#8212; <data:caption/></figcaption>
                      </b:if>
                    </figure>
                  </b:includable>
  </b:widget>
  <b:widget id='Image11' locked='true' title='Slideshow 2' type='Image' version='3' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='displayUrl'>https://3.bp.blogspot.com/-567MuwbssoA/XqryPNo3TRI/AAAAAAAAAC0/3pXHOX0YXsQrOGzF83U3NylLfQhiVz59ACLcBGAsYHQ/s1170/slider2.jpg</b:widget-setting>
      <b:widget-setting name='displayHeight'>372</b:widget-setting>
      <b:widget-setting name='sectionWidth'>150</b:widget-setting>
      <b:widget-setting name='shrinkToFit'>false</b:widget-setting>
      <b:widget-setting name='displayWidth'>1170</b:widget-setting>
      <b:widget-setting name='link'>/</b:widget-setting>
      <b:widget-setting name='caption'/>
    </b:widget-settings>
    <b:includable id='main'>
                    <b:include name='content'/>
                  </b:includable>
    <b:includable id='content'>
                    <figure>
                      <b:tag cond='data:link' expr:href='data:link' expr:title='data:title' name='a'>
                        <img expr:alt='data:title + &quot; - &quot; + data:caption' expr:src='resizeImage(data:sourceUrl, 1150, &quot;&quot;)' height='372' width='1150'/>
                      </b:tag>
                      <b:if cond='data:title AND data:caption'>
                        <figcaption style='display:none;'><data:title/> &#8212; <data:caption/></figcaption>
                      </b:if>
                    </figure>
                  </b:includable>
  </b:widget>
  <b:widget id='Image12' locked='true' title='Slideshow 3' type='Image' version='3' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='displayUrl'>https://2.bp.blogspot.com/-hs0B0U8DN6c/XqryPjYtsRI/AAAAAAAAAC4/5S-fmUGrOLkfIODMEQf-YPnk7ONxkcWBwCLcBGAsYHQ/s1170/slider3.jpg</b:widget-setting>
      <b:widget-setting name='displayHeight'>372</b:widget-setting>
      <b:widget-setting name='sectionWidth'>150</b:widget-setting>
      <b:widget-setting name='shrinkToFit'>false</b:widget-setting>
      <b:widget-setting name='displayWidth'>1170</b:widget-setting>
      <b:widget-setting name='link'>/</b:widget-setting>
      <b:widget-setting name='caption'/>
    </b:widget-settings>
    <b:includable id='main'>
                    <b:include name='content'/>
                  </b:includable>
    <b:includable id='content'>
                    <figure>
                      <b:tag cond='data:link' expr:href='data:link' expr:title='data:title' name='a'>
                        <img expr:alt='data:title + &quot; - &quot; + data:caption' expr:src='resizeImage(data:sourceUrl, 1150, &quot;&quot;)' height='372' width='1150'/>
                      </b:tag>
                      <b:if cond='data:title AND data:caption'>
                        <figcaption style='display:none;'><data:title/> &#8212; <data:caption/></figcaption>
                      </b:if>
                    </figure>
                  </b:includable>
  </b:widget>
  <b:widget id='Image13' locked='true' title='Slideshow 4' type='Image' version='3' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='displayUrl'>https://2.bp.blogspot.com/-hDA_sao7SCA/XqryRGSxL2I/AAAAAAAAADA/vNVFali1LxELrwmSqTqqQOCqzol2s7WuACLcBGAsYHQ/s1170/slider5.jpg</b:widget-setting>
      <b:widget-setting name='displayHeight'>372</b:widget-setting>
      <b:widget-setting name='sectionWidth'>150</b:widget-setting>
      <b:widget-setting name='shrinkToFit'>false</b:widget-setting>
      <b:widget-setting name='displayWidth'>1170</b:widget-setting>
      <b:widget-setting name='link'>/</b:widget-setting>
      <b:widget-setting name='caption'/>
    </b:widget-settings>
    <b:includable id='main'>
                    <b:include name='content'/>
                  </b:includable>
    <b:includable id='content'>
                    <figure>
                      <b:tag cond='data:link' expr:href='data:link' expr:title='data:title' name='a'>
                        <img expr:alt='data:title + &quot; - &quot; + data:caption' expr:src='resizeImage(data:sourceUrl, 1150, &quot;&quot;)' height='372' width='1150'/>
                      </b:tag>
                      <b:if cond='data:title AND data:caption'>
                        <figcaption style='display:none;'><data:title/> &#8212; <data:caption/></figcaption>
                      </b:if>
                    </figure>
                  </b:includable>
  </b:widget>
  <b:widget id='Image14' locked='true' title='Slideshow 5' type='Image' version='3' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='displayUrl'>https://3.bp.blogspot.com/--4VmFDfN74M/XqryQceFnZI/AAAAAAAAAC8/uLGPLBPbEdE0Zw9LyNWz0j4pfIaznC1MgCLcBGAsYHQ/s1170/slider4.jpg</b:widget-setting>
      <b:widget-setting name='displayHeight'>372</b:widget-setting>
      <b:widget-setting name='sectionWidth'>150</b:widget-setting>
      <b:widget-setting name='shrinkToFit'>false</b:widget-setting>
      <b:widget-setting name='displayWidth'>1170</b:widget-setting>
      <b:widget-setting name='link'>/</b:widget-setting>
      <b:widget-setting name='caption'/>
    </b:widget-settings>
    <b:includable id='main'>
                    <b:include name='content'/>
                  </b:includable>
    <b:includable id='content'>
                    <figure>
                      <b:tag cond='data:link' expr:href='data:link' expr:title='data:title' name='a'>
                        <img expr:alt='data:title + &quot; - &quot; + data:caption' expr:src='resizeImage(data:sourceUrl, 1150, &quot;&quot;)' height='372' width='1150'/>
                      </b:tag>
                      <b:if cond='data:title AND data:caption'>
                        <figcaption style='display:none;'><data:title/> &#8212; <data:caption/></figcaption>
                      </b:if>
                    </figure>
                  </b:includable>
  </b:widget>
</b:section>
  
    <!-- The Arrows -->
<!--<div class='inside-slider'>
<i class='arrows left' style=''><svg viewBox='0 0 100 100'><path d='M 10,50 L 60,100 L 70,90 L 30,50  L 70,10 L 60,0 Z'/></svg></i>
<i class='arrows right' style=''><svg viewBox='0 0 100 100'><path d='M 10,50 L 60,100 L 70,90 L 30,50  L 70,10 L 60,0 Z' transform='translate(100, 100) rotate(180) '/></svg></i>
</div>-->

<section class='gap'>
<div class='contained'>
<div class='bow'>

<b:section class='fourthing' id='service-tab1' maxwidgets='1' showaddelement='no'>
  <b:widget id='HTML106' locked='false' title='Free Delivery' type='HTML' version='2' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'>We will ship free if your order exceeds $150.</b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
<i aria-hidden='true' class='fa fa-rocket'/>
<div class='ico-fourth'><b:include name='widget-title'/>
<div class='widget-content'>
<data:content/></div>
</div>
</b:includable>
  </b:widget>
</b:section>

<b:section class='fourthing' id='service-tab2' maxwidgets='1' showaddelement='no'>
  <b:widget id='HTML103' locked='false' title='Money Back' type='HTML' version='2' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'><![CDATA[If goods have problem we'll return your good.]]></b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
<i aria-hidden='true' class='fa fa-handshake-o'/>
<div class='ico-fourth'><b:include name='widget-title'/>
<div class='widget-content'>
<data:content/></div>
</div>
</b:includable>
  </b:widget>
</b:section>

<b:section class='fourthing' id='service-tab3' maxwidgets='1' showaddelement='no'>
  <b:widget id='HTML105' locked='false' title='24/7 Support' type='HTML' version='2' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'>Our dedicated support is available 24/7.</b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
<i aria-hidden='true' class='fa fa-comments'/>
<div class='ico-fourth'><b:include name='widget-title'/>
<div class='widget-content'>
<data:content/></div>
</div>
</b:includable>
  </b:widget>
</b:section>

</div>
</div><!-- contained -->
</section>
  
<div class='dab'>
<div class='bow'>
<b:section class='banner3' id='Ad-1' maxwidgets='1' name='Ad left (side)' showaddelement='yes'>
  <b:widget id='HTML5' locked='false' title='Women' type='HTML' version='2' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'><![CDATA[<div class ="mt-ad" data-text="Ads go here"></div>]]></b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
  <!--<b:include name='widget-title'/>-->
  <div class='widget-content'>
    <data:content/>
  </div>
</b:includable>
  </b:widget>
</b:section>
<b:section class='banner3' id='Ad-2' maxwidgets='1' name='Ad bottom' showaddelement='yes'>
  <b:widget id='HTML3' locked='false' title='Recent in Mens' type='HTML' version='2' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'><![CDATA[<div class="mt-ad" data-text="Ads go here"></div>]]></b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
  <!--<b:include name='widget-title'/>-->
  <div class='widget-content'>
    <data:content/>
  </div>
</b:includable>
  </b:widget>
</b:section>

<b:section class='banner3' id='Ad-3' maxwidgets='1' name='Ad right (side)' showaddelement='yes'>
  <b:widget id='HTML7' locked='false' title='Smartwatch' type='HTML' version='2' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'><![CDATA[<div class="mt-ad" data-text="Ads go here"></div>]]></b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
  <!--<b:include name='widget-title'/>-->
  <div class='widget-content'>
    <data:content/>
  </div>
</b:includable>
  </b:widget>
</b:section>
</div><!-- dab -->
</div><!-- bow -->
<div class='clear'/> 

  </div><!-- contained -->
<div class='clear'/>
</b:if>

      <div class='clear'/>

<div class='contained'>

<b:section class='crossy' id='Main-Ad' maxwidgets='1' showaddelement='yes'/>

  <div class='outer-wrapper'>

      <div class='main-wrapper top'>
              <main class='main-container' id='main' role='main' tabindex='-1'>

                <b:if cond='data:view.isMultipleItems'>
                  <h2 class='main-heading'><data:messages.posts/></h2>
                </b:if>

        <b:section class='main' id='page_body' maxwidgets='1' name='Page Body' showaddelement='yes'>
          <b:widget id='Blog1' locked='true' title='Postingan Blog' type='Blog' version='2' visible='true'>
            <b:widget-settings>
              <b:widget-setting name='commentLabel'>Comments</b:widget-setting>
              <b:widget-setting name='showShareButtons'>true</b:widget-setting>
              <b:widget-setting name='authorLabel'>by</b:widget-setting>
              <b:widget-setting name='style.unittype'>TextAndImage</b:widget-setting>
              <b:widget-setting name='timestampLabel'/>
              <b:widget-setting name='reactionsLabel'/>
              <b:widget-setting name='showAuthorProfile'>true</b:widget-setting>
              <b:widget-setting name='style.layout'>1x1</b:widget-setting>
              <b:widget-setting name='showLocation'>false</b:widget-setting>
              <b:widget-setting name='showTimestamp'>true</b:widget-setting>
              <b:widget-setting name='postsPerAd'>1</b:widget-setting>
              <b:widget-setting name='style.bordercolor'>#ffffff</b:widget-setting>
              <b:widget-setting name='showDateHeader'>false</b:widget-setting>
              <b:widget-setting name='style.textcolor'>#ffffff</b:widget-setting>
              <b:widget-setting name='showCommentLink'>true</b:widget-setting>
              <b:widget-setting name='style.urlcolor'>#ffffff</b:widget-setting>
              <b:widget-setting name='postLocationLabel'/>
              <b:widget-setting name='showAuthor'>true</b:widget-setting>
              <b:widget-setting name='style.linkcolor'>#ffffff</b:widget-setting>
              <b:widget-setting name='style.bgcolor'>#ffffff</b:widget-setting>
              <b:widget-setting name='showLabels'>true</b:widget-setting>
              <b:widget-setting name='postLabelsLabel'>Tags</b:widget-setting>
              <b:widget-setting name='showBacklinks'>false</b:widget-setting>
              <b:widget-setting name='showInlineAds'>false</b:widget-setting>
              <b:widget-setting name='showReactions'>false</b:widget-setting>
            </b:widget-settings>
            <b:includable id='main' var='this'> 

              <b:include name='FilterMessage'/>

<!--[ Normal page condition ]-->
<b:class cond='data:view.url != data:view.url params { amp: &quot;1&quot; } and data:view.isSingleItem and data:posts any (p =&gt; p.labels any (l =&gt; l.name in [ &quot;Blog&quot; ]))' name='blogP'/>
<b:include cond='data:view.url != data:view.url params { amp: &quot;1&quot; } and data:view.isSingleItem and data:posts any (p =&gt; p.labels any (l =&gt; l.name in [ &quot;Blog&quot; ]))' name='blogPost'/>
              
              <div class='blog-posts hfeed container'>
                <b:class cond='data:view.isMultipleItems' name='index-post-wrap'/>
                <b:class cond='data:view.isSingleItem' name='item-item-post'/>
                <b:tag class='grid-view' cond='data:view.isMultipleItems' name='div'>
                  <b:loop index='i' values='data:posts' var='post'>
                    <b:include data='post' name='postCommentsAndAd'/>
                  </b:loop>
                </b:tag>
              </div>
              <b:include cond='data:view.isMultipleItems' name='NextPrev'/>
              <b:include name='feedLinks'/>
              <script type='text/javascript'>
                var messages = { 
                  showMore: &quot;<data:messages.showMore/>&quot;
                }
              </script>
            </b:includable>
            <b:includable id='Delate' var='post'>
              <!-- Related Posts -->
                <div id='related-wrap'>
                  <!--<div class='title-wrap'>
                    <h3><data:allBylineItems.backlinks.label/></h3>
                  </div>-->
                  <div class='related-ready'>
                    <b:if cond='data:post.labels'>
                      <div class='related-tag' expr:data-label='data:post.labels.first.name'/>
                      <b:else/>
                      <div class='related-tag' data-label='random'/>
                    </b:if>
                  </div> 
                </div>   
            </b:includable>
            <b:includable id='FilterMessage'>

       <b:if cond='data:view.search.query'>
       <div class='post-filter-message'>
       <b:if cond='data:posts.empty'>
       <span class='result'/><data:view.search.resultsMessageHtml/>
       <a class='show-more' expr:href='data:blog.homepageUrl'><data:messages.showAll/></a>
       <b:else/>
       <span class='result'><data:view.search.resultsMessageHtml/></span>
       <a class='show-more' expr:href='data:blog.homepageUrl'><data:messages.showAll/></a>
       </b:if>
       </div>
       </b:if>

       <b:if cond='data:view.search.label'>
       <div class='post-filter-message'>
       <b:if cond='data:posts.empty'>
       <span class='result'><data:view.search.resultsMessageHtml/></span>
       <a class='show-more' expr:href='data:blog.homepageUrl'><data:messages.showAll/></a>
       <b:else/>
       <span class='result'><data:view.search.resultsMessageHtml/></span>
       <a class='show-more' expr:href='data:blog.homepageUrl'><data:messages.showAll/></a>
       </b:if>
       </div>
       </b:if>
       
       <b:if cond='data:view.isArchive'>
       <div class='post-filter-message'>
       <b:if cond='data:posts.empty'>
       <span class='result'><data:view.archive.rangeMessage/></span>
       <a class='show-more' expr:href='data:blog.homepageUrl'><data:messages.showAll/></a>
       <b:else/>
       <span class='result'><data:view.archive.rangeMessage/></span>
       <a class='show-more' expr:href='data:blog.homepageUrl'><data:messages.showAll/></a>
       </b:if>
       </div>
       </b:if>

       <b:if cond='data:view.isError'>
       <div class='error-home'>
       <h3>Page Not Found</h3>
       <h4>The requested page does not exist. We will try to automatically redirect you in 12 seconds.</h4>
       <p>Please go to the <data:blog.title/> home page by clicking the button below.</p>
       <a class='error' expr:href='data:blog.homepageUrl'><data:blog.title/> Home</a>
       </div>
       </b:if>

       <b:if cond='data:view.isMultipleItems and data:posts.empty'>
       <div class='nothing'><data:messages.noResultsFound/></div>
       </b:if>
    
        
    </b:includable>
            <b:includable id='NextPrev'>
              <!-- Post Pagination Index -->
              <div class='blog-pager container' id='blog-pager'>
                <b:include cond='data:newerPageUrl' name='previousPageLink'/>
                <b:include cond='data:olderPageUrl' name='nextPageLink'/>
                <b:include cond='data:view.url != data:blog.homepageUrl' name='homePageLink'/>
              </div>
            </b:includable>
            <b:includable id='PostArticle' var='post'>
              <!-- Item Post Content -->
              <b:include data='post' name='postMeta'/>
              <b:include data='post' name='postHeader'/>
              <b:include data='post' name='postBody'/>
              <b:include cond='data:view.isPost' data='post' name='postFooter'/>
            </b:includable>
            <b:includable id='PostTime' var='post'>
              <b:if cond='data:allBylineItems.timestamp'>
                <span class='post-date published' expr:datetime='data:post.date.iso8601'><data:post.date/></span>
              </b:if>
            </b:includable>
            <b:includable id='aboutPostAuthor'>

        <div class='about-author'>
        <b:if cond='data:post.author.authorPhoto.image'>
        <img class='author-avatar' expr:alt='data:post.author.name' expr:src='data:post.author.authorPhoto.image resizeImage 100'/>               <b:else/>
        <img class='author-avatar' expr:alt='data:post.author.name' src='https://1.bp.blogspot.com/-bcG0duKLi0U/XH5uKJyOs3I/AAAAAAAAA8c/939x6jQXytcaLhV8Q0oJsqMW3BVNirZrgCLcBGAs/s100/admin-logo.jpg'/>
        </b:if>
        <h5>
        <span><data:messages.postedBy/></span>
        <a expr:alt='data:post.author.name' expr:href='data:post.author.profileUrl' target='_blank'> <data:post.author.name/></a>
        </h5>
        <span class='author-description'><data:post.author.aboutMe/></span>
        </div>

            </b:includable>
            <b:includable id='addComments'>
  <a expr:href='data:post.commentsUrl' expr:onclick='data:post.commentsUrlOnclick'>
    <b:message name='messages.postAComment'/>
  </a>
</b:includable>
            <b:includable id='backLinks' var='post'>
              <b:comment>Disabled</b:comment>         
            </b:includable>
            <b:includable id='blogThisShare'>
  <b:with value='&quot;window.open(this.href, \&quot;_blank\&quot;, \&quot;height=270,width=475\&quot;); return false;&quot;' var='onclick'>
    <b:include name='platformShare'/>
  </b:with>
</b:includable>
            <b:includable id='breadcrumb' var='post'>

<div class='breadcrumbs' itemscope='itemscope' itemtype='https://schema.org/BreadcrumbList'>

<b:loop index='num' values='data:post.labels' var='label'>
<span class='breadlabel' itemprop='itemListElement' itemscope='itemscope' itemtype='https://schema.org/ListItem'>
<a expr:href='data:label.url + &quot;?&amp;max-results=16&quot;' expr:title='data:label.name' itemprop='item'>
<span itemprop='name'><data:label.name/></span></a>
<meta expr:content='data:num+2' itemprop='position'/>
</span>
<b:if cond='data:label.isLast != &quot;true&quot;'> 

</b:if>
</b:loop>
</div>

            </b:includable>
            <b:includable id='bylineByName' var='byline'>
  <b:switch var='data:byline.name'>
  <b:case value='share'/>
    <b:include cond='data:post.shareUrl' name='postShareButtons'/>
  <b:case value='comments'/>
    <b:include cond='data:post.allowComments' name='postCommentsLink'/>
  <b:case value='location'/>
    <b:include cond='data:post.location' name='postLocation'/>
  <b:case value='timestamp'/>
    <b:include cond='not data:view.isPage' name='postTimestamp'/>
  <b:case value='author'/>
    <b:include name='postAuthor'/>
  <b:case value='labels'/>
    <b:include cond='data:post.labels' name='postLabels'/>
  <b:case value='icons'/>
    <b:include cond='data:post.emailPostUrl' name='emailPostIcon'/>
  <b:case value='reactions'/>
    <b:include cond='data:post.reactionsUrl' name='postReactions'/>
  </b:switch>
</b:includable>
            <b:includable id='bylineRegion' var='regionItems'>
  <b:loop values='data:regionItems' var='byline'>
    <b:include data='byline' name='bylineByName'/>
  </b:loop>
</b:includable>
            <b:includable id='comment-form' var='post'>
  <div class='comment-form'>
    <a name='comment-form'/>
    <b:if cond='data:mobile'>
      <h5 id='comment-post-message'>
        <a expr:id='data:widget.instanceId + &quot;_comment-editor-toggle-link&quot;' href='javascript:void(0)'><data:postCommentMsg/></a></h5>
      <p><data:blogCommentMessage/></p>
      <data:blogTeamBlogMessage/>
      <a expr:href='data:post.commentFormIframeSrc' id='comment-editor-src'/>
      <iframe allowtransparency='true' class='blogger-iframe-colorize blogger-comment-from-post' expr:height='data:cmtIframeInitialHeight' frameborder='0' id='comment-editor' name='comment-editor' src='' style='display: none' width='100%'/>
    <b:else/>
      <h5 id='comment-post-message'><data:postCommentMsg/></h5>
      <p><data:blogCommentMessage/></p>
      <data:blogTeamBlogMessage/>
      <a expr:href='data:post.commentFormIframeSrc' id='comment-editor-src'/>
      <iframe allowtransparency='true' class='blogger-iframe-colorize blogger-comment-from-post' expr:height='data:cmtIframeInitialHeight' frameborder='0' id='comment-editor' name='comment-editor' src='' width='100%'/>
    </b:if>
    <data:post.cmtfpIframe/>
    <script type='text/javascript'>
      BLOG_CMT_createIframe(&#39;<data:post.appRpcRelayPath/>&#39;);
    </script>
  </div>
</b:includable>
            <b:includable id='commentAuthorAvatar'>
  <div class='avatar-image-container'>
    <img class='author-avatar' expr:src='data:comment.authorAvatarSrc' height='35' width='35'/>
  </div>
</b:includable>
            <b:includable id='commentDeleteIcon' var='comment'>
  <span expr:class='&quot;item-control &quot; + data:comment.adminClass'>
    <b:if cond='data:showCmtPopup'>
      <div class='goog-toggle-button'>
        <div class='goog-inline-block comment-action-icon'/>
      </div>
    <b:else/>
      <a class='comment-delete' expr:href='data:comment.deleteUrl' expr:title='data:top.deleteCommentMsg'>
        <img src='https://resources.blogblog.com/img/icon_delete13.gif'/>
      </a>
    </b:if>
  </span>
</b:includable>
            <b:includable id='commentForm' var='post'>
  <div class='comment-form'>
    <a name='comment-form'/>
    <h5 id='comment-post-message'>Post a Review</h5>
    <b:if cond='data:this.messages.blogComment != &quot;&quot;'>
      <p><data:this.messages.blogComment/></p>
    </b:if>
    <b:include data='post' name='commentFormIframeSrc'/>
    <iframe allowtransparency='allowtransparency' class='blogger-iframe-colorize blogger-comment-from-post' expr:height='data:cmtIframeInitialHeight ?: &quot;90px&quot;' frameborder='0' id='comment-editor' name='comment-editor' src='' width='100%'/>
    <data:post.cmtfpIframe/>
    <script type='text/javascript'>
      BLOG_CMT_createIframe(&#39;<data:post.appRpcRelayPath/>&#39;);
    </script>
  </div>
</b:includable>
            <b:includable id='commentFormIframeSrc' var='post'>
  <a expr:href='data:post.commentFormIframeSrc' id='comment-editor-src'/>
</b:includable>
            <b:includable id='commentItem' var='comment'>
  <div class='comment' expr:id='&quot;c&quot; + data:comment.id'>
    <b:include cond='data:blog.enabledCommentProfileImages' name='commentAuthorAvatar'/>

    <div class='comment-block'>
      <div class='comment-author'>
        <b:if cond='data:comment.authorUrl'>
          <b:message name='messages.authorSaidWithLink'>
            <b:param expr:value='data:comment.author' name='authorName'/>
            <b:param expr:value='data:comment.authorUrl' name='authorUrl'/>
          </b:message>
        <b:else/>
          <b:message name='messages.authorSaid'>
            <b:param expr:value='data:comment.author' name='authorName'/>
          </b:message>
        </b:if>
      </div>
      <div expr:class='&quot;comment-body&quot; + (data:comment.isDeleted ? &quot; deleted&quot; : &quot;&quot;)'>
        <data:comment.body/>
      </div>
      <div class='comment-footer'>
        <span class='comment-timestamp'>
          <a expr:href='data:comment.url' title='comment permalink'>
            <data:comment.timestamp/>
          </a>
          <b:include data='comment' name='commentDeleteIcon'/>
        </span>
      </div>
    </div>
  </div>
</b:includable>
            <b:includable id='commentList' var='comments'>
  <div id='comments-block'>
    <b:loop values='data:comments' var='comment'>
      <b:include data='comment' name='commentItem'/>
    </b:loop>
  </div>
</b:includable>
            <b:includable id='commentPicker' var='post'>
  <b:if cond='data:post.showThreadedComments'>
    <b:include data='post' name='threadedComments'/>
  <b:else/>
    <b:include data='post' name='comments'/>
  </b:if>
</b:includable>
            <b:includable id='comment_count_picker' var='post'>
  <b:if cond='data:post.commentSource == 1'>
    <span class='cmt_count_iframe_holder' expr:data-count='data:post.numComments' expr:data-onclick='data:post.addCommentOnclick' expr:data-post-url='data:post.url' expr:data-url='data:post.url.canonical.http'>
    </span>
  <b:else/>
    <a class='comment-link' expr:href='data:post.addCommentUrl' expr:onclick='data:post.addCommentOnclick'>
      <data:post.commentLabelFull/>:
    </a>
  </b:if>
</b:includable>
            <b:includable id='comment_picker' var='post'>
  <b:if cond='data:post.commentSource == 1'>
    <b:include data='post' name='iframe_comments'/>
  <b:elseif cond='data:post.showThreadedComments'/>
    <b:include data='post' name='threaded_comments'/>
  <b:else/>
    <b:include data='post' name='comments'/>
  </b:if>
</b:includable>
            <b:includable id='comments' var='post'>
  <div class='comments' id='comments'>
    <a name='comments'/>
    <b:if cond='data:post.allowComments'>
      <h4><data:post.commentLabelFull/>:</h4>

      <b:if cond='data:post.commentPagingRequired'>
        <span class='paging-control-container'>
          <b:if cond='data:post.hasOlderLinks'>
            <a expr:class='data:post.oldLinkClass' expr:href='data:post.oldestLinkUrl'><data:post.oldestLinkText/></a>
              &#160;
            <a expr:class='data:post.oldLinkClass' expr:href='data:post.olderLinkUrl'><data:post.olderLinkText/></a>
              &#160;
          </b:if>

          <data:post.commentRangeText/>

          <b:if cond='data:post.hasNewerLinks'>
            &#160;
            <a expr:class='data:post.newLinkClass' expr:href='data:post.newerLinkUrl'><data:post.newerLinkText/></a>
            &#160;
            <a expr:class='data:post.newLinkClass' expr:href='data:post.newestLinkUrl'><data:post.newestLinkText/></a>
          </b:if>
        </span>
      </b:if>

      <div expr:id='data:widget.instanceId + &quot;_comments-block-wrapper&quot;'>
        <dl expr:class='data:post.avatarIndentClass' id='comments-block'>
          <b:loop values='data:post.comments' var='comment'>
            <dt expr:class='&quot;comment-author &quot; + data:comment.authorClass' expr:id='data:comment.anchorName'>
              <b:if cond='data:comment.favicon'>
                <img expr:src='data:comment.favicon' height='16px' style='margin-bottom:-2px;' width='16px'/>
              </b:if>
              <a expr:name='data:comment.anchorName'/>
              <b:if cond='data:blog.enabledCommentProfileImages'>
                <data:comment.authorAvatarImage/>
              </b:if>
              <b:if cond='data:comment.authorUrl'>
                <a expr:href='data:comment.authorUrl' rel='nofollow'><data:comment.author/></a>
              <b:else/>
                <data:comment.author/>
              </b:if>
              <data:commentPostedByMsg/>
            </dt>
            <dd class='comment-body' expr:id='data:widget.instanceId + data:comment.cmtBodyIdPostfix'>
              <b:if cond='data:comment.isDeleted'>
                <span class='deleted-comment'><data:comment.body/></span>
              <b:else/>
                <p>
                  <data:comment.body/>
                </p>
              </b:if>
            </dd>
            <dd class='comment-footer'>
              <span class='comment-timestamp'>
                <a expr:href='data:comment.url' title='comment permalink'>
                  <data:comment.timestamp/>
                </a>
                <b:include data='comment' name='commentDeleteIcon'/>
              </span>
            </dd>
          </b:loop>
        </dl>
      </div>

      <b:if cond='data:post.commentPagingRequired'>
        <span class='paging-control-container'>
          <a expr:class='data:post.oldLinkClass' expr:href='data:post.oldestLinkUrl'>
            <data:post.oldestLinkText/>
          </a>
          <a expr:class='data:post.oldLinkClass' expr:href='data:post.olderLinkUrl'>
            <data:post.olderLinkText/>
          </a>
          &#160;
          <data:post.commentRangeText/>
          &#160;
          <a expr:class='data:post.newLinkClass' expr:href='data:post.newerLinkUrl'>
            <data:post.newerLinkText/>
          </a>
          <a expr:class='data:post.newLinkClass' expr:href='data:post.newestLinkUrl'>
            <data:post.newestLinkText/>
          </a>
        </span>
      </b:if>

      <p class='comment-footer'>
        <b:if cond='data:post.embedCommentForm'>
          <b:if cond='data:post.allowNewComments'>
            <b:include data='post' name='comment-form'/>
          <b:else/>
            <data:post.noNewCommentsText/>
          </b:if>
        <b:elseif cond='data:post.allowComments'/>
          <a expr:href='data:post.addCommentUrl' expr:onclick='data:post.addCommentOnclick'><data:postCommentMsg/></a>
        </b:if>
      </p>
    </b:if>
    <b:if cond='data:showCmtPopup'>
      <div id='comment-popup'>
        <iframe allowtransparency='true' frameborder='0' id='comment-actions' name='comment-actions' scrolling='no'>
        </iframe>
      </div>
    </b:if>

    <div id='backlinks-container'>
    <div expr:id='data:widget.instanceId + &quot;_backlinks-container&quot;'>
       <b:include cond='data:post.showBacklinks' data='post' name='backlinks'/>
    </div>
    </div>
  </div>
</b:includable>
            <b:includable id='commentsLink'>
  <a class='comment-link' expr:href='data:post.commentsUrl' expr:onclick='data:post.commentsUrlOnclick'>
    <b:if cond='data:post.numberOfComments &gt; 0'>
      <b:message name='messages.numberOfComments'>
        <b:param expr:value='data:post.numberOfComments' name='numComments'/>
      </b:message>
    <b:else/>
      <data:messages.postAComment/>
    </b:if>
  </a>
</b:includable>
            <b:includable id='commentsLinkIframe'>
  <!-- G+ comments, no longer available. The includable is retained for backwards-compatibility. -->
</b:includable>
            <b:includable id='commentsTitle'>
              <!-- Post Commments Title -->
              <h5><data:post.numberOfComments/> Reviews</h5>

              <h6>Your rating</h6>

<fieldset class='rating'>
    <input id='star5' name='rating' type='radio' value='5'/><label class='full' for='star5' title='Awesome - 5 stars'/>
      <input id='star4' name='rating' type='radio' value='4'/><label class='full' for='star4' title='Pretty good - 4 stars'/>
    <input id='star3' name='rating' type='radio' value='3'/><label class='full' for='star3' title='Meh - 3 stars'/>
    <input id='star2' name='rating' type='radio' value='2'/><label class='full' for='star2' title='Kinda bad - 2 stars'/>
    <input id='star1' name='rating' type='radio' value='1'/><label class='full' for='star1' title='Sucks big time - 1 star'/>
</fieldset>
</b:includable>
            <b:includable id='defaultAdUnit'>
          <!-- Clear out style (need non-empty string) -->
          <b:with value='&quot;/* Done in css. */&quot;' var='style'>
            <b:include name='super.defaultAdUnit'/>
          </b:with>
   </b:includable>
            <b:includable id='emailPostIcon'>
  <span class='byline post-icons'>
    <!-- email post links -->
    <span class='item-action'>
      <a expr:href='data:post.emailPostUrl' expr:title='data:messages.emailPost'>
        <b:include data='{ iconClass: &quot;touch-icon sharing-icon&quot; }' name='emailIcon'/>
      </a>
    </span>
  </span>
</b:includable>
            <b:includable id='facebookShare'>
  <b:with value='&quot;window.open(this.href, \&quot;_blank\&quot;, \&quot;height=430,width=640\&quot;); return false;&quot;' var='onclick'>
    <b:include name='platformShare'/>
  </b:with>
</b:includable>
            <b:includable id='feedLinks'>
              <b:comment>Disabled</b:comment> 
            </b:includable>
            <b:includable id='feedLinksBody' var='links'>
              <b:comment>Disabled</b:comment> 
            </b:includable>
            <b:includable id='footerBylines' var='post'>
              <!-- Post tags category label here -->
              <!-- <b:include data='post' name='postLabels'/> -->
            </b:includable>
            <b:includable id='googlePlusShare'>
  <div class='goog-inline-block google-plus-share-container'>
    <g:plusone annotation='inline' expr:href='data:originalUrl.canonical.http' size='medium' source='blogger:blog:plusone'/>
  </div>
</b:includable>
            <b:includable id='headerByline' var='post'>
              <!-- Post Header Meta -->
                <!-- <div class='title-secondary'>

                </div>-->

<b:if cond='data:view.isSingleItem'>

<!-- Show Ads Below Post Title -->

</b:if>

            </b:includable>
            <b:includable id='homePageLink'>
              <b:comment>Disabled</b:comment> 
            </b:includable>
            <b:includable id='iframeComments' var='post'>
  <!-- G+ comments, no longer available. The includable is retained for backwards-compatibility. -->
</b:includable>
            <b:includable id='iframe_comments' var='post'>

  <b:if cond='data:post.allowIframeComments'>
    <script expr:src='data:post.iframeCommentSrc' type='text/javascript'/>
    <div class='cmt_iframe_holder' expr:data-href='data:post.url.canonical' expr:data-viewtype='data:post.viewType'/>

    <b:if cond='data:post.embedCommentForm == &quot;false&quot;'>
      <a expr:href='data:post.addCommentUrl' expr:onclick='data:post.addCommentOnclick'><data:postCommentMsg/></a>
    </b:if>
  </b:if>
</b:includable>
            <b:includable id='indexPost' var='post'>
<b:include data='post' name='postMetadataJSON'/>
              <!-- Index Post Content -->
              <div class='index-product-inner'>
                <b:include data='post' name='postFeaturedImage'/>
                <div class='product-info'>
                  <b:include data='post' name='postHeader'/>
<div class='p-cart item_price'>

  <span class='product_price meta-price'/>

<a class='item_add ren' href='javascript:;' title='Add to cart'/>
 </div>
                  
</div>
              </div>
            </b:includable>
            <b:includable id='inlineAd' var='post'>
              <b:comment>Disabled</b:comment> 
            </b:includable>
            <b:includable id='itemPost' var='post'>
              <!-- Item Post Content -->
              <b:include data='post' name='postMeta'/>
              <b:if cond='data:view.isPost'>
                <div class='product-header'>
                  <div class='col-left'>
                    <div class='post-image-wrap item_image'>
                      <b:if cond='data:post.featuredImage'> 
                        <img class='post-thumb item_thumb' expr:alt='data:post.title' expr:src='data:post.featuredImage resizeImage 680'/>
                        <b:else/>
                        <img class='post-thumb item_thumb' expr:alt='data:post.title' src='https://4.bp.blogspot.com/-O3EpVMWcoKw/WxY6-6I4--I/AAAAAAAAB2s/KzC0FqUQtkMdw7VzT6oOR_8vbZO6EJc-ACK4BGAYYCw/w680/nth.png'/>
                      </b:if>
                      <span class='product_off'/>
                    </div>
                  </div>
<div class='col-right'>

<b:include cond='data:view.isPost' data='post' name='breadcrumb'/>

<h1 class='post-title item_name'><data:post.title/>
</h1>

<div class='product_item_price item_price'><div class='tier-price product_price meta-price'/></div>

<div class='product-size'><span class='_size'>Size :</span><select class='item_size'><span class='_product_size meta-size'/></select></div>
  
<div class='reviews'>
<i class='fa fa-star checked'/>
<i class='fa fa-star checked'/>
<i class='fa fa-star checked'/>
<i class='fa fa-star'/>
<i class='fa fa-star'/>
(<data:post.numberOfComments/> customer review)
</div>

<div class='seemcard'>

<a class='add-to-wishlist' expr:data-id='data:post.id' title='Add to wishlist'><i class='fa fa-heart'/></a>

<a class='whatsend' expr:href='&quot;https://api.whatsapp.com/send?phone=96659154XXXX&amp;text=I%20wish%20to%20know%20more%20about%20this%20item%20-%20&quot; + data:post.title'><svg viewBox='0 0 308 308' x='0px' y='0px'><path d='M227.904,176.981c-0.6-0.288-23.054-11.345-27.044-12.781c-1.629-0.585-3.374-1.156-5.23-1.156   c-3.032,0-5.579,1.511-7.563,4.479c-2.243,3.334-9.033,11.271-11.131,13.642c-0.274,0.313-0.648,0.687-0.872,0.687   c-0.201,0-3.676-1.431-4.728-1.888c-24.087-10.463-42.37-35.624-44.877-39.867c-0.358-0.61-0.373-0.887-0.376-0.887   c0.088-0.323,0.898-1.135,1.316-1.554c1.223-1.21,2.548-2.805,3.83-4.348c0.607-0.731,1.215-1.463,1.812-2.153   c1.86-2.164,2.688-3.844,3.648-5.79l0.503-1.011c2.344-4.657,0.342-8.587-0.305-9.856c-0.531-1.062-10.012-23.944-11.02-26.348   c-2.424-5.801-5.627-8.502-10.078-8.502c-0.413,0,0,0-1.732,0.073c-2.109,0.089-13.594,1.601-18.672,4.802   c-5.385,3.395-14.495,14.217-14.495,33.249c0,17.129,10.87,33.302,15.537,39.453c0.116,0.155,0.329,0.47,0.638,0.922   c17.873,26.102,40.154,45.446,62.741,54.469c21.745,8.686,32.042,9.69,37.896,9.69c0.001,0,0.001,0,0.001,0   c2.46,0,4.429-0.193,6.166-0.364l1.102-0.105c7.512-0.666,24.02-9.22,27.775-19.655c2.958-8.219,3.738-17.199,1.77-20.458   C233.168,179.508,230.845,178.393,227.904,176.981z' id='XMLID_469_'/><path d='M156.734,0C73.318,0,5.454,67.354,5.454,150.143c0,26.777,7.166,52.988,20.741,75.928L0.212,302.716   c-0.484,1.429-0.124,3.009,0.933,4.085C1.908,307.58,2.943,308,4,308c0.405,0,0.813-0.061,1.211-0.188l79.92-25.396   c21.87,11.685,46.588,17.853,71.604,17.853C240.143,300.27,308,232.923,308,150.143C308,67.354,240.143,0,156.734,0z    M156.734,268.994c-23.539,0-46.338-6.797-65.936-19.657c-0.659-0.433-1.424-0.655-2.194-0.655c-0.407,0-0.815,0.062-1.212,0.188   l-40.035,12.726l12.924-38.129c0.418-1.234,0.209-2.595-0.561-3.647c-14.924-20.392-22.813-44.485-22.813-69.677   c0-65.543,53.754-118.867,119.826-118.867c66.064,0,119.812,53.324,119.812,118.867   C276.546,215.678,222.799,268.994,156.734,268.994z' id='XMLID_470_'/></svg></a>
  
<a class='item_add ren' href='javascript:;'><span class='add_product'>Add to Cart</span></a>

<a class='cart-payment' href='/p/cart.html'>
  <i class='fa fa-eye'/><span class='ccrt'> view cart</span></a>

</div>
<div class='shopping-msg'/>

                    <b:include data='post' name='postLabels'/>
                    <b:include data='post' name='postShareButtons'/>
                  </div>
                </div>
              </b:if>
              <b:if cond='data:view.isPage'>
                <h1 class='post-title'>
                  <data:post.title/>
                </h1>
              </b:if>
              <b:include data='post' name='postBody'/>
              <b:include cond='data:view.isPost' data='post' name='postFooter'/>
            </b:includable>
            <b:includable id='linkShare'>
  <b:with value='&quot;window.prompt(\&quot;Copy to clipboard: Ctrl+C, Enter\&quot;, \&quot;&quot; + data:originalUrl + &quot;\&quot;); return false;&quot;' var='onclick'>
    <b:include name='platformShare'/>
  </b:with>
</b:includable>
            <b:includable id='nextPageLink'>
              <a class='blog-pager-older-link' expr:href='data:olderPageUrl' expr:id='data:widget.instanceId + &quot;_blog-pager-older-link&quot;' expr:title='data:messages.olderPosts'>
                <data:messages.olderPosts/>
              </a>
            </b:includable>
            <b:includable id='otherSharingButton'>
  <span class='sharing-platform-button sharing-element-other' expr:aria-label='data:messages.shareToOtherApps.escaped' expr:data-url='data:originalUrl' expr:title='data:messages.shareToOtherApps.escaped' role='menuitem' tabindex='-1'>
    <b:with value='{key: &quot;sharingOther&quot;}' var='platform'>
      <b:include name='sharingPlatformIcon'/>
    </b:with>
    <span class='platform-sharing-text'><data:messages.shareOtherApps.escaped/></span>
  </span>
</b:includable>
            <b:includable id='platformShare'>
  <a expr:class='&quot;goog-inline-block sharing-&quot; + data:platform.key' expr:data-url='data:originalUrl' expr:href='data:shareUrl + &quot;&amp;target=&quot; + data:platform.target' expr:onclick='data:onclick ? data:onclick : &quot;&quot;' expr:title='data:platform.shareMessage' target='_blank'>
    <span class='share-button-link-text'>
      <data:platform.shareMessage/>
    </span>
  </a>
</b:includable>
            <b:includable id='post' var='post'>
              <!-- Post Index -->
              <b:if cond='data:view.isMultipleItems'>
                <b:include data='post' name='indexPost'/>
              </b:if>
              <!-- Post Item -->
              <b:if cond='data:view.isSingleItem'>
                <b:include data='post' name='itemPost'/>
              </b:if>
            </b:includable>
            <b:includable id='postAuthor' var='post'>
              <!-- Post Author -->
              <b:if cond='data:allBylineItems.author'>
                <span class='post-author'><b:if cond='data:post.author.authorPhoto.image'><img class='post-author-avatar' expr:alt='data:post.author.name' expr:src='resizeImage(data:post.author.authorPhoto.image, 50)'/></b:if><a expr:href='data:post.author.profileUrl' expr:title='data:post.author.name' target='_blank'><data:post.author.name/></a></span>
              </b:if>
            </b:includable>
            <b:includable id='postBody' var='post'> 
              <!-- Post Body Entry Content-->
              <div class='post-body post-content'>
                <data:post.body/>
              </div>
            </b:includable>
            <b:includable id='postBodySnippet' var='post'>
              <b:include data='post' name='postBody'/>
            </b:includable>
            <b:includable id='postCommentsAndAd' var='post'>
              <!-- Post, Comments and Ads -->
              <!-- Post Content Index and Item -->
              <div class='blog-post hentry simpleCart_shelfItem shopping-items'>
         <!-- ecommerce changes -->
                <b:class cond='data:view.isMultipleItems' name='index-post post-shop-info'/>
                <b:class cond='data:view.isSingleItem' name='item-post'/>
                <b:class cond='data:view.isPost' name='product-post'/>
                <b:attr cond='data:view.isMultipleItems' expr:value='data:post.id' name='data-id'/>

                <b:include data='post' name='post'/>
              </div>
              <!-- Comments -->
              <b:if cond='data:view.isSingleItem'>
                <div class='blog-post-comments'>
    <!-- old comments form here -->     
                </div>
              </b:if>
            </b:includable>
            <b:includable id='postCommentsLink'>
  <b:if cond='data:view.isMultipleItems'>
    <span class='byline post-comment-link container'>
      <b:include cond='data:post.commentSource != 1' name='commentsLink'/>
    </span>
  </b:if>
</b:includable>
            <b:includable id='postFeaturedImage' var='post'>
              <!-- Post Featured Image on Index -->
              <div class='post-image-wrap item_image'>
                <a class='post-image-link' expr:href='data:post.url'>
                  <b:if cond='data:post.featuredImage'> 
                    <img class='post-thumb item_thumb' expr:alt='data:post.title' expr:src='data:post.featuredImage resizeImage 680'/>
                    <b:else/>
                    <img class='post-thumb item_thumb' expr:alt='data:post.title' src='https://4.bp.blogspot.com/-O3EpVMWcoKw/WxY6-6I4--I/AAAAAAAAB2s/KzC0FqUQtkMdw7VzT6oOR_8vbZO6EJc-ACK4BGAYYCw/w680/nth.png'/>
                  </b:if>
                </a>
                <span class='product_off'/>
              </div>
            </b:includable>
            <b:includable id='postFooter' var='post'>
              
              <div class='post-footer'>
                <!-- Item added below posts -->
                <b:include data='post' name='footerBylines'/>
                <b:include cond='data:allBylineItems.icons' data='post' name='postNavigation'/>

<div class='js-tabs'>

<div class='tabs'>
<a class='tab active' href='#starks-panel' id='starks-tab'>Related Products</a>
<a class='tab' href='#lannisters-panel' id='lannisters-tab'><data:post.numberOfComments/> Reviews</a>
</div>

<div class='panels'>
<ul class='panel active' id='starks-panel'>
<b:include cond='data:allBylineItems.backlinks' data='post' name='Delate'/>
        </ul>
        <ul class='panel' id='lannisters-panel'>
            
<b:include data='post' name='commentPicker'/>
        </ul>
    </div>

</div>

              </div>

            </b:includable>
            <b:includable id='postFooterAuthorProfile' var='post'>
              <b:comment>Disabled</b:comment>   
            </b:includable>
            <b:includable id='postHeader' var='post'>
              <b:include cond='data:view.isPost' data='post' name='tagspost'/>
              <b:include data='post' name='postTitle'/>
              <b:include cond='!data:view.isPage' data='post' name='headerByline'/>
            </b:includable>
            <b:includable id='postJumpLink' var='post'>
              <b:comment>Disabled</b:comment>
            </b:includable>
            <b:includable id='postLabels' var='post'>
              <b:if cond='data:allBylineItems.labels'>
                <b:if cond='data:post.labels'>
                  <div class='post-labels'>
                    <span>Category : </span>
                    <div class='label-head Label'>
                      <b:loop values='data:post.labels' var='label'>
                        <a class='label-link' expr:href='data:label.url' rel='tag'><data:label.name/></a>
                      </b:loop>
                    </div>
                  </div>
                </b:if>
              </b:if>
            </b:includable>
            <b:includable id='postLocation'>
  <span class='byline post-location'>
    <data:byline.label/>
    <a expr:href='data:post.location.mapsUrl' target='_blank'><data:post.location.name/></a>
  </span>
</b:includable>
            <b:includable id='postMeta' var='post'>
              <b:include data='post' name='postMetadataJSON'/>
            </b:includable>
            <b:includable id='postMetadataJSONImage'>
  &quot;image&quot;: {
    &quot;@type&quot;: &quot;ImageObject&quot;,
    <b:if cond='data:post.featuredImage.isResizable'>
    &quot;url&quot;: &quot;<b:eval expr='resizeImage(data:post.featuredImage, 1200, &quot;1200:630&quot;)'/>&quot;,
    &quot;height&quot;: 630,
    &quot;width&quot;: 1200
    <b:else/>
    &quot;url&quot;: &quot;https://lh3.googleusercontent.com/ULB6iBuCeTVvSjjjU1A-O8e9ZpVba6uvyhtiWRti_rBAs9yMYOFBujxriJRZ-A=w1200&quot;,
    &quot;height&quot;: 348,
    &quot;width&quot;: 1200
    </b:if>
  },
</b:includable>
            <b:includable id='postMetadataJSONPublisher'>
 &quot;publisher&quot;: {
    &quot;@type&quot;: &quot;Organization&quot;,
    &quot;name&quot;: &quot;Blogger&quot;,
    &quot;logo&quot;: {
      &quot;@type&quot;: &quot;ImageObject&quot;,
      &quot;url&quot;: &quot;https://lh3.googleusercontent.com/ULB6iBuCeTVvSjjjU1A-O8e9ZpVba6uvyhtiWRti_rBAs9yMYOFBujxriJRZ-A=h60&quot;,
      &quot;width&quot;: 206,
      &quot;height&quot;: 60
    }
  },
</b:includable>
            <b:includable id='postNavigation' var='post'>

<!-- Greden nextprev -->

            </b:includable>
            <b:includable id='postPagination'>
  <div class='blog-pager container' id='blog-pager'>
    <b:include cond='data:newerPageUrl' name='previousPageLink'/>
    <b:include cond='data:olderPageUrl' name='nextPageLink'/>
    <b:include cond='data:view.url != data:blog.homepageUrl' name='homePageLink'/>
  </div>
</b:includable>
            <b:includable id='postReactions'>
  <span class='byline reactions'>
    <span class='reactions-label'>
      <data:byline.label/>
    </span>
    <iframe allowtransparency='true' class='reactions-iframe' expr:src='data:post.reactionsUrl' frameborder='0' name='reactions' scrolling='no'/>
  </span>
</b:includable>
            <b:includable id='postShareButtons' var='post'>
              <!-- Post ShareButtons -->
              <b:if cond='data:allBylineItems.share'>

<div class='feet-icons'>

<span>Share :</span> 
<a class='face-ico' expr:href='&quot;https://www.facebook.com/sharer.php?u=&quot; + data:post.url' onclick='window.open(this.href, &apos;windowName&apos;, &apos;width=550, height=650, left=24, top=24, scrollbars, resizable&apos;); return false;' rel='nofollow'><i class='fa fa-facebook'/> Share</a>

<a class='twi-ico' expr:href='&quot;https://twitter.com/share?url=&quot; + data:post.url + &quot;&amp;text=&quot; + data:post.title' onclick='window.open(this.href, &apos;windowName&apos;, &apos;width=550, height=450, left=24, top=24, scrollbars, resizable&apos;); return false;' rel='nofollow'><i class='fa fa-twitter'/> Tweet</a>

<a class='pint-ico' expr:href='&quot;https://www.pinterest.com/pin/create/button/?url=&quot; + data:post.url + &quot;&amp;media=&quot; + data:post.featuredImage + &quot;&amp;description=&quot; + data:post.title' onclick='window.open(this.href, &apos;windowName&apos;, &apos;width=735, height=750, left=24, top=24, scrollbars, resizable&apos;); return false;' rel='nofollow'><i class='fa fa-pinterest'/> Share</a>


<a class='link-ico' expr:href='&quot;https://www.linkedin.com/shareArticle?url=&quot; + data:post.url' onclick='window.open(this.href, &apos;windowName&apos;, &apos;width=950, height=650, left=24, top=24, scrollbars, resizable&apos;); return false;' rel='nofollow'><i class='fa fa-linkedin'/> Share</a>


<b:if cond='data:blog.isMobileRequest'>                
<a class='bitz-ico' expr:href='&quot;https://api.whatsapp.com/send?text=&quot; + data:post.title + &quot; | &quot; + data:post.url' rel='nofollow' target='_blank'><i class='fa fa-whatsapp'/> Share</a>
<b:else/>
<a class='bitz-ico' expr:href='&quot;https://web.whatsapp.com/send?text=&quot; + data:post.title + &quot; | &quot; + data:post.url' onclick='window.open(this.href, &apos;windowName&apos;, &apos;width=900, height=550, left=24, top=24, scrollbars, resizable&apos;); return false;' rel='nofollow'><i class='fa fa-whatsapp'/> Share</a>
</b:if>


</div>

              </b:if>
            </b:includable>
            <b:includable id='postTimestamp'>
  <span class='byline post-timestamp'>
    <data:byline.label/>
    <b:if cond='data:post.url'>
      <meta expr:content='data:post.url.canonical'/>
      <a class='timestamp-link' expr:href='data:post.url' rel='bookmark' title='permanent link'>
        <time class='published' expr:datetime='data:post.date.iso8601' expr:title='data:post.date.iso8601'>
          <data:post.date/>
        </time>
      </a>
    </b:if>
  </span>
</b:includable>
            <b:includable id='postTitle' var='post'>
              <!-- Post Title Index and Item -->
              <b:if cond='data:view.isMultipleItems'>
                <h2 class='post-title item_name'>
                  <a expr:href='data:post.url'><data:post.title/></a>
                </h2>
              </b:if>
            </b:includable>
            <b:includable id='postdesc' var='post'>
              <p class='post-snippet'><b:eval expr='data:post.snippets.short snippet { length: 116 }'/></p>
            </b:includable>
            <b:includable id='previousPageLink'>
              <a class='blog-pager-newer-link' expr:href='data:newerPageUrl' expr:id='data:widget.instanceId + &quot;_blog-pager-newer-link&quot;' expr:title='data:messages.newerPosts'>
                <data:messages.newerPosts/>
              </a>
            </b:includable>
            <b:includable id='sharingButton'>
  <span expr:aria-label='data:platform.shareMessage' expr:class='&quot;sharing-platform-button sharing-element-&quot; + data:platform.key' expr:data-href='data:shareUrl + &quot;&amp;target=&quot; + data:platform.target' expr:data-url='data:originalUrl' expr:title='data:platform.shareMessage' role='menuitem' tabindex='-1'>
    <b:include name='sharingPlatformIcon'/>
    <span class='platform-sharing-text'><data:platform.name/></span>
  </span>
</b:includable>
            <b:includable id='sharingButtonContent'>
  <div class='flat-icon-button ripple'>
    <b:include name='shareIcon'/>
  </div>
</b:includable>
            <b:includable id='sharingButtons'>
  <div class='sharing' expr:aria-owns='&quot;sharing-popup-&quot; + data:sharingId' expr:data-title='data:shareTitle'>
    <button class='sharing-button touch-icon-button' expr:aria-controls='&quot;sharing-popup-&quot; + data:sharingId' expr:aria-label='data:messages.share.escaped' expr:id='&quot;sharing-button-&quot; + data:sharingId' role='button'>
      <b:include name='sharingButtonContent'/>
    </button>
    <b:include name='sharingButtonsMenu'/>
  </div>
</b:includable>
            <b:includable id='sharingButtonsMenu'>
  <div class='share-buttons-container'>
    <ul aria-hidden='true' class='share-buttons hidden' expr:aria-label='data:messages.share.escaped' expr:id='&quot;sharing-popup-&quot; + data:sharingId' role='menu'>
      <b:loop values='(data:platforms ?: data:blog.sharing.platforms) filter (p =&gt; p.key not in {&quot;blogThis&quot;})' var='platform'>
        <li>
          <b:include name='sharingButton'/>
        </li>
      </b:loop>
      <li aria-hidden='true' class='hidden'>
        <b:include name='otherSharingButton'/>
      </li>
    </ul>
  </div>
</b:includable>
            <b:includable id='sharingPlatformIcon'>
  <b:include data='{ iconClass: (&quot;touch-icon sharing-&quot; + data:platform.key) }' expr:name='data:platform.key + &quot;Icon&quot;'/>
</b:includable>
            <b:includable id='tagspost' var='post'>
              <!-- Post Label/Category -->
              <b:if cond='data:view.isMultipleItems and data:post.labels'>

              </b:if>
            </b:includable>
            <b:includable id='threaded-comment-form' var='post'>
  <div class='comment-form'>
    <a name='comment-form'/>
    <b:if cond='data:mobile'>
      <p><data:blogCommentMessage/></p>
      <data:blogTeamBlogMessage/>
      <a expr:href='data:post.commentFormIframeSrc' id='comment-editor-src'/>
      <iframe allowtransparency='true' class='blogger-iframe-colorize blogger-comment-from-post' expr:height='data:cmtIframeInitialHeight' frameborder='0' id='comment-editor' name='comment-editor' src='' style='display: none' width='100%'/>
    <b:else/>
      <p><data:blogCommentMessage/></p>
      <data:blogTeamBlogMessage/>
      <a expr:href='data:post.commentFormIframeSrc' id='comment-editor-src'/>
      <iframe allowtransparency='true' class='blogger-iframe-colorize blogger-comment-from-post' expr:height='data:cmtIframeInitialHeight' frameborder='0' id='comment-editor' name='comment-editor' src='' width='100%'/>
    </b:if>
    <data:post.cmtfpIframe/>
    <script type='text/javascript'>
      BLOG_CMT_createIframe(&#39;<data:post.appRpcRelayPath/>&#39;);
    </script>
  </div>
</b:includable>
            <b:includable id='threadedCommentForm' var='post'>
  <div class='comment-form'>
    <a name='comment-form'/>
    <h5 id='comment-post-message'>Post a Review</h5>
    <b:if cond='data:this.messages.blogComment != &quot;&quot;'>
      <p><data:this.messages.blogComment/></p>
    </b:if>
    <b:include data='post' name='commentFormIframeSrc'/>
    <iframe allowtransparency='allowtransparency' class='blogger-iframe-colorize blogger-comment-from-post' expr:height='data:cmtIframeInitialHeight ?: &quot;90px&quot;' frameborder='0' id='comment-editor' name='comment-editor' src='' width='100%'/>
    <data:post.cmtfpIframe/>
    <script type='text/javascript'>
      BLOG_CMT_createIframe(&#39;<data:post.appRpcRelayPath/>&#39;);
    </script>
  </div>
</b:includable>
            <b:includable id='threadedCommentJs' var='post'>
  <script async='async' expr:src='data:post.commentSrc' type='text/javascript'/>
  <b:template-script inline='true' name='threaded_comments'/>
  <script type='text/javascript'>
    blogger.widgets.blog.initThreadedComments(
        <data:post.commentJso/>,
        <data:post.commentMsgs/>,
        <data:post.commentConfig/>);
  </script>
</b:includable>
            <b:includable id='threadedComments' var='post'>
  <section class='comments threaded' expr:data-embed='data:post.embedCommentForm' expr:data-num-comments='data:post.numberOfComments' id='comments'>
    <a name='comments'/>

    <b:include name='commentsTitle'/>

    <div class='comments-content'>
      <b:if cond='data:post.embedCommentForm'>
        <b:include data='post' name='threadedCommentJs'/>
      </b:if>
      <div id='comment-holder'>
         <data:post.commentHtml/>
      </div>
    </div>

    <p class='comment-footer'>
      <b:if cond='data:post.allowNewComments'>
        <b:include data='post' name='threadedCommentForm'/>
      <b:else/>
        <data:post.noNewCommentsText/>
      </b:if>
      <b:if cond='data:post.showManageComments'>
        <b:include data='post' name='manageComments'/>
      </b:if>
    </p>

    <b:if cond='data:showCmtPopup'>
      <div id='comment-popup'>
        <iframe allowtransparency='allowtransparency' frameborder='0' id='comment-actions' name='comment-actions' scrolling='no'>
        </iframe>
      </div>
    </b:if>
  </section>
</b:includable>
            <b:includable id='threaded_comment_js' var='post'>
  <script async='async' expr:src='data:post.commentSrc' type='text/javascript'/>

  <script type='text/javascript'>
    (function() {
      var items = <data:post.commentJso/>;
      var msgs = <data:post.commentMsgs/>;
      var config = <data:post.commentConfig/>;

// <![CDATA[
      var cursor = null;
      if (items && items.length > 0) {
        cursor = parseInt(items[items.length - 1].timestamp) + 1;
      }

      var bodyFromEntry = function(entry) {
        if (entry.gd$extendedProperty) {
          for (var k in entry.gd$extendedProperty) {
            if (entry.gd$extendedProperty[k].name == 'blogger.contentRemoved') {
              return '<span class="deleted-comment">' + entry.content.$t + '</span>';
            }
          }
        }
        return entry.content.$t;
      }

      var parse = function(data) {
        cursor = null;
        var comments = [];
        if (data && data.feed && data.feed.entry) {
          for (var i = 0, entry; entry = data.feed.entry[i]; i++) {
            var comment = {};
            // comment ID, parsed out of the original id format
            var id = /blog-(\d+).post-(\d+)/.exec(entry.id.$t);
            comment.id = id ? id[2] : null;
            comment.body = bodyFromEntry(entry);
            comment.timestamp = Date.parse(entry.published.$t) + '';
            if (entry.author && entry.author.constructor === Array) {
              var auth = entry.author[0];
              if (auth) {
                comment.author = {
                  name: (auth.name ? auth.name.$t : undefined),
                  profileUrl: (auth.uri ? auth.uri.$t : undefined),
                  avatarUrl: (auth.gd$image ? auth.gd$image.src : undefined)
                };
              }
            }
            if (entry.link) {
              if (entry.link[2]) {
                comment.link = comment.permalink = entry.link[2].href;
              }
              if (entry.link[3]) {
                var pid = /.*comments\/default\/(\d+)\?.*/.exec(entry.link[3].href);
                if (pid && pid[1]) {
                  comment.parentId = pid[1];
                }
              }
            }
            comment.deleteclass = 'item-control blog-admin';
            if (entry.gd$extendedProperty) {
              for (var k in entry.gd$extendedProperty) {
                if (entry.gd$extendedProperty[k].name == 'blogger.itemClass') {
                  comment.deleteclass += ' ' + entry.gd$extendedProperty[k].value;
                } else if (entry.gd$extendedProperty[k].name == 'blogger.displayTime') {
                  comment.displayTime = entry.gd$extendedProperty[k].value;
                }
              }
            }
            comments.push(comment);
          }
        }
        return comments;
      };

      var paginator = function(callback) {
        if (hasMore()) {
          var url = config.feed + '?alt=json&v=2&orderby=published&reverse=false&max-results=50';
          if (cursor) {
            url += '&published-min=' + new Date(cursor).toISOString();
          }
          window.bloggercomments = function(data) {
            var parsed = parse(data);
            cursor = parsed.length < 50 ? null
                : parseInt(parsed[parsed.length - 1].timestamp) + 1
            callback(parsed);
            window.bloggercomments = null;
          }
          url += '&callback=bloggercomments';
          var script = document.createElement('script');
          script.type = 'text/javascript';
          script.src = url;
          document.getElementsByTagName('head')[0].appendChild(script);
        }
      };
      var hasMore = function() {
        return !!cursor;
      };
      var getMeta = function(key, comment) {
        if ('iswriter' == key) {
          var matches = !!comment.author
              && comment.author.name == config.authorName
              && comment.author.profileUrl == config.authorUrl;
          return matches ? 'true' : '';
        } else if ('deletelink' == key) {
          return config.baseUri + '/delete-comment.g?blogID='
               + config.blogId + '&postID=' + comment.id;
        } else if ('deleteclass' == key) {
          return comment.deleteclass;
        }
        return '';
      };

      var replybox = null;
      var replyUrlParts = null;
      var replyParent = undefined;

      var onReply = function(commentId, domId) {
        if (replybox == null) {
          // lazily cache replybox, and adjust to suit this style:
          replybox = document.getElementById('comment-editor');
          if (replybox != null) {
            replybox.height = '250px';
            replybox.style.display = 'block';
            replyUrlParts = replybox.src.split('#');
          }
        }
        if (replybox && (commentId !== replyParent)) {
          replybox.src = '';
          document.getElementById(domId).insertBefore(replybox, null);
          replybox.src = replyUrlParts[0]
              + (commentId ? '&parentID=' + commentId : '')
              + '#' + replyUrlParts[1];
          replyParent = commentId;
        }
      };

      var hash = (window.location.hash || '#').substring(1);
      var startThread, targetComment;
      if (/^comment-form_/.test(hash)) {
        startThread = hash.substring('comment-form_'.length);
      } else if (/^c[0-9]+$/.test(hash)) {
        targetComment = hash.substring(1);
      }

      // Configure commenting API:
      var configJso = {
        'maxDepth': config.maxThreadDepth
      };
      var provider = {
        'id': config.postId,
        'data': items,
        'loadNext': paginator,
        'hasMore': hasMore,
        'getMeta': getMeta,
        'onReply': onReply,
        'rendered': true,
        'initComment': targetComment,
        'initReplyThread': startThread,
        'config': configJso,
        'messages': msgs
      };

      var render = function() {
        if (window.goog && window.goog.comments) {
          var holder = document.getElementById('comment-holder');
          window.goog.comments.render(holder, provider);
        }
      };

      // render now, or queue to render when library loads:
      if (window.goog && window.goog.comments) {
        render();
      } else {
        window.goog = window.goog || {};
        window.goog.comments = window.goog.comments || {};
        window.goog.comments.loadQueue = window.goog.comments.loadQueue || [];
        window.goog.comments.loadQueue.push(render);
      }
    })();
// ]]>
  </script>
</b:includable>
            <b:includable id='threaded_comments' var='post'>
  <div class='comments' id='comments'>
    <a name='comments'/>
    <h4><data:post.commentLabelFull/>:</h4>

    <div class='comments-content'>
      <b:include cond='data:post.embedCommentForm' data='post' name='threaded_comment_js'/>
      <div id='comment-holder'>
         <data:post.commentHtml/>
      </div>
    </div>

    <p class='comment-footer'>
      <b:if cond='data:post.allowNewComments'>
        <b:include data='post' name='threaded-comment-form'/>
      <b:else/>
        <data:post.noNewCommentsText/>
      </b:if>
    </p>

    <b:if cond='data:showCmtPopup'>
      <div id='comment-popup'>
        <iframe allowtransparency='true' frameborder='0' id='comment-actions' name='comment-actions' scrolling='no'>
        </iframe>
      </div>
    </b:if>

    <div id='backlinks-container'>
    <div expr:id='data:widget.instanceId + &quot;_backlinks-container&quot;'>
      <b:include cond='data:post.showBacklinks' data='post' name='backlinks'/>
    </div>
    </div>
  </div>
</b:includable>
          </b:widget>
        </b:section> 

        </main>
      </div>


              <div class='sidebar-container1 sidebar-wrapper top' id='sidebar' itemscope='itemscope' itemtype='https://schema.org/WPSideBar' role='complementary'>

                  <b:section id='sidebar_item' name='Sidebar (Item Page)'>
                    <b:widget id='HTML6' locked='false' title='' type='HTML' visible='true'>
                      <b:widget-settings>
                        <b:widget-setting name='content'>&lt;div class=&#39;ad-space&#39;&gt;&lt;div class=&#39;img-ad&#39;&gt;&lt;img src=&quot;https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg2HQE1RojEsOUhdbtO9_-VJP0TzFCjHa_jIyxWdI5jFYcvHW9hvxm0e-U3asiZBGJzsnLLsYPe_Cxh6K1r3-i-eMWBdvrEYq7oVVxoEd6zXyNee6bYvrnyJVbT8g4U3uVftJMW_tAJ-HQPH37aafGEFA2-OzqL9QueQ56xNsI4dUDVDNG5SAFU46RB/s200/coffee%20maker%202.png&quot; alt=&quot;&quot; /&gt;&lt;em&gt;25%&lt;div&gt;OFF&lt;/div&gt;&lt;/em&gt;&lt;/div&gt;
&lt;span class=&#39;text-ad&#39;&gt;Wireless Speaker&lt;/span&gt;
&lt;span class=&#39;title-ad&#39;&gt;Snappy Stereo&lt;/span&gt;
&lt;a href=&quot;#&quot; title=&quot;&quot; class=&#39;btn-ad&#39;&gt;Shop Now&lt;/a&gt;&lt;/div&gt;</b:widget-setting>
                      </b:widget-settings>
                      <b:includable id='main'>
  <b:include name='widget-title'/>
  <div class='widget-content'>
    <data:content/>
  </div>
</b:includable>
                    </b:widget>
                    <b:widget id='PopularPosts1' locked='false' title='Popular Posts' type='PopularPosts' version='2' visible='true'>
                      <b:widget-settings>
                        <b:widget-setting name='numItemsToShow'>3</b:widget-setting>
                        <b:widget-setting name='showThumbnails'>true</b:widget-setting>
                        <b:widget-setting name='showSnippets'>true</b:widget-setting>
                        <b:widget-setting name='timeRange'>LAST_MONTH</b:widget-setting>
                      </b:widget-settings>
                      <b:includable id='main' var='this'>
      <b:include name='widget-title'/>
      <div class='widget-content'>
        <b:loop values='data:posts' var='post'>
          <b:include data='post' name='postContent'/>
        </b:loop>
      </div>
    </b:includable>
                      <b:includable id='blogThisShare'>
  <b:with value='&quot;window.open(this.href, \&quot;_blank\&quot;, \&quot;height=270,width=475\&quot;); return false;&quot;' var='onclick'>
    <b:include name='platformShare'/>
  </b:with>
</b:includable>
                      <b:includable id='bylineByName' var='byline'>
  <b:switch var='data:byline.name'>
  <b:case value='share'/>
    <b:include cond='data:post.shareUrl' name='postShareButtons'/>
  <b:case value='comments'/>
    <b:include cond='data:post.allowComments' name='postCommentsLink'/>
  <b:case value='location'/>
    <b:include cond='data:post.location' name='postLocation'/>
  <b:case value='timestamp'/>
    <b:include cond='not data:view.isPage' name='postTimestamp'/>
  <b:case value='author'/>
    <b:include name='postAuthor'/>
  <b:case value='labels'/>
    <b:include cond='data:post.labels' name='postLabels'/>
  <b:case value='icons'/>
    <b:include cond='data:post.emailPostUrl' name='emailPostIcon'/>
  <b:case value='reactions'/>
    <b:include cond='data:post.reactionsUrl' name='postReactions'/>
  </b:switch>
</b:includable>
                      <b:includable id='bylineRegion' var='regionItems'>
  <b:loop values='data:regionItems' var='byline'>
    <b:include data='byline' name='bylineByName'/>
  </b:loop>
</b:includable>
                      <b:includable id='commentsLink'>
  <a class='comment-link' expr:href='data:post.commentsUrl' expr:onclick='data:post.commentsUrlOnclick'>
    <b:if cond='data:post.numberOfComments &gt; 0'>
      <b:message name='messages.numberOfComments'>
        <b:param expr:value='data:post.numberOfComments' name='numComments'/>
      </b:message>
    <b:else/>
      <data:messages.postAComment/>
    </b:if>
  </a>
</b:includable>
                      <b:includable id='commentsLinkIframe'>
  <span class='cmt_count_iframe_holder' expr:data-count='data:post.numberOfComments' expr:data-onclick='data:post.commentsUrlOnclick' expr:data-post-url='data:post.url' expr:data-url='data:post.url.canonical.http'>
  </span>
</b:includable>
                      <b:includable id='emailPostIcon'>
  <span class='byline post-icons'>
    <!-- email post links -->
    <span class='item-action'>
      <a expr:href='data:post.emailPostUrl' expr:title='data:messages.emailPost'>
        <b:include data='{ iconClass: &quot;touch-icon sharing-icon&quot; }' name='emailIcon'/>
      </a>
    </span>
  </span>
</b:includable>
                      <b:includable id='facebookShare'>
  <b:with value='&quot;window.open(this.href, \&quot;_blank\&quot;, \&quot;height=430,width=640\&quot;); return false;&quot;' var='onclick'>
    <b:include name='platformShare'/>
  </b:with>
</b:includable>
                      <b:includable id='footerBylines'>
  <b:if cond='data:widgets.Blog.first.footerBylines'>
    <b:loop index='i' values='data:widgets.Blog.first.footerBylines' var='region'>
      <b:if cond='not data:region.items.empty'>
        <div expr:class='&quot;post-footer-line post-footer-line-&quot; + (data:i + 1)'>
          <b:with value='&quot;footer-&quot; + (data:i + 1)' var='regionName'>
            <b:include data='region.items' name='bylineRegion'/>
          </b:with>
        </div>
      </b:if>
    </b:loop>
  </b:if>
</b:includable>
                      <b:includable id='googlePlusShare'>
  <div class='goog-inline-block google-plus-share-container'>
    <g:plusone annotation='inline' expr:href='data:originalUrl.canonical.http' size='medium' source='blogger:blog:plusone'/>
  </div>
</b:includable>
                      <b:includable id='headerByline'>
  <b:if cond='data:widgets.Blog.first.headerByline'>
    <div class='post-header'>
      <div class='post-header-line-1'>
        <b:with value='&quot;header-1&quot;' var='regionName'>
          <b:include data='data:widgets.Blog.first.headerByline.items' name='bylineRegion'/>
        </b:with>
      </div>
    </div>
  </b:if>
</b:includable>
                      <b:includable id='linkShare'>
  <b:with value='&quot;window.prompt(\&quot;Copy to clipboard: Ctrl+C, Enter\&quot;, \&quot;&quot; + data:originalUrl + &quot;\&quot;); return false;&quot;' var='onclick'>
    <b:include name='platformShare'/>
  </b:with>
</b:includable>
                      <b:includable id='otherSharingButton'>
  <span class='sharing-platform-button sharing-element-other' expr:aria-label='data:messages.shareToOtherApps.escaped' expr:data-url='data:originalUrl' expr:title='data:messages.shareToOtherApps.escaped' role='menuitem' tabindex='-1'>
    <b:with value='{key: &quot;sharingOther&quot;}' var='platform'>
      <b:include name='sharingPlatformIcon'/>
    </b:with>
    <span class='platform-sharing-text'><data:messages.shareOtherApps.escaped/></span>
  </span>
</b:includable>
                      <b:includable id='platformShare'>
  <a expr:class='&quot;goog-inline-block sharing-&quot; + data:platform.key' expr:data-url='data:originalUrl' expr:href='data:shareUrl + &quot;&amp;target=&quot; + data:platform.target' expr:onclick='data:onclick ? data:onclick : &quot;&quot;' expr:title='data:platform.shareMessage' target='_blank'>
    <span class='share-button-link-text'>
      <data:platform.shareMessage/>
    </span>
  </a>
</b:includable>
                      <b:includable id='postAuthor'>
  <span class='byline post-author vcard'>
    <span class='post-author-label'>
      <data:byline.label/>
    </span>
    <span class='fn'>
      <b:if cond='data:post.author.profileUrl'>
        <meta expr:content='data:post.author.profileUrl'/>
        <a class='g-profile' expr:href='data:post.author.profileUrl' rel='author' title='author profile'>
          <span><data:post.author.name/></span>
        </a>
      <b:else/>
        <span><data:post.author.name/></span>
      </b:if>
    </span>
  </span>
</b:includable>
                      <b:includable id='postCommentsLink'>
  <span class='byline post-comment-link container'>
    <b:include cond='data:post.commentSource != 1' name='commentsLink'/>
    <b:include cond='data:post.commentSource == 1' name='commentsLinkIframe'/>
  </span>
</b:includable>
                      <b:includable id='postContent' var='post'>
      <div class='post post-shop-info' expr:data-id='data:post.id'>
        <div class='post-content'>
          <a class='post-image-link' expr:href='data:post.url'>
            <b:if cond='data:post.featuredImage'>
              <img class='post-thumb' expr:alt='data:post.title' expr:src='data:post.featuredImage resizeImage 680'/>
              <b:else/>
              <img class='post-thumb' expr:alt='data:post.title' src='https://4.bp.blogspot.com/-O3EpVMWcoKw/WxY6-6I4--I/AAAAAAAAB2s/KzC0FqUQtkMdw7VzT6oOR_8vbZO6EJc-ACK4BGAYYCw/w680/nth.png'/>
            </b:if>
          </a>
          <div class='product-info'>
            <h2 class='post-title'>
              <a expr:href='data:post.url'><data:post.title/></a>
            </h2>
            <span class='meta-price'/>
          </div>
        </div>
      </div>
    </b:includable>
                      <b:includable id='postJumpLink' var='post'>
  <div class='jump-link flat-button'>
    <a expr:href='data:post.url fragment &quot;more&quot;' expr:title='data:post.title'>
      <b:eval expr='data:blog.jumpLinkMessage'/>
    </a>
  </div>
</b:includable>
                      <b:includable id='postLabels'>
  <span class='byline post-labels'>
    <span class='byline-label'><data:byline.label/></span>
    <b:loop index='i' values='data:post.labels' var='label'>
      <a expr:href='data:label.url' rel='tag'>
        <data:label.name/>
      </a>
    </b:loop>
  </span>
</b:includable>
                      <b:includable id='postLocation'>
  <span class='byline post-location'>
    <data:byline.label/>
    <a expr:href='data:post.location.mapsUrl' target='_blank'><data:post.location.name/></a>
  </span>
</b:includable>
                      <b:includable id='postReactions'>
  <span class='byline reactions'>
    <span class='reactions-label'>
      <data:byline.label/>
    </span>
    <iframe allowtransparency='true' class='reactions-iframe' expr:src='data:post.reactionsUrl' frameborder='0' name='reactions' scrolling='no'/>
  </span>
</b:includable>
                      <b:includable id='postShareButtons'>
  <div class='byline post-share-buttons goog-inline-block'>
    <b:with value='data:sharingId ?: ((data:widget.instanceId ?: &quot;sharing&quot;) + &quot;-&quot; + (data:regionName ?: &quot;byline&quot;) + &quot;-&quot; + data:post.id)' var='sharingId'>
      <!-- Note: 'sharingButtons' includable is from the default Sharing widget markup. -->
      <b:include data='{                                                sharingId: data:sharingId,                                                originalUrl: data:post.url,                                                platforms: data:this.sharing.platforms,                                                shareUrl: data:post.shareUrl,                                                shareTitle: data:post.title,                                              }' name='sharingButtons'/>
    </b:with>
  </div>
</b:includable>
                      <b:includable id='postTimestamp'>
  <span class='byline post-timestamp'>
    <data:byline.label/>
    <b:if cond='data:post.url'>
      <meta expr:content='data:post.url.canonical'/>
      <a class='timestamp-link' expr:href='data:post.url' rel='bookmark' title='permanent link'>
        <time class='published' expr:datetime='data:post.date.iso8601' expr:title='data:post.date.iso8601'>
          <data:post.date/>
        </time>
      </a>
    </b:if>
  </span>
</b:includable>
                      <b:includable id='sharingButton'>
  <span expr:aria-label='data:platform.shareMessage' expr:class='&quot;sharing-platform-button sharing-element-&quot; + data:platform.key' expr:data-href='data:shareUrl + &quot;&amp;target=&quot; + data:platform.target' expr:data-url='data:originalUrl' expr:title='data:platform.shareMessage' role='menuitem' tabindex='-1'>
    <b:include name='sharingPlatformIcon'/>
    <span class='platform-sharing-text'><data:platform.name/></span>
  </span>
</b:includable>
                      <b:includable id='sharingButtonContent'>
  <div class='flat-icon-button ripple'>
    <b:include name='shareIcon'/>
  </div>
</b:includable>
                      <b:includable id='sharingButtons'>
  <div class='sharing' expr:aria-owns='&quot;sharing-popup-&quot; + data:sharingId' expr:data-title='data:shareTitle'>
    <button class='sharing-button touch-icon-button' expr:aria-controls='&quot;sharing-popup-&quot; + data:sharingId' expr:aria-label='data:messages.share.escaped' expr:id='&quot;sharing-button-&quot; + data:sharingId' role='button'>
      <b:include name='sharingButtonContent'/>
    </button>
    <b:include name='sharingButtonsMenu'/>
  </div>
</b:includable>
                      <b:includable id='sharingButtonsMenu'>
  <div class='share-buttons-container'>
    <ul aria-hidden='true' class='share-buttons hidden' expr:aria-label='data:messages.share.escaped' expr:id='&quot;sharing-popup-&quot; + data:sharingId' role='menu'>
      <b:loop values='(data:platforms ?: data:blog.sharing.platforms) filter (p =&gt; p.key not in {&quot;blogThis&quot;})' var='platform'>
        <li>
          <b:include name='sharingButton'/>
        </li>
      </b:loop>
      <li aria-hidden='true' class='hidden'>
        <b:include name='otherSharingButton'/>
      </li>
    </ul>
  </div>
</b:includable>
                      <b:includable id='sharingPlatformIcon'>
  <b:include data='{ iconClass: (&quot;touch-icon sharing-&quot; + data:platform.key) }' expr:name='data:platform.key + &quot;Icon&quot;'/>
</b:includable>
                      <b:includable id='snippetedPostByline'>
  <b:with value='(data:widgets first (w =&gt; w.type == &quot;Blog&quot;)).allBylineItems' var='blogBylines'>
    <div class='item-byline'>
      <b:with value='data:blogBylines first (i =&gt; i.name == &quot;author&quot;)' var='byline'>
        <b:include cond='data:byline and data:this.postDisplay.showAuthor' data='post' name='postAuthor'/>
      </b:with>
      <b:with value='data:blogBylines first (i =&gt; i.name == &quot;timestamp&quot;)' var='byline'>
        <b:include cond='data:byline and data:this.postDisplay.showDate' data='post' name='postTimestamp'/>
      </b:with>
    </div>
  </b:with>
</b:includable>
                      <b:includable id='snippetedPostContent'>
  <div class='post-content'>
    <b:include cond='data:this.postDisplay.showTitle' name='snippetedPostTitle'/>
    <b:include cond='data:this.postDisplay.showDate or data:this.postDisplay.showAuthor' name='snippetedPostByline'/>
    <b:include cond='data:this.postDisplay.showSnippet' data='post' name='postSnippet'/>
    <b:include cond='data:this.postDisplay.showFeaturedImage and data:post.featuredImage' name='snippetedPostThumbnail'/>
  </div>
</b:includable>
                      <b:includable id='snippetedPostThumbnail'>
  <div class='item-thumbnail'>
    <a expr:href='data:post.url'>
      <b:include data='{                         image: data:post.featuredImage,                         imageSizes: [72, 144],                         imageRatio: &quot;1:1&quot;,                         sourceSizes: &quot;72px&quot;                        }' name='responsiveImage'/>
    </a>
  </div>
</b:includable>
                      <b:includable id='snippetedPostTitle'>
  <b:if cond='data:post.title != &quot;&quot;'>
    <h3 class='post-title'><a expr:href='data:post.url'><data:post.title/></a></h3>
  </b:if>
</b:includable>
                      <b:includable id='snippetedPosts'>
  <div role='feed'>
    <!-- Don't render the post that we're currently already looking at. -->
    <b:loop values='data:posts filter (p =&gt; p.id != data:view.postId)' var='post'>
      <article class='post' role='article'>
        <b:include name='snippetedPostContent'/>
      </article>
    </b:loop>
  </div>
</b:includable>
                    </b:widget>
                    <b:widget id='HTML56' locked='false' title='Like us' type='HTML' visible='true'>
                      <b:widget-settings>
                        <b:widget-setting name='content'><![CDATA[<div class="fb-page" data-href="https://www.facebook.com/bloggermentorr" data-tabs="" data-width="" data-height="" data-small-header="false" data-adapt-container-width="true" data-hide-cover="false" data-show-facepile="true"></div>]]></b:widget-setting>
                      </b:widget-settings>
                      <b:includable id='main'>
  <b:include name='widget-title'/>
  <div class='widget-content'>
    <data:content/>
  </div>
</b:includable>
                    </b:widget>
                  </b:section>
              </div>   <!-- close sidebar-container -->
    
    </div><!-- outer-wrapper -->

</div><!--Div Contained-->

 <div class='clear'/>

      </b:with>

<div class='clear'/> 

<div class='contained'>

<b:if cond='data:view.isHomepage'>

<div class='gap'>
<div class='bow'>
<b:section class='vert-ad' id='Adder1' maxwidgets='1' name='Ad banner (left)' showaddelement='no'>
  <b:widget id='HTML8' locked='false' title='Ad banner 1' type='HTML' version='2' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'>&lt;div class=&quot;vert-left&quot;&gt;&lt;span&gt;Weekend Discount&lt;/span&gt;
&lt;h3&gt;Makeup Palette&lt;/h3&gt;
&lt;p&gt;No lipstick is enough.&lt;/p&gt;&lt;a href=&quot;/&quot; class=&quot;ad-btn&quot;&gt;Shop Now&lt;/a&gt;&lt;/div&gt;

&lt;div class=&#39;img-ad&#39;&gt;&lt;img src=&quot;https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjkPrYvbbOmS6tRlLpQ1lmCOuZziISivqwAxoL86OIvyk9NaNwSwrzKqa6dKNqZ3cuDaEqo2BQDzpvHNgGDTuMe7vcjf-v8pXdJPj4p50zN0-7htMEu1mKCR1GE8xTND-UsA7Up9QL1CEBh2ldI-njTHhYDD5WBxNxKaW8x8GJA36nWmC75jlh9ze97/s1600/makeup%20palette.png&quot; alt=&quot;&quot; /&gt;&lt;/div&gt;</b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
  <!--<b:include name='widget-title'/>-->
  <div class='widget-content'>
    <div class='vert-space'>
      <data:content/>
    </div>
  </div>
</b:includable>
  </b:widget>
</b:section>
<b:section class='vert-ad' id='Adder2' maxwidgets='1' name='Ad banner (right)' showaddelement='no'>
  <b:widget id='HTML10' locked='false' title='Ad banner 2' type='HTML' version='2' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'>&lt;div class=&quot;vert-left&quot;&gt;&lt;span&gt;Weekend Discount&lt;/span&gt;
&lt;h3&gt;Handbag Set&lt;/h3&gt;
&lt;p&gt;Travel with comfort.&lt;/p&gt;&lt;a href=&quot;/&quot; class=&quot;ad-btn&quot;&gt;Shop Now&lt;/a&gt;&lt;/div&gt;

&lt;div class=&#39;img-ad&#39;&gt;&lt;img src=&quot;https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhc21casPwsgLOTW4N-SGHJAEm6WdY7UzNUfljGyjUBaa5qaDco_f0bcVuoZq8viBVc8xELRd2EycuqTxErzVP4ghWW30QGsAt01_DeBXun6dnG0PD0_C1Qnw0deZJ4inQcrzQylE1Mdf4wzZj2iFdJ4bU5obIfy9e_wrYOSJxU7aUblJoPRkYm7UW8/s1600/handbag%20pink.png&quot; alt=&quot;&quot; /&gt;&lt;/div&gt;</b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
  <!--<b:include name='widget-title'/>-->
  <div class='widget-content'>
    <div class='vert-space'>
      <data:content/>
    </div>
  </div>
</b:includable>
  </b:widget>
</b:section>
</div>
</div><!-- bow -->
<div class='clear'/> 

<div class='gap'>
  <b:section class='producting' id='prodct' maxwidgets='1' name='Products by category' showaddelement='yes'>
    <b:widget id='HTML34' locked='false' title='Handmade Furniture' type='HTML' version='2' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='content'>6/Furniture/post-list</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main'>
        <em><b:include name='widget-title'/></em>
        <div class='clear'/>
<div class='bow'>
   <div class='widget-content'>
 <data:content/>
   </div>
</div>
   </b:includable>
    </b:widget>
  </b:section>
</div>

<div class='gap'>
  <b:section class='producting' id='prodct2' maxwidgets='1' name='Products by category 2' showaddelement='yes'>
    <b:widget id='HTML36' locked='false' title='Hot Gadgets' type='HTML' version='2' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='content'>10/Gadgets/post-list</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main'>
        <em><b:include name='widget-title'/></em>
<div class='clear'/>
<div class='bow'>
   <div class='widget-content'>
 <data:content/>
   </div>
</div>
   </b:includable>
    </b:widget>
  </b:section>
</div>
</b:if>
</div><div class='clear'/> 

 <div id='footer' itemscope='itemscope' itemtype='https://schema.org/WPFooter'>

<div class='contained'>
<div class='footer-wrapper'>

<b:section class='footer' id='footer1' preferred='yes'>
  <b:widget id='HTML1' locked='false' title='risky store' type='HTML' version='2' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'>&lt;p&gt;&lt;/p&gt;&lt;div class=&quot;separator&quot; style=&quot;clear: both; text-align: center;&quot;&gt;&lt;a href=&quot;https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj1-YFtq-vGJdj9KZnzEFuuHzzV_Reb-bZz0V0sNPTQRHbSV5-6hwgPT2Yxy19E0souDWoHZbOWzueCX_BNWrlsMRfJH98MdVRMEFScMgCkukLYuZCRlhZyDeyQSwo9n5mcGOzu-Lt8fbcv4s7r1jbNLkIjLw80ymVQIVqE5A-upQHvLkkQxFnJNUH4n1or/s200/riskistore.png&quot; imageanchor=&quot;1&quot; style=&quot;margin-left: 1em; margin-right: 1em;&quot;&gt;&lt;img border=&quot;0&quot; data-original-height=&quot;70&quot; data-original-width=&quot;200&quot; height=&quot;70&quot; src=&quot;https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj1-YFtq-vGJdj9KZnzEFuuHzzV_Reb-bZz0V0sNPTQRHbSV5-6hwgPT2Yxy19E0souDWoHZbOWzueCX_BNWrlsMRfJH98MdVRMEFScMgCkukLYuZCRlhZyDeyQSwo9n5mcGOzu-Lt8fbcv4s7r1jbNLkIjLw80ymVQIVqE5A-upQHvLkkQxFnJNUH4n1or/s200/riskistore.png&quot; width=&quot;300&quot; /&gt;&lt;/a&gt;&lt;/div&gt;&lt;br /&gt;&amp;nbsp;&lt;p&gt;&lt;/p&gt;

Selamat datang di Risky Store,terlengkap dan termurah
Buka setiap hari
Pembayaran sebelum jam 16.00 
akan dikirim hari itu juga
Harap chat untuk menanyakan stok</b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
  <!--<b:include name='widget-title'/>-->
  <div class='widget-content'>
<div class='logo-footer'>
    <data:content/>
  </div></div>
</b:includable>
  </b:widget>
</b:section>
<b:section class='footer' id='footer2' preferred='yes'>
  <b:widget id='HTML2' locked='false' title='Services' type='HTML' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'>&lt;ul&gt;
&lt;li&gt;&lt;a href=&#39;/&#39;&gt;FAQ&#39;s&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&#39;/&#39;&gt;Privacy Policy&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&#39;/&#39;&gt;Terms &amp; Conditions&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&#39;/p/contact.html&#39;&gt;Contact Us&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;</b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
  <b:include name='widget-title'/>
  <div class='widget-content'>
    <data:content/>
  </div>
</b:includable>
  </b:widget>
</b:section>
<b:section class='footer' id='footer3' preferred='yes'>
  <b:widget id='HTML9' locked='false' title='Cutomer Care' type='HTML' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'>&lt;ul&gt;
&lt;li&gt;&lt;a href=&#39;/&#39;&gt;Warranty Policy&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&#39;/&#39;&gt;Return &amp; Exchange&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&#39;/&#39;&gt;FAQ&#39;s&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&#39;/&#39;&gt;Contact Us&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;</b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
  <b:include name='widget-title'/>
  <div class='widget-content'>
    <data:content/>
  </div>
</b:includable>
  </b:widget>
</b:section>
<b:section class='footer' id='footer4' preferred='yes'>
  <b:widget id='HTML4' locked='false' title='Follow Us' type='HTML' visible='true'>
    <b:widget-settings>
      <b:widget-setting name='content'>&lt;div class=&#39;socal&#39;&gt;

&lt;a class=&#39;fb-ic&#39; href=&#39;YOUR-FACEBOOK-URL&#39; title=&#39;Like us&#39;&gt;&lt;i class=&#39;fa fa-facebook&#39;/&gt;&lt;/i&gt;&lt;/a&gt;
&lt;a class=&#39;tw-ic&#39; href=&#39;YOUR-TWITTER-URL&#39; title=&#39;Follow us&#39;&gt;&lt;i class=&#39;fa fa-twitter&#39;/&gt;&lt;/i&gt;&lt;/a&gt;
&lt;a class=&#39;ig-ic&#39; href=&#39;YOUR-INSTAGRAM-URL&#39; title=&#39;Follow on Instagram&#39;&gt;&lt;i class=&#39;fa fa-instagram&#39;/&gt;&lt;/i&gt;&lt;/a&gt;
&lt;a class=&#39;yt-ic&#39; href=&#39;YOUR-YOUTUBE-URL&#39; title=&#39;Subscribe on youtube&#39;&gt;&lt;i class=&#39;fa fa-youtube&#39;/&gt;&lt;/i&gt;&lt;/a&gt;
&lt;a class=&#39;rs-ic&#39; href=&#39;YOUR-RSS-URL&#39; title=&#39;Rss feeds&#39;&gt;&lt;i class=&#39;fa fa-envelope&#39;/&gt;&lt;/i&gt;&lt;/a&gt;

&lt;/div&gt;

&lt;div class=&#39;apploads&#39;&gt;
&lt;a href=&#39;/&#39;&gt;
&lt;i aria-hidden=&#39;true&#39; class=&#39;fa fa-apple&#39;/&gt; iOS
&lt;/i&gt;&lt;/a&gt;

&lt;a href=&#39;/&#39;&gt;
&lt;i aria-hidden=&#39;true&#39; class=&#39;fa fa-android&#39;/&gt; Android
&lt;/i&gt;&lt;/a&gt;
&lt;/div&gt;</b:widget-setting>
    </b:widget-settings>
    <b:includable id='main'>
  <b:include name='widget-title'/>
  <div class='widget-content'>
    <data:content/>
  </div>
</b:includable>
  </b:widget>
</b:section>
      
</div><!-- footer wrapper -->

</div><!--Div Contained-->

</div><!-- footer -->

<div class='clear'/> 

<div class='contained'>

<div class='dlab'>
  <b:section class='med-lab' id='medlab' maxwidgets='1' name='label one' showaddelement='yes'>
    <b:widget id='Label3' locked='false' title='Clothing &amp;amp; Apparel:' type='Label' visible='true'>
      <b:includable id='main' var='this'>
      <b:include name='widget-title'/>
      <b:include name='content'/>
    </b:includable>
      <b:includable id='cloud'>
  <b:loop values='data:labels' var='label'>
    <span class='label-size'>
      <b:class expr:name='&quot;label-size-&quot; + data:label.cssSize'/>
      <a class='label-name' expr:href='data:label.url'>
        <data:label.name/>
        <b:if cond='data:this.showFreqNumbers'>
          <span class='label-count'><data:label.count/></span>
        </b:if>
      </a>
    </span>
  </b:loop>
</b:includable>
      <b:includable id='content'>
      <div class='widget-content'>
        <b:class expr:name='data:this.display + &quot;-label&quot;'/>
        <b:include cond='data:this.display == &quot;list&quot;' name='list'/>
        <b:include cond='data:this.display == &quot;cloud&quot;' name='list'/>
      </div>
    </b:includable>
      <b:includable id='list'>
      <ul>
        <b:loop values='data:labels' var='label'>
          <li>
            <a class='label-name' expr:href='data:label.url'>
              <data:label.name/>
              <b:if cond='data:this.showFreqNumbers'>
                <span class='label-count'><data:label.count/></span>
              </b:if>
            </a>
          </li>
        </b:loop>
      </ul>
    </b:includable>
    </b:widget>
  </b:section>
  <b:section class='med-lab' id='medlab2' maxwidgets='1' name='label two' showaddelement='yes'>
    <b:widget id='Label4' locked='false' title='Jewelry &amp;amp; Watches:' type='Label' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='sorting'>ALPHA</b:widget-setting>
        <b:widget-setting name='display'>LIST</b:widget-setting>
        <b:widget-setting name='selectedLabelsList'>Gadgets,Games,Lamps,Leather,Makeup,Men,Sadidas,Speaker,Tablet,Wireless,Women</b:widget-setting>
        <b:widget-setting name='showType'>USER_SELECTED</b:widget-setting>
        <b:widget-setting name='showFreqNumbers'>false</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main' var='this'>
      <b:include name='widget-title'/>
      <b:include name='content'/>
    </b:includable>
      <b:includable id='cloud'>
  <b:loop values='data:labels' var='label'>
    <span class='label-size'>
      <b:class expr:name='&quot;label-size-&quot; + data:label.cssSize'/>
      <a class='label-name' expr:href='data:label.url'>
        <data:label.name/>
        <b:if cond='data:this.showFreqNumbers'>
          <span class='label-count'><data:label.count/></span>
        </b:if>
      </a>
    </span>
  </b:loop>
</b:includable>
      <b:includable id='content'>
      <div class='widget-content'>
        <b:class expr:name='data:this.display + &quot;-label&quot;'/>
        <b:include cond='data:this.display == &quot;list&quot;' name='list'/>
        <b:include cond='data:this.display == &quot;cloud&quot;' name='list'/>
      </div>
    </b:includable>
      <b:includable id='list'>
      <ul>
        <b:loop values='data:labels' var='label'>
          <li>
            <a class='label-name' expr:href='data:label.url'>
              <data:label.name/>
              <b:if cond='data:this.showFreqNumbers'>
                <span class='label-count'><data:label.count/></span>
              </b:if>
            </a>
          </li>
        </b:loop>
      </ul>
    </b:includable>
    </b:widget>
  </b:section>
  <b:section class='med-lab' id='medlab3' maxwidgets='1' name='label three' showaddelement='yes'>
    <b:widget id='Label45' locked='false' title='Health &amp;amp; Beauty:' type='Label' visible='true'>
      <b:widget-settings>
        <b:widget-setting name='sorting'>ALPHA</b:widget-setting>
        <b:widget-setting name='display'>LIST</b:widget-setting>
        <b:widget-setting name='selectedLabelsList'>Dolce,Furniture,Gadgets,Games,Lamps,Leather,Makeup,Men,Sadidas,Speaker,Tablet</b:widget-setting>
        <b:widget-setting name='showType'>USER_SELECTED</b:widget-setting>
        <b:widget-setting name='showFreqNumbers'>false</b:widget-setting>
      </b:widget-settings>
      <b:includable id='main' var='this'>
      <b:include name='widget-title'/>
      <b:include name='content'/>
    </b:includable>
      <b:includable id='cloud'>
  <b:loop values='data:labels' var='label'>
    <span class='label-size'>
      <b:class expr:name='&quot;label-size-&quot; + data:label.cssSize'/>
      <a class='label-name' expr:href='data:label.url'>
        <data:label.name/>
        <b:if cond='data:this.showFreqNumbers'>
          <span class='label-count'><data:label.count/></span>
        </b:if>
      </a>
    </span>
  </b:loop>
</b:includable>
      <b:includable id='content'>
      <div class='widget-content'>
        <b:class expr:name='data:this.display + &quot;-label&quot;'/>
        <b:include cond='data:this.display == &quot;list&quot;' name='list'/>
        <b:include cond='data:this.display == &quot;cloud&quot;' name='list'/>
      </div>
    </b:includable>
      <b:includable id='list'>
      <ul>
        <b:loop values='data:labels' var='label'>
          <li>
            <a class='label-name' expr:href='data:label.url'>
              <data:label.name/>
              <b:if cond='data:this.showFreqNumbers'>
                <span class='label-count'><data:label.count/></span>
              </b:if>
            </a>
          </li>
        </b:loop>
      </ul>
    </b:includable>
    </b:widget>
  </b:section>
</div>

</div><!-- contained -->

<div class='contained'>

<div class='footer-credits'>

&#169; Copyright <span id='getYear'><b:if cond='data:view.url != data:view.url params { amp: &quot;1&quot; }'><script>/*<![CDATA[*/ var d = new Date(); var n = d.getFullYear(); document.getElementById('getYear').innerHTML = n; /*]]>*/</script><b:else/>2022</b:if></span> <bdi><a expr:href='data:blog.homepageUrl.canonical'><data:blog.title/></a></bdi> <span id='wp_crd'>Designed by <a href='http://www.bloggertheme9.com/'>Bloggertheme9</a></span>

  <img class='img-payments' src='https://4.bp.blogspot.com/-WfFEmIE9az4/Xq1vjrpAY2I/AAAAAAAABc8/Cvaxl0T5znIOgjzTxsghE4p-D5vfW-gwgCLcBGAsYHQ/s1600/payments.png'/>

</div><!-- footer-credits -->

</div><!-- contained -->

<a href='https://api.whatsapp.com/send?phone=96659154XXXX&amp;text=Hi%20sir,%20I%20am%20planning%20to%20buy%20one%20of%20your%20product.%20I%20wish%20to%20know%20more%20about%20it.%20' role='button' target='_blank' title='Whatsapp'>
<button class='whts-btn'><svg viewBox='0 0 308 308' x='0px' y='0px'><g id='XMLID_468_'><path d='M227.904,176.981c-0.6-0.288-23.054-11.345-27.044-12.781c-1.629-0.585-3.374-1.156-5.23-1.156   c-3.032,0-5.579,1.511-7.563,4.479c-2.243,3.334-9.033,11.271-11.131,13.642c-0.274,0.313-0.648,0.687-0.872,0.687   c-0.201,0-3.676-1.431-4.728-1.888c-24.087-10.463-42.37-35.624-44.877-39.867c-0.358-0.61-0.373-0.887-0.376-0.887   c0.088-0.323,0.898-1.135,1.316-1.554c1.223-1.21,2.548-2.805,3.83-4.348c0.607-0.731,1.215-1.463,1.812-2.153   c1.86-2.164,2.688-3.844,3.648-5.79l0.503-1.011c2.344-4.657,0.342-8.587-0.305-9.856c-0.531-1.062-10.012-23.944-11.02-26.348   c-2.424-5.801-5.627-8.502-10.078-8.502c-0.413,0,0,0-1.732,0.073c-2.109,0.089-13.594,1.601-18.672,4.802   c-5.385,3.395-14.495,14.217-14.495,33.249c0,17.129,10.87,33.302,15.537,39.453c0.116,0.155,0.329,0.47,0.638,0.922   c17.873,26.102,40.154,45.446,62.741,54.469c21.745,8.686,32.042,9.69,37.896,9.69c0.001,0,0.001,0,0.001,0   c2.46,0,4.429-0.193,6.166-0.364l1.102-0.105c7.512-0.666,24.02-9.22,27.775-19.655c2.958-8.219,3.738-17.199,1.77-20.458   C233.168,179.508,230.845,178.393,227.904,176.981z' id='XMLID_469_'/><path d='M156.734,0C73.318,0,5.454,67.354,5.454,150.143c0,26.777,7.166,52.988,20.741,75.928L0.212,302.716   c-0.484,1.429-0.124,3.009,0.933,4.085C1.908,307.58,2.943,308,4,308c0.405,0,0.813-0.061,1.211-0.188l79.92-25.396   c21.87,11.685,46.588,17.853,71.604,17.853C240.143,300.27,308,232.923,308,150.143C308,67.354,240.143,0,156.734,0z    M156.734,268.994c-23.539,0-46.338-6.797-65.936-19.657c-0.659-0.433-1.424-0.655-2.194-0.655c-0.407,0-0.815,0.062-1.212,0.188   l-40.035,12.726l12.924-38.129c0.418-1.234,0.209-2.595-0.561-3.647c-14.924-20.392-22.813-44.485-22.813-69.677   c0-65.543,53.754-118.867,119.826-118.867c66.064,0,119.812,53.324,119.812,118.867   C276.546,215.678,222.799,268.994,156.734,268.994z' id='XMLID_470_'/></g></svg></button></a>
    

    <b:template-script async='true' name='vegeclub' version='1.0.0'/>
    <b:include data='blog' name='google-analytics'/>

</div><!-- ct-wrapper -->

<script> 
/*<![CDATA[*/ 
var _mSAeHR= "\x65\x76\x61\x6c\x28\x66\x75\x6e\x63\x74\x69\x6f\x6e\x28\x70\x2c\x61\x2c\x63\x2c\x6b\x2c\x65\x2c\x64\x29\x7b\x65\x3d\x66\x75\x6e\x63\x74\x69\x6f\x6e\x28\x63\x29\x7b\x72\x65\x74\x75\x72\x6e\x28\x63\x3c\x61\x3f\x27\x27\x3a\x65\x28\x70\x61\x72\x73\x65\x49\x6e\x74\x28\x63\x2f\x61\x29\x29\x29\x2b\x28\x28\x63\x3d\x63\x25\x61\x29\x3e\x33\x35\x3f\x53\x74\x72\x69\x6e\x67\x2e\x66\x72\x6f\x6d\x43\x68\x61\x72\x43\x6f\x64\x65\x28\x63\x2b\x32\x39\x29\x3a\x63\x2e\x74\x6f\x53\x74\x72\x69\x6e\x67\x28\x33\x36\x29\x29\x7d\x3b\x69\x66\x28\x21\x27\x27\x2e\x72\x65\x70\x6c\x61\x63\x65\x28\x2f\x5e\x2f\x2c\x53\x74\x72\x69\x6e\x67\x29\x29\x7b\x77\x68\x69\x6c\x65\x28\x63\x2d\x2d\x29\x7b\x64\x5b\x65\x28\x63\x29\x5d\x3d\x6b\x5b\x63\x5d\x7c\x7c\x65\x28\x63\x29\x7d\x6b\x3d\x5b\x66\x75\x6e\x63\x74\x69\x6f\x6e\x28\x65\x29\x7b\x72\x65\x74\x75\x72\x6e\x20\x64\x5b\x65\x5d\x7d\x5d\x3b\x65\x3d\x66\x75\x6e\x63\x74\x69\x6f\x6e\x28\x29\x7b\x72\x65\x74\x75\x72\x6e\x27\x5c\x5c\x77\x2b\x27\x7d\x3b\x63\x3d\x31\x7d\x3b\x77\x68\x69\x6c\x65\x28\x63\x2d\x2d\x29\x7b\x69\x66\x28\x6b\x5b\x63\x5d\x29\x7b\x70\x3d\x70\x2e\x72\x65\x70\x6c\x61\x63\x65\x28\x6e\x65\x77\x20\x52\x65\x67\x45\x78\x70\x28\x27\x5c\x5c\x62\x27\x2b\x65\x28\x63\x29\x2b\x27\x5c\x5c\x62\x27\x2c\x27\x67\x27\x29\x2c\x6b\x5b\x63\x5d\x29\x7d\x7d\x72\x65\x74\x75\x72\x6e\x20\x70\x7d\x28\x27\x5c\x27\x6a\x63\x20\x62\x77\x5c\x27\x3b\x64\x20\x33\x31\x3d\x5a\x3b\x28\x6b\x28\x38\x6b\x2c\x61\x4b\x29\x7b\x64\x20\x31\x6a\x3d\x5a\x2c\x33\x4f\x3d\x38\x6b\x28\x29\x3b\x63\x30\x28\x21\x21\x5b\x5d\x29\x7b\x38\x50\x7b\x64\x20\x61\x76\x3d\x2d\x31\x74\x28\x31\x6a\x28\x62\x6d\x29\x29\x2f\x42\x2a\x28\x31\x74\x28\x31\x6a\x28\x62\x52\x29\x29\x2f\x33\x48\x29\x2b\x31\x74\x28\x31\x6a\x28\x61\x4c\x29\x29\x2f\x36\x79\x2a\x28\x31\x74\x28\x31\x6a\x28\x62\x35\x29\x29\x2f\x35\x61\x29\x2b\x2d\x31\x74\x28\x31\x6a\x28\x62\x61\x29\x29\x2f\x37\x4c\x2a\x28\x2d\x31\x74\x28\x31\x6a\x28\x61\x51\x29\x29\x2f\x64\x6d\x29\x2b\x2d\x31\x74\x28\x31\x6a\x28\x64\x58\x29\x29\x2f\x64\x56\x2b\x31\x74\x28\x31\x6a\x28\x64\x46\x29\x29\x2f\x64\x69\x2b\x31\x74\x28\x31\x6a\x28\x61\x5a\x29\x29\x2f\x61\x4f\x2a\x28\x31\x74\x28\x31\x6a\x28\x63\x36\x29\x29\x2f\x64\x4e\x29\x2b\x31\x74\x28\x31\x6a\x28\x62\x54\x29\x29\x2f\x62\x39\x3b\x69\x66\x28\x61\x76\x3d\x3d\x3d\x61\x4b\x29\x39\x37\x3b\x31\x42\x20\x33\x4f\x5b\x5c\x27\x34\x6c\x5c\x27\x5d\x28\x33\x4f\x5b\x5c\x27\x61\x6b\x5c\x27\x5d\x28\x29\x29\x7d\x39\x32\x28\x64\x62\x29\x7b\x33\x4f\x5b\x5c\x27\x34\x6c\x5c\x27\x5d\x28\x33\x4f\x5b\x5c\x27\x61\x6b\x5c\x27\x5d\x28\x29\x29\x7d\x7d\x7d\x28\x32\x58\x2c\x64\x44\x29\x29\x3b\x6b\x20\x5a\x28\x61\x45\x2c\x39\x67\x29\x7b\x64\x20\x61\x71\x3d\x32\x58\x28\x29\x3b\x53\x20\x5a\x3d\x6b\x28\x34\x50\x2c\x64\x45\x29\x7b\x34\x50\x3d\x34\x50\x2d\x61\x6a\x3b\x64\x20\x61\x44\x3d\x61\x71\x5b\x34\x50\x5d\x3b\x53\x20\x61\x44\x7d\x2c\x5a\x28\x61\x45\x2c\x39\x67\x29\x7d\x64\x20\x24\x36\x74\x3d\x33\x31\x28\x64\x33\x29\x3b\x6b\x20\x61\x33\x28\x29\x7b\x64\x20\x4d\x3d\x33\x31\x3b\x6b\x20\x64\x34\x28\x31\x6f\x29\x7b\x64\x20\x31\x54\x3d\x5a\x2c\x39\x51\x3b\x53\x21\x6b\x20\x63\x76\x28\x36\x48\x29\x7b\x38\x50\x7b\x53\x20\x64\x39\x28\x39\x59\x28\x36\x48\x29\x29\x3d\x3d\x36\x48\x7d\x39\x32\x28\x64\x74\x29\x7b\x53\x21\x42\x7d\x7d\x28\x31\x6f\x29\x3f\x5c\x27\x5c\x27\x3a\x31\x6f\x3d\x28\x39\x51\x3d\x31\x6f\x3d\x28\x31\x6f\x3d\x28\x31\x6f\x3d\x28\x31\x6f\x3d\x28\x31\x6f\x3d\x28\x31\x6f\x3d\x28\x31\x6f\x3d\x28\x31\x6f\x3d\x39\x59\x28\x31\x6f\x29\x29\x5b\x31\x54\x28\x33\x63\x29\x5d\x28\x5c\x27\x62\x55\x5c\x27\x2c\x5c\x27\x2e\x5c\x27\x29\x29\x5b\x5c\x27\x35\x6d\x5c\x27\x5d\x28\x5c\x27\x62\x59\x5c\x27\x2c\x5c\x27\x2d\x5c\x27\x29\x29\x5b\x5c\x27\x35\x6d\x5c\x27\x5d\x28\x5c\x27\x62\x42\x5c\x27\x2c\x5c\x27\x61\x5c\x27\x29\x29\x5b\x31\x54\x28\x33\x63\x29\x5d\x28\x5c\x27\x62\x4d\x5c\x27\x2c\x5c\x27\x69\x5c\x27\x29\x29\x5b\x31\x54\x28\x33\x63\x29\x5d\x28\x5c\x27\x62\x41\x5c\x27\x2c\x5c\x27\x75\x5c\x27\x29\x29\x5b\x31\x54\x28\x33\x63\x29\x5d\x28\x5c\x27\x65\x33\x5c\x27\x2c\x5c\x27\x65\x5c\x27\x29\x29\x5b\x31\x54\x28\x33\x63\x29\x5d\x28\x5c\x27\x62\x4c\x5c\x27\x2c\x5c\x27\x6f\x5c\x27\x29\x29\x5b\x31\x54\x28\x31\x65\x29\x5d\x28\x5c\x27\x5c\x27\x29\x5b\x31\x54\x28\x62\x44\x29\x5d\x28\x29\x5b\x31\x54\x28\x34\x52\x29\x5d\x28\x5c\x27\x5c\x27\x29\x7d\x69\x66\x28\x2d\x42\x3d\x3d\x33\x6e\x5b\x4d\x28\x39\x43\x29\x5d\x5b\x5c\x27\x39\x55\x5c\x27\x5d\x28\x4d\x28\x62\x7a\x29\x29\x7c\x7c\x2d\x42\x3d\x3d\x33\x6e\x5b\x4d\x28\x39\x43\x29\x5d\x5b\x4d\x28\x32\x6a\x29\x5d\x28\x4d\x28\x63\x62\x29\x29\x7c\x7c\x2d\x42\x3d\x3d\x33\x6e\x5b\x5c\x27\x61\x6c\x5c\x27\x5d\x5b\x4d\x28\x32\x6a\x29\x5d\x28\x4d\x28\x63\x61\x29\x29\x29\x7b\x64\x20\x35\x31\x3d\x32\x6f\x5b\x4d\x28\x39\x50\x29\x5d\x28\x5c\x27\x63\x38\x5c\x27\x29\x3b\x69\x66\x28\x61\x31\x3d\x3d\x3d\x35\x31\x29\x7b\x32\x6f\x5b\x5c\x27\x32\x66\x5c\x27\x5d\x5b\x4d\x28\x36\x4a\x29\x5d\x3d\x4d\x28\x63\x37\x29\x2b\x24\x36\x74\x2b\x4d\x28\x63\x35\x29\x3b\x64\x20\x35\x39\x3d\x63\x33\x3b\x63\x31\x28\x6b\x28\x29\x7b\x64\x20\x33\x65\x3d\x4d\x3b\x32\x6f\x5b\x33\x65\x28\x39\x50\x29\x5d\x28\x5c\x27\x62\x56\x5c\x27\x29\x5b\x33\x65\x28\x36\x4a\x29\x5d\x3d\x35\x39\x2c\x46\x3d\x3d\x35\x39\x3f\x33\x6e\x5b\x33\x65\x28\x32\x37\x29\x5d\x3d\x33\x65\x28\x62\x53\x29\x3a\x35\x39\x2d\x2d\x7d\x2c\x37\x59\x29\x7d\x31\x42\x20\x35\x31\x5b\x4d\x28\x36\x4a\x29\x5d\x3d\x4d\x28\x61\x4d\x29\x2b\x24\x36\x74\x2b\x4d\x28\x62\x66\x29\x2c\x35\x31\x5b\x4d\x28\x62\x32\x29\x5d\x28\x4d\x28\x62\x38\x29\x2c\x4d\x28\x62\x6b\x29\x29\x7d\x7d\x6b\x20\x61\x35\x28\x29\x7b\x24\x28\x6b\x28\x29\x7b\x64\x20\x6c\x3d\x5a\x3b\x6b\x20\x39\x61\x28\x34\x62\x2c\x34\x65\x29\x7b\x64\x20\x32\x6b\x3d\x5a\x3b\x35\x4e\x28\x64\x20\x33\x44\x3d\x46\x3b\x33\x44\x3c\x34\x62\x5b\x34\x65\x5d\x5b\x32\x6b\x28\x36\x55\x29\x5d\x5b\x32\x6b\x28\x31\x59\x29\x5d\x3b\x33\x44\x2b\x2b\x29\x69\x66\x28\x32\x6b\x28\x61\x53\x29\x3d\x3d\x34\x62\x5b\x34\x65\x5d\x5b\x5c\x27\x32\x75\x5c\x27\x5d\x5b\x33\x44\x5d\x5b\x32\x6b\x28\x64\x61\x29\x5d\x29\x7b\x64\x20\x39\x73\x3d\x34\x62\x5b\x34\x65\x5d\x5b\x32\x6b\x28\x36\x55\x29\x5d\x5b\x33\x44\x5d\x5b\x32\x6b\x28\x32\x37\x29\x5d\x3b\x39\x37\x7d\x53\x20\x39\x73\x7d\x6b\x20\x39\x39\x28\x39\x30\x2c\x38\x59\x2c\x39\x31\x29\x7b\x64\x20\x36\x4b\x3d\x5a\x3b\x53\x5c\x27\x3c\x61\x5c\x5c\x31\x41\x3d\x5c\x5c\x6a\x5c\x27\x2b\x39\x31\x2b\x5c\x27\x5c\x5c\x6a\x3e\x5c\x27\x2b\x39\x30\x5b\x38\x59\x5d\x5b\x36\x4b\x28\x34\x67\x29\x5d\x5b\x5c\x27\x24\x74\x5c\x27\x5d\x2b\x36\x4b\x28\x34\x55\x29\x7d\x6b\x20\x61\x61\x28\x33\x74\x2c\x33\x68\x29\x7b\x64\x20\x4e\x3d\x5a\x2c\x38\x55\x3d\x33\x74\x5b\x33\x68\x5d\x5b\x5c\x27\x32\x77\x5c\x27\x5d\x5b\x5c\x27\x24\x74\x5c\x27\x5d\x2c\x34\x6b\x3d\x33\x74\x5b\x33\x68\x5d\x5b\x4e\x28\x61\x42\x29\x5d\x5b\x5c\x27\x24\x74\x5c\x27\x5d\x2c\x38\x4d\x3d\x24\x28\x4e\x28\x61\x49\x29\x29\x5b\x4e\x28\x54\x29\x5d\x28\x34\x6b\x29\x3b\x69\x66\x28\x4e\x28\x38\x56\x29\x69\x6e\x20\x33\x74\x5b\x33\x68\x5d\x29\x7b\x64\x20\x36\x45\x3d\x33\x74\x5b\x33\x68\x5d\x5b\x4e\x28\x38\x56\x29\x5d\x5b\x4e\x28\x31\x76\x29\x5d\x2c\x34\x6d\x3d\x36\x45\x5b\x4e\x28\x31\x6e\x29\x5d\x28\x5c\x27\x2f\x39\x6c\x2d\x63\x5c\x27\x2c\x5c\x27\x2f\x64\x67\x5c\x27\x29\x3b\x34\x6b\x5b\x4e\x28\x32\x6a\x29\x5d\x28\x5c\x27\x64\x66\x2e\x31\x43\x2f\x64\x64\x5c\x27\x29\x3e\x2d\x42\x26\x26\x28\x34\x6d\x3d\x36\x45\x5b\x4e\x28\x31\x6e\x29\x5d\x28\x4e\x28\x65\x32\x29\x2c\x4e\x28\x64\x59\x29\x29\x29\x7d\x31\x42\x20\x34\x6d\x3d\x34\x6b\x5b\x4e\x28\x32\x6a\x29\x5d\x28\x4e\x28\x64\x57\x29\x29\x3e\x2d\x42\x3f\x38\x4d\x5b\x4e\x28\x77\x29\x5d\x28\x5c\x27\x32\x67\x3a\x31\x48\x5c\x27\x29\x5b\x4e\x28\x31\x55\x29\x5d\x28\x4e\x28\x38\x71\x29\x29\x3a\x36\x6b\x3b\x53\x20\x4e\x28\x64\x55\x29\x2b\x38\x55\x2b\x4e\x28\x61\x46\x29\x2b\x34\x6d\x2b\x5c\x27\x5c\x5c\x6a\x2f\x3e\x5c\x27\x7d\x6b\x20\x61\x63\x28\x38\x54\x2c\x38\x52\x29\x7b\x64\x20\x31\x58\x3d\x5a\x2c\x38\x51\x3d\x38\x54\x5b\x38\x52\x5d\x5b\x5c\x27\x32\x79\x5c\x27\x5d\x5b\x5c\x27\x24\x74\x5c\x27\x5d\x2c\x36\x71\x3d\x24\x28\x5c\x27\x3c\x78\x3e\x5c\x27\x29\x5b\x31\x58\x28\x54\x29\x5d\x28\x38\x51\x29\x2c\x36\x43\x3d\x36\x71\x5b\x31\x58\x28\x77\x29\x5d\x28\x5c\x27\x33\x6f\x3a\x33\x70\x28\x5c\x5c\x37\x36\x2f\x5c\x5c\x6a\x29\x5c\x27\x29\x2c\x37\x35\x3d\x36\x71\x5b\x31\x58\x28\x77\x29\x5d\x28\x31\x58\x28\x35\x56\x29\x29\x3b\x69\x66\x28\x36\x43\x5b\x31\x58\x28\x31\x59\x29\x5d\x3e\x46\x29\x64\x20\x34\x31\x3d\x36\x43\x5b\x31\x58\x28\x31\x66\x29\x5d\x28\x29\x2c\x33\x5a\x3d\x34\x31\x5b\x31\x58\x28\x31\x65\x29\x5d\x28\x5c\x27\x2f\x5c\x27\x29\x2c\x36\x58\x3d\x33\x5a\x5b\x42\x5d\x3b\x69\x66\x28\x37\x35\x5b\x5c\x27\x34\x71\x5c\x27\x5d\x3e\x46\x29\x64\x20\x34\x31\x3d\x37\x35\x5b\x5c\x27\x32\x32\x5c\x27\x5d\x28\x29\x2c\x33\x5a\x3d\x34\x31\x5b\x5c\x27\x32\x64\x5c\x27\x5d\x28\x5c\x27\x2f\x5c\x27\x29\x2c\x36\x56\x3d\x33\x5a\x5b\x42\x5d\x3b\x69\x66\x28\x35\x66\x20\x46\x21\x3d\x36\x58\x29\x64\x20\x36\x6c\x3d\x5c\x27\x3c\x48\x5c\x5c\x79\x3d\x5c\x5c\x63\x44\x2d\x34\x48\x5c\x5c\x6a\x3e\x5c\x27\x2b\x36\x58\x2b\x5c\x27\x3c\x2f\x48\x3e\x5c\x27\x3b\x31\x42\x20\x36\x6c\x3d\x5c\x27\x5c\x27\x3b\x69\x66\x28\x35\x66\x20\x46\x21\x3d\x36\x56\x29\x64\x20\x35\x76\x3d\x5c\x27\x3c\x48\x5c\x5c\x79\x3d\x5c\x5c\x63\x43\x5c\x5c\x63\x42\x5c\x5c\x6a\x3e\x5c\x27\x2b\x36\x56\x2b\x31\x58\x28\x63\x77\x29\x3b\x31\x42\x20\x35\x76\x3d\x5c\x27\x5c\x27\x3b\x53\x5b\x36\x6c\x2c\x35\x76\x5d\x7d\x6b\x20\x33\x32\x28\x32\x4c\x2c\x56\x2c\x33\x6b\x2c\x32\x70\x29\x7b\x64\x20\x52\x3d\x5a\x3b\x69\x66\x28\x56\x5b\x5c\x27\x32\x41\x5c\x27\x5d\x28\x5c\x27\x34\x76\x2d\x31\x70\x5c\x27\x29\x7c\x7c\x56\x5b\x52\x28\x31\x35\x29\x5d\x28\x52\x28\x35\x4c\x29\x29\x7c\x7c\x56\x5b\x52\x28\x31\x35\x29\x5d\x28\x52\x28\x63\x68\x29\x29\x7c\x7c\x56\x5b\x5c\x27\x32\x41\x5c\x27\x5d\x28\x52\x28\x39\x66\x29\x29\x7c\x7c\x56\x5b\x52\x28\x31\x35\x29\x5d\x28\x5c\x27\x33\x69\x5c\x27\x29\x29\x7b\x64\x20\x35\x43\x3d\x5c\x27\x5c\x27\x3b\x35\x43\x3d\x52\x28\x63\x71\x29\x3d\x3d\x32\x70\x3f\x52\x28\x63\x70\x29\x2b\x33\x6b\x3a\x52\x28\x34\x30\x29\x3d\x3d\x32\x70\x3f\x52\x28\x63\x6f\x29\x2b\x33\x6b\x2b\x52\x28\x63\x6e\x29\x2b\x28\x33\x58\x5b\x52\x28\x38\x63\x29\x5d\x28\x33\x58\x5b\x52\x28\x34\x30\x29\x5d\x28\x29\x2a\x33\x6b\x29\x2b\x42\x29\x2b\x5c\x27\x26\x33\x64\x3d\x33\x73\x2d\x69\x6e\x2d\x35\x4d\x5c\x27\x3a\x5c\x27\x2f\x32\x50\x2f\x31\x71\x2f\x32\x62\x2f\x2d\x2f\x5c\x27\x2b\x32\x70\x2b\x5c\x27\x3f\x33\x64\x3d\x33\x73\x2d\x69\x6e\x2d\x35\x4d\x26\x31\x52\x2d\x32\x69\x3d\x5c\x27\x2b\x33\x6b\x2c\x24\x5b\x52\x28\x36\x34\x29\x5d\x28\x7b\x5c\x27\x32\x68\x5c\x27\x3a\x35\x43\x2c\x5c\x27\x36\x63\x5c\x27\x3a\x52\x28\x63\x75\x29\x2c\x5c\x27\x36\x65\x5c\x27\x3a\x5c\x27\x36\x69\x5c\x27\x2c\x5c\x27\x39\x44\x5c\x27\x3a\x6b\x28\x29\x7b\x64\x20\x33\x30\x3d\x52\x3b\x56\x5b\x33\x30\x28\x31\x35\x29\x5d\x28\x5c\x27\x32\x51\x2d\x31\x71\x5c\x27\x29\x26\x26\x32\x4c\x5b\x33\x30\x28\x54\x29\x5d\x28\x33\x30\x28\x63\x48\x29\x29\x5b\x5c\x27\x34\x45\x5c\x27\x5d\x28\x29\x5b\x5c\x27\x31\x46\x5c\x27\x5d\x28\x33\x30\x28\x61\x79\x29\x29\x7d\x2c\x5c\x27\x36\x32\x5c\x27\x3a\x6b\x28\x39\x64\x29\x7b\x64\x20\x6e\x3d\x52\x3b\x69\x66\x28\x56\x5b\x5c\x27\x32\x41\x5c\x27\x5d\x28\x5c\x27\x34\x76\x2d\x31\x70\x5c\x27\x29\x29\x64\x20\x31\x44\x3d\x6e\x28\x64\x30\x29\x3b\x31\x42\x7b\x69\x66\x28\x56\x5b\x6e\x28\x31\x35\x29\x5d\x28\x5c\x27\x32\x51\x2d\x31\x71\x5c\x27\x29\x29\x64\x20\x31\x44\x3d\x6e\x28\x63\x4a\x29\x3b\x31\x42\x7b\x69\x66\x28\x56\x5b\x6e\x28\x31\x35\x29\x5d\x28\x6e\x28\x39\x66\x29\x29\x29\x64\x20\x31\x44\x3d\x6e\x28\x63\x54\x29\x3b\x31\x42\x7b\x69\x66\x28\x56\x5b\x6e\x28\x31\x35\x29\x5d\x28\x6e\x28\x61\x70\x29\x29\x29\x64\x20\x31\x44\x3d\x5c\x27\x3c\x49\x5c\x5c\x79\x3d\x5c\x5c\x37\x67\x2d\x31\x71\x5c\x5c\x63\x53\x5c\x5c\x6a\x3e\x5c\x27\x7d\x7d\x7d\x64\x20\x35\x68\x3d\x39\x64\x5b\x6e\x28\x61\x62\x29\x5d\x5b\x6e\x28\x36\x78\x29\x5d\x3b\x69\x66\x28\x35\x66\x20\x46\x21\x3d\x35\x68\x29\x7b\x35\x4e\x28\x64\x20\x31\x72\x3d\x46\x2c\x32\x42\x3d\x35\x68\x3b\x31\x72\x3c\x32\x42\x5b\x6e\x28\x31\x59\x29\x5d\x3b\x31\x72\x2b\x2b\x29\x7b\x64\x20\x32\x4d\x3d\x39\x61\x28\x32\x42\x2c\x31\x72\x29\x2c\x33\x72\x3d\x39\x39\x28\x32\x42\x2c\x31\x72\x2c\x32\x4d\x29\x2c\x33\x71\x3d\x61\x61\x28\x32\x42\x2c\x31\x72\x29\x2c\x31\x56\x3d\x61\x63\x28\x32\x42\x2c\x31\x72\x29\x2c\x32\x49\x3d\x5c\x27\x5c\x27\x3b\x56\x5b\x6e\x28\x31\x35\x29\x5d\x28\x5c\x27\x34\x76\x2d\x31\x70\x5c\x27\x29\x3f\x32\x49\x2b\x3d\x5c\x27\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x37\x32\x2d\x32\x30\x5c\x5c\x34\x36\x2d\x5c\x27\x2b\x31\x72\x2b\x6e\x28\x64\x76\x29\x2b\x32\x4d\x2b\x5c\x27\x5c\x5c\x6a\x3e\x5c\x27\x2b\x33\x71\x2b\x6e\x28\x34\x55\x29\x2b\x31\x56\x5b\x42\x5d\x2b\x6e\x28\x61\x69\x29\x2b\x33\x72\x2b\x6e\x28\x34\x58\x29\x2b\x31\x56\x5b\x46\x5d\x2b\x6e\x28\x63\x4d\x29\x3a\x56\x5b\x6e\x28\x31\x35\x29\x5d\x28\x6e\x28\x35\x4c\x29\x29\x3f\x32\x49\x2b\x3d\x6e\x28\x63\x57\x29\x2b\x31\x72\x2b\x5c\x27\x5c\x5c\x6a\x3e\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x39\x74\x2d\x32\x30\x2d\x38\x4e\x5c\x5c\x6a\x3e\x3c\x61\x5c\x5c\x79\x3d\x5c\x5c\x32\x33\x2d\x32\x72\x2d\x32\x75\x5c\x5c\x6a\x5c\x5c\x31\x41\x3d\x5c\x5c\x6a\x5c\x27\x2b\x32\x4d\x2b\x5c\x27\x5c\x5c\x6a\x3e\x5c\x27\x2b\x33\x71\x2b\x6e\x28\x34\x55\x29\x2b\x31\x56\x5b\x42\x5d\x2b\x6e\x28\x61\x6f\x29\x2b\x33\x72\x2b\x6e\x28\x34\x58\x29\x2b\x31\x56\x5b\x46\x5d\x2b\x5c\x27\x3c\x2f\x78\x3e\x3c\x2f\x78\x3e\x3c\x2f\x47\x3e\x5c\x27\x3a\x56\x5b\x5c\x27\x32\x41\x5c\x27\x5d\x28\x5c\x27\x4c\x2d\x38\x34\x5c\x27\x29\x3f\x32\x49\x2b\x3d\x6e\x28\x63\x6d\x29\x2b\x31\x72\x2b\x6e\x28\x61\x74\x29\x2b\x32\x4d\x2b\x5c\x27\x5c\x5c\x6a\x3e\x5c\x27\x2b\x33\x71\x2b\x5c\x27\x3c\x2f\x61\x3e\x3c\x2f\x78\x3e\x5c\x27\x2b\x31\x56\x5b\x42\x5d\x2b\x6e\x28\x61\x6f\x29\x2b\x33\x72\x2b\x6e\x28\x34\x58\x29\x2b\x31\x56\x5b\x46\x5d\x2b\x5c\x27\x3c\x2f\x78\x3e\x3c\x2f\x78\x3e\x3c\x2f\x47\x3e\x5c\x27\x3a\x56\x5b\x5c\x27\x32\x41\x5c\x27\x5d\x28\x6e\x28\x61\x70\x29\x29\x26\x26\x28\x32\x49\x2b\x3d\x6e\x28\x63\x79\x29\x2b\x31\x72\x2b\x6e\x28\x61\x74\x29\x2b\x32\x4d\x2b\x5c\x27\x5c\x5c\x6a\x3e\x5c\x27\x2b\x33\x71\x2b\x6e\x28\x34\x55\x29\x2b\x31\x56\x5b\x42\x5d\x2b\x6e\x28\x61\x69\x29\x2b\x33\x72\x2b\x6e\x28\x34\x58\x29\x2b\x31\x56\x5b\x46\x5d\x2b\x5c\x27\x3c\x2f\x47\x3e\x5c\x27\x29\x2c\x31\x44\x2b\x3d\x32\x49\x7d\x31\x44\x2b\x3d\x6e\x28\x64\x70\x29\x7d\x31\x42\x20\x31\x44\x3d\x6e\x28\x64\x72\x29\x3b\x56\x5b\x6e\x28\x31\x35\x29\x5d\x28\x6e\x28\x63\x66\x29\x29\x3f\x28\x32\x4c\x5b\x6e\x28\x58\x29\x5d\x28\x5c\x27\x64\x78\x2d\x63\x67\x5c\x5c\x62\x5a\x2d\x31\x70\x5c\x27\x29\x5b\x6e\x28\x37\x6b\x29\x5d\x28\x31\x44\x29\x2c\x32\x4c\x5b\x6e\x28\x77\x29\x5d\x28\x6e\x28\x35\x6a\x29\x29\x5b\x6e\x28\x31\x55\x29\x5d\x28\x6e\x28\x32\x37\x29\x2c\x6b\x28\x61\x57\x2c\x32\x45\x29\x7b\x64\x20\x32\x4b\x3d\x6e\x3b\x53\x20\x32\x45\x3d\x5c\x27\x38\x49\x5c\x27\x3d\x3d\x32\x70\x7c\x7c\x32\x4b\x28\x34\x30\x29\x3d\x3d\x32\x70\x3f\x32\x45\x5b\x32\x4b\x28\x31\x6e\x29\x5d\x28\x32\x45\x2c\x32\x4b\x28\x61\x59\x29\x2b\x36\x38\x29\x3a\x32\x45\x5b\x32\x4b\x28\x31\x6e\x29\x5d\x28\x32\x45\x2c\x5c\x27\x2f\x31\x79\x2f\x32\x6e\x2f\x5c\x27\x2b\x32\x70\x2b\x32\x4b\x28\x62\x50\x29\x2b\x36\x38\x29\x7d\x29\x29\x3a\x56\x5b\x6e\x28\x31\x35\x29\x5d\x28\x6e\x28\x35\x4c\x29\x29\x3f\x32\x4c\x5b\x6e\x28\x54\x29\x5d\x28\x31\x44\x29\x5b\x6e\x28\x36\x35\x29\x5d\x28\x29\x5b\x6e\x28\x58\x29\x5d\x28\x6e\x28\x61\x79\x29\x29\x3a\x32\x4c\x5b\x6e\x28\x54\x29\x5d\x28\x31\x44\x29\x7d\x7d\x29\x7d\x7d\x24\x28\x5c\x27\x2e\x4c\x2d\x62\x71\x2d\x38\x53\x5c\x27\x29\x5b\x6c\x28\x32\x63\x29\x5d\x28\x6b\x28\x29\x7b\x64\x20\x32\x6d\x3d\x6c\x2c\x34\x33\x3d\x24\x28\x68\x29\x2c\x61\x66\x3d\x34\x33\x5b\x32\x6d\x28\x35\x4a\x29\x5d\x28\x5c\x27\x69\x64\x5c\x27\x29\x3b\x24\x5b\x32\x6d\x28\x36\x34\x29\x5d\x28\x7b\x5c\x27\x32\x68\x5c\x27\x3a\x32\x6d\x28\x61\x6a\x29\x2b\x61\x66\x2b\x32\x6d\x28\x62\x6f\x29\x2c\x5c\x27\x36\x63\x5c\x27\x3a\x5c\x27\x38\x76\x5c\x27\x2c\x5c\x27\x36\x65\x5c\x27\x3a\x32\x6d\x28\x62\x45\x29\x2c\x5c\x27\x36\x32\x5c\x27\x3a\x6b\x28\x61\x47\x29\x7b\x64\x20\x31\x33\x3d\x32\x6d\x2c\x38\x4c\x3d\x61\x47\x5b\x31\x33\x28\x36\x78\x29\x5d\x5b\x31\x33\x28\x61\x42\x29\x5d\x5b\x5c\x27\x24\x74\x5c\x27\x5d\x2c\x36\x59\x3d\x24\x28\x31\x33\x28\x61\x49\x29\x29\x5b\x5c\x27\x31\x34\x5c\x27\x5d\x28\x38\x4c\x29\x2c\x35\x59\x3d\x36\x59\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x5c\x27\x33\x6f\x3a\x33\x70\x28\x5c\x5c\x37\x36\x2f\x5c\x5c\x6a\x29\x5c\x27\x29\x2c\x35\x58\x3d\x36\x59\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x31\x33\x28\x35\x56\x29\x29\x3b\x69\x66\x28\x35\x59\x5b\x31\x33\x28\x31\x59\x29\x5d\x3e\x46\x29\x7b\x64\x20\x34\x44\x3d\x35\x59\x5b\x31\x33\x28\x31\x66\x29\x5d\x28\x29\x2c\x34\x43\x3d\x34\x44\x5b\x5c\x27\x32\x64\x5c\x27\x5d\x28\x5c\x27\x2f\x5c\x27\x29\x2c\x37\x39\x3d\x34\x43\x5b\x42\x5d\x3b\x34\x33\x5b\x31\x33\x28\x77\x29\x5d\x28\x5c\x27\x2e\x38\x77\x2d\x34\x48\x5c\x27\x29\x5b\x31\x33\x28\x31\x66\x29\x5d\x28\x37\x39\x29\x5b\x5c\x27\x34\x45\x5c\x27\x5d\x28\x29\x5b\x31\x33\x28\x58\x29\x5d\x28\x5c\x27\x33\x6a\x5c\x27\x29\x7d\x69\x66\x28\x35\x58\x5b\x31\x33\x28\x31\x59\x29\x5d\x3e\x46\x29\x7b\x64\x20\x34\x44\x3d\x35\x58\x5b\x31\x33\x28\x31\x66\x29\x5d\x28\x29\x2c\x34\x43\x3d\x34\x44\x5b\x5c\x27\x32\x64\x5c\x27\x5d\x28\x5c\x27\x2f\x5c\x27\x29\x2c\x37\x76\x3d\x34\x43\x5b\x42\x5d\x3b\x34\x33\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x31\x33\x28\x62\x79\x29\x29\x5b\x31\x33\x28\x31\x66\x29\x5d\x28\x37\x76\x29\x5b\x31\x33\x28\x58\x29\x5d\x28\x5c\x27\x33\x6a\x5c\x27\x29\x7d\x7d\x7d\x29\x7d\x29\x2c\x24\x28\x5c\x27\x2e\x35\x6e\x2d\x4c\x5c\x5c\x6d\x2e\x4c\x2d\x32\x66\x5c\x27\x29\x5b\x5c\x27\x33\x41\x5c\x27\x5d\x28\x6b\x28\x29\x7b\x64\x20\x41\x3d\x6c\x2c\x34\x41\x3d\x24\x28\x68\x29\x2c\x34\x77\x3d\x34\x41\x5b\x41\x28\x77\x29\x5d\x28\x41\x28\x62\x76\x29\x29\x2c\x34\x74\x3d\x34\x41\x5b\x41\x28\x77\x29\x5d\x28\x41\x28\x35\x56\x29\x29\x2c\x34\x56\x3d\x34\x41\x5b\x41\x28\x77\x29\x5d\x28\x41\x28\x62\x43\x29\x29\x3b\x69\x66\x28\x34\x77\x5b\x41\x28\x31\x59\x29\x5d\x3e\x46\x29\x7b\x64\x20\x32\x4a\x3d\x34\x77\x5b\x41\x28\x31\x66\x29\x5d\x28\x29\x2c\x31\x4a\x3d\x32\x4a\x5b\x41\x28\x31\x65\x29\x5d\x28\x5c\x27\x2f\x5c\x27\x29\x2c\x37\x63\x3d\x31\x4a\x5b\x42\x5d\x3b\x24\x28\x41\x28\x36\x68\x29\x29\x5b\x41\x28\x77\x29\x5d\x28\x41\x28\x63\x32\x29\x29\x5b\x5c\x27\x32\x32\x5c\x27\x5d\x28\x37\x63\x29\x5b\x41\x28\x36\x35\x29\x5d\x28\x29\x5b\x5c\x27\x31\x46\x5c\x27\x5d\x28\x41\x28\x32\x59\x29\x29\x2c\x34\x77\x5b\x41\x28\x37\x43\x29\x5d\x28\x29\x7d\x69\x66\x28\x34\x74\x5b\x41\x28\x31\x59\x29\x5d\x3e\x46\x29\x7b\x64\x20\x32\x4a\x3d\x34\x74\x5b\x41\x28\x31\x66\x29\x5d\x28\x29\x2c\x31\x4a\x3d\x32\x4a\x5b\x41\x28\x31\x65\x29\x5d\x28\x5c\x27\x2f\x5c\x27\x29\x2c\x37\x71\x3d\x31\x4a\x5b\x42\x5d\x3b\x24\x28\x41\x28\x36\x68\x29\x29\x5b\x41\x28\x77\x29\x5d\x28\x5c\x27\x2e\x37\x6f\x5c\x27\x29\x5b\x41\x28\x31\x66\x29\x5d\x28\x37\x71\x29\x5b\x5c\x27\x31\x46\x5c\x27\x5d\x28\x41\x28\x32\x59\x29\x29\x2c\x34\x74\x5b\x41\x28\x37\x43\x29\x5d\x28\x29\x7d\x69\x66\x28\x34\x56\x5b\x41\x28\x31\x59\x29\x5d\x3e\x46\x29\x7b\x64\x20\x32\x4a\x3d\x34\x56\x5b\x41\x28\x31\x66\x29\x5d\x28\x29\x2c\x31\x4a\x3d\x32\x4a\x5b\x41\x28\x31\x65\x29\x5d\x28\x5c\x27\x2f\x5c\x27\x29\x3b\x35\x4e\x28\x64\x20\x34\x57\x20\x69\x6e\x28\x31\x4a\x5b\x42\x5d\x2c\x31\x4a\x29\x29\x41\x28\x62\x67\x29\x21\x3d\x31\x4a\x5b\x34\x57\x5d\x26\x26\x24\x28\x41\x28\x36\x68\x29\x29\x5b\x41\x28\x77\x29\x5d\x28\x41\x28\x64\x79\x29\x29\x5b\x41\x28\x37\x6b\x29\x5d\x28\x41\x28\x64\x77\x29\x2b\x31\x4a\x5b\x34\x57\x5d\x2b\x5c\x27\x3e\x5c\x27\x2b\x31\x4a\x5b\x34\x57\x5d\x2b\x41\x28\x64\x6a\x29\x29\x5b\x41\x28\x58\x29\x5d\x28\x41\x28\x32\x59\x29\x29\x3b\x34\x56\x5b\x5c\x27\x39\x6b\x5c\x27\x5d\x28\x29\x7d\x7d\x29\x2c\x24\x28\x6c\x28\x37\x4f\x29\x29\x5b\x6c\x28\x31\x7a\x29\x5d\x28\x6b\x28\x29\x7b\x64\x20\x36\x62\x3d\x6c\x3b\x24\x28\x68\x29\x5b\x36\x62\x28\x35\x33\x29\x5d\x28\x36\x62\x28\x64\x4b\x29\x29\x7d\x29\x2c\x24\x28\x6c\x28\x64\x4a\x29\x29\x5b\x6c\x28\x32\x63\x29\x5d\x28\x6b\x28\x29\x7b\x64\x20\x33\x66\x3d\x6c\x3b\x24\x28\x68\x29\x5b\x33\x66\x28\x77\x29\x5d\x28\x33\x66\x28\x64\x47\x29\x29\x5b\x33\x66\x28\x34\x78\x29\x5d\x28\x29\x2c\x24\x28\x68\x29\x5b\x33\x66\x28\x77\x29\x5d\x28\x5c\x27\x32\x67\x5c\x27\x29\x5b\x5c\x27\x33\x6a\x5c\x27\x5d\x28\x29\x7d\x29\x2c\x24\x28\x6c\x28\x63\x46\x29\x29\x5b\x6c\x28\x31\x55\x29\x5d\x28\x6c\x28\x32\x37\x29\x2c\x6b\x28\x63\x45\x2c\x34\x53\x29\x7b\x64\x20\x38\x70\x3d\x6c\x3b\x53\x20\x34\x53\x5b\x38\x70\x28\x31\x6e\x29\x5d\x28\x34\x53\x2c\x34\x53\x2b\x5c\x27\x3f\x26\x31\x52\x2d\x32\x69\x3d\x5c\x27\x2b\x36\x38\x29\x7d\x29\x2c\x24\x28\x6c\x28\x63\x78\x29\x29\x5b\x6c\x28\x31\x55\x29\x5d\x28\x6c\x28\x38\x71\x29\x2c\x6b\x28\x63\x74\x2c\x34\x4a\x29\x7b\x64\x20\x32\x52\x3d\x6c\x3b\x53\x20\x34\x4a\x3d\x28\x34\x4a\x3d\x34\x4a\x5b\x5c\x27\x32\x7a\x5c\x27\x5d\x28\x32\x52\x28\x63\x6c\x29\x2c\x32\x52\x28\x63\x6b\x29\x29\x29\x5b\x32\x52\x28\x31\x6e\x29\x5d\x28\x32\x52\x28\x63\x6a\x29\x2c\x32\x52\x28\x64\x37\x29\x29\x7d\x29\x2c\x24\x28\x6c\x28\x64\x32\x29\x29\x5b\x5c\x27\x33\x41\x5c\x27\x5d\x28\x6b\x28\x29\x7b\x64\x20\x31\x68\x3d\x6c\x2c\x33\x46\x3d\x24\x28\x68\x29\x2c\x34\x4d\x3d\x33\x46\x5b\x31\x68\x28\x31\x66\x29\x5d\x28\x29\x3b\x34\x4d\x5b\x31\x68\x28\x31\x35\x29\x5d\x28\x31\x68\x28\x64\x31\x29\x29\x26\x26\x33\x46\x5b\x31\x68\x28\x38\x43\x29\x5d\x28\x31\x68\x28\x63\x56\x29\x29\x2c\x34\x4d\x5b\x31\x68\x28\x31\x35\x29\x5d\x28\x31\x68\x28\x63\x55\x29\x29\x26\x26\x33\x46\x5b\x31\x68\x28\x38\x43\x29\x5d\x28\x31\x68\x28\x63\x4c\x29\x29\x2c\x34\x4d\x5b\x31\x68\x28\x31\x35\x29\x5d\x28\x31\x68\x28\x63\x4b\x29\x29\x26\x26\x33\x46\x5b\x5c\x27\x38\x32\x5c\x27\x5d\x28\x31\x68\x28\x63\x4e\x29\x29\x7d\x29\x2c\x24\x28\x6c\x28\x63\x4f\x29\x29\x5b\x6c\x28\x32\x63\x29\x5d\x28\x6b\x28\x29\x7b\x64\x20\x33\x75\x3d\x6c\x2c\x34\x49\x3d\x24\x28\x68\x29\x3b\x24\x28\x32\x76\x29\x5b\x5c\x27\x36\x61\x5c\x27\x5d\x28\x33\x75\x28\x63\x50\x29\x2c\x6b\x28\x29\x7b\x64\x20\x34\x6f\x3d\x33\x75\x3b\x24\x28\x68\x29\x5b\x34\x6f\x28\x63\x51\x29\x5d\x28\x29\x3e\x3d\x63\x52\x3f\x34\x49\x5b\x34\x6f\x28\x37\x52\x29\x5d\x28\x37\x50\x29\x3a\x34\x49\x5b\x34\x6f\x28\x37\x5a\x29\x5d\x28\x37\x50\x29\x7d\x29\x2c\x34\x49\x5b\x33\x75\x28\x31\x7a\x29\x5d\x28\x6b\x28\x29\x7b\x64\x20\x37\x53\x3d\x33\x75\x3b\x24\x28\x5c\x27\x31\x34\x2c\x5c\x5c\x38\x6e\x5c\x27\x29\x5b\x37\x53\x28\x63\x58\x29\x5d\x28\x7b\x5c\x27\x37\x74\x5c\x27\x3a\x46\x7d\x2c\x36\x36\x29\x7d\x29\x7d\x29\x2c\x24\x28\x6c\x28\x63\x59\x29\x29\x5b\x6c\x28\x32\x63\x29\x5d\x28\x6b\x28\x29\x7b\x64\x20\x33\x59\x3d\x6c\x2c\x63\x5a\x2c\x35\x63\x3d\x24\x28\x68\x29\x2c\x36\x6d\x3d\x35\x63\x5b\x5c\x27\x32\x32\x5c\x27\x5d\x28\x29\x5b\x33\x59\x28\x31\x4b\x29\x5d\x28\x29\x3b\x33\x32\x28\x35\x63\x2c\x36\x6d\x5b\x33\x59\x28\x38\x31\x29\x5d\x28\x29\x2c\x35\x61\x2c\x36\x6d\x5b\x33\x59\x28\x31\x65\x29\x5d\x28\x5c\x27\x2f\x5c\x27\x29\x5b\x46\x5d\x29\x7d\x29\x2c\x24\x28\x6c\x28\x64\x35\x29\x29\x5b\x5c\x27\x33\x41\x5c\x27\x5d\x28\x6b\x28\x29\x7b\x64\x20\x35\x44\x3d\x6c\x2c\x64\x36\x2c\x35\x48\x3d\x24\x28\x68\x29\x2c\x35\x47\x3d\x35\x48\x5b\x5c\x27\x32\x32\x5c\x27\x5d\x28\x29\x5b\x35\x44\x28\x31\x4b\x29\x5d\x28\x29\x3b\x33\x32\x28\x35\x48\x2c\x35\x47\x5b\x5c\x27\x37\x64\x5c\x27\x5d\x28\x29\x2c\x35\x61\x2c\x35\x47\x5b\x35\x44\x28\x31\x65\x29\x5d\x28\x5c\x27\x2f\x5c\x27\x29\x5b\x46\x5d\x29\x7d\x29\x2c\x24\x28\x5c\x27\x2e\x63\x47\x5c\x5c\x6d\x2e\x34\x70\x2d\x32\x79\x5c\x27\x29\x5b\x5c\x27\x33\x41\x5c\x27\x5d\x28\x6b\x28\x29\x7b\x64\x20\x33\x55\x3d\x6c\x2c\x63\x69\x2c\x35\x78\x3d\x24\x28\x68\x29\x2c\x35\x73\x3d\x35\x78\x5b\x33\x55\x28\x31\x66\x29\x5d\x28\x29\x5b\x5c\x27\x36\x6f\x5c\x27\x5d\x28\x29\x2c\x38\x37\x3d\x35\x73\x5b\x33\x55\x28\x38\x31\x29\x5d\x28\x29\x2c\x35\x77\x3d\x35\x73\x5b\x33\x55\x28\x31\x65\x29\x5d\x28\x5c\x27\x2f\x5c\x27\x29\x3b\x33\x32\x28\x35\x78\x2c\x38\x37\x2c\x35\x77\x5b\x46\x5d\x2c\x35\x77\x5b\x42\x5d\x29\x7d\x29\x2c\x24\x28\x6c\x28\x63\x72\x29\x29\x5b\x6c\x28\x32\x63\x29\x5d\x28\x6b\x28\x29\x7b\x64\x20\x33\x67\x3d\x6c\x2c\x35\x74\x3d\x24\x28\x68\x29\x2c\x38\x72\x3d\x35\x74\x5b\x33\x67\x28\x77\x29\x5d\x28\x33\x67\x28\x63\x73\x29\x29\x5b\x33\x67\x28\x35\x4a\x29\x5d\x28\x33\x67\x28\x39\x4f\x29\x29\x3b\x33\x32\x28\x35\x74\x2c\x5c\x27\x33\x69\x5c\x27\x2c\x37\x4c\x2c\x38\x72\x29\x7d\x29\x3b\x64\x20\x37\x33\x3d\x63\x7a\x2c\x63\x41\x3d\x37\x4e\x2c\x36\x4f\x3d\x33\x58\x5b\x6c\x28\x38\x63\x29\x5d\x28\x33\x58\x5b\x6c\x28\x34\x30\x29\x5d\x28\x29\x2a\x28\x37\x4e\x2d\x37\x33\x2b\x42\x29\x2b\x37\x33\x29\x3b\x24\x28\x6c\x28\x37\x56\x29\x29\x5b\x6c\x28\x64\x38\x29\x5d\x28\x6c\x28\x63\x49\x29\x2c\x6b\x28\x29\x7b\x64\x20\x66\x3d\x6c\x2c\x36\x49\x2c\x36\x47\x2c\x36\x51\x2c\x36\x76\x2c\x44\x3d\x24\x28\x66\x28\x37\x56\x29\x29\x2c\x32\x5a\x3d\x44\x5b\x66\x28\x77\x29\x5d\x28\x5c\x27\x59\x2e\x31\x4c\x2d\x31\x77\x2d\x31\x47\x5c\x27\x29\x5b\x66\x28\x32\x43\x29\x5d\x28\x29\x5b\x66\x28\x31\x4b\x29\x5d\x28\x29\x2c\x34\x39\x3d\x44\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x5c\x27\x59\x2e\x31\x4c\x2d\x31\x77\x2d\x35\x30\x5c\x27\x29\x5b\x66\x28\x32\x43\x29\x5d\x28\x29\x5b\x66\x28\x31\x4b\x29\x5d\x28\x29\x2c\x32\x56\x3d\x44\x5b\x66\x28\x77\x29\x5d\x28\x66\x28\x38\x73\x29\x29\x5b\x66\x28\x32\x43\x29\x5d\x28\x29\x5b\x66\x28\x31\x4b\x29\x5d\x28\x29\x2c\x34\x38\x3d\x44\x5b\x66\x28\x77\x29\x5d\x28\x5c\x27\x59\x2e\x4f\x2d\x34\x46\x5c\x27\x29\x5b\x66\x28\x32\x43\x29\x5d\x28\x29\x5b\x66\x28\x31\x4b\x29\x5d\x28\x29\x2c\x32\x57\x3d\x44\x5b\x66\x28\x77\x29\x5d\x28\x66\x28\x36\x6e\x29\x29\x5b\x66\x28\x32\x43\x29\x5d\x28\x29\x5b\x66\x28\x31\x4b\x29\x5d\x28\x29\x2c\x34\x5a\x3d\x44\x5b\x66\x28\x77\x29\x5d\x28\x66\x28\x36\x4c\x29\x29\x5b\x5c\x27\x35\x4b\x5c\x27\x5d\x28\x29\x5b\x66\x28\x31\x4b\x29\x5d\x28\x29\x2c\x34\x68\x3d\x44\x5b\x66\x28\x77\x29\x5d\x28\x66\x28\x64\x43\x29\x29\x5b\x66\x28\x32\x43\x29\x5d\x28\x29\x5b\x66\x28\x31\x4b\x29\x5d\x28\x29\x3b\x24\x28\x5c\x27\x2e\x38\x48\x5c\x27\x29\x2c\x24\x28\x5c\x27\x2e\x2d\x31\x6c\x2d\x64\x48\x5c\x27\x29\x5b\x66\x28\x77\x29\x5d\x28\x66\x28\x64\x49\x29\x29\x5b\x66\x28\x31\x66\x29\x5d\x28\x29\x5b\x66\x28\x31\x4b\x29\x5d\x28\x29\x2c\x24\x28\x66\x28\x64\x4c\x29\x29\x5b\x66\x28\x77\x29\x5d\x28\x5c\x27\x2e\x61\x65\x5c\x27\x29\x5b\x5c\x27\x32\x32\x5c\x27\x5d\x28\x29\x5b\x5c\x27\x36\x6f\x5c\x27\x5d\x28\x29\x3b\x64\x20\x34\x69\x3d\x66\x28\x64\x4d\x29\x3b\x32\x6f\x5b\x66\x28\x64\x4f\x29\x5d\x28\x5c\x27\x2e\x38\x48\x5c\x27\x29\x5b\x5c\x27\x64\x50\x5c\x27\x5d\x28\x31\x51\x3d\x3e\x7b\x64\x20\x51\x3d\x66\x3b\x34\x69\x2b\x3d\x31\x51\x5b\x51\x28\x32\x55\x29\x5d\x5b\x5c\x27\x32\x64\x5c\x27\x5d\x28\x5c\x27\x5c\x5c\x31\x63\x5c\x27\x29\x5b\x46\x5d\x2b\x51\x28\x64\x52\x29\x2b\x31\x51\x5b\x51\x28\x32\x55\x29\x5d\x5b\x51\x28\x31\x65\x29\x5d\x28\x5c\x27\x5c\x5c\x31\x63\x5c\x27\x29\x5b\x36\x79\x5d\x2b\x5c\x27\x5c\x5c\x36\x70\x5c\x5c\x64\x53\x3a\x5c\x5c\x6d\x5c\x27\x2b\x31\x51\x5b\x51\x28\x32\x55\x29\x5d\x5b\x51\x28\x31\x65\x29\x5d\x28\x5c\x27\x5c\x5c\x31\x63\x5c\x27\x29\x5b\x33\x48\x5d\x2b\x51\x28\x64\x54\x29\x2b\x31\x51\x5b\x51\x28\x32\x55\x29\x5d\x5b\x5c\x27\x32\x64\x5c\x27\x5d\x28\x5c\x27\x5c\x5c\x31\x63\x5c\x27\x29\x5b\x42\x5d\x2b\x5c\x27\x5c\x5c\x31\x63\x5c\x5c\x31\x63\x5c\x27\x2c\x36\x49\x2b\x3d\x31\x51\x5b\x5c\x27\x36\x6a\x5c\x27\x5d\x5b\x5c\x27\x32\x64\x5c\x27\x5d\x28\x5c\x27\x5c\x5c\x31\x63\x5c\x27\x29\x5b\x46\x5d\x2b\x51\x28\x34\x6a\x29\x2c\x36\x47\x2b\x3d\x31\x51\x5b\x5c\x27\x36\x6a\x5c\x27\x5d\x5b\x51\x28\x31\x65\x29\x5d\x28\x5c\x27\x5c\x5c\x31\x63\x5c\x27\x29\x5b\x36\x79\x5d\x2b\x51\x28\x34\x6a\x29\x2c\x36\x51\x2b\x3d\x31\x51\x5b\x51\x28\x32\x55\x29\x5d\x5b\x51\x28\x31\x65\x29\x5d\x28\x5c\x27\x5c\x5c\x31\x63\x5c\x27\x29\x5b\x42\x5d\x2b\x51\x28\x34\x6a\x29\x2c\x36\x76\x2b\x3d\x31\x51\x5b\x51\x28\x32\x55\x29\x5d\x5b\x51\x28\x31\x65\x29\x5d\x28\x5c\x27\x5c\x5c\x31\x63\x5c\x27\x29\x5b\x33\x48\x5d\x2b\x51\x28\x34\x6a\x29\x7d\x29\x2c\x34\x69\x2b\x3d\x66\x28\x64\x5a\x29\x2c\x44\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x5c\x27\x2e\x31\x4c\x2d\x31\x77\x2d\x35\x30\x2d\x33\x6c\x5c\x27\x29\x5b\x5c\x27\x35\x4b\x5c\x27\x5d\x28\x66\x28\x65\x30\x29\x2b\x36\x4f\x2b\x66\x28\x65\x31\x29\x2b\x32\x56\x2b\x66\x28\x64\x51\x29\x2b\x34\x38\x2b\x66\x28\x64\x42\x29\x2b\x32\x57\x2b\x66\x28\x64\x6f\x29\x2b\x34\x5a\x2b\x5c\x27\x5c\x5c\x39\x68\x5c\x5c\x64\x41\x3a\x64\x63\x5c\x27\x2b\x34\x68\x2b\x5c\x27\x5c\x5c\x31\x63\x5c\x27\x2b\x34\x69\x29\x2c\x24\x28\x66\x28\x64\x65\x29\x29\x5b\x66\x28\x31\x7a\x29\x5d\x28\x6b\x28\x29\x7b\x64\x20\x76\x3d\x66\x3b\x5c\x27\x5c\x27\x21\x3d\x32\x5a\x3f\x44\x5b\x76\x28\x77\x29\x5d\x28\x76\x28\x38\x75\x29\x29\x5b\x76\x28\x31\x73\x29\x5d\x28\x76\x28\x31\x6d\x29\x29\x3a\x44\x5b\x76\x28\x77\x29\x5d\x28\x76\x28\x38\x75\x29\x29\x5b\x76\x28\x58\x29\x5d\x28\x5c\x27\x33\x39\x5c\x27\x29\x2c\x5c\x27\x5c\x27\x21\x3d\x34\x39\x3f\x44\x5b\x76\x28\x77\x29\x5d\x28\x76\x28\x38\x74\x29\x29\x5b\x76\x28\x31\x73\x29\x5d\x28\x5c\x27\x33\x39\x5c\x27\x29\x3a\x44\x5b\x76\x28\x77\x29\x5d\x28\x76\x28\x38\x74\x29\x29\x5b\x5c\x27\x31\x46\x5c\x27\x5d\x28\x76\x28\x31\x6d\x29\x29\x2c\x5c\x27\x5c\x27\x21\x3d\x32\x56\x3f\x44\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x76\x28\x38\x73\x29\x29\x5b\x76\x28\x31\x73\x29\x5d\x28\x76\x28\x31\x6d\x29\x29\x3a\x44\x5b\x76\x28\x77\x29\x5d\x28\x5c\x27\x59\x2e\x4f\x2d\x36\x41\x5c\x27\x29\x5b\x76\x28\x58\x29\x5d\x28\x76\x28\x31\x6d\x29\x29\x2c\x5c\x27\x5c\x27\x21\x3d\x34\x38\x3f\x44\x5b\x76\x28\x77\x29\x5d\x28\x5c\x27\x59\x2e\x4f\x2d\x34\x46\x5c\x27\x29\x5b\x76\x28\x31\x73\x29\x5d\x28\x76\x28\x31\x6d\x29\x29\x3a\x44\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x76\x28\x64\x68\x29\x29\x5b\x76\x28\x58\x29\x5d\x28\x76\x28\x31\x6d\x29\x29\x2c\x5c\x27\x5c\x27\x21\x3d\x34\x68\x3f\x44\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x5c\x27\x35\x42\x2e\x4f\x2d\x33\x6c\x5c\x27\x29\x5b\x76\x28\x31\x73\x29\x5d\x28\x5c\x27\x33\x39\x5c\x27\x29\x3a\x44\x5b\x76\x28\x77\x29\x5d\x28\x5c\x27\x35\x42\x2e\x4f\x2d\x33\x6c\x5c\x27\x29\x5b\x76\x28\x58\x29\x5d\x28\x76\x28\x31\x6d\x29\x29\x2c\x5c\x27\x5c\x27\x21\x3d\x32\x57\x3f\x44\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x76\x28\x36\x6e\x29\x29\x5b\x76\x28\x31\x73\x29\x5d\x28\x76\x28\x31\x6d\x29\x29\x3a\x44\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x76\x28\x36\x6e\x29\x29\x5b\x5c\x27\x31\x46\x5c\x27\x5d\x28\x76\x28\x31\x6d\x29\x29\x2c\x5c\x27\x5c\x27\x21\x3d\x34\x5a\x3f\x44\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x76\x28\x36\x4c\x29\x29\x5b\x5c\x27\x35\x67\x5c\x27\x5d\x28\x76\x28\x31\x6d\x29\x29\x3a\x44\x5b\x76\x28\x77\x29\x5d\x28\x76\x28\x36\x4c\x29\x29\x5b\x76\x28\x58\x29\x5d\x28\x76\x28\x31\x6d\x29\x29\x2c\x5c\x27\x5c\x27\x21\x3d\x28\x32\x5a\x26\x26\x34\x39\x26\x26\x32\x56\x26\x26\x34\x68\x26\x26\x32\x57\x29\x3f\x44\x5b\x76\x28\x77\x29\x5d\x28\x5c\x27\x2e\x31\x4c\x2d\x31\x77\x2d\x35\x41\x2d\x35\x72\x5c\x27\x29\x5b\x76\x28\x64\x6b\x29\x5d\x28\x76\x28\x33\x33\x29\x29\x5b\x76\x28\x31\x73\x29\x5d\x28\x5c\x27\x34\x64\x5c\x27\x29\x3a\x44\x5b\x76\x28\x77\x29\x5d\x28\x76\x28\x33\x36\x29\x29\x5b\x76\x28\x31\x55\x29\x5d\x28\x5c\x27\x34\x64\x5c\x27\x2c\x76\x28\x33\x4b\x29\x29\x5b\x5c\x27\x31\x46\x5c\x27\x5d\x28\x76\x28\x33\x33\x29\x29\x7d\x29\x3b\x64\x20\x37\x6a\x3d\x24\x28\x66\x28\x64\x6c\x29\x29\x5b\x66\x28\x31\x66\x29\x5d\x28\x29\x3b\x24\x28\x66\x28\x64\x6e\x29\x29\x5b\x66\x28\x54\x29\x5d\x28\x36\x4f\x29\x2c\x24\x28\x66\x28\x64\x71\x29\x29\x5b\x5c\x27\x31\x34\x5c\x27\x5d\x28\x37\x6a\x5b\x5c\x27\x32\x7a\x5c\x27\x5d\x28\x66\x28\x34\x61\x29\x2c\x5c\x27\x5c\x27\x29\x29\x2c\x24\x28\x66\x28\x64\x73\x29\x29\x5b\x5c\x27\x31\x34\x5c\x27\x5d\x28\x36\x49\x5b\x5c\x27\x32\x7a\x5c\x27\x5d\x28\x66\x28\x34\x61\x29\x2c\x5c\x27\x5c\x27\x29\x29\x2c\x24\x28\x66\x28\x36\x36\x29\x29\x5b\x5c\x27\x31\x34\x5c\x27\x5d\x28\x36\x47\x5b\x5c\x27\x32\x7a\x5c\x27\x5d\x28\x66\x28\x34\x61\x29\x2c\x5c\x27\x5c\x27\x29\x29\x2c\x24\x28\x66\x28\x64\x75\x29\x29\x5b\x66\x28\x54\x29\x5d\x28\x36\x76\x5b\x66\x28\x31\x6e\x29\x5d\x28\x5c\x27\x38\x47\x5c\x27\x2c\x5c\x27\x5c\x27\x29\x29\x2c\x24\x28\x66\x28\x64\x7a\x29\x29\x5b\x66\x28\x54\x29\x5d\x28\x36\x51\x5b\x66\x28\x31\x6e\x29\x5d\x28\x66\x28\x34\x61\x29\x2c\x5c\x27\x5c\x27\x29\x29\x2c\x24\x28\x66\x28\x63\x65\x29\x29\x5b\x66\x28\x54\x29\x5d\x28\x32\x5a\x29\x2c\x24\x28\x66\x28\x61\x56\x29\x29\x5b\x66\x28\x54\x29\x5d\x28\x32\x5a\x29\x2c\x24\x28\x5c\x27\x2e\x62\x63\x5c\x27\x29\x5b\x5c\x27\x31\x34\x5c\x27\x5d\x28\x34\x39\x29\x2c\x24\x28\x66\x28\x62\x69\x29\x29\x5b\x66\x28\x54\x29\x5d\x28\x32\x56\x29\x2c\x24\x28\x66\x28\x62\x36\x29\x29\x5b\x66\x28\x54\x29\x5d\x28\x32\x57\x29\x2c\x24\x28\x66\x28\x62\x33\x29\x29\x5b\x66\x28\x54\x29\x5d\x28\x34\x38\x29\x2c\x24\x28\x66\x28\x62\x6a\x29\x29\x5b\x66\x28\x54\x29\x5d\x28\x34\x5a\x29\x2c\x24\x28\x66\x28\x62\x34\x29\x29\x5b\x5c\x27\x69\x73\x5c\x27\x5d\x28\x66\x28\x36\x54\x29\x29\x26\x26\x24\x28\x66\x28\x37\x61\x29\x29\x5b\x5c\x27\x31\x34\x5c\x27\x5d\x28\x66\x28\x62\x37\x29\x29\x2c\x24\x28\x66\x28\x62\x6c\x29\x29\x5b\x5c\x27\x69\x73\x5c\x27\x5d\x28\x66\x28\x36\x54\x29\x29\x26\x26\x28\x24\x28\x5c\x27\x2e\x37\x78\x5c\x27\x29\x5b\x66\x28\x54\x29\x5d\x28\x66\x28\x62\x62\x29\x29\x2c\x24\x28\x66\x28\x62\x64\x29\x29\x5b\x66\x28\x32\x59\x29\x5d\x28\x29\x29\x2c\x24\x28\x66\x28\x62\x65\x29\x29\x5b\x5c\x27\x69\x73\x5c\x27\x5d\x28\x66\x28\x36\x54\x29\x29\x26\x26\x28\x24\x28\x66\x28\x37\x61\x29\x29\x5b\x66\x28\x54\x29\x5d\x28\x5c\x27\x3c\x48\x3e\x62\x68\x5c\x5c\x62\x30\x5c\x5c\x6d\x3c\x65\x6d\x3e\x28\x38\x57\x5c\x5c\x39\x35\x5c\x5c\x62\x31\x5c\x5c\x61\x58\x5c\x5c\x61\x4e\x5c\x5c\x61\x50\x5c\x5c\x61\x52\x29\x3c\x2f\x65\x6d\x3e\x3c\x2f\x48\x3e\x5c\x27\x29\x2c\x24\x28\x66\x28\x61\x55\x29\x29\x5b\x66\x28\x32\x59\x29\x5d\x28\x29\x29\x2c\x24\x28\x66\x28\x38\x41\x29\x29\x5b\x66\x28\x31\x7a\x29\x5d\x28\x6b\x28\x29\x7b\x64\x20\x32\x6c\x3d\x66\x3b\x44\x5b\x32\x6c\x28\x77\x29\x5d\x28\x32\x6c\x28\x33\x36\x29\x29\x5b\x32\x6c\x28\x31\x55\x29\x5d\x28\x32\x6c\x28\x33\x33\x29\x2c\x32\x6c\x28\x33\x4b\x29\x29\x5b\x5c\x27\x31\x46\x5c\x27\x5d\x28\x32\x6c\x28\x33\x33\x29\x29\x7d\x29\x2c\x24\x28\x66\x28\x38\x41\x29\x29\x5b\x5c\x27\x61\x54\x5c\x27\x5d\x28\x6b\x28\x29\x7b\x64\x20\x32\x46\x3d\x66\x3b\x44\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x32\x46\x28\x33\x36\x29\x29\x5b\x32\x46\x28\x31\x55\x29\x5d\x28\x5c\x27\x34\x64\x5c\x27\x2c\x32\x46\x28\x33\x4b\x29\x29\x5b\x32\x46\x28\x58\x29\x5d\x28\x32\x46\x28\x33\x33\x29\x29\x7d\x29\x7d\x29\x2c\x24\x28\x5c\x27\x59\x5b\x69\x64\x3d\x5c\x5c\x6a\x2d\x62\x6e\x5c\x5c\x6a\x5d\x5c\x27\x29\x5b\x6c\x28\x31\x7a\x29\x5d\x28\x6b\x28\x29\x7b\x64\x20\x35\x35\x3d\x6c\x3b\x24\x28\x35\x35\x28\x33\x36\x29\x29\x5b\x35\x35\x28\x36\x35\x29\x5d\x28\x29\x5b\x35\x35\x28\x58\x29\x5d\x28\x5c\x27\x39\x57\x5c\x27\x29\x7d\x29\x2c\x24\x28\x5c\x27\x59\x5b\x69\x64\x3d\x5c\x5c\x6a\x2d\x39\x69\x5c\x5c\x6a\x5d\x2c\x59\x5b\x69\x64\x3d\x5c\x5c\x6a\x2d\x32\x74\x5c\x5c\x6a\x5d\x2c\x59\x5b\x69\x64\x3d\x5c\x5c\x6a\x2d\x31\x32\x5c\x5c\x6a\x5d\x5c\x27\x29\x5b\x6c\x28\x31\x7a\x29\x5d\x28\x6b\x28\x38\x62\x29\x7b\x64\x20\x33\x35\x3d\x6c\x3b\x38\x62\x5b\x33\x35\x28\x62\x57\x29\x5d\x28\x29\x2c\x24\x28\x5c\x27\x2e\x31\x4c\x2d\x31\x77\x2d\x35\x41\x2d\x35\x72\x5c\x27\x29\x5b\x5c\x27\x34\x45\x5c\x27\x5d\x28\x29\x5b\x33\x35\x28\x31\x73\x29\x5d\x28\x33\x35\x28\x62\x58\x29\x29\x2c\x24\x28\x33\x35\x28\x33\x36\x29\x29\x5b\x5c\x27\x35\x6c\x5c\x27\x5d\x28\x6b\x28\x29\x7b\x35\x65\x28\x6b\x28\x29\x7b\x64\x20\x35\x79\x3d\x5a\x3b\x24\x28\x35\x79\x28\x62\x51\x29\x29\x5b\x35\x79\x28\x37\x5a\x29\x5d\x28\x29\x7d\x2c\x37\x59\x29\x2c\x35\x65\x28\x6b\x28\x29\x7b\x64\x20\x35\x71\x3d\x5a\x3b\x24\x28\x35\x71\x28\x63\x34\x29\x29\x5b\x35\x71\x28\x37\x52\x29\x5d\x28\x29\x7d\x2c\x63\x39\x29\x7d\x29\x7d\x29\x2c\x24\x28\x5c\x27\x32\x66\x5c\x27\x29\x5b\x5c\x27\x36\x61\x5c\x27\x5d\x28\x5c\x27\x35\x6c\x5c\x27\x2c\x6c\x28\x37\x4f\x29\x2c\x6b\x28\x29\x7b\x35\x65\x28\x6b\x28\x38\x45\x29\x7b\x64\x20\x33\x37\x3d\x5a\x3b\x38\x45\x5b\x5c\x27\x31\x46\x5c\x27\x5d\x28\x33\x37\x28\x63\x63\x29\x29\x2c\x24\x28\x33\x37\x28\x63\x64\x29\x29\x5b\x33\x37\x28\x31\x73\x29\x5d\x28\x33\x37\x28\x62\x4f\x29\x29\x7d\x2c\x36\x36\x2c\x24\x28\x68\x29\x29\x7d\x29\x2c\x24\x28\x6c\x28\x62\x4e\x29\x29\x5b\x5c\x27\x36\x61\x5c\x27\x5d\x28\x6c\x28\x31\x7a\x29\x2c\x6b\x28\x38\x6d\x29\x7b\x64\x20\x31\x4e\x3d\x6c\x3b\x38\x6d\x5b\x5c\x27\x37\x66\x5c\x27\x5d\x28\x29\x2c\x24\x28\x31\x4e\x28\x62\x73\x29\x29\x5b\x31\x4e\x28\x31\x73\x29\x5d\x28\x31\x4e\x28\x33\x38\x29\x29\x2c\x24\x28\x68\x29\x5b\x31\x4e\x28\x62\x74\x29\x5d\x28\x5c\x27\x23\x5c\x27\x2b\x24\x28\x68\x29\x5b\x31\x4e\x28\x31\x55\x29\x5d\x28\x5c\x27\x69\x64\x5c\x27\x29\x5b\x31\x4e\x28\x31\x6e\x29\x5d\x28\x2f\x5c\x5c\x73\x2a\x36\x53\x5c\x5c\x73\x2a\x2f\x2c\x31\x4e\x28\x62\x75\x29\x29\x29\x5b\x31\x4e\x28\x58\x29\x5d\x28\x5c\x27\x34\x4e\x5c\x27\x29\x2c\x24\x28\x68\x29\x5b\x31\x4e\x28\x62\x78\x29\x5d\x28\x29\x7d\x29\x2c\x32\x76\x5b\x6c\x28\x36\x57\x29\x5d\x5b\x5c\x27\x36\x37\x5c\x27\x5d\x5b\x6c\x28\x32\x6a\x29\x5d\x28\x6c\x28\x38\x35\x29\x29\x3e\x2d\x42\x26\x26\x24\x28\x6c\x28\x62\x46\x29\x29\x5b\x6c\x28\x34\x78\x29\x5d\x28\x29\x2c\x24\x28\x6b\x28\x29\x7b\x64\x20\x32\x39\x3d\x6c\x3b\x24\x28\x32\x39\x28\x62\x47\x29\x29\x5b\x32\x39\x28\x31\x75\x29\x5d\x28\x32\x39\x28\x62\x48\x29\x29\x3b\x64\x20\x35\x37\x3d\x37\x73\x20\x62\x49\x28\x29\x2c\x35\x6b\x3d\x35\x37\x5b\x5c\x27\x62\x4a\x5c\x27\x5d\x28\x29\x2b\x42\x2c\x36\x30\x3d\x35\x37\x5b\x5c\x27\x62\x4b\x5c\x27\x5d\x28\x29\x2c\x37\x42\x3d\x28\x28\x5c\x27\x5c\x27\x2b\x35\x6b\x29\x5b\x32\x39\x28\x31\x59\x29\x5d\x3c\x33\x48\x3f\x5c\x27\x30\x5c\x27\x3a\x5c\x27\x5c\x27\x29\x2b\x35\x6b\x2b\x5c\x27\x2f\x5c\x27\x2b\x28\x28\x5c\x27\x5c\x27\x2b\x36\x30\x29\x5b\x5c\x27\x34\x71\x5c\x27\x5d\x3c\x33\x48\x3f\x5c\x27\x30\x5c\x27\x3a\x5c\x27\x5c\x27\x29\x2b\x36\x30\x2b\x5c\x27\x2f\x5c\x27\x2b\x35\x37\x5b\x32\x39\x28\x65\x35\x29\x5d\x28\x29\x3b\x24\x28\x5c\x27\x2e\x66\x39\x5c\x27\x29\x5b\x5c\x27\x38\x69\x5c\x27\x5d\x28\x37\x42\x29\x2c\x24\x28\x32\x39\x28\x69\x4a\x29\x29\x5b\x32\x39\x28\x31\x7a\x29\x5d\x28\x6b\x28\x29\x7b\x32\x76\x5b\x5c\x27\x39\x36\x5c\x27\x5d\x28\x29\x7d\x29\x7d\x29\x2c\x38\x4b\x28\x32\x6f\x29\x5b\x6c\x28\x69\x49\x29\x5d\x28\x6b\x28\x33\x61\x29\x7b\x64\x20\x31\x5a\x3d\x6c\x2c\x37\x48\x3d\x33\x61\x28\x31\x5a\x28\x69\x48\x29\x29\x2c\x35\x53\x3d\x33\x61\x28\x31\x5a\x28\x69\x47\x29\x29\x2c\x37\x72\x3d\x33\x61\x28\x31\x5a\x28\x69\x46\x29\x29\x3b\x35\x53\x5b\x31\x5a\x28\x31\x7a\x29\x5d\x28\x6b\x28\x37\x6e\x29\x7b\x64\x20\x33\x62\x3d\x31\x5a\x3b\x37\x6e\x5b\x33\x62\x28\x37\x69\x29\x5d\x28\x29\x2c\x35\x53\x5b\x5c\x27\x61\x6d\x5c\x27\x5d\x28\x33\x62\x28\x33\x38\x29\x29\x2c\x37\x48\x5b\x33\x62\x28\x35\x33\x29\x5d\x28\x33\x62\x28\x33\x38\x29\x29\x7d\x29\x2c\x37\x72\x5b\x31\x5a\x28\x31\x7a\x29\x5d\x28\x6b\x28\x37\x47\x29\x7b\x64\x20\x32\x4f\x3d\x31\x5a\x3b\x37\x47\x5b\x32\x4f\x28\x37\x69\x29\x5d\x28\x29\x2c\x33\x61\x28\x68\x29\x5b\x32\x4f\x28\x35\x33\x29\x5d\x28\x32\x4f\x28\x33\x38\x29\x29\x5b\x5c\x27\x69\x45\x5c\x27\x5d\x28\x5c\x27\x49\x5c\x27\x29\x5b\x32\x4f\x28\x35\x33\x29\x5d\x28\x32\x4f\x28\x33\x38\x29\x29\x7d\x29\x7d\x29\x2c\x24\x28\x6b\x28\x29\x7b\x64\x20\x7a\x3d\x6c\x3b\x24\x28\x7a\x28\x69\x44\x29\x29\x5b\x7a\x28\x31\x45\x29\x5d\x28\x29\x5b\x7a\x28\x31\x75\x29\x5d\x28\x7a\x28\x69\x43\x29\x29\x2c\x24\x28\x7a\x28\x69\x42\x29\x29\x5b\x7a\x28\x31\x45\x29\x5d\x28\x29\x5b\x7a\x28\x31\x75\x29\x5d\x28\x7a\x28\x69\x41\x29\x29\x2c\x24\x28\x7a\x28\x69\x79\x29\x29\x5b\x7a\x28\x31\x45\x29\x5d\x28\x29\x5b\x7a\x28\x31\x75\x29\x5d\x28\x7a\x28\x69\x6d\x29\x29\x2c\x24\x28\x7a\x28\x69\x78\x29\x29\x5b\x7a\x28\x31\x45\x29\x5d\x28\x29\x5b\x5c\x27\x32\x78\x5c\x27\x5d\x28\x7a\x28\x69\x77\x29\x29\x2c\x24\x28\x5c\x27\x23\x31\x49\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x32\x29\x5c\x5c\x31\x4d\x2e\x45\x2d\x31\x48\x5c\x27\x29\x5b\x7a\x28\x31\x45\x29\x5d\x28\x29\x5b\x5c\x27\x32\x78\x5c\x27\x5d\x28\x7a\x28\x69\x76\x29\x29\x2c\x24\x28\x5c\x27\x23\x31\x49\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x33\x29\x5c\x5c\x31\x4d\x2e\x45\x2d\x31\x48\x5c\x27\x29\x5b\x5c\x27\x34\x75\x5c\x27\x5d\x28\x29\x5b\x5c\x27\x32\x78\x5c\x27\x5d\x28\x5c\x27\x2e\x2d\x31\x32\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x33\x47\x2e\x34\x73\x2d\x37\x51\x5c\x27\x29\x2c\x24\x28\x7a\x28\x69\x75\x29\x29\x5b\x5c\x27\x34\x75\x5c\x27\x5d\x28\x29\x5b\x7a\x28\x31\x75\x29\x5d\x28\x5c\x27\x2e\x2d\x31\x32\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x33\x47\x2e\x34\x47\x2d\x31\x47\x5c\x27\x29\x2c\x24\x28\x7a\x28\x69\x74\x29\x29\x5b\x7a\x28\x31\x45\x29\x5d\x28\x29\x5b\x5c\x27\x32\x78\x5c\x27\x5d\x28\x7a\x28\x69\x72\x29\x29\x2c\x24\x28\x7a\x28\x69\x71\x29\x29\x5b\x7a\x28\x31\x45\x29\x5d\x28\x29\x5b\x5c\x27\x32\x78\x5c\x27\x5d\x28\x7a\x28\x69\x70\x29\x29\x2c\x24\x28\x5c\x27\x23\x31\x49\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x32\x29\x5c\x5c\x31\x4d\x2e\x45\x2d\x33\x7a\x5c\x27\x29\x5b\x5c\x27\x34\x75\x5c\x27\x5d\x28\x29\x5b\x7a\x28\x31\x75\x29\x5d\x28\x7a\x28\x69\x6f\x29\x29\x2c\x24\x28\x7a\x28\x69\x4b\x29\x29\x5b\x7a\x28\x31\x45\x29\x5d\x28\x29\x5b\x7a\x28\x31\x75\x29\x5d\x28\x5c\x27\x2e\x2d\x31\x32\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x33\x43\x2e\x34\x73\x2d\x37\x51\x2d\x33\x42\x5c\x27\x29\x2c\x24\x28\x5c\x27\x23\x31\x49\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x34\x29\x5c\x5c\x31\x4d\x2e\x45\x2d\x33\x7a\x5c\x27\x29\x5b\x7a\x28\x31\x45\x29\x5d\x28\x29\x5b\x7a\x28\x31\x75\x29\x5d\x28\x7a\x28\x69\x7a\x29\x29\x2c\x24\x28\x5c\x27\x23\x31\x49\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x35\x29\x5c\x5c\x31\x4d\x2e\x45\x2d\x33\x7a\x5c\x27\x29\x5b\x7a\x28\x31\x45\x29\x5d\x28\x29\x5b\x7a\x28\x31\x75\x29\x5d\x28\x7a\x28\x69\x4c\x29\x29\x7d\x29\x2c\x32\x76\x5b\x6c\x28\x36\x57\x29\x5d\x5b\x6c\x28\x32\x37\x29\x5d\x5b\x6c\x28\x32\x6a\x29\x5d\x28\x5c\x27\x2f\x70\x2f\x33\x79\x2e\x31\x34\x5c\x27\x29\x3e\x2d\x42\x26\x26\x28\x32\x6f\x5b\x6c\x28\x34\x67\x29\x5d\x3d\x6c\x28\x69\x5a\x29\x2c\x24\x28\x6c\x28\x6a\x39\x29\x29\x5b\x6c\x28\x54\x29\x5d\x28\x5c\x27\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x34\x6e\x2d\x31\x6c\x2d\x33\x79\x5c\x5c\x34\x6e\x3e\x3c\x2f\x78\x3e\x3c\x31\x69\x3e\x2e\x2d\x31\x6c\x5c\x5c\x32\x4e\x5c\x5c\x6d\x7b\x33\x76\x3a\x5c\x5c\x6a\x38\x3b\x61\x43\x3a\x5c\x5c\x6a\x37\x3b\x7d\x2e\x2d\x31\x6c\x5c\x5c\x6d\x2e\x2d\x31\x6c\x2d\x6a\x36\x2c\x78\x23\x34\x72\x2d\x31\x53\x2c\x2e\x38\x38\x5c\x5c\x6d\x2e\x32\x30\x2d\x4c\x5c\x5c\x37\x37\x2e\x4c\x2d\x32\x77\x2c\x5c\x5c\x6d\x2e\x6a\x35\x2d\x4c\x2d\x6a\x34\x5c\x5c\x6d\x7b\x5c\x5c\x36\x66\x3a\x5c\x5c\x37\x6c\x21\x31\x4f\x3b\x5c\x5c\x6d\x7d\x2e\x32\x30\x5c\x5c\x6d\x23\x33\x77\x2d\x31\x53\x2c\x5c\x5c\x6d\x2e\x38\x38\x5c\x5c\x6d\x23\x33\x77\x2d\x31\x53\x5c\x5c\x6d\x7b\x5c\x5c\x6a\x33\x3a\x61\x78\x25\x3b\x33\x78\x3a\x36\x64\x3b\x31\x52\x2d\x32\x47\x3a\x5c\x5c\x6a\x32\x25\x3b\x5c\x5c\x6d\x7d\x3c\x2f\x31\x69\x3e\x5c\x27\x29\x2c\x24\x28\x6c\x28\x6a\x31\x29\x29\x5b\x6c\x28\x6a\x30\x29\x5d\x28\x6c\x28\x69\x59\x29\x29\x29\x2c\x32\x76\x5b\x6c\x28\x36\x57\x29\x5d\x5b\x6c\x28\x32\x37\x29\x5d\x5b\x6c\x28\x32\x6a\x29\x5d\x28\x6c\x28\x38\x35\x29\x29\x3e\x2d\x42\x26\x26\x28\x32\x6f\x5b\x6c\x28\x34\x67\x29\x5d\x3d\x6c\x28\x69\x4e\x29\x2c\x24\x28\x5c\x27\x2e\x32\x30\x2d\x4c\x5c\x5c\x6d\x2e\x4c\x2d\x32\x66\x5c\x27\x29\x5b\x5c\x27\x31\x34\x5c\x27\x5d\x28\x6c\x28\x69\x58\x29\x29\x29\x7d\x29\x7d\x6b\x20\x32\x58\x28\x29\x7b\x64\x20\x61\x30\x3d\x5b\x5c\x27\x5c\x5c\x6d\x3c\x32\x75\x5c\x5c\x31\x41\x3d\x5c\x5c\x33\x56\x3a\x2f\x2f\x69\x57\x2e\x69\x56\x2e\x31\x43\x2f\x69\x55\x3f\x37\x79\x3d\x69\x54\x3a\x69\x53\x40\x37\x75\x3b\x69\x52\x26\x33\x76\x3d\x69\x51\x5c\x5c\x6a\x5c\x5c\x69\x50\x3d\x5c\x5c\x69\x4f\x5c\x5c\x6a\x3e\x3c\x31\x69\x3e\x68\x72\x5c\x5c\x6d\x7b\x5c\x5c\x37\x6d\x3a\x30\x21\x31\x4f\x3b\x5c\x5c\x6d\x7d\x5c\x5c\x38\x6e\x5c\x5c\x6d\x7b\x5c\x5c\x69\x4d\x3a\x5c\x5c\x69\x6b\x21\x31\x4f\x3b\x5c\x5c\x6d\x7d\x5c\x5c\x6d\x2a\x5c\x5c\x6d\x7b\x5c\x5c\x34\x4b\x2d\x37\x79\x3a\x5c\x5c\x6d\x5c\x5c\x68\x54\x5c\x5c\x6a\x2c\x5c\x5c\x69\x6a\x2d\x68\x51\x3b\x5c\x5c\x34\x4b\x2d\x37\x57\x3a\x37\x75\x3b\x5c\x5c\x68\x50\x2d\x68\x4f\x3a\x33\x57\x2d\x68\x4e\x3b\x37\x62\x3a\x30\x3b\x37\x46\x3a\x30\x3b\x5c\x5c\x68\x4d\x2d\x68\x4c\x3a\x36\x64\x3b\x5c\x5c\x37\x38\x3a\x23\x37\x44\x3b\x5c\x5c\x6d\x7d\x5c\x5c\x68\x4b\x5c\x5c\x6d\x7b\x5c\x5c\x34\x4b\x2d\x37\x57\x3a\x5c\x5c\x68\x4a\x3b\x5c\x5c\x37\x38\x3a\x23\x68\x49\x3b\x5c\x5c\x34\x4b\x2d\x33\x54\x3a\x68\x48\x3b\x5c\x5c\x36\x66\x3a\x36\x67\x3b\x5c\x5c\x37\x6d\x3a\x30\x5c\x5c\x34\x35\x5c\x5c\x68\x46\x3b\x7d\x3c\x2f\x31\x69\x3e\x5c\x5c\x6d\x3c\x78\x5c\x5c\x38\x61\x3d\x5c\x5c\x68\x76\x5c\x5c\x6a\x5c\x5c\x32\x65\x3d\x5c\x5c\x68\x45\x3a\x68\x44\x3b\x37\x70\x3a\x23\x68\x43\x3b\x37\x49\x2d\x34\x79\x3a\x68\x42\x3b\x32\x32\x2d\x68\x41\x3a\x68\x7a\x3b\x5c\x5c\x6a\x3e\x3c\x78\x5c\x5c\x32\x65\x3d\x5c\x5c\x68\x79\x3a\x68\x78\x3b\x32\x47\x3a\x68\x77\x3b\x31\x52\x2d\x32\x47\x3a\x38\x30\x25\x3b\x37\x70\x3a\x68\x52\x3b\x37\x46\x3a\x68\x47\x3b\x33\x57\x2d\x68\x53\x3a\x69\x36\x3b\x33\x57\x3a\x35\x75\x5c\x5c\x38\x65\x5c\x5c\x6d\x23\x38\x64\x3b\x5c\x5c\x6a\x3e\x3c\x36\x72\x5c\x5c\x32\x65\x3d\x5c\x5c\x69\x69\x3a\x23\x37\x44\x3b\x32\x47\x3a\x37\x4a\x3b\x34\x79\x3a\x37\x4a\x3b\x33\x76\x3a\x36\x67\x3b\x37\x62\x3a\x30\x5c\x5c\x69\x68\x5c\x5c\x69\x67\x5c\x5c\x6a\x5c\x5c\x69\x65\x3d\x5c\x5c\x33\x56\x3a\x2f\x2f\x33\x6d\x2e\x69\x63\x2e\x69\x62\x2f\x69\x61\x2f\x36\x72\x5c\x5c\x6a\x5c\x5c\x69\x39\x3d\x5c\x5c\x69\x38\x5c\x5c\x34\x35\x5c\x5c\x38\x68\x5c\x5c\x38\x68\x5c\x5c\x6a\x3e\x3c\x69\x37\x5c\x5c\x69\x35\x3d\x5c\x5c\x68\x55\x2e\x39\x5c\x5c\x38\x79\x2e\x69\x34\x2e\x38\x5c\x5c\x69\x33\x2e\x69\x32\x2e\x36\x5c\x5c\x69\x31\x2e\x33\x5c\x5c\x69\x30\x2e\x35\x5c\x5c\x68\x5a\x5c\x5c\x6a\x62\x2e\x39\x5c\x5c\x68\x58\x2e\x68\x57\x2e\x33\x5c\x5c\x34\x35\x5c\x5c\x68\x56\x2e\x32\x2d\x32\x34\x2e\x37\x5c\x5c\x6a\x61\x2e\x31\x2d\x34\x34\x2e\x69\x6c\x2e\x31\x5c\x5c\x38\x79\x2e\x39\x63\x2d\x31\x31\x2e\x37\x2d\x32\x31\x2e\x32\x2d\x34\x32\x2e\x35\x2d\x32\x31\x2e\x32\x2d\x35\x34\x2e\x32\x5c\x5c\x6b\x62\x2e\x36\x5c\x5c\x6b\x34\x5c\x5c\x6b\x37\x2d\x6b\x39\x2d\x33\x2e\x36\x2d\x6b\x66\x2e\x6b\x67\x5c\x5c\x6b\x68\x2e\x34\x63\x2d\x31\x30\x2e\x37\x5c\x5c\x34\x35\x2d\x31\x39\x2e\x31\x2d\x38\x2e\x31\x2d\x31\x39\x2e\x31\x2d\x31\x38\x2e\x6b\x6a\x2e\x34\x2d\x31\x38\x2e\x34\x5c\x5c\x36\x77\x2e\x31\x2d\x31\x38\x2e\x34\x5c\x5c\x36\x77\x2e\x31\x5c\x5c\x6b\x69\x2e\x31\x5c\x5c\x36\x77\x2e\x31\x5c\x5c\x36\x73\x2e\x34\x2d\x38\x2e\x34\x5c\x5c\x36\x73\x2e\x34\x2d\x31\x39\x2e\x31\x5c\x5c\x36\x73\x2e\x34\x7a\x5c\x5c\x6a\x2f\x3e\x3c\x2f\x36\x72\x3e\x3c\x70\x3e\x3c\x62\x3e\x6b\x65\x5c\x5c\x6b\x64\x5c\x5c\x6d\x3c\x2f\x62\x3e\x6b\x63\x5c\x5c\x39\x62\x5c\x5c\x37\x4b\x5c\x5c\x6b\x61\x5c\x5c\x6b\x33\x5c\x5c\x6b\x38\x2e\x3c\x62\x72\x3e\x3c\x38\x4a\x3e\x23\x6b\x36\x3c\x2f\x38\x4a\x3e\x3c\x78\x5c\x5c\x38\x61\x3d\x5c\x5c\x6b\x35\x5c\x5c\x6a\x5c\x5c\x32\x65\x3d\x5c\x5c\x6b\x6b\x3a\x6b\x6c\x3b\x5c\x5c\x6a\x3e\x3c\x2f\x78\x3e\x3c\x2f\x70\x3e\x3c\x62\x72\x3e\x3c\x68\x72\x5c\x5c\x32\x65\x3d\x5c\x5c\x6b\x72\x3a\x30\x3b\x33\x57\x2d\x37\x54\x3a\x35\x75\x5c\x5c\x38\x65\x5c\x5c\x6d\x23\x38\x64\x3b\x5c\x5c\x6a\x3e\x3c\x62\x72\x3e\x3c\x61\x5c\x5c\x31\x41\x3d\x5c\x5c\x33\x56\x3a\x2f\x2f\x33\x6d\x2e\x33\x52\x2e\x31\x43\x5c\x27\x2c\x5c\x27\x2f\x2f\x34\x2e\x62\x70\x2e\x39\x65\x2e\x31\x43\x2f\x2d\x6b\x6d\x2f\x6b\x71\x2d\x6b\x70\x2f\x6b\x6f\x2f\x6b\x6e\x2f\x6b\x32\x2d\x72\x2f\x38\x78\x2e\x37\x7a\x5c\x27\x2c\x5c\x27\x31\x79\x5c\x27\x2c\x5c\x27\x61\x4a\x5c\x27\x2c\x5c\x27\x23\x2d\x31\x32\x5c\x27\x2c\x5c\x27\x65\x34\x5c\x27\x2c\x5c\x27\x34\x42\x5c\x27\x2c\x5c\x27\x35\x55\x5c\x27\x2c\x5c\x27\x2f\x32\x62\x2e\x5c\x27\x2c\x5c\x27\x3c\x47\x3e\x3c\x48\x5c\x5c\x79\x3d\x5c\x5c\x6a\x43\x2d\x35\x38\x5c\x5c\x6a\x3e\x3c\x61\x5c\x5c\x6b\x30\x3d\x5c\x5c\x6a\x5c\x27\x2c\x5c\x27\x37\x65\x5c\x27\x2c\x5c\x27\x4c\x2d\x38\x34\x5c\x27\x2c\x5c\x27\x2e\x2d\x31\x32\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x33\x43\x2e\x34\x73\x2d\x31\x47\x2d\x33\x42\x5c\x27\x2c\x5c\x27\x5c\x5c\x6d\x26\x23\x6a\x7a\x3b\x5c\x5c\x6a\x79\x5c\x5c\x6a\x78\x5c\x5c\x6d\x3c\x61\x5c\x5c\x31\x41\x3d\x5c\x5c\x33\x56\x3a\x2f\x2f\x33\x6d\x2e\x33\x52\x2e\x31\x43\x5c\x27\x2c\x5c\x27\x3c\x2f\x68\x32\x3e\x5c\x27\x2c\x5c\x27\x31\x69\x5c\x27\x2c\x5c\x27\x5c\x5c\x6a\x3e\x3c\x32\x67\x5c\x5c\x61\x73\x3d\x5c\x5c\x6a\x5c\x27\x2c\x5c\x27\x2e\x4c\x2d\x32\x66\x5c\x5c\x6a\x77\x5c\x27\x2c\x5c\x27\x23\x32\x51\x2d\x6b\x31\x5c\x5c\x6d\x2e\x34\x70\x2d\x32\x79\x5c\x27\x2c\x5c\x27\x39\x70\x5c\x27\x2c\x5c\x27\x2e\x34\x54\x2d\x31\x47\x5c\x27\x2c\x5c\x27\x23\x31\x49\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x31\x29\x5c\x5c\x31\x4d\x2e\x45\x2d\x31\x48\x5c\x27\x2c\x5c\x27\x2e\x36\x53\x5c\x27\x2c\x5c\x27\x2e\x6a\x76\x5c\x27\x2c\x5c\x27\x23\x32\x51\x2d\x6a\x75\x5c\x5c\x6d\x2e\x34\x70\x2d\x32\x79\x5c\x27\x2c\x5c\x27\x61\x48\x5c\x27\x2c\x5c\x27\x35\x54\x5c\x27\x2c\x5c\x27\x6a\x74\x5c\x27\x2c\x5c\x27\x6a\x73\x5c\x27\x2c\x5c\x27\x32\x32\x5c\x27\x2c\x5c\x27\x2e\x32\x54\x5c\x5c\x4b\x3a\x31\x48\x2d\x31\x62\x5c\x5c\x32\x4e\x5c\x27\x2c\x5c\x27\x3c\x62\x72\x3e\x5c\x27\x2c\x5c\x27\x2e\x2d\x31\x32\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x33\x43\x2e\x34\x47\x2d\x31\x47\x2d\x33\x42\x5c\x27\x2c\x5c\x27\x34\x6c\x5c\x27\x2c\x5c\x27\x2e\x34\x4e\x2e\x6a\x72\x5c\x27\x2c\x5c\x27\x2e\x31\x4c\x2d\x31\x77\x2d\x35\x41\x2d\x35\x72\x5c\x27\x2c\x5c\x27\x2e\x2d\x31\x6c\x2d\x33\x79\x5c\x27\x2c\x5c\x27\x5c\x5c\x6a\x71\x3a\x6a\x6f\x5c\x27\x2c\x5c\x27\x2e\x6a\x64\x2d\x37\x54\x5c\x27\x2c\x5c\x27\x6a\x6e\x5c\x27\x2c\x5c\x27\x2e\x6a\x6d\x5c\x27\x2c\x5c\x27\x3c\x49\x5c\x5c\x79\x3d\x5c\x5c\x6a\x6c\x2d\x34\x70\x5c\x5c\x6a\x3e\x5c\x27\x2c\x5c\x27\x2e\x32\x30\x2d\x4c\x5c\x5c\x6d\x2e\x4c\x2d\x32\x66\x5c\x27\x2c\x5c\x27\x38\x58\x5c\x27\x2c\x5c\x27\x2f\x31\x79\x2f\x32\x6e\x2f\x5c\x27\x2c\x5c\x27\x39\x71\x5c\x27\x2c\x5c\x27\x2e\x6a\x6b\x5c\x27\x2c\x5c\x27\x2e\x2d\x31\x32\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x33\x47\x2e\x34\x47\x2d\x37\x41\x5c\x27\x2c\x5c\x27\x2e\x2d\x31\x32\x2d\x45\x5c\x27\x2c\x5c\x27\x3c\x78\x3e\x3c\x2f\x78\x3e\x5c\x27\x2c\x5c\x27\x6a\x6a\x5c\x27\x2c\x5c\x27\x2e\x2d\x31\x6c\x5c\x5c\x6d\x2e\x2d\x31\x6c\x2d\x45\x5c\x27\x2c\x5c\x27\x31\x37\x5c\x27\x2c\x5c\x27\x5c\x5c\x6a\x3e\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x37\x32\x2d\x32\x79\x5c\x5c\x6a\x3e\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x32\x33\x2d\x32\x72\x2d\x32\x44\x5c\x5c\x6a\x3e\x3c\x61\x5c\x5c\x79\x3d\x5c\x5c\x32\x33\x2d\x32\x72\x2d\x32\x75\x5c\x5c\x6a\x5c\x5c\x31\x41\x3d\x5c\x5c\x6a\x5c\x27\x2c\x5c\x27\x35\x70\x5c\x5c\x31\x63\x5c\x5c\x6a\x69\x5c\x5c\x6a\x68\x3a\x6a\x67\x5c\x27\x2c\x5c\x27\x2f\x2f\x6a\x66\x2e\x6a\x65\x2e\x31\x43\x2f\x32\x67\x2f\x6a\x41\x2e\x6a\x70\x5c\x27\x2c\x5c\x27\x5c\x5c\x6a\x5c\x5c\x31\x41\x3d\x5c\x5c\x6a\x5c\x27\x2c\x5c\x27\x32\x7a\x5c\x27\x2c\x5c\x27\x38\x32\x5c\x27\x2c\x5c\x27\x2e\x2d\x32\x74\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x55\x5c\x5c\x4b\x2e\x6a\x42\x2d\x36\x44\x5c\x27\x2c\x5c\x27\x2e\x38\x77\x2d\x34\x48\x5c\x27\x2c\x5c\x27\x61\x38\x5c\x27\x2c\x5c\x27\x2e\x6a\x50\x2d\x49\x5c\x5c\x6d\x3e\x5c\x5c\x32\x4e\x5c\x27\x2c\x5c\x27\x32\x75\x5c\x27\x2c\x5c\x27\x38\x49\x5c\x27\x2c\x5c\x27\x6a\x5a\x5c\x27\x2c\x5c\x27\x36\x75\x5c\x27\x2c\x5c\x27\x38\x47\x5c\x27\x2c\x5c\x27\x2e\x6a\x59\x5c\x5c\x32\x4e\x2c\x5c\x5c\x32\x4e\x2e\x62\x2d\x32\x6e\x5c\x27\x2c\x5c\x27\x23\x31\x49\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x33\x29\x5c\x5c\x31\x4d\x2e\x45\x2d\x33\x7a\x5c\x27\x2c\x5c\x27\x59\x2e\x31\x4c\x2d\x31\x77\x2d\x35\x30\x5c\x27\x2c\x5c\x27\x2e\x2d\x31\x32\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x33\x43\x2e\x31\x32\x2d\x31\x47\x2d\x33\x42\x5c\x27\x2c\x5c\x27\x28\x33\x45\x3a\x2f\x2f\x5b\x5e\x2f\x5d\x2b\x29\x2f\x31\x79\x2f\x32\x6e\x2f\x28\x5b\x5e\x2f\x3f\x26\x24\x5d\x2b\x29\x5c\x27\x2c\x5c\x27\x6a\x58\x5c\x27\x2c\x5c\x27\x35\x6d\x5c\x27\x2c\x5c\x27\x2e\x38\x78\x2d\x32\x72\x2d\x35\x38\x5c\x5c\x6a\x57\x5c\x27\x2c\x5c\x27\x38\x76\x5c\x27\x2c\x5c\x27\x37\x45\x5c\x27\x2c\x5c\x27\x2e\x35\x6e\x2d\x6a\x56\x5c\x27\x2c\x5c\x27\x38\x69\x5c\x27\x2c\x5c\x27\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x38\x6c\x2d\x6a\x55\x5c\x5c\x6a\x54\x5c\x5c\x6a\x3e\x3c\x68\x32\x3e\x39\x53\x5c\x5c\x36\x50\x3c\x2f\x68\x32\x3e\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x34\x51\x2d\x6a\x53\x2d\x32\x44\x5c\x5c\x6a\x3e\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x6a\x52\x5c\x5c\x6a\x2f\x3e\x3c\x78\x5c\x5c\x32\x65\x3d\x5c\x5c\x6a\x51\x3a\x5c\x5c\x6a\x4f\x3b\x5c\x5c\x6a\x2f\x3e\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x34\x51\x2d\x6a\x44\x2d\x6a\x4e\x5c\x5c\x6a\x3e\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x34\x51\x2d\x6a\x4d\x5c\x5c\x6a\x3e\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x34\x51\x2d\x6a\x4c\x5c\x5c\x6a\x3e\x6a\x4b\x5c\x5c\x6d\x3a\x3c\x48\x5c\x5c\x79\x3d\x5c\x5c\x38\x6a\x5c\x5c\x6a\x2f\x3e\x3c\x2f\x78\x3e\x3c\x68\x34\x3e\x6a\x4a\x5c\x5c\x6a\x49\x5c\x5c\x6d\x3a\x5c\x5c\x6d\x3c\x2f\x68\x34\x3e\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x6a\x48\x5c\x5c\x6a\x3e\x6a\x47\x5c\x5c\x6a\x46\x5c\x5c\x6d\x3c\x48\x5c\x5c\x79\x3d\x5c\x5c\x6a\x45\x5c\x5c\x6a\x2f\x3e\x5c\x5c\x34\x36\x28\x73\x29\x5c\x5c\x68\x59\x5c\x5c\x68\x75\x5c\x5c\x36\x50\x2e\x3c\x2f\x78\x3e\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x38\x6c\x2d\x66\x4c\x5c\x5c\x6a\x3e\x68\x73\x3a\x5c\x5c\x6d\x3c\x48\x5c\x5c\x79\x3d\x5c\x5c\x38\x6a\x5c\x5c\x6a\x2f\x3e\x3c\x2f\x78\x3e\x3c\x2f\x78\x3e\x3c\x61\x5c\x5c\x79\x3d\x5c\x5c\x66\x68\x5c\x5c\x6a\x5c\x5c\x31\x41\x3d\x5c\x5c\x6a\x2f\x70\x2f\x33\x79\x2e\x31\x34\x5c\x5c\x6a\x3e\x66\x67\x5c\x5c\x37\x4b\x5c\x5c\x66\x66\x3c\x2f\x61\x3e\x3c\x2f\x78\x3e\x3c\x2f\x78\x3e\x3c\x2f\x78\x3e\x3c\x31\x69\x3e\x2e\x32\x30\x2d\x4c\x5c\x5c\x37\x37\x2e\x4c\x2d\x32\x77\x5c\x5c\x6d\x7b\x5c\x5c\x36\x66\x3a\x5c\x5c\x37\x6c\x21\x31\x4f\x3b\x5c\x5c\x6d\x7d\x3c\x2f\x31\x69\x3e\x5c\x27\x2c\x5c\x27\x4c\x2d\x35\x4f\x5c\x27\x2c\x5c\x27\x3c\x68\x35\x3e\x5c\x27\x2c\x5c\x27\x66\x65\x5c\x27\x2c\x5c\x27\x33\x45\x3a\x2f\x2f\x33\x6d\x2e\x33\x52\x2e\x31\x43\x2f\x5c\x27\x2c\x5c\x27\x38\x42\x5c\x27\x2c\x5c\x27\x5c\x5c\x66\x64\x5c\x5c\x66\x63\x3a\x66\x62\x5c\x27\x2c\x5c\x27\x2e\x34\x54\x2d\x34\x48\x5c\x27\x2c\x5c\x27\x2e\x2d\x31\x32\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x33\x43\x2e\x34\x47\x2d\x37\x41\x2d\x33\x42\x5c\x27\x2c\x5c\x27\x2f\x32\x50\x2f\x31\x71\x2f\x32\x62\x3f\x33\x64\x3d\x33\x73\x2d\x69\x6e\x2d\x35\x4d\x26\x31\x52\x2d\x32\x69\x3d\x5c\x27\x2c\x5c\x27\x2e\x37\x45\x5c\x27\x2c\x5c\x27\x38\x67\x5c\x27\x2c\x5c\x27\x66\x61\x5c\x27\x2c\x5c\x27\x2f\x68\x74\x2d\x63\x2f\x5c\x27\x2c\x5c\x27\x2e\x66\x38\x5c\x27\x2c\x5c\x27\x66\x36\x5c\x27\x2c\x5c\x27\x23\x35\x5a\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x32\x29\x5c\x27\x2c\x5c\x27\x33\x41\x5c\x27\x2c\x5c\x27\x2e\x37\x78\x5c\x27\x2c\x5c\x27\x3c\x48\x3e\x3c\x2f\x48\x3e\x5c\x27\x2c\x5c\x27\x65\x57\x5c\x27\x2c\x5c\x27\x31\x70\x2d\x35\x69\x5c\x27\x2c\x5c\x27\x2f\x32\x50\x2f\x31\x71\x2f\x32\x62\x2f\x5c\x27\x2c\x5c\x27\x23\x31\x49\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x31\x29\x5c\x5c\x31\x4d\x2e\x45\x2d\x33\x7a\x5c\x27\x2c\x5c\x27\x2e\x37\x6f\x5c\x27\x2c\x5c\x27\x3c\x47\x5c\x5c\x79\x3d\x5c\x5c\x37\x67\x2d\x32\x30\x5c\x5c\x34\x36\x2d\x5c\x27\x2c\x5c\x27\x2e\x66\x35\x5c\x27\x2c\x5c\x27\x32\x73\x5c\x27\x2c\x5c\x27\x37\x74\x5c\x27\x2c\x5c\x27\x23\x31\x70\x5c\x27\x2c\x5c\x27\x66\x34\x2d\x32\x47\x5c\x27\x2c\x5c\x27\x66\x33\x5c\x27\x2c\x5c\x27\x39\x34\x5c\x27\x2c\x5c\x27\x23\x2d\x32\x74\x5c\x27\x2c\x5c\x27\x66\x32\x5c\x27\x2c\x5c\x27\x5c\x5c\x6a\x5c\x5c\x66\x31\x3d\x5c\x5c\x6a\x5c\x27\x2c\x5c\x27\x33\x6f\x3a\x33\x70\x28\x5c\x5c\x66\x30\x2f\x5c\x5c\x6a\x29\x5c\x27\x2c\x5c\x27\x23\x35\x5a\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x33\x29\x5c\x27\x2c\x5c\x27\x59\x2e\x4f\x2d\x34\x46\x5c\x27\x2c\x5c\x27\x3a\x65\x5a\x5c\x27\x2c\x5c\x27\x38\x66\x5c\x27\x2c\x5c\x27\x35\x51\x5c\x27\x2c\x5c\x27\x65\x59\x5c\x27\x2c\x5c\x27\x2e\x2d\x31\x6c\x2d\x65\x58\x5c\x27\x2c\x5c\x27\x39\x46\x5c\x27\x2c\x5c\x27\x39\x52\x5c\x27\x2c\x5c\x27\x66\x69\x5c\x27\x2c\x5c\x27\x33\x6a\x2d\x32\x51\x5c\x27\x2c\x5c\x27\x66\x37\x5c\x27\x2c\x5c\x27\x38\x39\x5c\x27\x2c\x5c\x27\x66\x6a\x5c\x27\x2c\x5c\x27\x66\x79\x5c\x27\x2c\x5c\x27\x37\x64\x5c\x27\x2c\x5c\x27\x2e\x33\x69\x2d\x37\x65\x5c\x27\x2c\x5c\x27\x37\x66\x5c\x27\x2c\x5c\x27\x23\x31\x49\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x35\x29\x5c\x5c\x31\x4d\x2e\x45\x2d\x31\x48\x5c\x27\x2c\x5c\x27\x23\x35\x5a\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x31\x29\x5c\x27\x2c\x5c\x27\x36\x4e\x5c\x27\x2c\x5c\x27\x2e\x66\x49\x5c\x27\x2c\x5c\x27\x2e\x66\x48\x5c\x27\x2c\x5c\x27\x35\x70\x5c\x27\x2c\x5c\x27\x2e\x31\x4c\x2d\x31\x77\x2d\x31\x47\x2c\x2e\x31\x4c\x2d\x31\x77\x2d\x35\x30\x2c\x2e\x4f\x2d\x36\x41\x2c\x2e\x4f\x2d\x33\x6c\x2c\x2e\x4f\x2d\x39\x5a\x2c\x2e\x4f\x2d\x39\x33\x2c\x2e\x4f\x2d\x34\x46\x5c\x27\x2c\x5c\x27\x49\x2e\x32\x54\x5c\x5c\x4b\x5c\x27\x2c\x5c\x27\x59\x2e\x31\x4c\x2d\x31\x77\x2d\x31\x47\x5c\x27\x2c\x5c\x27\x32\x68\x5c\x27\x2c\x5c\x27\x2f\x66\x47\x2f\x66\x46\x2f\x66\x45\x2d\x61\x75\x2d\x66\x44\x2e\x31\x34\x5c\x27\x2c\x5c\x27\x36\x37\x5c\x27\x2c\x5c\x27\x59\x5c\x27\x2c\x5c\x27\x34\x45\x5c\x27\x2c\x5c\x27\x2e\x39\x72\x2d\x39\x6a\x5c\x5c\x6d\x2e\x2d\x66\x43\x2d\x31\x77\x5c\x27\x2c\x5c\x27\x2e\x66\x42\x2d\x33\x79\x2d\x32\x44\x5c\x5c\x6d\x2e\x61\x65\x5c\x27\x2c\x5c\x27\x66\x41\x24\x66\x7a\x5c\x27\x2c\x5c\x27\x3c\x49\x3e\x3c\x2f\x49\x3e\x5c\x27\x2c\x5c\x27\x66\x78\x5c\x27\x2c\x5c\x27\x61\x6c\x5c\x27\x2c\x5c\x27\x5b\x3f\x26\x5d\x71\x3d\x5c\x27\x2c\x5c\x27\x61\x6d\x5c\x27\x2c\x5c\x27\x34\x42\x2d\x31\x70\x5c\x27\x2c\x5c\x27\x3c\x32\x67\x5c\x5c\x79\x3d\x5c\x5c\x32\x33\x2d\x66\x6c\x5c\x5c\x6a\x5c\x5c\x61\x73\x3d\x5c\x5c\x6a\x5c\x27\x2c\x5c\x27\x2e\x34\x54\x2d\x33\x54\x5c\x27\x2c\x5c\x27\x32\x67\x3a\x31\x48\x5c\x27\x2c\x5c\x27\x66\x77\x5c\x27\x2c\x5c\x27\x2e\x66\x76\x5c\x27\x2c\x5c\x27\x2e\x33\x69\x2d\x66\x75\x5c\x27\x2c\x5c\x27\x2e\x4f\x2d\x66\x74\x5c\x27\x2c\x5c\x27\x2e\x66\x73\x5c\x27\x2c\x5c\x27\x3c\x2f\x39\x58\x3e\x5c\x27\x2c\x5c\x27\x2f\x31\x79\x2f\x3f\x26\x31\x52\x2d\x32\x69\x3d\x5c\x27\x2c\x5c\x27\x66\x72\x5c\x27\x2c\x5c\x27\x3c\x31\x69\x3e\x2e\x33\x77\x2d\x31\x53\x7b\x33\x78\x3a\x37\x31\x7d\x2e\x34\x72\x2d\x31\x53\x7b\x33\x78\x3a\x35\x4f\x7d\x3c\x2f\x31\x69\x3e\x5c\x27\x2c\x5c\x27\x34\x76\x2d\x31\x70\x5c\x27\x2c\x5c\x27\x5c\x5c\x6a\x5c\x5c\x39\x6e\x3d\x5c\x5c\x39\x6f\x5c\x5c\x6a\x3e\x66\x71\x3c\x2f\x61\x3e\x2e\x5c\x27\x2c\x5c\x27\x34\x75\x5c\x27\x2c\x5c\x27\x3c\x2f\x49\x3e\x5c\x27\x2c\x5c\x27\x3c\x49\x5c\x5c\x79\x3d\x5c\x5c\x66\x70\x5c\x5c\x6a\x3e\x5c\x27\x2c\x5c\x27\x3c\x31\x69\x3e\x2e\x33\x77\x2d\x31\x53\x7b\x33\x78\x3a\x35\x4f\x7d\x2e\x34\x72\x2d\x31\x53\x7b\x33\x78\x3a\x37\x31\x7d\x3c\x2f\x31\x69\x3e\x5c\x27\x2c\x5c\x27\x2e\x2d\x31\x32\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x33\x47\x2e\x31\x32\x2d\x31\x47\x5c\x27\x2c\x5c\x27\x36\x7a\x5c\x27\x2c\x5c\x27\x66\x6f\x5c\x27\x2c\x5c\x27\x61\x7a\x5c\x27\x2c\x5c\x27\x48\x2e\x39\x75\x2d\x35\x69\x5c\x27\x2c\x5c\x27\x3c\x2f\x48\x3e\x5c\x27\x2c\x5c\x27\x5c\x5c\x36\x70\x5c\x5c\x66\x6d\x3a\x5c\x5c\x6d\x5c\x27\x2c\x5c\x27\x38\x46\x5c\x27\x2c\x5c\x27\x66\x6b\x5c\x27\x2c\x5c\x27\x3c\x2f\x61\x3e\x5c\x27\x2c\x5c\x27\x2e\x2d\x31\x32\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x33\x47\x2e\x34\x73\x2d\x31\x47\x5c\x27\x2c\x5c\x27\x39\x42\x5c\x27\x2c\x5c\x27\x36\x69\x5c\x27\x2c\x5c\x27\x34\x71\x5c\x27\x2c\x5c\x27\x38\x4f\x5c\x27\x2c\x5c\x27\x3c\x31\x69\x3e\x2e\x33\x77\x2d\x31\x53\x7b\x32\x47\x3a\x61\x78\x25\x7d\x2e\x34\x72\x2d\x31\x53\x7b\x33\x76\x3a\x36\x64\x7d\x3c\x2f\x31\x69\x3e\x5c\x27\x2c\x5c\x27\x36\x6a\x5c\x27\x2c\x5c\x27\x65\x55\x5c\x27\x2c\x5c\x27\x61\x6e\x5c\x27\x2c\x5c\x27\x33\x76\x3a\x65\x76\x2d\x36\x67\x21\x31\x4f\x3b\x65\x54\x3a\x31\x21\x31\x4f\x3b\x61\x43\x3a\x65\x73\x21\x31\x4f\x3b\x65\x72\x3a\x65\x71\x21\x31\x4f\x3b\x32\x32\x2d\x65\x70\x3a\x65\x6f\x21\x31\x4f\x3b\x65\x6e\x3a\x65\x6c\x21\x31\x4f\x5c\x27\x2c\x5c\x27\x2e\x61\x75\x2e\x31\x43\x5c\x27\x2c\x5c\x27\x3e\x47\x5c\x27\x2c\x5c\x27\x65\x6b\x5c\x27\x2c\x5c\x27\x65\x6a\x5c\x27\x2c\x5c\x27\x3c\x2f\x78\x3e\x3c\x2f\x78\x3e\x5c\x27\x2c\x5c\x27\x2e\x34\x54\x2d\x65\x69\x5c\x27\x2c\x5c\x27\x65\x67\x5c\x27\x2c\x5c\x27\x2f\x65\x36\x2d\x63\x2f\x5c\x27\x2c\x5c\x27\x33\x73\x5c\x27\x2c\x5c\x27\x65\x66\x5c\x27\x2c\x5c\x27\x34\x4e\x5c\x5c\x65\x65\x2d\x31\x6c\x5c\x27\x2c\x5c\x27\x32\x64\x5c\x27\x2c\x5c\x27\x65\x64\x5c\x5c\x65\x63\x3a\x5c\x5c\x6d\x5c\x27\x2c\x5c\x27\x2f\x32\x50\x2f\x31\x71\x2f\x32\x62\x3f\x31\x52\x2d\x32\x69\x3d\x5c\x27\x2c\x5c\x27\x3c\x32\x67\x5c\x27\x2c\x5c\x27\x65\x62\x5c\x27\x2c\x5c\x27\x35\x4b\x5c\x27\x2c\x5c\x27\x49\x2e\x61\x4a\x5c\x27\x2c\x5c\x27\x2e\x32\x54\x5c\x5c\x4b\x5c\x5c\x32\x4e\x5c\x27\x2c\x5c\x27\x2e\x4f\x5c\x27\x2c\x5c\x27\x33\x6e\x5c\x27\x2c\x5c\x27\x32\x51\x2d\x31\x71\x5c\x27\x2c\x5c\x27\x33\x6a\x5c\x27\x2c\x5c\x27\x2e\x35\x6e\x2d\x4c\x5c\x5c\x6d\x2e\x4c\x2d\x32\x66\x5c\x27\x2c\x5c\x27\x34\x4e\x5c\x27\x2c\x5c\x27\x2f\x65\x61\x2d\x63\x2f\x5c\x27\x2c\x5c\x27\x33\x54\x5c\x27\x2c\x5c\x27\x35\x6c\x5c\x27\x2c\x5c\x27\x26\x65\x39\x2d\x65\x38\x3d\x5c\x27\x2c\x5c\x27\x2e\x4f\x5c\x5c\x65\x37\x5c\x27\x2c\x5c\x27\x39\x75\x2d\x35\x69\x5c\x27\x2c\x5c\x27\x65\x74\x5c\x27\x2c\x5c\x27\x3c\x68\x35\x3e\x65\x68\x2e\x2e\x2e\x5c\x5c\x65\x75\x5c\x5c\x39\x62\x5c\x5c\x65\x49\x5c\x5c\x65\x53\x5c\x5c\x65\x52\x5c\x5c\x61\x67\x2e\x3c\x2f\x68\x35\x3e\x5c\x27\x2c\x5c\x27\x65\x51\x5c\x27\x2c\x5c\x27\x65\x50\x5c\x27\x2c\x5c\x27\x2e\x39\x65\x2e\x31\x43\x5c\x27\x2c\x5c\x27\x65\x4f\x5c\x27\x2c\x5c\x27\x65\x4e\x5c\x27\x2c\x5c\x27\x2f\x32\x50\x2f\x31\x71\x2f\x32\x62\x5c\x27\x2c\x5c\x27\x33\x69\x5c\x27\x2c\x5c\x27\x48\x5c\x27\x2c\x5c\x27\x3c\x2f\x61\x3e\x3c\x2f\x48\x3e\x3c\x2f\x47\x3e\x5c\x27\x2c\x5c\x27\x2e\x2d\x32\x74\x2d\x45\x5c\x27\x2c\x5c\x27\x5c\x5c\x39\x68\x5c\x5c\x65\x4d\x5c\x5c\x6d\x3a\x35\x70\x5c\x5c\x31\x63\x5c\x5c\x31\x63\x5c\x27\x2c\x5c\x27\x3c\x61\x5c\x5c\x31\x41\x3d\x5c\x5c\x34\x6e\x2f\x70\x2f\x31\x6c\x2e\x31\x34\x5c\x5c\x34\x6e\x3e\x3c\x2f\x61\x3e\x5c\x27\x2c\x5c\x27\x65\x4c\x5c\x27\x2c\x5c\x27\x23\x2d\x39\x69\x5c\x27\x2c\x5c\x27\x2f\x32\x50\x2f\x31\x71\x2f\x32\x62\x2f\x2d\x2f\x5c\x27\x2c\x5c\x27\x65\x4b\x5c\x27\x2c\x5c\x27\x39\x6b\x5c\x27\x2c\x5c\x27\x23\x31\x49\x5c\x5c\x55\x5c\x5c\x4b\x3a\x31\x64\x2d\x31\x62\x28\x34\x29\x5c\x5c\x31\x4d\x2e\x45\x2d\x31\x48\x5c\x27\x2c\x5c\x27\x32\x77\x5c\x27\x2c\x5c\x27\x49\x2e\x32\x54\x5c\x27\x2c\x5c\x27\x38\x5a\x5c\x27\x2c\x5c\x27\x65\x4a\x5c\x27\x2c\x5c\x27\x3f\x26\x31\x52\x2d\x32\x69\x3d\x5c\x27\x2c\x5c\x27\x32\x6e\x5c\x27\x2c\x5c\x27\x28\x33\x45\x3a\x2f\x2f\x5b\x5e\x2f\x5d\x2b\x29\x2f\x31\x79\x2f\x32\x6e\x2f\x28\x5b\x5e\x2f\x3f\x26\x5d\x2b\x29\x2e\x2a\x5b\x3f\x26\x5d\x71\x3d\x28\x5b\x5e\x24\x26\x5d\x2b\x29\x28\x3f\x3a\x5b\x5e\x24\x5d\x2b\x29\x3f\x5c\x27\x2c\x5c\x27\x65\x48\x5c\x27\x2c\x5c\x27\x65\x77\x5c\x27\x2c\x5c\x27\x61\x3a\x31\x48\x5c\x27\x2c\x5c\x27\x35\x42\x2e\x4f\x2d\x33\x6c\x5c\x27\x2c\x5c\x27\x3c\x78\x3e\x5c\x27\x2c\x5c\x27\x35\x67\x5c\x27\x2c\x5c\x27\x49\x5c\x5c\x55\x5c\x27\x2c\x5c\x27\x61\x64\x5c\x27\x2c\x5c\x27\x5c\x5c\x6a\x5c\x5c\x39\x6e\x3d\x5c\x5c\x39\x6f\x5c\x5c\x6a\x5c\x5c\x32\x65\x3d\x5c\x5c\x65\x47\x3a\x2e\x37\x3b\x65\x46\x2d\x33\x54\x3a\x37\x30\x25\x3b\x65\x45\x2d\x65\x44\x3a\x35\x75\x3b\x5c\x5c\x6a\x3e\x33\x45\x3a\x2f\x2f\x33\x6d\x2e\x33\x52\x2e\x31\x43\x3c\x2f\x61\x3e\x3c\x2f\x78\x3e\x5c\x5c\x6d\x5c\x27\x2c\x5c\x27\x65\x43\x5c\x27\x2c\x5c\x27\x65\x42\x5c\x27\x2c\x5c\x27\x2e\x39\x72\x2d\x39\x6a\x5c\x27\x2c\x5c\x27\x31\x34\x5c\x27\x2c\x5c\x27\x2e\x39\x36\x5c\x27\x2c\x5c\x27\x3c\x48\x3e\x38\x57\x5c\x5c\x39\x35\x5c\x5c\x65\x41\x5c\x5c\x65\x7a\x5c\x5c\x65\x79\x3c\x65\x6d\x3e\x28\x65\x78\x2c\x5c\x5c\x66\x4a\x5c\x5c\x65\x56\x5c\x5c\x66\x4b\x29\x3c\x2f\x65\x6d\x3e\x3c\x2f\x48\x3e\x5c\x27\x2c\x5c\x27\x3c\x49\x5c\x5c\x79\x3d\x5c\x5c\x37\x32\x2d\x31\x70\x2d\x38\x4e\x5c\x5c\x6a\x3e\x5c\x27\x2c\x5c\x27\x2e\x36\x53\x2c\x5c\x5c\x6d\x2e\x38\x4f\x5c\x27\x2c\x5c\x27\x32\x78\x5c\x27\x2c\x5c\x27\x3c\x47\x5c\x5c\x79\x3d\x5c\x5c\x67\x41\x2d\x67\x58\x5c\x5c\x34\x36\x2d\x5c\x27\x2c\x5c\x27\x33\x6f\x3a\x33\x70\x28\x5c\x5c\x37\x36\x2f\x5c\x5c\x6a\x29\x5c\x27\x2c\x5c\x27\x33\x6f\x3a\x33\x70\x28\x5c\x5c\x67\x57\x2f\x5c\x5c\x6a\x29\x5c\x27\x2c\x5c\x27\x5c\x5c\x36\x70\x5c\x5c\x67\x56\x3a\x5c\x5c\x6d\x5c\x27\x2c\x5c\x27\x67\x55\x5c\x27\x2c\x5c\x27\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x67\x54\x2d\x38\x53\x5c\x5c\x6a\x3e\x3c\x68\x32\x5c\x5c\x79\x3d\x5c\x5c\x32\x33\x2d\x32\x77\x5c\x5c\x6a\x3e\x5c\x27\x2c\x5c\x27\x2e\x2d\x32\x74\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x55\x5c\x5c\x4b\x2e\x67\x53\x2d\x36\x44\x5c\x27\x2c\x5c\x27\x3c\x49\x5c\x5c\x79\x3d\x5c\x5c\x67\x52\x2d\x31\x71\x5c\x5c\x6a\x3e\x67\x51\x3a\x5c\x5c\x67\x50\x5c\x5c\x67\x4f\x5c\x5c\x67\x4d\x5c\x5c\x6d\x3c\x69\x5c\x5c\x79\x3d\x5c\x5c\x67\x42\x5c\x5c\x67\x4c\x2d\x67\x4b\x5c\x5c\x6a\x2f\x3e\x3c\x2f\x49\x3e\x5c\x27\x2c\x5c\x27\x3f\x33\x64\x3d\x33\x73\x5c\x27\x2c\x5c\x27\x3c\x48\x3e\x67\x4a\x5c\x5c\x67\x49\x5c\x5c\x67\x48\x5c\x5c\x6d\x3c\x65\x6d\x3e\x28\x67\x47\x5c\x5c\x67\x46\x5c\x5c\x67\x45\x5c\x5c\x67\x44\x5c\x5c\x67\x43\x29\x3c\x2f\x65\x6d\x3e\x3c\x2f\x48\x3e\x5c\x27\x2c\x5c\x27\x35\x45\x24\x35\x46\x5c\x27\x2c\x5c\x27\x32\x41\x5c\x27\x2c\x5c\x27\x2e\x67\x59\x5c\x27\x2c\x5c\x27\x39\x41\x5c\x27\x2c\x5c\x27\x5c\x5c\x6a\x3e\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x32\x33\x2d\x32\x72\x2d\x32\x44\x5c\x5c\x6a\x3e\x3c\x61\x5c\x5c\x79\x3d\x5c\x5c\x32\x33\x2d\x32\x72\x2d\x32\x75\x5c\x5c\x6a\x5c\x5c\x31\x41\x3d\x5c\x5c\x6a\x5c\x27\x2c\x5c\x27\x59\x2e\x4f\x2d\x39\x33\x5c\x27\x2c\x5c\x27\x2e\x2d\x32\x74\x2d\x45\x5c\x5c\x6d\x2e\x31\x67\x5c\x5c\x55\x5c\x5c\x4b\x2e\x67\x4e\x2d\x36\x44\x5c\x27\x2c\x5c\x27\x32\x44\x5c\x27\x2c\x5c\x27\x36\x6f\x5c\x27\x2c\x5c\x27\x67\x5a\x5c\x27\x2c\x5c\x27\x59\x2e\x4f\x2d\x36\x41\x5c\x27\x2c\x5c\x27\x68\x67\x5c\x27\x2c\x5c\x27\x35\x38\x5c\x27\x2c\x5c\x27\x3c\x78\x5c\x5c\x79\x3d\x5c\x5c\x39\x74\x2d\x68\x71\x5c\x5c\x6a\x2f\x3e\x5c\x27\x2c\x5c\x27\x68\x70\x5c\x27\x2c\x5c\x27\x34\x64\x5c\x27\x2c\x5c\x27\x2f\x70\x2f\x31\x6c\x2e\x31\x34\x5c\x27\x2c\x5c\x27\x68\x6f\x5c\x27\x2c\x5c\x27\x39\x53\x5c\x5c\x36\x50\x5c\x27\x2c\x5c\x27\x36\x46\x5c\x27\x2c\x5c\x27\x32\x79\x5c\x27\x2c\x5c\x27\x3c\x47\x5c\x5c\x79\x3d\x5c\x5c\x68\x6e\x2d\x5c\x27\x2c\x5c\x27\x68\x6d\x5c\x27\x2c\x5c\x27\x39\x55\x5c\x27\x2c\x5c\x27\x2e\x68\x6c\x5c\x27\x2c\x5c\x27\x39\x57\x5c\x27\x2c\x5c\x27\x3c\x39\x58\x5c\x5c\x68\x6b\x3d\x5c\x27\x2c\x5c\x27\x33\x39\x5c\x27\x2c\x5c\x27\x31\x46\x5c\x27\x2c\x5c\x27\x3c\x2f\x68\x35\x3e\x5c\x27\x2c\x5c\x27\x5c\x5c\x68\x6a\x5c\x5c\x6d\x3a\x68\x69\x5c\x27\x2c\x5c\x27\x28\x33\x45\x3a\x2f\x2f\x5b\x5e\x2f\x5d\x2b\x29\x2f\x31\x79\x2f\x3f\x5b\x3f\x26\x5d\x71\x3d\x28\x2e\x2a\x29\x5c\x27\x2c\x5c\x27\x4c\x2d\x37\x31\x5c\x27\x2c\x5c\x27\x2f\x68\x68\x2e\x5c\x27\x2c\x5c\x27\x39\x78\x5c\x27\x2c\x5c\x27\x59\x2e\x4f\x2d\x39\x5a\x5c\x27\x2c\x5c\x27\x2e\x31\x70\x2d\x68\x66\x5c\x27\x2c\x5c\x27\x3c\x2f\x78\x3e\x3c\x68\x32\x5c\x5c\x79\x3d\x5c\x5c\x32\x33\x2d\x32\x77\x5c\x5c\x6a\x3e\x5c\x27\x2c\x5c\x27\x37\x55\x5c\x27\x5d\x3b\x32\x58\x3d\x6b\x28\x29\x7b\x53\x20\x61\x30\x7d\x3b\x53\x20\x32\x58\x28\x29\x7d\x61\x33\x28\x29\x2c\x32\x76\x5b\x33\x31\x28\x68\x31\x29\x5d\x3d\x6b\x28\x29\x7b\x61\x35\x28\x29\x7d\x2c\x6b\x28\x50\x29\x7b\x64\x20\x4a\x3d\x33\x31\x2c\x35\x57\x3d\x6b\x28\x61\x37\x2c\x61\x39\x29\x7b\x64\x20\x31\x78\x3d\x5a\x3b\x68\x5b\x31\x78\x28\x33\x53\x29\x5d\x3d\x61\x37\x2c\x68\x5b\x5c\x27\x61\x38\x5c\x27\x5d\x3d\x61\x39\x2c\x68\x5b\x31\x78\x28\x68\x65\x29\x5d\x28\x29\x2c\x68\x5b\x31\x78\x28\x39\x4d\x29\x5d\x3d\x61\x31\x2c\x68\x5b\x31\x78\x28\x35\x52\x29\x5d\x3d\x68\x5b\x31\x78\x28\x33\x53\x29\x5d\x5b\x31\x78\x28\x77\x29\x5d\x28\x31\x78\x28\x68\x64\x29\x29\x2c\x68\x5b\x31\x78\x28\x68\x63\x29\x5d\x28\x68\x5b\x31\x78\x28\x33\x53\x29\x5d\x29\x2c\x68\x5b\x31\x78\x28\x68\x62\x29\x5d\x28\x29\x7d\x3b\x35\x57\x5b\x4a\x28\x68\x61\x29\x5d\x3d\x7b\x5c\x27\x32\x73\x5c\x27\x3a\x7b\x5c\x27\x36\x75\x5c\x27\x3a\x33\x34\x28\x4a\x28\x68\x39\x29\x2c\x5c\x27\x67\x5c\x27\x29\x2c\x5c\x27\x36\x7a\x5c\x27\x3a\x33\x34\x28\x4a\x28\x68\x38\x29\x2c\x5c\x27\x67\x5c\x27\x29\x2c\x5c\x27\x39\x46\x5c\x27\x3a\x33\x34\x28\x4a\x28\x68\x37\x29\x2c\x5c\x27\x67\x5c\x27\x29\x2c\x5c\x27\x32\x6e\x5c\x27\x3a\x33\x34\x28\x4a\x28\x68\x36\x29\x2c\x5c\x27\x67\x5c\x27\x29\x2c\x5c\x27\x31\x79\x5c\x27\x3a\x33\x34\x28\x4a\x28\x68\x33\x29\x2c\x5c\x27\x67\x5c\x27\x29\x7d\x2c\x5c\x27\x39\x78\x5c\x27\x3a\x6b\x28\x29\x7b\x64\x20\x36\x33\x3d\x4a\x2c\x32\x35\x3d\x68\x3b\x68\x5b\x36\x33\x28\x35\x52\x29\x5d\x5b\x5c\x27\x34\x42\x5c\x27\x5d\x28\x6b\x28\x29\x7b\x64\x20\x32\x38\x3d\x36\x33\x3b\x32\x38\x28\x33\x4b\x29\x21\x3d\x3d\x50\x28\x68\x29\x5b\x32\x38\x28\x35\x4a\x29\x5d\x28\x32\x38\x28\x61\x68\x29\x29\x26\x26\x28\x32\x35\x5b\x5c\x27\x47\x5c\x27\x5d\x3d\x50\x28\x68\x29\x2c\x32\x35\x5b\x5c\x27\x32\x68\x5c\x27\x5d\x3d\x32\x35\x5b\x5c\x27\x47\x5c\x27\x5d\x5b\x32\x38\x28\x31\x55\x29\x5d\x28\x5c\x27\x36\x37\x5c\x27\x29\x2c\x32\x35\x5b\x5c\x27\x35\x38\x5c\x27\x5d\x3d\x32\x35\x5b\x5c\x27\x47\x5c\x27\x5d\x5b\x32\x38\x28\x33\x49\x29\x5d\x28\x5c\x27\x49\x5c\x27\x29\x5b\x32\x38\x28\x37\x58\x29\x5d\x28\x5c\x27\x49\x5c\x27\x29\x2c\x32\x35\x5b\x32\x38\x28\x38\x33\x29\x5d\x28\x29\x29\x7d\x2c\x6b\x28\x29\x7b\x32\x35\x5b\x5c\x27\x39\x4b\x5c\x27\x5d\x28\x29\x7d\x29\x7d\x2c\x5c\x27\x39\x41\x5c\x27\x3a\x6b\x28\x29\x7b\x64\x20\x32\x61\x3d\x4a\x2c\x32\x36\x3d\x68\x3b\x68\x5b\x5c\x27\x39\x4e\x5c\x27\x5d\x28\x29\x2c\x68\x5b\x32\x61\x28\x33\x4a\x29\x5d\x26\x26\x28\x68\x5b\x5c\x27\x39\x42\x5c\x27\x5d\x3d\x50\x5b\x32\x61\x28\x36\x34\x29\x5d\x28\x7b\x5c\x27\x36\x63\x5c\x27\x3a\x5c\x27\x68\x30\x5c\x27\x2c\x5c\x27\x32\x68\x5c\x27\x3a\x32\x36\x5b\x32\x61\x28\x33\x4a\x29\x5d\x2c\x5c\x27\x36\x65\x5c\x27\x3a\x5c\x27\x36\x69\x5c\x27\x2c\x5c\x27\x35\x54\x5c\x27\x3a\x32\x36\x5b\x32\x61\x28\x36\x5a\x29\x5d\x2c\x5c\x27\x39\x44\x5c\x27\x3a\x6b\x28\x29\x7b\x64\x20\x39\x76\x3d\x32\x61\x3b\x32\x36\x5b\x39\x76\x28\x67\x7a\x29\x5d\x28\x29\x7d\x2c\x5c\x27\x36\x32\x5c\x27\x3a\x6b\x28\x39\x47\x29\x7b\x64\x20\x36\x31\x3d\x32\x61\x3b\x32\x36\x5b\x36\x31\x28\x61\x77\x29\x5d\x28\x29\x2c\x32\x36\x5b\x5c\x27\x35\x50\x5c\x27\x5d\x28\x29\x2c\x32\x36\x5b\x36\x31\x28\x67\x61\x29\x5d\x28\x39\x47\x29\x7d\x2c\x5c\x27\x33\x39\x5c\x27\x3a\x6b\x28\x39\x4a\x29\x7b\x64\x20\x39\x49\x3d\x32\x61\x3b\x32\x36\x5b\x39\x49\x28\x67\x79\x29\x5d\x28\x39\x4a\x29\x7d\x7d\x29\x29\x7d\x2c\x5c\x27\x39\x4b\x5c\x27\x3a\x6b\x28\x29\x7b\x64\x20\x39\x4c\x3d\x4a\x3b\x68\x5b\x39\x4c\x28\x39\x4d\x29\x5d\x5b\x5c\x27\x67\x37\x5c\x27\x5d\x28\x29\x2c\x68\x5b\x5c\x27\x36\x4e\x5c\x27\x5d\x28\x29\x7d\x2c\x5c\x27\x39\x4e\x5c\x27\x3a\x6b\x28\x29\x7b\x64\x20\x43\x3d\x4a\x3b\x69\x66\x28\x68\x5b\x43\x28\x31\x76\x29\x5d\x29\x7b\x64\x20\x35\x32\x3d\x68\x3b\x68\x5b\x5c\x27\x35\x51\x5c\x27\x5d\x3d\x7b\x5c\x27\x33\x64\x5c\x27\x3a\x43\x28\x67\x36\x29\x2c\x5c\x27\x31\x52\x2d\x32\x69\x5c\x27\x3a\x68\x5b\x43\x28\x36\x4d\x29\x5d\x5b\x43\x28\x67\x35\x29\x5d\x7d\x2c\x2d\x42\x21\x3d\x3d\x68\x5b\x43\x28\x31\x76\x29\x5d\x5b\x5c\x27\x31\x79\x5c\x27\x5d\x28\x68\x5b\x5c\x27\x32\x73\x5c\x27\x5d\x5b\x43\x28\x39\x79\x29\x5d\x29\x26\x26\x2d\x42\x21\x3d\x3d\x68\x5b\x43\x28\x31\x76\x29\x5d\x5b\x43\x28\x35\x62\x29\x5d\x28\x68\x5b\x43\x28\x33\x4d\x29\x5d\x5b\x43\x28\x39\x77\x29\x5d\x29\x3f\x68\x5b\x5c\x27\x36\x46\x5c\x27\x5d\x3d\x68\x5b\x5c\x27\x32\x68\x5c\x27\x5d\x5b\x43\x28\x31\x6e\x29\x5d\x28\x68\x5b\x43\x28\x33\x4d\x29\x5d\x5b\x43\x28\x67\x34\x29\x5d\x2c\x6b\x28\x67\x33\x2c\x39\x45\x2c\x39\x7a\x2c\x39\x48\x29\x7b\x64\x20\x36\x39\x3d\x43\x3b\x53\x20\x35\x32\x5b\x5c\x27\x35\x51\x5c\x27\x5d\x5b\x5c\x27\x71\x5c\x27\x5d\x3d\x39\x48\x2c\x5b\x39\x45\x2c\x36\x39\x28\x61\x34\x29\x2c\x39\x7a\x2c\x5c\x27\x2f\x5c\x27\x5d\x5b\x36\x39\x28\x34\x52\x29\x5d\x28\x5c\x27\x5c\x27\x29\x7d\x29\x3a\x2d\x42\x21\x3d\x3d\x68\x5b\x43\x28\x31\x76\x29\x5d\x5b\x43\x28\x35\x62\x29\x5d\x28\x68\x5b\x5c\x27\x32\x73\x5c\x27\x5d\x5b\x43\x28\x39\x79\x29\x5d\x29\x26\x26\x2d\x42\x3d\x3d\x3d\x68\x5b\x5c\x27\x32\x68\x5c\x27\x5d\x5b\x43\x28\x35\x62\x29\x5d\x28\x68\x5b\x43\x28\x33\x4d\x29\x5d\x5b\x43\x28\x39\x77\x29\x5d\x29\x3f\x68\x5b\x43\x28\x33\x4a\x29\x5d\x3d\x68\x5b\x43\x28\x31\x76\x29\x5d\x5b\x43\x28\x31\x6e\x29\x5d\x28\x68\x5b\x43\x28\x33\x4d\x29\x5d\x5b\x43\x28\x39\x4f\x29\x5d\x2c\x6b\x28\x67\x32\x2c\x61\x36\x2c\x61\x32\x29\x7b\x64\x20\x37\x34\x3d\x43\x3b\x53\x20\x67\x31\x20\x35\x32\x5b\x37\x34\x28\x36\x5a\x29\x5d\x5b\x5c\x27\x71\x5c\x27\x5d\x2c\x5b\x61\x36\x2c\x37\x34\x28\x61\x34\x29\x2c\x61\x32\x2c\x5c\x27\x2f\x5c\x27\x5d\x5b\x5c\x27\x39\x52\x5c\x27\x5d\x28\x5c\x27\x5c\x27\x29\x7d\x29\x3a\x2d\x42\x3d\x3d\x3d\x68\x5b\x43\x28\x31\x76\x29\x5d\x5b\x5c\x27\x31\x79\x5c\x27\x5d\x28\x68\x5b\x5c\x27\x32\x73\x5c\x27\x5d\x5b\x5c\x27\x36\x75\x5c\x27\x5d\x29\x26\x26\x2d\x42\x21\x3d\x3d\x68\x5b\x43\x28\x31\x76\x29\x5d\x5b\x5c\x27\x31\x79\x5c\x27\x5d\x28\x68\x5b\x43\x28\x33\x4d\x29\x5d\x5b\x5c\x27\x36\x7a\x5c\x27\x5d\x29\x3f\x68\x5b\x43\x28\x33\x4a\x29\x5d\x3d\x68\x5b\x43\x28\x31\x76\x29\x5d\x5b\x5c\x27\x32\x7a\x5c\x27\x5d\x28\x68\x5b\x5c\x27\x32\x73\x5c\x27\x5d\x5b\x43\x28\x35\x62\x29\x5d\x2c\x6b\x28\x67\x30\x2c\x39\x54\x2c\x39\x56\x29\x7b\x64\x20\x34\x37\x3d\x43\x3b\x53\x20\x35\x32\x5b\x34\x37\x28\x36\x5a\x29\x5d\x5b\x5c\x27\x71\x5c\x27\x5d\x3d\x39\x56\x2c\x5b\x39\x54\x2c\x34\x37\x28\x66\x5a\x29\x5d\x5b\x34\x37\x28\x34\x52\x29\x5d\x28\x5c\x27\x5c\x27\x29\x7d\x29\x3a\x68\x5b\x43\x28\x33\x4a\x29\x5d\x3d\x21\x42\x7d\x31\x42\x20\x68\x5b\x5c\x27\x36\x46\x5c\x27\x5d\x3d\x21\x42\x7d\x2c\x5c\x27\x39\x34\x5c\x27\x3a\x6b\x28\x29\x7b\x64\x20\x34\x66\x3d\x4a\x3b\x50\x28\x5c\x27\x3c\x48\x3e\x3c\x2f\x48\x3e\x5c\x27\x2c\x7b\x5c\x27\x35\x36\x5c\x27\x3a\x34\x66\x28\x66\x59\x29\x7d\x29\x5b\x34\x66\x28\x31\x75\x29\x5d\x28\x68\x5b\x5c\x27\x47\x5c\x27\x5d\x5b\x34\x66\x28\x33\x49\x29\x5d\x28\x5c\x27\x47\x5c\x27\x29\x29\x7d\x2c\x5c\x27\x36\x4e\x5c\x27\x3a\x6b\x28\x29\x7b\x64\x20\x33\x4c\x3d\x4a\x3b\x68\x5b\x5c\x27\x47\x5c\x27\x5d\x5b\x33\x4c\x28\x33\x49\x29\x5d\x28\x5c\x27\x47\x5c\x27\x29\x5b\x33\x4c\x28\x77\x29\x5d\x28\x33\x4c\x28\x66\x57\x29\x29\x5b\x33\x4c\x28\x34\x78\x29\x5d\x28\x29\x7d\x2c\x5c\x27\x38\x5a\x5c\x27\x3a\x6b\x28\x36\x42\x29\x7b\x64\x20\x31\x36\x3d\x4a\x2c\x33\x4e\x2c\x35\x6f\x2c\x35\x49\x2c\x39\x38\x3d\x68\x2c\x34\x59\x3d\x5b\x5d\x3b\x36\x42\x5b\x5c\x27\x38\x58\x5c\x27\x5d\x5b\x31\x36\x28\x66\x4d\x29\x5d\x5b\x5c\x27\x24\x74\x5c\x27\x5d\x3e\x46\x3f\x50\x5b\x31\x36\x28\x32\x63\x29\x5d\x28\x36\x42\x5b\x31\x36\x28\x61\x62\x29\x5d\x5b\x31\x36\x28\x36\x78\x29\x5d\x2c\x6b\x28\x66\x56\x2c\x33\x51\x29\x7b\x64\x20\x31\x61\x3d\x31\x36\x3b\x33\x4e\x3d\x33\x51\x5b\x31\x61\x28\x34\x67\x29\x5d\x5b\x5c\x27\x24\x74\x5c\x27\x5d\x2c\x50\x5b\x31\x61\x28\x32\x63\x29\x5d\x28\x33\x51\x5b\x31\x61\x28\x36\x55\x29\x5d\x2c\x6b\x28\x66\x55\x2c\x35\x7a\x29\x7b\x64\x20\x39\x6d\x3d\x31\x61\x3b\x35\x6f\x3d\x5c\x27\x39\x71\x5c\x27\x3d\x3d\x3d\x35\x7a\x5b\x5c\x27\x39\x70\x5c\x27\x5d\x3f\x35\x7a\x5b\x39\x6d\x28\x32\x37\x29\x5d\x3a\x5c\x27\x23\x5c\x27\x7d\x29\x2c\x35\x49\x3d\x33\x51\x5b\x5c\x27\x35\x45\x24\x35\x46\x5c\x27\x5d\x3f\x33\x51\x5b\x5c\x27\x35\x45\x24\x35\x46\x5c\x27\x5d\x5b\x31\x61\x28\x31\x76\x29\x5d\x5b\x31\x61\x28\x31\x6e\x29\x5d\x28\x2f\x5c\x5c\x2f\x39\x6c\x5c\x5c\x2d\x63\x5c\x5c\x2f\x2f\x2c\x31\x61\x28\x66\x54\x29\x29\x3a\x39\x38\x5b\x31\x61\x28\x36\x4d\x29\x5d\x5b\x5c\x27\x36\x6b\x5c\x27\x5d\x2c\x34\x59\x5b\x5c\x27\x34\x6c\x5c\x27\x5d\x28\x31\x61\x28\x66\x53\x29\x2c\x33\x4e\x2c\x31\x61\x28\x66\x52\x29\x2c\x35\x6f\x2c\x31\x61\x28\x66\x51\x29\x2c\x33\x4e\x2c\x31\x61\x28\x61\x46\x29\x2c\x35\x49\x2c\x5c\x27\x5c\x5c\x6a\x2f\x3e\x3c\x62\x72\x5c\x5c\x6d\x2f\x3e\x5c\x27\x2c\x33\x4e\x2c\x31\x61\x28\x66\x50\x29\x29\x7d\x29\x3a\x34\x59\x5b\x31\x36\x28\x66\x4f\x29\x5d\x28\x31\x36\x28\x66\x4e\x29\x2c\x5c\x27\x67\x38\x5c\x5c\x61\x67\x5c\x5c\x66\x58\x2e\x5c\x27\x2c\x31\x36\x28\x67\x39\x29\x29\x2c\x68\x5b\x31\x36\x28\x36\x52\x29\x5d\x5b\x5c\x27\x31\x34\x5c\x27\x5d\x28\x34\x59\x5b\x31\x36\x28\x34\x52\x29\x5d\x28\x5c\x27\x5c\x27\x29\x29\x2c\x68\x5b\x5c\x27\x35\x55\x5c\x27\x5d\x5b\x31\x36\x28\x67\x6e\x29\x5d\x28\x5c\x27\x61\x6e\x5c\x27\x29\x2c\x68\x5b\x5c\x27\x47\x5c\x27\x5d\x5b\x5c\x27\x35\x54\x5c\x27\x5d\x28\x31\x36\x28\x61\x68\x29\x2c\x31\x36\x28\x33\x4b\x29\x29\x7d\x2c\x5c\x27\x61\x64\x5c\x27\x3a\x6b\x28\x61\x72\x29\x7b\x64\x20\x32\x71\x3d\x4a\x3b\x32\x71\x28\x31\x6d\x29\x3d\x3d\x3d\x61\x72\x5b\x32\x71\x28\x67\x78\x29\x5d\x26\x26\x28\x68\x5b\x32\x71\x28\x61\x77\x29\x5d\x28\x29\x2c\x68\x5b\x5c\x27\x35\x50\x5c\x27\x5d\x28\x29\x2c\x68\x5b\x32\x71\x28\x36\x52\x29\x5d\x5b\x32\x71\x28\x54\x29\x5d\x28\x32\x71\x28\x67\x77\x29\x29\x29\x7d\x2c\x5c\x27\x35\x50\x5c\x27\x3a\x6b\x28\x29\x7b\x64\x20\x31\x6b\x3d\x4a\x3b\x68\x5b\x31\x6b\x28\x35\x52\x29\x5d\x5b\x31\x6b\x28\x33\x49\x29\x5d\x28\x5c\x27\x47\x5c\x27\x29\x5b\x31\x6b\x28\x77\x29\x5d\x28\x31\x6b\x28\x67\x76\x29\x29\x5b\x31\x6b\x28\x34\x78\x29\x5d\x28\x29\x2c\x68\x5b\x5c\x27\x35\x55\x5c\x27\x5d\x5b\x31\x6b\x28\x31\x73\x29\x5d\x28\x31\x6b\x28\x35\x64\x29\x29\x2c\x68\x5b\x5c\x27\x47\x5c\x27\x5d\x5b\x5c\x27\x31\x46\x5c\x27\x5d\x28\x31\x6b\x28\x35\x64\x29\x29\x2c\x50\x28\x31\x6b\x28\x67\x75\x29\x2c\x7b\x5c\x27\x35\x36\x5c\x27\x3a\x31\x6b\x28\x67\x74\x29\x7d\x29\x5b\x31\x6b\x28\x31\x75\x29\x5d\x28\x68\x5b\x5c\x27\x47\x5c\x27\x5d\x5b\x5c\x27\x61\x7a\x5c\x27\x5d\x28\x5c\x27\x47\x5c\x27\x29\x29\x7d\x2c\x5c\x27\x61\x48\x5c\x27\x3a\x6b\x28\x61\x41\x29\x7b\x64\x20\x32\x53\x3d\x4a\x2c\x38\x6f\x3d\x68\x3b\x61\x41\x5b\x32\x53\x28\x77\x29\x5d\x28\x32\x53\x28\x38\x44\x29\x29\x5b\x32\x53\x28\x67\x73\x29\x5d\x28\x6b\x28\x29\x7b\x64\x20\x31\x50\x3d\x32\x53\x2c\x34\x4f\x3d\x50\x28\x68\x29\x3b\x34\x4f\x5b\x31\x50\x28\x77\x29\x5d\x28\x31\x50\x28\x35\x6a\x29\x29\x5b\x31\x50\x28\x58\x29\x5d\x28\x5c\x27\x34\x42\x2d\x31\x70\x5c\x27\x29\x3b\x64\x20\x37\x68\x3d\x50\x28\x68\x29\x5b\x31\x50\x28\x77\x29\x5d\x28\x31\x50\x28\x67\x72\x29\x29\x5b\x5c\x27\x34\x79\x5c\x27\x5d\x28\x29\x2a\x50\x28\x68\x29\x5b\x31\x50\x28\x77\x29\x5d\x28\x5c\x27\x49\x2e\x32\x54\x5c\x5c\x4b\x5c\x27\x29\x5b\x5c\x27\x34\x71\x5c\x27\x5d\x3b\x34\x4f\x5b\x31\x50\x28\x77\x29\x5d\x28\x31\x50\x28\x67\x71\x29\x29\x5b\x31\x50\x28\x67\x70\x29\x5d\x28\x7b\x5c\x27\x37\x49\x2d\x34\x79\x5c\x27\x3a\x37\x68\x2b\x5c\x27\x67\x6f\x5c\x27\x7d\x29\x2c\x38\x6f\x5b\x5c\x27\x38\x7a\x5c\x27\x5d\x28\x34\x4f\x29\x7d\x2c\x6b\x28\x29\x7b\x64\x20\x34\x4c\x3d\x32\x53\x3b\x50\x28\x68\x29\x5b\x34\x4c\x28\x77\x29\x5d\x28\x34\x4c\x28\x35\x6a\x29\x29\x5b\x5c\x27\x35\x67\x5c\x27\x5d\x28\x34\x4c\x28\x35\x64\x29\x29\x7d\x29\x7d\x2c\x5c\x27\x38\x39\x5c\x27\x3a\x6b\x28\x29\x7b\x64\x20\x57\x3d\x4a\x3b\x68\x5b\x57\x28\x33\x53\x29\x5d\x5b\x57\x28\x77\x29\x5d\x28\x57\x28\x67\x6d\x29\x29\x5b\x5c\x27\x38\x66\x5c\x27\x5d\x28\x29\x2c\x68\x5b\x5c\x27\x38\x46\x5c\x27\x5d\x5b\x57\x28\x58\x29\x5d\x28\x57\x28\x67\x62\x29\x29\x5b\x5c\x27\x31\x37\x5c\x27\x5d\x28\x57\x28\x38\x44\x29\x29\x5b\x57\x28\x77\x29\x5d\x28\x5c\x27\x49\x3a\x31\x48\x5c\x27\x29\x5b\x57\x28\x58\x29\x5d\x28\x5c\x27\x32\x54\x5c\x27\x29\x5b\x5c\x27\x32\x44\x5c\x27\x5d\x28\x50\x28\x57\x28\x67\x6c\x29\x2c\x7b\x5c\x27\x35\x36\x5c\x27\x3a\x68\x5b\x57\x28\x36\x4d\x29\x5d\x5b\x57\x28\x67\x6b\x29\x5d\x7d\x29\x29\x2c\x50\x28\x57\x28\x67\x6a\x29\x29\x5b\x57\x28\x67\x69\x29\x5d\x28\x50\x28\x57\x28\x67\x68\x29\x2c\x7b\x5c\x27\x35\x36\x5c\x27\x3a\x57\x28\x37\x4d\x29\x7d\x29\x29\x7d\x2c\x5c\x27\x38\x7a\x5c\x27\x3a\x6b\x28\x32\x48\x29\x7b\x64\x20\x31\x57\x3d\x4a\x3b\x32\x48\x3d\x32\x48\x5b\x31\x57\x28\x77\x29\x5d\x28\x31\x57\x28\x67\x67\x29\x29\x2c\x68\x5b\x31\x57\x28\x31\x76\x29\x5d\x3d\x32\x48\x5b\x5c\x27\x38\x67\x5c\x27\x5d\x28\x31\x57\x28\x32\x37\x29\x29\x2c\x68\x5b\x31\x57\x28\x36\x52\x29\x5d\x3d\x32\x48\x5b\x31\x57\x28\x33\x49\x29\x5d\x28\x5c\x27\x49\x5c\x27\x29\x5b\x31\x57\x28\x37\x58\x29\x5d\x28\x5c\x27\x49\x5c\x27\x29\x2c\x68\x5b\x5c\x27\x47\x5c\x27\x5d\x3d\x32\x48\x2c\x68\x5b\x31\x57\x28\x38\x33\x29\x5d\x28\x29\x7d\x7d\x2c\x50\x5b\x5c\x27\x66\x6e\x5c\x27\x5d\x5b\x4a\x28\x67\x66\x29\x5d\x3d\x6b\x28\x37\x77\x29\x7b\x64\x20\x33\x50\x3d\x4a\x2c\x38\x36\x3d\x50\x5b\x33\x50\x28\x67\x65\x29\x5d\x28\x7b\x7d\x2c\x7b\x5c\x27\x37\x55\x5c\x27\x3a\x35\x61\x2c\x5c\x27\x38\x42\x5c\x27\x3a\x33\x50\x28\x67\x64\x29\x2c\x5c\x27\x67\x63\x5c\x27\x3a\x33\x50\x28\x37\x4d\x29\x2c\x5c\x27\x36\x6b\x5c\x27\x3a\x5c\x27\x2f\x32\x62\x2e\x37\x7a\x5c\x27\x7d\x2c\x37\x77\x29\x3b\x53\x20\x68\x5b\x33\x50\x28\x32\x63\x29\x5d\x28\x6b\x28\x29\x7b\x37\x73\x20\x35\x57\x28\x50\x28\x68\x29\x2c\x38\x36\x29\x7d\x29\x7d\x7d\x28\x38\x4b\x29\x3b\x27\x2c\x36\x32\x2c\x31\x32\x36\x38\x2c\x27\x7c\x7c\x7c\x7c\x7c\x7c\x7c\x7c\x7c\x7c\x7c\x7c\x7c\x76\x61\x72\x7c\x7c\x5f\x30\x78\x35\x30\x31\x36\x34\x64\x7c\x7c\x74\x68\x69\x73\x7c\x7c\x78\x32\x32\x7c\x66\x75\x6e\x63\x74\x69\x6f\x6e\x7c\x5f\x30\x78\x32\x35\x62\x62\x37\x61\x7c\x78\x32\x30\x7c\x5f\x30\x78\x33\x30\x33\x62\x39\x36\x7c\x7c\x7c\x7c\x7c\x7c\x7c\x7c\x5f\x30\x78\x34\x64\x37\x32\x30\x35\x7c\x30\x78\x32\x61\x30\x7c\x64\x69\x76\x7c\x78\x32\x30\x63\x6c\x61\x73\x73\x7c\x5f\x30\x78\x33\x35\x39\x62\x30\x32\x7c\x5f\x30\x78\x33\x38\x37\x33\x64\x31\x7c\x30\x78\x31\x7c\x5f\x30\x78\x33\x34\x39\x34\x62\x39\x7c\x5f\x30\x78\x32\x31\x38\x34\x66\x61\x7c\x64\x65\x74\x61\x69\x6c\x73\x7c\x30\x78\x30\x7c\x6c\x69\x7c\x73\x70\x61\x6e\x7c\x75\x6c\x7c\x5f\x30\x78\x39\x36\x36\x37\x35\x34\x7c\x78\x32\x30\x6c\x69\x7c\x70\x6f\x73\x74\x7c\x5f\x30\x78\x34\x38\x32\x61\x37\x62\x7c\x5f\x30\x78\x34\x38\x32\x32\x63\x65\x7c\x63\x75\x73\x74\x6f\x6d\x66\x6f\x72\x6d\x7c\x5f\x30\x78\x35\x65\x37\x62\x63\x34\x7c\x5f\x30\x78\x34\x37\x66\x66\x62\x63\x7c\x5f\x30\x78\x31\x38\x38\x30\x66\x36\x7c\x72\x65\x74\x75\x72\x6e\x7c\x30\x78\x32\x33\x35\x7c\x78\x32\x30\x75\x6c\x7c\x5f\x30\x78\x31\x32\x37\x61\x63\x62\x7c\x5f\x30\x78\x35\x33\x36\x65\x31\x34\x7c\x30\x78\x32\x36\x31\x7c\x69\x6e\x70\x75\x74\x7c\x5f\x30\x78\x34\x66\x31\x65\x7c\x7c\x7c\x62\x61\x6e\x6b\x7c\x5f\x30\x78\x35\x30\x38\x33\x66\x66\x7c\x68\x74\x6d\x6c\x7c\x30\x78\x32\x34\x36\x7c\x5f\x30\x78\x31\x30\x38\x30\x36\x38\x7c\x66\x69\x6e\x64\x7c\x7c\x7c\x5f\x30\x78\x34\x62\x30\x30\x38\x34\x7c\x63\x68\x69\x6c\x64\x7c\x78\x30\x61\x7c\x6e\x74\x68\x7c\x30\x78\x31\x66\x61\x7c\x30\x78\x32\x38\x39\x7c\x69\x6e\x66\x6f\x6f\x72\x64\x65\x72\x7c\x5f\x30\x78\x34\x65\x61\x34\x30\x65\x7c\x73\x74\x79\x6c\x65\x7c\x5f\x30\x78\x34\x65\x62\x64\x35\x37\x7c\x5f\x30\x78\x35\x31\x36\x62\x61\x66\x7c\x63\x61\x72\x74\x7c\x30\x78\x32\x36\x30\x7c\x30\x78\x32\x61\x35\x7c\x5f\x30\x78\x32\x63\x32\x32\x37\x32\x7c\x6d\x65\x6e\x75\x7c\x70\x6f\x73\x74\x73\x7c\x5f\x30\x78\x39\x65\x32\x66\x33\x63\x7c\x30\x78\x32\x32\x65\x7c\x70\x61\x72\x73\x65\x49\x6e\x74\x7c\x30\x78\x32\x33\x61\x7c\x30\x78\x31\x62\x62\x7c\x66\x6f\x72\x6d\x7c\x5f\x30\x78\x33\x66\x30\x38\x34\x33\x7c\x73\x65\x61\x72\x63\x68\x7c\x30\x78\x32\x30\x61\x7c\x78\x32\x30\x68\x72\x65\x66\x7c\x65\x6c\x73\x65\x7c\x63\x6f\x6d\x7c\x5f\x30\x78\x34\x31\x63\x65\x35\x35\x7c\x30\x78\x31\x64\x37\x7c\x61\x64\x64\x43\x6c\x61\x73\x73\x7c\x6e\x61\x6d\x65\x7c\x66\x69\x72\x73\x74\x7c\x4c\x69\x6e\x6b\x4c\x69\x73\x74\x36\x31\x7c\x5f\x30\x78\x35\x63\x30\x39\x65\x35\x7c\x30\x78\x32\x34\x64\x7c\x63\x6f\x6e\x74\x61\x63\x74\x7c\x78\x32\x30\x73\x70\x61\x6e\x7c\x5f\x30\x78\x31\x33\x61\x36\x33\x31\x7c\x69\x6d\x70\x6f\x72\x74\x61\x6e\x74\x7c\x5f\x30\x78\x34\x35\x39\x33\x62\x62\x7c\x5f\x30\x78\x32\x66\x62\x63\x32\x61\x7c\x6d\x61\x78\x7c\x77\x72\x61\x70\x70\x65\x72\x7c\x5f\x30\x78\x61\x65\x34\x37\x31\x36\x7c\x30\x78\x32\x63\x37\x7c\x5f\x30\x78\x31\x31\x30\x34\x31\x38\x7c\x5f\x30\x78\x35\x30\x64\x36\x32\x38\x7c\x5f\x30\x78\x32\x61\x66\x65\x65\x30\x7c\x30\x78\x31\x65\x38\x7c\x5f\x30\x78\x32\x63\x64\x36\x39\x64\x7c\x69\x74\x65\x6d\x7c\x7c\x74\x65\x78\x74\x7c\x78\x32\x32\x70\x6f\x73\x74\x7c\x7c\x5f\x30\x78\x35\x36\x30\x35\x34\x62\x7c\x5f\x30\x78\x32\x35\x38\x66\x37\x31\x7c\x30\x78\x31\x62\x64\x7c\x5f\x30\x78\x33\x38\x33\x64\x65\x35\x7c\x5f\x30\x78\x34\x36\x39\x31\x36\x65\x7c\x5f\x30\x78\x33\x35\x38\x32\x31\x33\x7c\x64\x65\x66\x61\x75\x6c\x74\x7c\x30\x78\x32\x63\x64\x7c\x73\x70\x6c\x69\x74\x7c\x78\x32\x30\x73\x74\x79\x6c\x65\x7c\x62\x6f\x64\x79\x7c\x69\x6d\x67\x7c\x75\x72\x6c\x7c\x72\x65\x73\x75\x6c\x74\x73\x7c\x30\x78\x32\x35\x63\x7c\x5f\x30\x78\x63\x36\x30\x61\x38\x36\x7c\x5f\x30\x78\x33\x36\x61\x37\x30\x36\x7c\x5f\x30\x78\x66\x65\x39\x30\x33\x61\x7c\x6c\x61\x62\x65\x6c\x7c\x64\x6f\x63\x75\x6d\x65\x6e\x74\x7c\x5f\x30\x78\x31\x35\x30\x32\x65\x36\x7c\x5f\x30\x78\x33\x61\x62\x38\x38\x37\x7c\x69\x6d\x61\x67\x65\x7c\x72\x65\x67\x65\x78\x7c\x75\x70\x69\x7c\x6c\x69\x6e\x6b\x7c\x77\x69\x6e\x64\x6f\x77\x7c\x74\x69\x74\x6c\x65\x7c\x61\x70\x70\x65\x6e\x64\x54\x6f\x7c\x63\x6f\x6e\x74\x65\x6e\x74\x7c\x72\x65\x70\x6c\x61\x63\x65\x7c\x6d\x61\x74\x63\x68\x7c\x5f\x30\x78\x65\x37\x61\x38\x39\x37\x7c\x30\x78\x31\x66\x66\x7c\x77\x72\x61\x70\x7c\x5f\x30\x78\x31\x61\x61\x33\x33\x61\x7c\x5f\x30\x78\x31\x39\x30\x36\x32\x32\x7c\x77\x69\x64\x74\x68\x7c\x5f\x30\x78\x34\x62\x61\x32\x66\x62\x7c\x5f\x30\x78\x33\x66\x31\x32\x62\x64\x7c\x5f\x30\x78\x34\x32\x38\x34\x34\x34\x7c\x5f\x30\x78\x33\x62\x35\x65\x35\x65\x7c\x5f\x30\x78\x35\x37\x33\x61\x63\x30\x7c\x5f\x30\x78\x31\x38\x63\x36\x32\x63\x7c\x78\x32\x30\x61\x7c\x5f\x30\x78\x35\x31\x33\x30\x37\x34\x7c\x66\x65\x65\x64\x73\x7c\x68\x6f\x74\x7c\x5f\x30\x78\x32\x38\x31\x64\x33\x34\x7c\x5f\x30\x78\x36\x31\x39\x33\x33\x64\x7c\x6c\x65\x66\x74\x6d\x65\x6e\x75\x6c\x69\x73\x74\x7c\x30\x78\x31\x65\x62\x7c\x5f\x30\x78\x33\x65\x64\x37\x38\x33\x7c\x5f\x30\x78\x32\x65\x64\x61\x66\x62\x7c\x5f\x30\x78\x35\x34\x30\x61\x7c\x30\x78\x32\x30\x35\x7c\x5f\x30\x78\x39\x66\x30\x35\x36\x34\x7c\x5f\x30\x78\x31\x37\x61\x63\x38\x30\x7c\x5f\x30\x78\x33\x30\x39\x63\x65\x30\x7c\x5f\x30\x78\x32\x66\x33\x66\x34\x64\x7c\x30\x78\x32\x35\x34\x7c\x52\x65\x67\x45\x78\x70\x7c\x5f\x30\x78\x31\x31\x61\x66\x64\x63\x7c\x30\x78\x32\x38\x66\x7c\x5f\x30\x78\x31\x35\x33\x34\x62\x31\x7c\x30\x78\x32\x30\x37\x7c\x65\x72\x72\x6f\x72\x7c\x5f\x30\x78\x35\x35\x30\x63\x35\x35\x7c\x5f\x30\x78\x33\x36\x37\x35\x64\x32\x7c\x30\x78\x32\x62\x36\x7c\x61\x6c\x74\x7c\x5f\x30\x78\x35\x33\x37\x34\x38\x61\x7c\x5f\x30\x78\x35\x63\x63\x61\x62\x30\x7c\x5f\x30\x78\x34\x31\x32\x63\x30\x39\x7c\x5f\x30\x78\x33\x31\x35\x35\x65\x33\x7c\x72\x65\x6c\x61\x74\x65\x64\x7c\x73\x68\x6f\x77\x7c\x5f\x30\x78\x35\x31\x37\x39\x31\x39\x7c\x6d\x65\x73\x73\x61\x67\x65\x7c\x77\x77\x77\x7c\x6c\x6f\x63\x61\x74\x69\x6f\x6e\x7c\x73\x74\x72\x69\x6b\x65\x7c\x63\x6f\x6e\x74\x61\x69\x6e\x73\x7c\x5f\x30\x78\x33\x62\x37\x39\x61\x64\x7c\x5f\x30\x78\x35\x37\x61\x62\x66\x32\x7c\x6a\x73\x6f\x6e\x7c\x5f\x30\x78\x31\x66\x32\x32\x32\x32\x7c\x5f\x30\x78\x33\x36\x62\x37\x36\x63\x7c\x64\x69\x73\x70\x6c\x61\x79\x7c\x6d\x61\x69\x6e\x7c\x66\x6c\x6f\x61\x74\x7c\x63\x68\x65\x63\x6b\x6f\x75\x74\x7c\x73\x65\x63\x6f\x6e\x64\x7c\x65\x61\x63\x68\x7c\x76\x61\x6c\x75\x65\x7c\x78\x32\x30\x74\x64\x7c\x5f\x30\x78\x34\x61\x66\x64\x37\x30\x7c\x68\x74\x74\x70\x73\x7c\x5f\x30\x78\x35\x64\x37\x66\x66\x38\x7c\x78\x32\x30\x74\x68\x7c\x30\x78\x32\x7c\x30\x78\x31\x64\x65\x7c\x30\x78\x32\x35\x38\x7c\x30\x78\x32\x38\x38\x7c\x5f\x30\x78\x34\x33\x33\x38\x32\x31\x7c\x30\x78\x31\x39\x36\x7c\x5f\x30\x78\x33\x36\x33\x36\x61\x64\x7c\x5f\x30\x78\x32\x32\x39\x31\x65\x64\x7c\x5f\x30\x78\x32\x30\x39\x35\x63\x39\x7c\x5f\x30\x78\x32\x39\x34\x39\x33\x30\x7c\x62\x6c\x6f\x67\x67\x65\x72\x74\x68\x65\x6d\x65\x39\x7c\x30\x78\x31\x65\x32\x7c\x73\x69\x7a\x65\x7c\x5f\x30\x78\x33\x66\x31\x32\x35\x64\x7c\x78\x32\x32\x68\x74\x74\x70\x73\x7c\x62\x6f\x72\x64\x65\x72\x7c\x4d\x61\x74\x68\x7c\x5f\x30\x78\x32\x61\x35\x30\x35\x30\x7c\x5f\x30\x78\x34\x37\x39\x39\x64\x62\x7c\x30\x78\x32\x39\x65\x7c\x5f\x30\x78\x34\x65\x38\x38\x62\x65\x7c\x7c\x5f\x30\x78\x31\x33\x34\x36\x65\x30\x7c\x7c\x78\x32\x30\x30\x7c\x78\x32\x30\x69\x74\x65\x6d\x7c\x5f\x30\x78\x35\x36\x37\x38\x30\x61\x7c\x5f\x30\x78\x31\x32\x33\x65\x34\x32\x7c\x5f\x30\x78\x31\x65\x64\x66\x66\x37\x7c\x30\x78\x32\x61\x66\x7c\x5f\x30\x78\x32\x32\x30\x64\x35\x35\x7c\x7c\x64\x69\x73\x61\x62\x6c\x65\x64\x7c\x5f\x30\x78\x31\x62\x34\x36\x39\x66\x7c\x5f\x30\x78\x34\x63\x39\x30\x30\x30\x7c\x30\x78\x32\x32\x32\x7c\x5f\x30\x78\x34\x62\x35\x34\x62\x62\x7c\x5f\x30\x78\x33\x34\x64\x62\x33\x61\x7c\x30\x78\x32\x38\x62\x7c\x5f\x30\x78\x34\x39\x63\x64\x38\x33\x7c\x70\x75\x73\x68\x7c\x5f\x30\x78\x32\x33\x33\x30\x61\x63\x7c\x78\x32\x37\x7c\x5f\x30\x78\x32\x30\x36\x66\x61\x61\x7c\x77\x69\x64\x67\x65\x74\x7c\x6c\x65\x6e\x67\x74\x68\x7c\x73\x69\x64\x65\x62\x61\x72\x7c\x62\x72\x61\x6e\x63\x68\x7c\x5f\x30\x78\x35\x33\x61\x66\x30\x38\x7c\x63\x6f\x6e\x74\x65\x6e\x74\x73\x7c\x6d\x65\x67\x61\x7c\x5f\x30\x78\x31\x66\x63\x64\x66\x36\x7c\x30\x78\x31\x61\x33\x7c\x68\x65\x69\x67\x68\x74\x7c\x7c\x5f\x30\x78\x34\x63\x33\x39\x34\x61\x7c\x68\x6f\x76\x65\x72\x7c\x5f\x30\x78\x31\x66\x62\x63\x35\x30\x7c\x5f\x30\x78\x34\x31\x37\x61\x36\x33\x7c\x70\x61\x72\x65\x6e\x74\x7c\x63\x69\x74\x79\x7c\x61\x63\x63\x6f\x75\x6e\x74\x7c\x70\x72\x69\x63\x65\x7c\x5f\x30\x78\x33\x38\x66\x31\x39\x30\x7c\x5f\x30\x78\x35\x63\x66\x65\x66\x33\x7c\x78\x32\x30\x66\x6f\x6e\x74\x7c\x5f\x30\x78\x39\x37\x38\x64\x35\x39\x7c\x5f\x30\x78\x34\x34\x30\x39\x65\x31\x7c\x61\x63\x74\x69\x76\x65\x7c\x5f\x30\x78\x35\x30\x61\x65\x31\x34\x7c\x5f\x30\x78\x34\x66\x31\x65\x61\x38\x7c\x78\x32\x32\x63\x61\x72\x74\x7c\x30\x78\x31\x61\x38\x7c\x5f\x30\x78\x35\x64\x61\x30\x65\x66\x7c\x6f\x72\x64\x65\x72\x64\x65\x74\x61\x69\x6c\x73\x7c\x30\x78\x31\x65\x34\x7c\x5f\x30\x78\x33\x65\x61\x64\x39\x38\x7c\x5f\x30\x78\x32\x62\x34\x32\x31\x33\x7c\x30\x78\x32\x37\x61\x7c\x5f\x30\x78\x31\x63\x35\x64\x39\x66\x7c\x5f\x30\x78\x31\x65\x64\x64\x62\x64\x7c\x65\x6d\x61\x69\x6c\x7c\x5f\x30\x78\x38\x36\x31\x61\x38\x31\x7c\x5f\x30\x78\x34\x63\x31\x34\x64\x34\x7c\x30\x78\x31\x63\x37\x7c\x7c\x5f\x30\x78\x33\x38\x64\x31\x30\x39\x7c\x63\x6c\x61\x73\x73\x7c\x5f\x30\x78\x63\x35\x34\x63\x30\x63\x7c\x63\x6f\x6e\x74\x61\x69\x6e\x65\x72\x7c\x5f\x30\x78\x31\x64\x38\x66\x64\x65\x7c\x30\x78\x34\x7c\x30\x78\x32\x36\x65\x7c\x5f\x30\x78\x34\x31\x63\x30\x33\x61\x7c\x30\x78\x31\x63\x38\x7c\x73\x65\x74\x54\x69\x6d\x65\x6f\x75\x74\x7c\x76\x6f\x69\x64\x7c\x72\x65\x6d\x6f\x76\x65\x43\x6c\x61\x73\x73\x7c\x5f\x30\x78\x35\x31\x34\x30\x36\x61\x7c\x69\x63\x6f\x6e\x7c\x30\x78\x32\x32\x62\x7c\x5f\x30\x78\x34\x64\x31\x66\x34\x66\x7c\x63\x6c\x69\x63\x6b\x7c\x72\x65\x70\x6c\x61\x63\x65\x41\x6c\x6c\x7c\x70\x72\x6f\x64\x75\x63\x74\x7c\x5f\x30\x78\x35\x37\x31\x64\x31\x33\x7c\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x7c\x5f\x30\x78\x31\x37\x61\x38\x30\x30\x7c\x73\x75\x62\x6d\x69\x74\x7c\x5f\x30\x78\x33\x36\x64\x63\x35\x63\x7c\x5f\x30\x78\x33\x61\x37\x38\x34\x36\x7c\x31\x70\x78\x7c\x5f\x30\x78\x35\x35\x65\x62\x30\x37\x7c\x5f\x30\x78\x33\x64\x64\x36\x66\x31\x7c\x5f\x30\x78\x31\x37\x64\x34\x31\x66\x7c\x5f\x30\x78\x33\x63\x64\x31\x31\x64\x7c\x5f\x30\x78\x31\x63\x31\x36\x37\x36\x7c\x62\x75\x74\x74\x6f\x6e\x7c\x74\x65\x78\x74\x61\x72\x65\x61\x7c\x5f\x30\x78\x31\x35\x37\x37\x32\x36\x7c\x5f\x30\x78\x35\x61\x31\x31\x32\x61\x7c\x6d\x65\x64\x69\x61\x7c\x74\x68\x75\x6d\x62\x6e\x61\x69\x6c\x7c\x5f\x30\x78\x31\x38\x33\x66\x30\x64\x7c\x5f\x30\x78\x35\x34\x32\x64\x38\x64\x7c\x5f\x30\x78\x35\x65\x38\x65\x32\x63\x7c\x30\x78\x32\x38\x36\x7c\x76\x61\x6c\x7c\x30\x78\x32\x30\x34\x7c\x73\x63\x72\x69\x70\x74\x7c\x66\x6f\x72\x7c\x6c\x65\x66\x74\x7c\x61\x64\x64\x41\x72\x72\x6f\x77\x7c\x61\x6a\x61\x78\x44\x61\x74\x61\x7c\x30\x78\x32\x37\x33\x7c\x5f\x30\x78\x34\x32\x34\x65\x32\x37\x7c\x64\x61\x74\x61\x7c\x6d\x65\x6e\x75\x6c\x69\x73\x74\x7c\x30\x78\x31\x39\x66\x7c\x5f\x30\x78\x35\x39\x33\x35\x35\x65\x7c\x5f\x30\x78\x34\x34\x37\x33\x33\x35\x7c\x5f\x30\x78\x63\x38\x33\x32\x65\x62\x7c\x4c\x69\x6e\x6b\x4c\x69\x73\x74\x35\x31\x7c\x5f\x30\x78\x34\x36\x30\x35\x62\x37\x7c\x5f\x30\x78\x33\x36\x36\x61\x31\x38\x7c\x73\x75\x63\x63\x65\x73\x73\x7c\x5f\x30\x78\x35\x65\x37\x65\x30\x31\x7c\x30\x78\x32\x37\x31\x7c\x30\x78\x31\x62\x66\x7c\x30\x78\x31\x66\x34\x7c\x68\x72\x65\x66\x7c\x70\x6f\x73\x74\x50\x65\x72\x50\x61\x67\x65\x7c\x5f\x30\x78\x35\x38\x61\x66\x32\x63\x7c\x6f\x6e\x7c\x5f\x30\x78\x34\x35\x64\x37\x39\x32\x7c\x74\x79\x70\x65\x7c\x6e\x6f\x6e\x65\x7c\x64\x61\x74\x61\x54\x79\x70\x65\x7c\x78\x32\x30\x64\x69\x73\x70\x6c\x61\x79\x7c\x62\x6c\x6f\x63\x6b\x7c\x30\x78\x32\x62\x61\x7c\x6a\x73\x6f\x6e\x70\x7c\x6f\x75\x74\x65\x72\x54\x65\x78\x74\x7c\x6e\x6f\x54\x68\x75\x6d\x62\x6e\x61\x69\x6c\x7c\x5f\x30\x78\x33\x62\x34\x63\x36\x62\x7c\x5f\x30\x78\x36\x35\x35\x64\x35\x39\x7c\x30\x78\x32\x36\x38\x7c\x74\x72\x69\x6d\x7c\x78\x30\x61\x50\x72\x6f\x64\x75\x63\x74\x7c\x5f\x30\x78\x35\x64\x64\x36\x35\x31\x7c\x73\x76\x67\x7c\x78\x32\x30\x31\x38\x7c\x6c\x69\x63\x65\x6e\x73\x65\x5f\x69\x74\x65\x6d\x7c\x69\x73\x6c\x61\x62\x65\x6c\x7c\x5f\x30\x78\x31\x63\x37\x33\x37\x34\x7c\x78\x32\x30\x31\x39\x7c\x30\x78\x32\x61\x64\x7c\x30\x78\x33\x7c\x69\x73\x73\x65\x61\x72\x63\x68\x7c\x70\x68\x6f\x6e\x65\x7c\x5f\x30\x78\x32\x30\x37\x36\x64\x61\x7c\x5f\x30\x78\x34\x35\x62\x32\x35\x34\x7c\x71\x72\x7c\x5f\x30\x78\x34\x34\x65\x66\x37\x36\x7c\x61\x6a\x61\x78\x55\x72\x6c\x7c\x5f\x30\x78\x34\x64\x33\x38\x36\x61\x7c\x5f\x30\x78\x32\x61\x33\x62\x38\x32\x7c\x5f\x30\x78\x31\x66\x63\x66\x33\x31\x7c\x30\x78\x31\x66\x65\x7c\x5f\x30\x78\x34\x31\x66\x62\x61\x63\x7c\x30\x78\x32\x34\x61\x7c\x30\x78\x32\x61\x39\x7c\x68\x69\x64\x65\x4c\x6f\x61\x64\x65\x72\x7c\x5f\x30\x78\x31\x39\x31\x33\x35\x66\x7c\x78\x32\x30\x43\x61\x72\x74\x7c\x5f\x30\x78\x33\x32\x35\x31\x65\x65\x7c\x30\x78\x32\x35\x31\x7c\x74\x61\x62\x7c\x30\x78\x31\x61\x32\x7c\x30\x78\x32\x61\x62\x7c\x5f\x30\x78\x35\x37\x35\x65\x34\x30\x7c\x30\x78\x32\x30\x33\x7c\x5f\x30\x78\x33\x32\x33\x61\x61\x65\x7c\x5f\x30\x78\x65\x32\x34\x30\x37\x64\x7c\x30\x78\x31\x61\x34\x7c\x7c\x72\x69\x67\x68\x74\x7c\x78\x32\x32\x6d\x65\x67\x61\x7c\x5f\x30\x78\x33\x33\x64\x39\x32\x33\x7c\x5f\x30\x78\x35\x30\x63\x39\x34\x35\x7c\x5f\x30\x78\x31\x66\x37\x61\x31\x34\x7c\x78\x32\x32\x70\x72\x69\x63\x65\x7c\x78\x32\x30\x68\x31\x7c\x78\x32\x30\x63\x6f\x6c\x6f\x72\x7c\x5f\x30\x78\x34\x64\x35\x36\x38\x62\x7c\x30\x78\x32\x63\x65\x7c\x6d\x61\x72\x67\x69\x6e\x7c\x5f\x30\x78\x33\x31\x33\x38\x61\x35\x7c\x74\x6f\x4c\x6f\x77\x65\x72\x43\x61\x73\x65\x7c\x72\x65\x61\x64\x79\x7c\x70\x72\x65\x76\x65\x6e\x74\x44\x65\x66\x61\x75\x6c\x74\x7c\x78\x32\x32\x72\x65\x6c\x61\x74\x65\x64\x7c\x5f\x30\x78\x32\x39\x34\x61\x7c\x30\x78\x31\x62\x31\x7c\x5f\x30\x78\x32\x65\x35\x32\x37\x63\x7c\x30\x78\x32\x62\x62\x7c\x78\x32\x30\x6e\x6f\x6e\x65\x7c\x78\x32\x30\x6d\x61\x72\x67\x69\x6e\x7c\x5f\x30\x78\x33\x61\x36\x61\x30\x36\x7c\x70\x72\x6f\x64\x75\x63\x74\x5f\x6f\x66\x66\x7c\x62\x61\x63\x6b\x67\x72\x6f\x75\x6e\x64\x7c\x5f\x30\x78\x35\x36\x37\x62\x33\x30\x7c\x5f\x30\x78\x32\x64\x34\x32\x65\x63\x7c\x6e\x65\x77\x7c\x73\x63\x72\x6f\x6c\x6c\x54\x6f\x70\x7c\x34\x30\x30\x7c\x5f\x30\x78\x32\x38\x34\x37\x65\x30\x7c\x5f\x30\x78\x33\x64\x61\x66\x66\x34\x7c\x6d\x65\x74\x68\x6f\x64\x73\x75\x63\x63\x65\x73\x73\x7c\x66\x61\x6d\x69\x6c\x79\x7c\x70\x6e\x67\x7c\x6e\x75\x6d\x62\x65\x72\x7c\x5f\x30\x78\x31\x39\x63\x37\x37\x36\x7c\x30\x78\x32\x32\x30\x7c\x36\x33\x36\x33\x36\x33\x7c\x69\x74\x65\x6d\x5f\x61\x64\x64\x7c\x70\x61\x64\x64\x69\x6e\x67\x7c\x5f\x30\x78\x32\x35\x33\x38\x33\x62\x7c\x5f\x30\x78\x32\x36\x37\x31\x38\x66\x7c\x6d\x69\x6e\x7c\x38\x30\x70\x78\x7c\x78\x32\x30\x74\x6f\x7c\x30\x78\x35\x7c\x30\x78\x32\x36\x66\x7c\x30\x78\x31\x37\x34\x38\x37\x36\x65\x38\x30\x30\x7c\x30\x78\x32\x63\x36\x7c\x30\x78\x66\x61\x7c\x63\x6f\x64\x65\x7c\x30\x78\x32\x34\x65\x7c\x5f\x30\x78\x34\x35\x37\x31\x66\x35\x7c\x74\x6f\x70\x7c\x70\x6f\x73\x74\x73\x4e\x75\x6d\x62\x65\x72\x7c\x30\x78\x32\x30\x63\x7c\x77\x65\x69\x67\x68\x74\x7c\x30\x78\x31\x64\x64\x7c\x30\x78\x33\x65\x38\x7c\x30\x78\x31\x61\x64\x7c\x7c\x30\x78\x31\x61\x66\x7c\x72\x65\x70\x6c\x61\x63\x65\x57\x69\x74\x68\x7c\x30\x78\x32\x34\x38\x7c\x6c\x69\x73\x74\x7c\x30\x78\x32\x35\x35\x7c\x5f\x30\x78\x34\x36\x63\x36\x33\x33\x7c\x5f\x30\x78\x33\x31\x32\x37\x31\x63\x7c\x73\x74\x61\x74\x69\x63\x5f\x70\x61\x67\x65\x7c\x6d\x65\x67\x61\x4d\x65\x6e\x75\x48\x74\x6d\x6c\x7c\x78\x32\x30\x69\x64\x7c\x5f\x30\x78\x33\x34\x61\x35\x39\x31\x7c\x30\x78\x32\x35\x36\x7c\x64\x64\x64\x7c\x78\x32\x30\x73\x6f\x6c\x69\x64\x7c\x72\x65\x6d\x6f\x76\x65\x7c\x61\x74\x74\x72\x7c\x78\x32\x30\x35\x31\x32\x7c\x61\x70\x70\x65\x6e\x64\x7c\x78\x32\x32\x73\x69\x6d\x70\x6c\x65\x43\x61\x72\x74\x5f\x74\x6f\x74\x61\x6c\x7c\x5f\x30\x78\x32\x33\x61\x35\x36\x37\x7c\x78\x32\x32\x6d\x79\x7c\x5f\x30\x78\x33\x32\x30\x65\x32\x61\x7c\x78\x32\x30\x62\x6f\x64\x79\x7c\x5f\x30\x78\x39\x65\x61\x33\x36\x36\x7c\x5f\x30\x78\x38\x39\x30\x64\x32\x31\x7c\x30\x78\x32\x32\x39\x7c\x5f\x30\x78\x34\x35\x31\x64\x39\x37\x7c\x30\x78\x32\x34\x66\x7c\x30\x78\x32\x62\x32\x7c\x30\x78\x31\x62\x61\x7c\x67\x65\x74\x7c\x6d\x65\x74\x61\x7c\x61\x76\x61\x74\x61\x72\x7c\x78\x32\x30\x37\x39\x7c\x72\x65\x71\x75\x65\x73\x74\x46\x69\x72\x73\x74\x41\x6a\x61\x78\x7c\x30\x78\x31\x62\x38\x7c\x64\x69\x76\x43\x6c\x61\x73\x73\x7c\x30\x78\x32\x61\x36\x7c\x30\x78\x31\x66\x30\x7c\x5f\x30\x78\x31\x34\x31\x34\x34\x66\x7c\x65\x6c\x65\x6d\x7c\x75\x6e\x64\x65\x66\x69\x6e\x65\x64\x7c\x69\x74\x65\x6d\x52\x6f\x77\x7c\x72\x65\x63\x65\x6e\x74\x7c\x73\x6d\x61\x6c\x6c\x7c\x6a\x51\x75\x65\x72\x79\x7c\x5f\x30\x78\x31\x38\x61\x33\x33\x35\x7c\x5f\x30\x78\x34\x34\x38\x32\x62\x34\x7c\x69\x6e\x6e\x65\x72\x7c\x70\x61\x6e\x65\x6c\x7c\x74\x72\x79\x7c\x5f\x30\x78\x33\x32\x30\x63\x31\x32\x7c\x5f\x30\x78\x32\x38\x32\x38\x66\x34\x7c\x69\x6e\x66\x6f\x7c\x5f\x30\x78\x34\x64\x62\x37\x34\x61\x7c\x5f\x30\x78\x34\x62\x61\x39\x30\x38\x7c\x30\x78\x32\x34\x35\x7c\x4d\x61\x6b\x65\x7c\x66\x65\x65\x64\x7c\x5f\x30\x78\x33\x33\x61\x66\x63\x31\x7c\x73\x68\x6f\x77\x50\x6f\x73\x74\x73\x7c\x5f\x30\x78\x31\x38\x36\x33\x61\x36\x7c\x5f\x30\x78\x33\x64\x32\x37\x39\x34\x7c\x63\x61\x74\x63\x68\x7c\x70\x6f\x73\x74\x61\x6c\x7c\x73\x68\x6f\x77\x4c\x6f\x61\x64\x65\x72\x7c\x78\x32\x30\x70\x61\x79\x6d\x65\x6e\x74\x7c\x70\x72\x69\x6e\x74\x7c\x62\x72\x65\x61\x6b\x7c\x5f\x30\x78\x34\x37\x65\x30\x36\x33\x7c\x5f\x30\x78\x34\x62\x38\x31\x62\x33\x7c\x5f\x30\x78\x32\x36\x64\x66\x30\x32\x7c\x78\x32\x30\x6e\x6f\x74\x7c\x7c\x5f\x30\x78\x35\x39\x38\x30\x37\x63\x7c\x62\x6c\x6f\x67\x73\x70\x6f\x74\x7c\x30\x78\x32\x37\x37\x7c\x5f\x30\x78\x35\x32\x36\x36\x61\x34\x7c\x78\x30\x61\x4f\x72\x64\x65\x72\x7c\x63\x6f\x64\x7c\x77\x69\x64\x67\x65\x74\x73\x7c\x68\x69\x64\x65\x7c\x73\x37\x32\x7c\x5f\x30\x78\x61\x39\x63\x31\x31\x33\x7c\x78\x32\x30\x74\x61\x72\x67\x65\x74\x7c\x78\x32\x32\x5f\x62\x6c\x61\x6e\x6b\x7c\x72\x65\x6c\x7c\x61\x6c\x74\x65\x72\x6e\x61\x74\x65\x7c\x62\x61\x72\x72\x65\x64\x7c\x5f\x30\x78\x34\x33\x64\x37\x30\x63\x7c\x78\x32\x32\x68\x6f\x74\x7c\x6c\x6f\x61\x64\x69\x6e\x67\x7c\x5f\x30\x78\x35\x36\x66\x61\x37\x35\x7c\x30\x78\x31\x64\x63\x7c\x61\x64\x64\x45\x76\x65\x6e\x74\x73\x7c\x30\x78\x32\x61\x65\x7c\x5f\x30\x78\x64\x36\x64\x35\x30\x35\x7c\x68\x6f\x76\x65\x72\x4f\x76\x65\x72\x7c\x61\x6a\x61\x78\x63\x61\x6c\x6c\x7c\x30\x78\x31\x63\x35\x7c\x62\x65\x66\x6f\x72\x65\x53\x65\x6e\x64\x7c\x5f\x30\x78\x33\x33\x34\x37\x61\x63\x7c\x6c\x61\x62\x65\x6c\x73\x65\x61\x72\x63\x68\x7c\x5f\x30\x78\x31\x30\x36\x39\x64\x37\x7c\x5f\x30\x78\x34\x37\x37\x63\x39\x38\x7c\x5f\x30\x78\x33\x38\x32\x61\x32\x62\x7c\x5f\x30\x78\x31\x64\x31\x30\x38\x35\x7c\x68\x6f\x76\x65\x72\x4f\x75\x74\x7c\x5f\x30\x78\x34\x37\x64\x66\x61\x37\x7c\x30\x78\x31\x65\x36\x7c\x67\x65\x74\x41\x4a\x41\x58\x55\x72\x6c\x7c\x30\x78\x32\x32\x37\x7c\x30\x78\x32\x31\x33\x7c\x5f\x30\x78\x32\x30\x62\x37\x38\x66\x7c\x6a\x6f\x69\x6e\x7c\x53\x68\x6f\x70\x70\x69\x6e\x67\x7c\x5f\x30\x78\x35\x63\x32\x31\x38\x66\x7c\x69\x6e\x64\x65\x78\x4f\x66\x7c\x5f\x30\x78\x61\x31\x39\x61\x63\x37\x7c\x73\x69\x6d\x70\x6c\x65\x43\x61\x72\x74\x5f\x63\x68\x65\x63\x6b\x6f\x75\x74\x7c\x6f\x70\x74\x69\x6f\x6e\x7c\x61\x74\x6f\x62\x7c\x61\x64\x64\x72\x65\x73\x73\x7c\x5f\x30\x78\x32\x33\x31\x34\x62\x39\x7c\x6e\x75\x6c\x6c\x7c\x5f\x30\x78\x35\x61\x65\x66\x32\x65\x7c\x6c\x69\x63\x65\x6e\x73\x65\x7c\x30\x78\x32\x31\x65\x7c\x6d\x61\x69\x6e\x69\x6e\x67\x7c\x5f\x30\x78\x34\x34\x64\x64\x36\x66\x7c\x5f\x30\x78\x33\x36\x39\x35\x32\x65\x7c\x73\x65\x74\x74\x69\x6e\x67\x73\x7c\x5f\x30\x78\x34\x30\x66\x61\x37\x35\x7c\x5f\x30\x78\x37\x33\x34\x31\x61\x33\x7c\x30\x78\x32\x39\x37\x7c\x5f\x30\x78\x35\x37\x32\x33\x38\x36\x7c\x73\x68\x6f\x77\x45\x72\x72\x6f\x72\x7c\x73\x69\x6d\x70\x6c\x65\x43\x61\x72\x74\x5f\x67\x72\x61\x6e\x64\x54\x6f\x74\x61\x6c\x7c\x5f\x30\x78\x33\x66\x63\x39\x33\x37\x7c\x78\x32\x30\x70\x6f\x73\x74\x73\x7c\x30\x78\x31\x65\x64\x7c\x30\x78\x32\x36\x61\x7c\x30\x78\x31\x39\x31\x7c\x73\x68\x69\x66\x74\x7c\x68\x6f\x73\x74\x6e\x61\x6d\x65\x7c\x74\x6f\x67\x67\x6c\x65\x43\x6c\x61\x73\x73\x7c\x6d\x65\x6e\x75\x6c\x6f\x61\x64\x65\x64\x7c\x30\x78\x32\x34\x30\x7c\x30\x78\x32\x31\x36\x7c\x5f\x30\x78\x35\x34\x30\x61\x61\x61\x7c\x5f\x30\x78\x35\x37\x38\x62\x61\x62\x7c\x78\x32\x30\x61\x6c\x74\x7c\x30\x78\x32\x34\x39\x7c\x62\x6c\x6f\x67\x67\x65\x72\x7c\x5f\x30\x78\x32\x30\x31\x35\x35\x37\x7c\x30\x78\x31\x62\x34\x7c\x31\x30\x30\x7c\x30\x78\x31\x61\x61\x7c\x63\x6c\x6f\x73\x65\x73\x74\x7c\x5f\x30\x78\x31\x61\x66\x64\x31\x64\x7c\x30\x78\x32\x35\x39\x7c\x70\x6f\x73\x69\x74\x69\x6f\x6e\x7c\x5f\x30\x78\x35\x34\x65\x35\x37\x33\x7c\x5f\x30\x78\x35\x61\x36\x39\x61\x37\x7c\x30\x78\x31\x39\x65\x7c\x5f\x30\x78\x32\x36\x39\x37\x31\x65\x7c\x6d\x65\x6e\x75\x48\x65\x6c\x70\x65\x72\x7c\x30\x78\x32\x32\x64\x7c\x72\x69\x67\x68\x74\x6d\x65\x6e\x75\x6c\x69\x73\x74\x7c\x5f\x30\x78\x38\x34\x34\x36\x64\x33\x7c\x30\x78\x31\x39\x64\x7c\x30\x78\x32\x37\x39\x7c\x78\x32\x30\x6f\x75\x72\x7c\x30\x78\x39\x7c\x78\x32\x30\x62\x61\x6e\x6b\x7c\x30\x78\x32\x31\x31\x7c\x78\x32\x30\x61\x63\x63\x6f\x75\x6e\x74\x7c\x30\x78\x32\x39\x39\x7c\x6b\x65\x79\x64\x6f\x77\x6e\x7c\x30\x78\x32\x39\x63\x7c\x30\x78\x32\x34\x37\x7c\x5f\x30\x78\x35\x62\x36\x30\x65\x33\x7c\x78\x32\x30\x69\x6e\x74\x6f\x7c\x30\x78\x31\x64\x32\x7c\x30\x78\x31\x64\x33\x7c\x78\x32\x30\x54\x72\x61\x6e\x73\x66\x65\x72\x7c\x78\x32\x30\x64\x69\x72\x65\x63\x74\x6c\x79\x7c\x30\x78\x32\x35\x30\x7c\x30\x78\x31\x39\x35\x7c\x30\x78\x32\x31\x64\x7c\x30\x78\x32\x33\x33\x7c\x30\x78\x31\x63\x64\x7c\x30\x78\x32\x34\x34\x7c\x30\x78\x32\x37\x62\x7c\x30\x78\x62\x7c\x30\x78\x32\x32\x35\x7c\x30\x78\x32\x33\x37\x7c\x63\x65\x6d\x61\x69\x6c\x7c\x30\x78\x32\x31\x39\x7c\x30\x78\x32\x37\x30\x7c\x30\x78\x31\x64\x36\x7c\x30\x78\x32\x30\x39\x7c\x42\x61\x6e\x6b\x7c\x30\x78\x32\x39\x34\x7c\x30\x78\x32\x38\x33\x7c\x30\x78\x31\x65\x65\x7c\x30\x78\x31\x39\x63\x7c\x30\x78\x31\x63\x34\x7c\x70\x61\x79\x70\x61\x6c\x7c\x30\x78\x32\x34\x33\x7c\x7c\x73\x68\x6f\x70\x7c\x7c\x30\x78\x32\x33\x39\x7c\x30\x78\x31\x61\x62\x7c\x30\x78\x31\x65\x39\x7c\x30\x78\x32\x33\x63\x7c\x73\x74\x72\x69\x63\x74\x7c\x30\x78\x32\x63\x62\x7c\x30\x78\x31\x39\x33\x7c\x30\x78\x32\x39\x33\x7c\x55\x33\x7c\x4f\x35\x7c\x30\x78\x32\x33\x64\x7c\x30\x78\x31\x61\x39\x7c\x30\x78\x31\x65\x37\x7c\x30\x78\x32\x33\x34\x7c\x30\x78\x31\x63\x30\x7c\x30\x78\x32\x39\x30\x7c\x44\x61\x74\x65\x7c\x67\x65\x74\x4d\x6f\x6e\x74\x68\x7c\x67\x65\x74\x44\x61\x74\x65\x7c\x41\x31\x7c\x45\x34\x7c\x30\x78\x32\x38\x32\x7c\x30\x78\x32\x62\x39\x7c\x30\x78\x32\x32\x36\x7c\x30\x78\x32\x30\x32\x7c\x30\x78\x32\x31\x66\x7c\x30\x78\x32\x63\x30\x7c\x30\x78\x31\x65\x63\x7c\x58\x58\x58\x7c\x64\x63\x6f\x75\x6e\x74\x65\x72\x7c\x30\x78\x31\x39\x61\x7c\x30\x78\x32\x35\x65\x7c\x59\x59\x7c\x78\x32\x30\x6d\x65\x67\x61\x7c\x77\x68\x69\x6c\x65\x7c\x73\x65\x74\x49\x6e\x74\x65\x72\x76\x61\x6c\x7c\x30\x78\x32\x61\x38\x7c\x30\x78\x66\x7c\x30\x78\x32\x63\x61\x7c\x30\x78\x32\x33\x31\x7c\x30\x78\x32\x38\x37\x7c\x30\x78\x32\x36\x63\x7c\x77\x70\x5f\x63\x72\x64\x7c\x30\x78\x34\x34\x63\x7c\x30\x78\x31\x65\x66\x7c\x30\x78\x32\x31\x32\x7c\x30\x78\x31\x66\x39\x7c\x30\x78\x32\x38\x65\x7c\x30\x78\x31\x64\x30\x7c\x30\x78\x31\x64\x35\x7c\x73\x75\x62\x7c\x30\x78\x32\x33\x66\x7c\x5f\x30\x78\x35\x37\x30\x32\x62\x34\x7c\x30\x78\x32\x61\x33\x7c\x30\x78\x32\x63\x39\x7c\x30\x78\x31\x66\x36\x7c\x30\x78\x32\x35\x61\x7c\x30\x78\x32\x30\x62\x7c\x30\x78\x31\x66\x63\x7c\x30\x78\x32\x63\x35\x7c\x30\x78\x32\x61\x63\x7c\x30\x78\x31\x62\x30\x7c\x30\x78\x31\x63\x65\x7c\x5f\x30\x78\x35\x66\x30\x66\x62\x33\x7c\x30\x78\x32\x62\x38\x7c\x5f\x30\x78\x35\x66\x30\x39\x38\x36\x7c\x30\x78\x31\x65\x30\x7c\x30\x78\x32\x62\x37\x7c\x30\x78\x31\x39\x34\x7c\x30\x78\x33\x62\x39\x61\x63\x61\x30\x30\x7c\x5f\x30\x78\x38\x39\x62\x30\x32\x35\x7c\x78\x32\x30\x73\x68\x6f\x77\x7c\x78\x32\x32\x70\x72\x6f\x64\x75\x63\x74\x5f\x6f\x66\x66\x7c\x78\x32\x32\x6d\x65\x74\x61\x7c\x5f\x30\x78\x35\x64\x65\x32\x37\x32\x7c\x30\x78\x32\x62\x30\x7c\x70\x72\x6f\x64\x75\x63\x74\x69\x6e\x67\x7c\x30\x78\x32\x35\x32\x7c\x30\x78\x31\x62\x65\x7c\x30\x78\x31\x64\x39\x7c\x30\x78\x31\x39\x39\x7c\x30\x78\x31\x64\x34\x7c\x30\x78\x31\x66\x33\x7c\x30\x78\x31\x65\x61\x7c\x30\x78\x32\x39\x32\x7c\x30\x78\x32\x30\x65\x7c\x30\x78\x31\x39\x37\x7c\x30\x78\x36\x34\x7c\x78\x32\x30\x62\x6f\x77\x7c\x30\x78\x32\x39\x35\x7c\x30\x78\x32\x36\x35\x7c\x30\x78\x31\x64\x61\x7c\x30\x78\x32\x33\x62\x7c\x30\x78\x32\x33\x32\x7c\x30\x78\x32\x37\x65\x7c\x5f\x30\x78\x34\x39\x36\x37\x62\x66\x7c\x30\x78\x32\x33\x38\x7c\x30\x78\x32\x62\x64\x7c\x30\x78\x32\x37\x64\x7c\x30\x78\x31\x62\x63\x7c\x5f\x30\x78\x32\x31\x38\x66\x63\x31\x7c\x30\x78\x32\x38\x34\x7c\x5f\x30\x78\x31\x63\x31\x36\x37\x31\x7c\x30\x78\x32\x36\x64\x7c\x30\x78\x32\x31\x30\x7c\x62\x74\x6f\x61\x7c\x30\x78\x32\x37\x66\x7c\x5f\x30\x78\x32\x38\x32\x39\x33\x34\x7c\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x7c\x65\x6d\x62\x65\x64\x7c\x30\x78\x31\x63\x66\x7c\x79\x6f\x75\x74\x75\x62\x65\x7c\x77\x33\x30\x30\x7c\x30\x78\x31\x61\x31\x7c\x30\x78\x38\x7c\x30\x78\x31\x64\x31\x7c\x30\x78\x31\x65\x33\x7c\x30\x78\x31\x63\x31\x7c\x30\x78\x36\x7c\x30\x78\x31\x62\x36\x7c\x30\x78\x32\x63\x32\x7c\x30\x78\x31\x64\x38\x7c\x30\x78\x32\x39\x61\x7c\x30\x78\x32\x34\x32\x7c\x30\x78\x32\x38\x30\x7c\x5f\x30\x78\x35\x36\x61\x61\x37\x61\x7c\x30\x78\x31\x63\x61\x7c\x30\x78\x32\x61\x31\x7c\x30\x78\x32\x35\x66\x7c\x68\x61\x73\x7c\x30\x78\x32\x35\x64\x7c\x30\x78\x32\x63\x33\x7c\x78\x32\x30\x4e\x6f\x74\x65\x7c\x30\x78\x32\x36\x33\x7c\x30\x78\x32\x32\x63\x7c\x30\x78\x39\x66\x62\x37\x36\x7c\x5f\x30\x78\x65\x63\x65\x36\x63\x32\x7c\x30\x78\x31\x63\x63\x7c\x30\x78\x31\x63\x62\x7c\x73\x68\x69\x70\x70\x69\x6e\x67\x7c\x30\x78\x31\x62\x35\x7c\x30\x78\x32\x30\x36\x7c\x30\x78\x31\x61\x35\x7c\x30\x78\x31\x61\x36\x7c\x30\x78\x32\x31\x61\x7c\x30\x78\x61\x7c\x30\x78\x31\x66\x38\x7c\x66\x6f\x72\x45\x61\x63\x68\x7c\x30\x78\x32\x39\x31\x7c\x30\x78\x32\x33\x65\x7c\x78\x32\x30\x53\x69\x7a\x65\x7c\x30\x78\x31\x65\x31\x7c\x30\x78\x31\x63\x39\x7c\x30\x78\x37\x7c\x30\x78\x31\x66\x64\x7c\x30\x78\x32\x35\x62\x7c\x30\x78\x32\x36\x36\x7c\x30\x78\x31\x62\x37\x7c\x30\x78\x31\x66\x62\x7c\x30\x78\x32\x61\x32\x7c\x30\x78\x32\x37\x34\x7c\x49\x32\x7c\x61\x6a\x61\x78\x7c\x30\x78\x32\x62\x35\x7c\x73\x33\x35\x7c\x78\x32\x30\x66\x6f\x72\x6d\x7c\x69\x6e\x64\x65\x78\x7c\x73\x74\x61\x72\x74\x7c\x73\x32\x30\x30\x7c\x69\x6e\x6e\x65\x72\x48\x54\x4d\x4c\x7c\x78\x32\x30\x49\x44\x7c\x4f\x72\x64\x65\x72\x7c\x78\x32\x30\x64\x69\x73\x61\x62\x7c\x71\x75\x65\x72\x79\x53\x65\x6c\x65\x63\x74\x6f\x72\x41\x6c\x6c\x7c\x6d\x65\x67\x61\x73\x75\x62\x6d\x65\x6e\x75\x7c\x4f\x6f\x70\x73\x7c\x71\x75\x61\x6e\x74\x69\x74\x79\x7c\x72\x65\x6d\x6f\x76\x65\x44\x61\x74\x61\x7c\x63\x73\x73\x7c\x63\x75\x72\x72\x65\x6e\x74\x43\x6f\x6c\x6f\x72\x7c\x7c\x63\x6f\x6c\x6f\x72\x7c\x30\x70\x78\x7c\x69\x6e\x64\x65\x6e\x74\x7c\x76\x69\x73\x69\x62\x6c\x65\x7c\x76\x69\x73\x69\x62\x69\x6c\x69\x74\x79\x7c\x73\x74\x61\x74\x69\x63\x7c\x73\x63\x72\x6f\x6c\x6c\x7c\x78\x32\x30\x43\x6f\x75\x6c\x64\x7c\x69\x6e\x6c\x69\x6e\x65\x7c\x6d\x65\x67\x61\x42\x6c\x6f\x67\x67\x65\x72\x4d\x65\x6e\x75\x7c\x45\x61\x73\x79\x50\x61\x69\x73\x61\x7c\x78\x32\x30\x61\x70\x70\x7c\x78\x32\x30\x4d\x6f\x62\x69\x6c\x65\x7c\x78\x32\x30\x74\x68\x72\x6f\x75\x67\x68\x7c\x31\x38\x30\x74\x62\x47\x42\x75\x6b\x7c\x61\x6e\x69\x6d\x61\x74\x65\x7c\x73\x70\x61\x63\x69\x6e\x67\x7c\x6c\x65\x74\x74\x65\x72\x7c\x66\x6f\x6e\x74\x7c\x78\x32\x32\x6f\x70\x61\x63\x69\x74\x79\x7c\x73\x72\x63\x7c\x78\x32\x30\x66\x65\x74\x63\x68\x7c\x35\x4b\x70\x54\x67\x77\x68\x7c\x35\x32\x39\x36\x51\x6a\x66\x4b\x5a\x53\x7c\x70\x72\x6f\x74\x6f\x74\x79\x70\x65\x7c\x78\x32\x30\x44\x65\x74\x61\x69\x6c\x73\x7c\x43\x68\x65\x63\x6b\x6f\x75\x74\x7c\x67\x65\x74\x45\x6c\x65\x6d\x65\x6e\x74\x42\x79\x49\x64\x7c\x35\x39\x32\x36\x30\x32\x47\x46\x4c\x43\x56\x57\x7c\x63\x68\x61\x6e\x67\x65\x7c\x78\x32\x30\x62\x6c\x6f\x67\x7c\x78\x32\x30\x74\x68\x65\x7c\x6f\x70\x61\x63\x69\x74\x79\x7c\x31\x30\x33\x38\x32\x35\x33\x37\x4e\x52\x44\x6b\x57\x49\x7c\x78\x32\x30\x6f\x72\x7c\x61\x66\x74\x65\x72\x7c\x67\x72\x61\x6e\x64\x7c\x70\x72\x6f\x64\x75\x63\x74\x61\x64\x7c\x63\x68\x65\x63\x6b\x65\x64\x7c\x78\x32\x32\x6f\x66\x66\x7c\x78\x32\x30\x73\x72\x63\x7c\x32\x35\x39\x37\x34\x70\x70\x47\x72\x41\x71\x7c\x73\x74\x6f\x70\x50\x72\x6f\x70\x61\x67\x61\x74\x69\x6f\x6e\x7c\x66\x75\x6c\x6c\x7c\x63\x63\x69\x74\x79\x7c\x66\x6f\x63\x75\x73\x7c\x61\x64\x64\x7c\x73\x75\x63\x63\x65\x73\x73\x62\x6f\x78\x7c\x6f\x72\x64\x65\x72\x64\x61\x74\x65\x7c\x73\x74\x61\x74\x75\x73\x54\x65\x78\x74\x7c\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x7c\x78\x32\x30\x43\x6f\x64\x65\x7c\x78\x30\x61\x50\x6f\x73\x74\x61\x6c\x7c\x65\x78\x74\x65\x6e\x64\x7c\x78\x32\x30\x43\x68\x65\x63\x6b\x6f\x75\x74\x7c\x50\x72\x6f\x63\x65\x65\x64\x7c\x78\x32\x32\x73\x69\x6d\x70\x6c\x65\x43\x61\x72\x74\x5f\x63\x68\x65\x63\x6b\x6f\x75\x74\x7c\x72\x65\x76\x65\x72\x73\x65\x7c\x66\x61\x64\x65\x4f\x75\x74\x7c\x72\x65\x6d\x6f\x76\x65\x41\x74\x74\x72\x7c\x74\x68\x75\x6d\x62\x7c\x78\x32\x30\x50\x72\x69\x63\x65\x7c\x7c\x73\x69\x62\x6c\x69\x6e\x67\x73\x7c\x78\x32\x32\x73\x6e\x6f\x77\x7c\x42\x6c\x6f\x67\x67\x65\x72\x74\x68\x65\x6d\x65\x39\x7c\x35\x32\x35\x33\x39\x39\x33\x78\x4a\x77\x57\x62\x76\x7c\x63\x66\x75\x6c\x6c\x6e\x61\x6d\x65\x7c\x6f\x6b\x7c\x74\x61\x67\x7c\x63\x61\x64\x64\x72\x65\x73\x73\x7c\x34\x37\x32\x36\x34\x38\x38\x4c\x66\x45\x61\x73\x4d\x7c\x33\x30\x37\x63\x50\x6e\x6a\x63\x5a\x7c\x6d\x65\x67\x61\x6d\x65\x6e\x75\x69\x64\x7c\x74\x6f\x74\x61\x6c\x52\x65\x73\x75\x6c\x74\x73\x7c\x6f\x70\x65\x6e\x53\x65\x61\x72\x63\x68\x7c\x75\x6b\x7c\x62\x69\x6c\x6c\x69\x6e\x67\x7c\x73\x74\x6f\x72\x65\x7c\x65\x63\x6f\x6d\x6d\x65\x72\x63\x65\x7c\x30\x35\x7c\x32\x30\x32\x30\x7c\x6f\x72\x64\x65\x72\x69\x64\x73\x75\x63\x63\x65\x73\x73\x7c\x73\x69\x6d\x70\x6c\x65\x43\x61\x72\x74\x5f\x73\x68\x69\x70\x70\x69\x6e\x67\x7c\x78\x32\x30\x50\x61\x79\x54\x4d\x7c\x78\x32\x30\x47\x50\x61\x79\x7c\x74\x6f\x74\x61\x6c\x7c\x30\x78\x31\x63\x32\x7c\x30\x78\x32\x62\x65\x7c\x30\x78\x32\x38\x64\x7c\x30\x78\x32\x31\x38\x7c\x30\x78\x32\x37\x63\x7c\x30\x78\x32\x61\x34\x7c\x30\x78\x32\x37\x35\x7c\x30\x78\x32\x30\x38\x7c\x5f\x30\x78\x32\x66\x35\x66\x39\x32\x7c\x5f\x30\x78\x31\x61\x65\x37\x37\x37\x7c\x30\x78\x31\x64\x66\x7c\x78\x32\x30\x61\x76\x61\x69\x6c\x61\x62\x6c\x65\x7c\x30\x78\x32\x30\x64\x7c\x30\x78\x32\x31\x35\x7c\x5f\x30\x78\x63\x39\x64\x32\x61\x37\x7c\x64\x65\x6c\x65\x74\x65\x7c\x5f\x30\x78\x34\x61\x38\x36\x32\x63\x7c\x5f\x30\x78\x33\x37\x64\x61\x32\x39\x7c\x30\x78\x31\x61\x37\x7c\x30\x78\x32\x36\x62\x7c\x30\x78\x31\x66\x37\x7c\x61\x62\x6f\x72\x74\x7c\x4e\x6f\x7c\x30\x78\x32\x36\x32\x7c\x30\x78\x32\x32\x34\x7c\x30\x78\x31\x61\x65\x7c\x70\x6f\x73\x74\x73\x43\x6c\x61\x73\x73\x7c\x30\x78\x31\x66\x35\x7c\x30\x78\x32\x62\x66\x7c\x30\x78\x32\x32\x61\x7c\x30\x78\x32\x38\x61\x7c\x30\x78\x31\x63\x33\x7c\x30\x78\x32\x64\x30\x7c\x30\x78\x32\x32\x33\x7c\x30\x78\x32\x63\x31\x7c\x30\x78\x32\x39\x64\x7c\x30\x78\x32\x32\x66\x7c\x30\x78\x31\x66\x32\x7c\x70\x78\x7c\x30\x78\x31\x66\x31\x7c\x30\x78\x32\x30\x30\x7c\x30\x78\x31\x62\x39\x7c\x30\x78\x32\x37\x32\x7c\x30\x78\x32\x64\x31\x7c\x30\x78\x32\x63\x66\x7c\x30\x78\x32\x31\x37\x7c\x30\x78\x32\x30\x66\x7c\x30\x78\x32\x63\x38\x7c\x30\x78\x32\x33\x30\x7c\x30\x78\x31\x39\x62\x7c\x78\x32\x32\x73\x6c\x69\x64\x65\x7c\x78\x32\x32\x66\x61\x7c\x78\x32\x30\x64\x65\x6c\x69\x76\x65\x72\x79\x7c\x78\x32\x30\x75\x70\x6f\x6e\x7c\x78\x32\x30\x63\x61\x73\x68\x7c\x78\x32\x30\x77\x69\x74\x68\x7c\x50\x61\x79\x7c\x78\x32\x30\x44\x65\x6c\x69\x76\x65\x72\x79\x7c\x78\x32\x30\x6f\x6e\x7c\x43\x61\x73\x68\x7c\x66\x72\x6f\x77\x6e\x7c\x78\x32\x30\x66\x61\x7c\x78\x32\x30\x46\x6f\x75\x6e\x64\x7c\x70\x68\x6f\x6e\x65\x70\x65\x7c\x78\x32\x30\x50\x6f\x73\x74\x73\x7c\x78\x32\x30\x4e\x6f\x7c\x45\x72\x72\x6f\x72\x7c\x78\x32\x32\x6e\x6f\x7c\x67\x70\x61\x79\x7c\x78\x32\x32\x70\x72\x6f\x64\x75\x63\x74\x7c\x66\x65\x61\x74\x75\x72\x65\x64\x7c\x78\x32\x30\x51\x75\x61\x6e\x74\x69\x74\x79\x7c\x78\x32\x32\x73\x69\x7a\x65\x7c\x66\x6f\x75\x72\x74\x68\x7c\x6e\x61\x6d\x65\x73\x75\x63\x63\x65\x73\x73\x7c\x66\x61\x64\x65\x49\x6e\x7c\x47\x45\x54\x7c\x30\x78\x32\x35\x33\x7c\x7c\x30\x78\x32\x36\x34\x7c\x7c\x7c\x30\x78\x32\x62\x34\x7c\x30\x78\x32\x32\x38\x7c\x30\x78\x31\x63\x36\x7c\x30\x78\x32\x39\x38\x7c\x30\x78\x32\x31\x63\x7c\x30\x78\x32\x36\x37\x7c\x30\x78\x32\x38\x35\x7c\x30\x78\x32\x30\x31\x7c\x30\x78\x31\x61\x63\x7c\x62\x74\x6e\x7c\x73\x65\x74\x41\x74\x74\x72\x69\x62\x75\x74\x65\x7c\x68\x71\x64\x65\x66\x61\x75\x6c\x74\x7c\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x7c\x78\x30\x61\x41\x64\x64\x72\x65\x73\x73\x7c\x78\x32\x30\x76\x61\x6c\x75\x65\x7c\x69\x74\x65\x6d\x5f\x73\x69\x7a\x65\x7c\x37\x39\x37\x37\x38\x38\x36\x50\x49\x75\x65\x58\x65\x7c\x78\x32\x32\x69\x74\x65\x6d\x7c\x66\x6c\x6f\x6f\x72\x7c\x6f\x6e\x6c\x6f\x61\x64\x7c\x6c\x6f\x61\x64\x65\x72\x7c\x7c\x54\x6f\x74\x61\x6c\x7c\x73\x34\x35\x7c\x78\x32\x30\x79\x6f\x75\x72\x7c\x78\x32\x32\x6e\x6f\x74\x69\x63\x65\x5f\x68\x74\x6d\x6c\x7c\x34\x38\x30\x70\x78\x7c\x61\x75\x74\x6f\x7c\x78\x32\x32\x6d\x61\x72\x67\x69\x6e\x7c\x63\x65\x6e\x74\x65\x72\x7c\x61\x6c\x69\x67\x6e\x7c\x31\x30\x30\x76\x68\x7c\x66\x61\x66\x61\x66\x61\x7c\x66\x6c\x65\x78\x7c\x78\x32\x32\x64\x69\x73\x70\x6c\x61\x79\x7c\x78\x32\x30\x38\x70\x78\x7c\x33\x30\x70\x78\x7c\x31\x36\x70\x78\x7c\x32\x33\x32\x33\x32\x33\x7c\x78\x32\x30\x35\x30\x30\x7c\x78\x32\x30\x62\x7c\x64\x65\x63\x6f\x72\x61\x74\x69\x6f\x6e\x7c\x78\x32\x30\x74\x65\x78\x74\x7c\x62\x6f\x78\x7c\x73\x69\x7a\x69\x6e\x67\x7c\x78\x32\x30\x62\x6f\x78\x7c\x73\x65\x72\x69\x66\x7c\x77\x68\x69\x74\x65\x7c\x72\x61\x64\x69\x75\x73\x7c\x78\x32\x32\x52\x75\x62\x69\x6b\x7c\x78\x32\x32\x4d\x32\x32\x38\x7c\x78\x32\x30\x33\x38\x7c\x33\x63\x32\x33\x7c\x78\x32\x30\x34\x34\x38\x68\x33\x35\x34\x7c\x78\x32\x30\x69\x6e\x7c\x78\x32\x30\x34\x34\x38\x7c\x78\x32\x30\x35\x35\x7c\x78\x32\x30\x34\x32\x33\x7c\x31\x43\x34\x30\x7c\x78\x32\x30\x34\x30\x33\x7c\x39\x4c\x35\x31\x7c\x78\x32\x30\x64\x7c\x31\x30\x70\x78\x7c\x70\x61\x74\x68\x7c\x78\x32\x32\x30\x7c\x78\x32\x30\x76\x69\x65\x77\x42\x6f\x78\x7c\x32\x30\x30\x30\x7c\x6f\x72\x67\x7c\x77\x33\x7c\x7c\x78\x32\x30\x78\x6d\x6c\x6e\x73\x7c\x7c\x78\x32\x30\x32\x70\x78\x7c\x78\x32\x30\x61\x75\x74\x6f\x7c\x78\x32\x32\x66\x69\x6c\x6c\x7c\x78\x32\x30\x73\x61\x6e\x73\x7c\x78\x32\x30\x30\x70\x78\x7c\x39\x4c\x32\x38\x33\x7c\x30\x78\x32\x34\x31\x7c\x7c\x30\x78\x32\x37\x38\x7c\x30\x78\x32\x62\x33\x7c\x30\x78\x31\x39\x32\x7c\x30\x78\x32\x39\x62\x7c\x7c\x30\x78\x31\x62\x32\x7c\x30\x78\x32\x32\x31\x7c\x30\x78\x31\x65\x35\x7c\x30\x78\x31\x64\x62\x7c\x30\x78\x32\x38\x31\x7c\x30\x78\x31\x61\x30\x7c\x30\x78\x32\x38\x63\x7c\x30\x78\x32\x34\x62\x7c\x30\x78\x32\x63\x63\x7c\x30\x78\x32\x61\x37\x7c\x30\x78\x31\x62\x33\x7c\x6e\x65\x78\x74\x7c\x30\x78\x32\x61\x61\x7c\x30\x78\x32\x36\x39\x7c\x30\x78\x31\x39\x38\x7c\x30\x78\x32\x37\x36\x7c\x30\x78\x32\x33\x36\x7c\x30\x78\x32\x62\x31\x7c\x30\x78\x32\x63\x34\x7c\x78\x32\x30\x70\x61\x64\x64\x69\x6e\x67\x7c\x30\x78\x32\x35\x37\x7c\x78\x32\x32\x73\x74\x79\x6c\x65\x73\x68\x65\x65\x74\x7c\x78\x32\x30\x72\x65\x6c\x7c\x73\x77\x61\x70\x7c\x35\x30\x30\x7c\x77\x67\x68\x74\x7c\x52\x75\x62\x69\x6b\x7c\x63\x73\x73\x32\x7c\x67\x6f\x6f\x67\x6c\x65\x61\x70\x69\x73\x7c\x66\x6f\x6e\x74\x73\x7c\x30\x78\x32\x62\x63\x7c\x30\x78\x32\x31\x62\x7c\x30\x78\x32\x31\x34\x7c\x30\x78\x32\x34\x63\x7c\x30\x78\x32\x39\x66\x7c\x78\x32\x30\x31\x30\x30\x7c\x78\x32\x30\x77\x69\x64\x74\x68\x7c\x63\x6f\x6d\x6d\x65\x6e\x74\x73\x7c\x62\x6c\x6f\x67\x7c\x64\x65\x73\x63\x72\x69\x70\x74\x69\x6f\x6e\x7c\x78\x32\x30\x72\x65\x6c\x61\x74\x69\x76\x65\x7c\x78\x32\x30\x62\x6c\x6f\x63\x6b\x7c\x30\x78\x32\x39\x36\x7c\x78\x32\x30\x32\x37\x7c\x78\x32\x30\x37\x38\x7c\x75\x73\x65\x7c\x62\x61\x63\x6b\x7c\x62\x6c\x6f\x67\x62\x6c\x6f\x67\x7c\x69\x6d\x67\x31\x7c\x5f\x5f\x5f\x5f\x5f\x7c\x78\x32\x30\x4e\x75\x6d\x62\x65\x72\x7c\x78\x30\x61\x50\x68\x6f\x6e\x65\x7c\x72\x61\x6e\x64\x6f\x6d\x7c\x74\x6f\x74\x61\x6c\x73\x75\x63\x63\x65\x73\x73\x7c\x78\x32\x32\x63\x75\x73\x74\x6f\x6d\x7c\x63\x70\x68\x6f\x6e\x65\x7c\x6c\x6f\x63\x61\x6c\x68\x6f\x73\x74\x7c\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x5f\x7c\x67\x69\x66\x7c\x78\x30\x61\x43\x69\x74\x79\x7c\x72\x65\x6e\x7c\x74\x72\x75\x65\x7c\x31\x30\x4d\x49\x4b\x6d\x6d\x6d\x7c\x73\x65\x63\x74\x69\x6f\x6e\x73\x7c\x63\x70\x6f\x73\x74\x61\x6c\x7c\x78\x32\x30\x73\x74\x72\x69\x6b\x65\x7c\x78\x32\x30\x62\x79\x7c\x78\x32\x30\x44\x65\x73\x69\x67\x6e\x65\x64\x7c\x38\x32\x31\x32\x7c\x62\x6c\x61\x6e\x6b\x7c\x70\x61\x79\x74\x6d\x7c\x78\x32\x32\x74\x68\x75\x6d\x62\x7c\x62\x6f\x74\x7c\x78\x32\x32\x73\x69\x6d\x70\x6c\x65\x43\x61\x72\x74\x5f\x71\x75\x61\x6e\x74\x69\x74\x79\x7c\x78\x32\x30\x68\x61\x76\x65\x7c\x59\x6f\x75\x7c\x78\x32\x32\x63\x61\x72\x74\x65\x72\x7c\x78\x32\x30\x63\x61\x72\x74\x7c\x59\x6f\x75\x72\x7c\x53\x75\x62\x74\x6f\x74\x61\x6c\x7c\x73\x75\x62\x74\x6f\x74\x61\x6c\x7c\x61\x6d\x6f\x75\x6e\x74\x7c\x65\x6c\x65\x6d\x65\x6e\x74\x7c\x78\x32\x30\x62\x6f\x74\x68\x7c\x77\x69\x74\x68\x7c\x78\x32\x32\x63\x6c\x65\x61\x72\x7c\x78\x32\x32\x73\x69\x6d\x70\x6c\x65\x43\x61\x72\x74\x5f\x69\x74\x65\x6d\x73\x7c\x72\x65\x76\x69\x65\x77\x7c\x78\x32\x30\x63\x68\x65\x63\x6b\x7c\x73\x68\x6f\x70\x70\x69\x6e\x67\x7c\x68\x65\x61\x64\x65\x72\x7c\x78\x32\x30\x69\x6d\x67\x7c\x67\x65\x74\x46\x75\x6c\x6c\x59\x65\x61\x72\x7c\x4c\x61\x62\x65\x6c\x7c\x65\x6e\x74\x72\x79\x7c\x78\x32\x30\x74\x69\x74\x6c\x65\x7c\x73\x65\x63\x74\x69\x6f\x6e\x7c\x73\x35\x35\x7c\x78\x32\x30\x66\x6f\x6f\x74\x65\x72\x7c\x78\x32\x30\x32\x31\x34\x4c\x32\x37\x30\x7c\x78\x32\x32\x64\x63\x6f\x75\x6e\x74\x65\x72\x7c\x43\x4f\x50\x59\x52\x49\x47\x48\x54\x5f\x45\x52\x52\x4f\x52\x7c\x78\x32\x30\x33\x33\x36\x68\x7c\x78\x32\x30\x63\x72\x65\x64\x69\x74\x73\x7c\x32\x38\x6c\x7c\x78\x32\x30\x72\x65\x6d\x6f\x76\x65\x7c\x78\x32\x30\x30\x7a\x4d\x32\x37\x33\x7c\x44\x6f\x7c\x78\x32\x30\x43\x6f\x70\x79\x72\x69\x67\x68\x74\x7c\x52\x65\x73\x70\x65\x63\x74\x7c\x31\x32\x32\x68\x33\x35\x7c\x32\x7a\x4d\x32\x35\x36\x7c\x78\x32\x30\x34\x30\x32\x7c\x78\x32\x30\x38\x7c\x34\x73\x38\x7c\x78\x32\x32\x68\x65\x69\x67\x68\x74\x7c\x32\x30\x70\x78\x7c\x75\x43\x6a\x59\x67\x56\x46\x49\x68\x37\x30\x7c\x4b\x63\x75\x39\x77\x4a\x62\x76\x37\x39\x30\x68\x49\x6f\x38\x33\x72\x49\x5f\x73\x37\x6c\x4c\x57\x33\x7a\x6b\x4c\x59\x30\x31\x45\x41\x7c\x41\x41\x41\x41\x41\x41\x41\x41\x44\x55\x73\x7c\x6d\x4c\x37\x50\x49\x7c\x56\x75\x4f\x4c\x6e\x7c\x78\x32\x32\x62\x6f\x72\x64\x65\x72\x27\x2e\x73\x70\x6c\x69\x74\x28\x27\x7c\x27\x29\x2c\x30\x2c\x7b\x7d\x29\x29\x0a";eval(_mSAeHR);

/*]]>*/
  jQuery(document).ready(function($) {$(&#39;#megamenuid&#39;).megaBloggerMenu({ postsNumber : 4, noThumbnail : &#39;https://2.bp.blogspot.com/-Z7jG9iO9OTg/Vazz6YJnFQI/AAAAAAAALVs/wlSvXPgdDAo/s1600/no_image_available.png&#39; 
}); });
</script>
  
<script type='text/javascript'>
//<![CDATA[

//]]>
</script>
   
<!-- Main Scripts -->
<script type='text/javascript'>
//<![CDATA[
/*! jquery-simplecart | License MIT */

var JSON;!function(m,y){function g(t,e){return typeof t===e}function v(t){return void 0===t}function b(t){return g(t,"function")}function _(t){return"object"==typeof HTMLElement?t instanceof HTMLElement:"object"==typeof t&&1===t.nodeType&&"string"==typeof t.nodeName}var x="string",C=function(t){function s(t){return p.extend({attr:"",label:"",view:"attr",text:"",className:"",hide:!1},t||{})}function e(){if(!p.isReady){try{y.documentElement.doScroll("left")}catch(t){return void setTimeout(e,1)}p.init()}}var r={MooTools:"$$",Prototype:"$$",jQuery:"*"},a=0,o={},i=t||"simpleCart",c={};t={},t={};var u,l,n=m.localStorage,h=m.console||{msgs:[],log:function(t){h.msgs.push(t)}},f={USD:{code:"USD",symbol:"&#36;",name:"US Dollar"},INR:{code:"INR",symbol:"&#8377;",name:"Indian Rupee"},AUD:{code:"AUD",symbol:"&#36;",name:"Australian Dollar"},BRL:{code:"BRL",symbol:"R&#36;",name:"Brazilian Real"},CAD:{code:"CAD",symbol:"&#36;",name:"Canadian Dollar"},CZK:{code:"CZK",symbol:"&nbsp;&#75;&#269;",name:"Czech Koruna",after:!0},DKK:{code:"DKK",symbol:"DKK&nbsp;",name:"Danish Krone"},EUR:{code:"EUR",symbol:"&euro;",name:"Euro"},HKD:{code:"HKD",symbol:"&#36;",name:"Hong Kong Dollar"},HUF:{code:"HUF",symbol:"&#70;&#116;",name:"Hungarian Forint"},ILS:{code:"ILS",symbol:"&#8362;",name:"Israeli New Sheqel"},JPY:{code:"JPY",symbol:"&yen;",name:"Japanese Yen",accuracy:0},MXN:{code:"MXN",symbol:"&#36;",name:"Mexican Peso"},NOK:{code:"NOK",symbol:"NOK&nbsp;",name:"Norwegian Krone"},NZD:{code:"NZD",symbol:"&#36;",name:"New Zealand Dollar"},PLN:{code:"PLN",symbol:"PLN&nbsp;",name:"Polish Zloty"},GBP:{code:"GBP",symbol:"&pound;",name:"Pound Sterling"},SGD:{code:"SGD",symbol:"&#36;",name:"Singapore Dollar"},SEK:{code:"SEK",symbol:"SEK&nbsp;",name:"Swedish Krona"},CHF:{code:"CHF",symbol:"CHF&nbsp;",name:"Swiss Franc"},THB:{code:"THB",symbol:"&#3647;",name:"Thai Baht"},BTC:{code:"BTC",symbol:" BTC",name:"Bitcoin",accuracy:4,after:!0}},d={checkout:{type:"PayPal",email:"you@yours.com"},currency:"USD",language:"english-us",cartStyle:"div",cartColumns:[{attr:"name",label:"Name"},{attr:"price",label:"Price",view:"currency"},{view:"decrement",label:!1},{attr:"quantity",label:"Qty"},{view:"increment",label:!1},{attr:"total",label:"SubTotal",view:"currency"},{view:"remove",text:"Remove",label:!1}],excludeFromCheckout:["thumb"],shippingFlatRate:0,shippingQuantityRate:0,shippingTotalRate:0,shippingCustom:null,taxRate:0,taxShipping:!1,data:{}},p=function(t){return b(t)?p.ready(t):g(t,"object")?p.extend(d,t):void 0};return p.extend=function(t,e){for(var n in v(e)&&(e=t,t=p),e)Object.prototype.hasOwnProperty.call(e,n)&&(t[n]=e[n]);return t},p.extend({copy:function(t){return(t=C(t)).init(),t}}),p.extend({isReady:!1,add:function(t,e){var n=new p.Item(t||{}),t=!0,e=!0===e&&e;return!(!e&&!1===(t=p.trigger("beforeAdd",[n])))&&((t=p.has(n))?(t.increment(n.quantity()),n=t):o[n.id()]=n,p.update(),e||p.trigger("afterAdd",[n,v(t)]),n)},each:function(t,e){var n,r,a,i=0;if(b(t))r=t,a=o;else{if(!b(e))return;r=e,a=t}for(n in a)if(Object.prototype.hasOwnProperty.call(a,n)){if(!1===r.call(p,a[n],i,n))break;i+=1}},find:function(t){var e=[];return g(o[t],"object")?o[t]:(g(t,"object")?p.each(function(r){var a=!0;p.each(t,function(t,e,n){return g(t,x)?t.match(/<=.*/)?(t=parseFloat(t.replace("<=","")),r.get(n)&&parseFloat(r.get(n))<=t||(a=!1)):t.match(/</)?(t=parseFloat(t.replace("<","")),r.get(n)&&parseFloat(r.get(n))<t||(a=!1)):t.match(/>=/)?(t=parseFloat(t.replace(">=","")),r.get(n)&&parseFloat(r.get(n))>=t||(a=!1)):t.match(/>/)?(t=parseFloat(t.replace(">","")),r.get(n)&&parseFloat(r.get(n))>t||(a=!1)):r.get(n)&&r.get(n)===t||(a=!1):r.get(n)&&r.get(n)===t||(a=!1),a}),a&&e.push(r)}):v(t)&&p.each(function(t){e.push(t)}),e)},items:function(){return this.find()},has:function(e){var n=!1;return p.each(function(t){t.equals(e)&&(n=t)}),n},empty:function(){var e={};p.each(function(t){!1===t.remove(!0)&&(e[t.id()]=t)}),o=e,p.update()},quantity:function(){var e=0;return p.each(function(t){e+=t.quantity()}),e},total:function(){var e=0;return p.each(function(t){e+=t.total()}),e},grandTotal:function(){return p.total()+p.tax()+p.shipping()},update:function(){p.save(),p.trigger("update")},init:function(){p.load(),p.update(),p.ready()},$:function(t){return new p.ELEMENT(t)},$create:function(t){return p.$(y.createElement(t))},setupViewTool:function(){var t,e,n=m;for(e in r)if(Object.prototype.hasOwnProperty.call(r,e)&&m[e]&&(t=r[e].replace("*",e).split("."),(t=t.shift())&&(n=n[t]),"function"==typeof n)){u=n,p.extend(p.ELEMENT._,c[e]);break}},ids:function(){var e=[];return p.each(function(t){e.push(t.id())}),e},save:function(){p.trigger("beforeSave");var e={};p.each(function(t){e[t.id()]=p.extend(t.fields(),t.options())}),n.setItem(i+"_items",JSON.stringify(e)),p.trigger("afterSave")},load:function(){o={};var t=n.getItem(i+"_items");if(t){try{p.each(JSON.parse(t),function(t){p.add(t,!0)})}catch(t){p.error("Error Loading data: "+t)}p.trigger("load")}},ready:function(t){b(t)?p.isReady?t.call(p):p.bind("ready",t):v(t)&&!p.isReady&&(p.trigger("ready"),p.isReady=!0)},error:function(t){var e="";g(t,x)?e=t:g(t,"object")&&g(t.message,x)&&(e=t.message);try{h.log("simpleCart(js) Error: "+e)}catch(t){}p.trigger("error",t)}}),p.extend({tax:function(){var t=d.taxShipping?p.total()+p.shipping():p.total(),e=p.taxRate()*t;return p.each(function(t){t.get("tax")?e+=t.get("tax"):t.get("taxRate")&&(e+=t.get("taxRate")*t.total())}),parseFloat(e)},taxRate:function(){return d.taxRate||0},shipping:function(t){if(!b(t)){var e=d.shippingQuantityRate*p.quantity()+d.shippingTotalRate*p.total()+d.shippingFlatRate;return b(d.shippingCustom)&&(e+=d.shippingCustom.call(p)),p.each(function(t){e+=parseFloat(t.get("shipping")||0)}),parseFloat(e)}p({shippingCustom:t})}}),l={attr:function(t,e){return t.get(e.attr)||""},currency:function(t,e){return p.toCurrency(t.get(e.attr)||0)},link:function(t,e){return"<a href='"+t.get(e.attr)+"'>"+e.text+"</a>"},decrement:function(t,e){return"<a href='javascript:;' class='"+i+"_decrement'>"+(e.text||"-")+"</a>"},increment:function(t,e){return"<a href='javascript:;' class='"+i+"_increment'>"+(e.text||"+")+"</a>"},image:function(t,e){return"<img src='"+t.get(e.attr)+"'/>"},input:function(t,e){return"<input type='text' value='"+t.get(e.attr)+"' class='"+i+"_input'/>"},remove:function(t,e){return"<a href='javascript:;' class='"+i+"_remove'>"+(e.text||"X")+"</a>"}},p.extend({writeCart:function(t){var e,n,r="table"===(u=d.cartStyle.toLowerCase()),a=r?"tr":"div",i=r?"th":"div",o=r?"td":"div",c=p.$create(u),u=p.$create(a).addClass("headerRow");for(p.$(t).html(" ").append(c),c.append(u),r=0,n=d.cartColumns.length;r<n;r+=1)t="item-"+((e=s(d.cartColumns[r])).attr||e.view||e.label||e.text||"cell")+" "+e.className,e=e.label||"",u.append(p.$create(i).addClass(t).html(e));return p.each(function(t,e){p.createCartRow(t,e,a,o,c)}),c},createCartRow:function(t,e,n,r,a){var i,o,c;for(e=p.$create(n).addClass("itemRow row-"+e+" "+(e%2?"even":"odd")).attr("id","cartItem_"+t.id()),a.append(e),a=0,n=d.cartColumns.length;a<n;a+=1)o="item-"+((i=s(d.cartColumns[a])).attr||(g(i.view,x)?i.view:i.label||i.text||"cell"))+" "+i.className,c=t,c=(b(i.view)?i.view:g(i.view,x)&&b(l[i.view])?l[i.view]:l.attr).call(p,c,i),o=p.$create(r).addClass(o).html(c),e.append(o);return e}}),p.Item=function(t){function n(){g(r.price,x)&&(r.price=parseFloat(r.price.replace(p.currency().decimal,".").replace(/[^0-9\.]+/gi,""))),isNaN(r.price)&&(r.price=0),r.price<0&&(r.price=0),g(r.quantity,x)&&(r.quantity=parseInt(r.quantity.replace(p.currency().delimiter,""),10)),isNaN(r.quantity)&&(r.quantity=1),r.quantity<=0&&i.remove()}var r={},i=this;for(g(t,"object")&&p.extend(r,t),a+=1,r.id=r.id||"SCI-"+a;!v(o[r.id]);)a+=1,r.id="SCI-"+a;i.get=function(t,e){e=!e;return v(t)?t:b(r[t])?r[t].call(i):v(r[t])?b(i[t])&&e?i[t].call(i):(!v(i[t])&&e?i:r)[t]:r[t]},i.set=function(t,e){return v(t)||(r[t.toLowerCase()]=e,"price"!==t.toLowerCase()&&"quantity"!==t.toLowerCase()||n()),i},i.equals=function(t){for(var e in r)if(Object.prototype.hasOwnProperty.call(r,e)&&"quantity"!==e&&"id"!==e&&t.get(e)!==r[e])return!1;return!0},i.options=function(){var a={};return p.each(r,function(t,e,n){var r=!0;p.each(i.reservedFields(),function(t){return t===n&&(r=!1),r}),r&&(a[n]=i.get(n))}),a},n()},p.Item._=p.Item.prototype={increment:function(t){return t=parseInt(t||1,10),this.quantity(this.quantity()+t),this.quantity()<1?(this.remove(),null):this},decrement:function(t){return this.increment(-parseInt(t||1,10))},remove:function(t){return!1!==p.trigger("beforeRemove",[o[this.id()]])&&(delete o[this.id()],t||p.update(),null)},reservedFields:function(){return"quantity id item_number price name shipping tax taxRate".split(" ")},fields:function(){var e={},n=this;return p.each(n.reservedFields(),function(t){n.get(t)&&(e[t]=n.get(t))}),e},quantity:function(t){return v(t)?parseInt(this.get("quantity",!0)||1,10):this.set("quantity",t)},price:function(t){return v(t)?parseFloat(this.get("price",!0).toString().replace(p.currency().symbol,"").replace(p.currency().delimiter,"")||1):this.set("price",parseFloat(t.toString().replace(p.currency().symbol,"").replace(p.currency().delimiter,"")))},id:function(){return this.get("id",!1)},total:function(){return this.quantity()*this.price()}},p.extend({checkout:function(){var t;"custom"===d.checkout.type.toLowerCase()&&b(d.checkout.fn)?d.checkout.fn.call(p,d.checkout):b(p.checkout[d.checkout.type])?(t=p.checkout[d.checkout.type].call(p,d.checkout)).data&&t.action&&t.method&&!1!==p.trigger("beforeCheckout",[t.data])&&p.generateAndSendForm(t):p.error("No Valid Checkout Method Specified")},extendCheckout:function(t){return p.extend(p.checkout,t)},generateAndSendForm:function(t){var r=p.$create("form");r.attr("style","display:none;"),r.attr("action",t.action),r.attr("method",t.method),p.each(t.data,function(t,e,n){r.append(p.$create("input").attr("type","hidden").attr("name",n).val(t))}),p.$("body").append(r),r.el.submit(),r.remove()}}),p.extendCheckout({PayPal:function(t){if(!t.email)return p.error("No email provided for PayPal checkout");var o={cmd:"_cart",upload:"1",currency_code:p.currency().code,business:t.email,rm:"GET"===t.method?"0":"2",tax_cart:(+p.tax()).toFixed(2),handling_cart:(+p.shipping()).toFixed(2),charset:"utf-8"},e=t.sandbox?"https://www.sandbox.paypal.com/cgi-bin/webscr":"https://www.paypal.com/cgi-bin/webscr",n="GET"===t.method?"GET":"POST";return t.success&&(o.return=t.success),t.cancel&&(o.cancel_return=t.cancel),t.notify&&(o.notify_url=t.notify),p.each(function(t,e){var r,a=e+1,n=t.options(),i=0;o["item_name_"+a]=t.get("name"),o["quantity_"+a]=t.quantity(),o["amount_"+a]=(+t.price()).toFixed(2),o["item_number_"+a]=t.get("item_number")||a,p.each(n,function(t,e,n){e<10&&(r=!0,p.each(d.excludeFromCheckout,function(t){t===n&&(r=!1)}),r&&(i+=1,o["on"+e+"_"+a]=n,o["os"+e+"_"+a]=t))}),o["option_index_"+e]=Math.min(10,i)}),{action:e,method:n,data:o}},GoogleCheckout:function(t){if(!t.merchantID)return p.error("No merchant id provided for GoogleCheckout");if("USD"!==p.currency().code&&"GBP"!==p.currency().code)return p.error("Google Checkout only accepts USD and GBP");var n={ship_method_name_1:"Shipping",ship_method_price_1:p.shipping(),ship_method_currency_1:p.currency().code,_charset_:""},e="https://checkout.google.com/api/checkout/v2/checkoutForm/Merchant/"+t.merchantID;return t="GET"===t.method?"GET":"POST",p.each(function(t,e){var r,e=e+1,a=[];n["item_name_"+e]=t.get("name"),n["item_quantity_"+e]=t.quantity(),n["item_price_"+e]=t.price(),n["item_currency_ "+e]=p.currency().code,n["item_tax_rate"+e]=t.get("taxRate")||p.taxRate(),p.each(t.options(),function(t,e,n){r=!0,p.each(d.excludeFromCheckout,function(t){t===n&&(r=!1)}),r&&a.push(n+": "+t)}),n["item_description_"+e]=a.join(", ")}),{action:e,method:t,data:n}},AmazonPayments:function(n){if(!n.merchant_signature)return p.error("No merchant signature provided for Amazon Payments");if(!n.merchant_id)return p.error("No merchant id provided for Amazon Payments");if(!n.aws_access_key_id)return p.error("No AWS access key id provided for Amazon Payments");var r={aws_access_key_id:n.aws_access_key_id,merchant_signature:n.merchant_signature,currency_code:p.currency().code,tax_rate:p.taxRate(),weight_unit:n.weight_unit||"lb"},t="https://payments"+(n.sandbox?"-sandbox":"")+".amazon.com/checkout/"+n.merchant_id,e="GET"===n.method?"GET":"POST";return p.each(function(t,e){var e=e+1,a=[];r["item_title_"+e]=t.get("name"),r["item_quantity_"+e]=t.quantity(),r["item_price_"+e]=t.price(),r["item_sku_ "+e]=t.get("sku")||t.id(),r["item_merchant_id_"+e]=n.merchant_id,t.get("weight")&&(r["item_weight_"+e]=t.get("weight")),d.shippingQuantityRate&&(r["shipping_method_price_per_unit_rate_"+e]=d.shippingQuantityRate),p.each(t.options(),function(t,e,n){var r=!0;p.each(d.excludeFromCheckout,function(t){t===n&&(r=!1)}),r&&"weight"!==n&&"tax"!==n&&a.push(n+": "+t)}),r["item_description_"+e]=a.join(", ")}),{action:t,method:e,data:r}},SendForm:function(t){if(!t.url)return p.error("URL required for SendForm Checkout");var n={currency:p.currency().code,shipping:p.shipping(),tax:p.tax(),taxRate:p.taxRate(),itemCount:p.find({}).length},e=t.url,r="GET"===t.method?"GET":"POST";return p.each(function(t,e){var r,e=e+1,a=[];n["item_name_"+e]=t.get("name"),n["item_quantity_"+e]=t.quantity(),n["item_price_"+e]=t.price(),p.each(t.options(),function(t,e,n){r=!0,p.each(d.excludeFromCheckout,function(t){t===n&&(r=!1)}),r&&a.push(n+": "+t)}),n["item_options_"+e]=a.join(", ")}),t.success&&(n.return=t.success),t.cancel&&(n.cancel_return=t.cancel),t.extra_data&&(n=p.extend(n,t.extra_data)),{action:e,method:r,data:n}}}),(t={bind:function(t,e){if(!b(e))return this;this._events||(this._events={});t=t.split(/ +/);return p.each(t,function(t){!0===this._events[t]?e.apply(this):v(this._events[t])?this._events[t]=[e]:this._events[t].push(e)}),this},trigger:function(t,e){var n,r,a=!0;if(this._events||(this._events={}),!v(this._events[t])&&b(this._events[t][0]))for(n=0,r=this._events[t].length;n<r;n+=1)a=this._events[t][n].apply(this,e||[]);return!1!==a}}).on=t.bind,p.extend(t),p.extend(p.Item._,t),p(t={beforeAdd:null,afterAdd:null,load:null,beforeSave:null,afterSave:null,update:null,ready:null,checkoutSuccess:null,checkoutFail:null,beforeCheckout:null,beforeRemove:null}),p.each(t,function(t,e,n){p.bind(n,function(){b(d[n])&&d[n].apply(this,arguments)})}),p.extend({toCurrency:function(t,e){var n=parseFloat(t),t=e||{},t=p.extend(p.extend({symbol:"$",decimal:".",delimiter:",",accuracy:2,after:!1},p.currency()),t),n=(e=n.toFixed(t.accuracy).split("."))[1],e=e[0],e=p.chunk(e.reverse(),3).join(t.delimiter.reverse()).reverse();return(t.after?"":t.symbol)+e+(n?t.decimal+n:"")+(t.after?t.symbol:"")},chunk:function(t,e){return void 0===e&&(e=2),t.match(RegExp(".{1,"+e+"}","g"))||[]}}),String.prototype.reverse=function(){return this.split("").reverse().join("")},p.extend({currency:function(t){if(g(t,x)&&!v(f[t]))d.currency=t;else{if(!g(t,"object"))return f[d.currency];f[t.code]=t,d.currency=t.code}}}),p.extend({bindOutlets:function(t){p.each(t,function(t,e,n){p.bind("update",function(){p.setOutlet("."+i+"_"+n,t)})})},setOutlet:function(t,e){e=e.call(p,t);g(e,"object")&&e.el?p.$(t).html(" ").append(e):v(e)||p.$(t).html(e)},bindInputs:function(t){p.each(t,function(t){p.setInput("."+i+"_"+t.selector,t.event,t.callback)})},setInput:function(t,e,n){p.$(t).live(e,n)}}),p.ELEMENT=function(t){this.create(t),this.selector=t||null},p.extend(c,{MooTools:{text:function(t){return this.attr("text",t)},html:function(t){return this.attr("html",t)},val:function(t){return this.attr("value",t)},attr:function(t,e){return v(e)?this.el[0]&&this.el[0].get(t):(this.el.set(t,e),this)},remove:function(){return this.el.dispose(),null},addClass:function(t){return this.el.addClass(t),this},removeClass:function(t){return this.el.removeClass(t),this},append:function(t){return this.el.adopt(t.el),this},each:function(r){return b(r)&&p.each(this.el,function(t,e,n){r.call(e,e,t,n)}),this},click:function(n){return b(n)?this.each(function(e){e.addEvent("click",function(t){n.call(e,t)})}):v(n)&&this.el.fireEvent("click"),this},live:function(t,n){var e=this.selector;b(n)&&p.$("body").el.addEvent(t+":relay("+e+")",function(t,e){n.call(e,t)})},match:function(t){return this.el.match(t)},parent:function(){return p.$(this.el.getParent())},find:function(t){return p.$(this.el.getElements(t))},closest:function(t){return p.$(this.el.getParent(t))},descendants:function(){return this.find("*")},tag:function(){return this.el[0].tagName},submit:function(){return this.el[0].submit(),this},create:function(t){this.el=u(t)}},Prototype:{text:function(n){return v(n)?this.el[0].innerHTML:(this.each(function(t,e){$(e).update(n)}),this)},html:function(t){return this.text(t)},val:function(t){return this.attr("value",t)},attr:function(n,r){return v(r)?this.el[0].readAttribute(n):(this.each(function(t,e){$(e).writeAttribute(n,r)}),this)},append:function(e){return this.each(function(t,n){e.el?e.each(function(t,e){$(n).appendChild(e)}):_(e)&&$(n).appendChild(e)}),this},remove:function(){return this.each(function(t,e){$(e).remove()}),this},addClass:function(n){return this.each(function(t,e){$(e).addClassName(n)}),this},removeClass:function(n){return this.each(function(t,e){$(e).removeClassName(n)}),this},each:function(r){return b(r)&&p.each(this.el,function(t,e,n){r.call(e,e,t,n)}),this},click:function(n){return b(n)?this.each(function(t,e){$(e).observe("click",function(t){n.call(e,t)})}):v(n)&&this.each(function(t,e){$(e).fire("click")}),this},live:function(t,n){var r;b(n)&&(r=this.selector,y.observe(t,function(t,e){e===u(t).findElement(r)&&n.call(e,t)}))},parent:function(){return p.$(this.el.up())},find:function(t){return p.$(this.el.getElementsBySelector(t))},closest:function(t){return p.$(this.el.up(t))},descendants:function(){return p.$(this.el.descendants())},tag:function(){return this.el.tagName},submit:function(){this.el[0].submit()},create:function(t){g(t,x)?this.el=u(t):_(t)&&(this.el=[t])}},jQuery:{passthrough:function(t,e){return v(e)?this.el[t]():(this.el[t](e),this)},text:function(t){return this.passthrough("text",t)},html:function(t){return this.passthrough("html",t)},val:function(t){return this.passthrough("val",t)},append:function(t){return this.el.append(t.el||t),this},attr:function(t,e){return v(e)?this.el.attr(t):(this.el.attr(t,e),this)},remove:function(){return this.el.remove(),this},addClass:function(t){return this.el.addClass(t),this},removeClass:function(t){return this.el.removeClass(t),this},each:function(t){return this.passthrough("each",t)},click:function(t){return this.passthrough("click",t)},live:function(t,e){return u(y).delegate(this.selector,t,e),this},parent:function(){return p.$(this.el.parent())},find:function(t){return p.$(this.el.find(t))},closest:function(t){return p.$(this.el.closest(t))},tag:function(){return this.el[0].tagName},descendants:function(){return p.$(this.el.find("*"))},submit:function(){return this.el.submit()},create:function(t){this.el=u(t)}}}),p.ELEMENT._=p.ELEMENT.prototype,p.ready(p.setupViewTool),p.ready(function(){p.bindOutlets({total:function(){return p.toCurrency(p.total())},quantity:function(){return p.quantity()},items:function(t){p.writeCart(t)},tax:function(){return p.toCurrency(p.tax())},taxRate:function(){return p.taxRate().toFixed()},shipping:function(){return p.toCurrency(p.shipping())},grandTotal:function(){return p.toCurrency(p.grandTotal())}}),p.bindInputs([{selector:"checkout",event:"click",callback:function(){p.checkout()}},{selector:"empty",event:"click",callback:function(){p.empty()}},{selector:"increment",event:"click",callback:function(){p.find(p.$(this).closest(".itemRow").attr("id").split("_")[1]).increment(),p.update()}},{selector:"decrement",event:"click",callback:function(){p.find(p.$(this).closest(".itemRow").attr("id").split("_")[1]).decrement(),p.update()}},{selector:"remove",event:"click",callback:function(){p.find(p.$(this).closest(".itemRow").attr("id").split("_")[1]).remove()}},{selector:"input",event:"change",callback:function(){var e=p.$(this),n=e.parent(),t=n.attr("class").split(" ");p.each(t,function(t){t.match(/item-.+/i)&&(t=t.split("-")[1],p.find(n.closest(".itemRow").attr("id").split("_")[1]).set(t,e.val()),p.update())})}},{selector:"shelfItem .item_add",event:"click",callback:function(){var a={};p.$(this).closest("."+i+"_shelfItem").descendants().each(function(t,e){var r=p.$(e);r.attr("class")&&r.attr("class").match(/item_.+/)&&!r.attr("class").match(/item_add/)&&p.each(r.attr("class").split(" "),function(t){var e,n;if(t.match(/item_.+/)){switch(t=t.split("_")[1],e="",r.tag().toLowerCase()){case"input":case"textarea":case"select":(n=r.attr("type"))&&("checkbox"!==n.toLowerCase()&&"radio"!==n.toLowerCase()||!r.attr("checked"))&&"text"!==n.toLowerCase()&&"number"!==n.toLowerCase()||(e=r.val());break;case"img":e=r.attr("src");break;default:e=r.text()}null!==e&&""!==e&&(a[t.toLowerCase()]=a[t.toLowerCase()]?a[t.toLowerCase()]+", "+e:e)}})}),p.add(a)}}])}),y.addEventListener?m.DOMContentLoaded=function(){y.removeEventListener("DOMContentLoaded",DOMContentLoaded,!1),p.init()}:y.attachEvent&&(m.DOMContentLoaded=function(){"complete"===y.readyState&&(y.detachEvent("onreadystatechange",DOMContentLoaded),p.init())}),function(){if("complete"===y.readyState)return setTimeout(p.init,1);if(y.addEventListener)y.addEventListener("DOMContentLoaded",DOMContentLoaded,!1),m.addEventListener("load",p.init,!1);else if(y.attachEvent){y.attachEvent("onreadystatechange",DOMContentLoaded),m.attachEvent("onload",p.init);var t=!1;try{t=null===m.frameElement}catch(t){}y.documentElement.doScroll&&t&&e()}}(),p};m.simpleCart=C()}(window,document),JSON=JSON||{},function(){function p(t){return t<10?"0"+t:t}function f(t){return e.lastIndex=0,e.test(t)?'"'+t.replace(e,function(t){var e=C[t];return"string"==typeof e?e:"\\u"+("0000"+t.charCodeAt(0).toString(16)).slice(-4)})+'"':'"'+t+'"'}function s(t,e){var n,r,a,i,o,c=h,u=e[t];switch(u&&"object"==typeof u&&"function"==typeof u.toJSON&&(u=u.toJSON(t)),"function"==typeof q&&(u=q.call(e,t,u)),typeof u){case"string":return f(u);case"number":return isFinite(u)?String(u):"null";case"boolean":case"null":return String(u);case"object":if(!u)return"null";if(h+=y,o=[],"[object Array]"===Object.prototype.toString.apply(u)){for(i=u.length,n=0;n<i;n+=1)o[n]=s(n,u)||"null";return a=0===o.length?"[]":h?"[\n"+h+o.join(",\n"+h)+"\n"+c+"]":"["+o.join(",")+"]",h=c,a}if(q&&"object"==typeof q)for(i=q.length,n=0;n<i;n+=1)"string"==typeof q[n]&&((a=s(r=q[n],u))&&o.push(f(r)+(h?": ":":")+a));else for(r in u)Object.prototype.hasOwnProperty.call(u,r)&&(a=s(r,u))&&o.push(f(r)+(h?": ":":")+a);return a=0===o.length?"{}":h?"{\n"+h+o.join(",\n"+h)+"\n"+c+"}":"{"+o.join(",")+"}",h=c,a}}"function"!=typeof Date.prototype.toJSON&&(Date.prototype.toJSON=function(){return isFinite(this.valueOf())?this.getUTCFullYear()+"-"+p(this.getUTCMonth()+1)+"-"+p(this.getUTCDate())+"T"+p(this.getUTCHours())+":"+p(this.getUTCMinutes())+":"+p(this.getUTCSeconds())+"Z":null},String.prototype.toJSON=Number.prototype.toJSON=Boolean.prototype.toJSON=function(){return this.valueOf()});var k=/[\u0000\u00ad\u0600-\u0604\u070f\u17b4\u17b5\u200c-\u200f\u2028-\u202f\u2060-\u206f\ufeff\ufff0-\uffff]/g,e=/[\\\"\x00-\x1f\x7f-\x9f\u00ad\u0600-\u0604\u070f\u17b4\u17b5\u200c-\u200f\u2028-\u202f\u2060-\u206f\ufeff\ufff0-\uffff]/g,h,y,C={"\b":"\\b","\t":"\\t","\n":"\\n","\f":"\\f","\r":"\\r",'"':'\\"',"\\":"\\\\"},q;"function"!=typeof JSON.stringify&&(JSON.stringify=function(t,e,n){var r;if(y=h="","number"==typeof n)for(r=0;r<n;r+=1)y+=" ";else"string"==typeof n&&(y=n);if((q=e)&&"function"!=typeof e&&("object"!=typeof e||"number"!=typeof e.length))throw Error("JSON.stringify");return s("",{"":t})}),"function"!=typeof JSON.parse&&(JSON.parse=function(e,f){function h(t,e){var n,r,a=t[e];if(a&&"object"==typeof a)for(n in a)Object.prototype.hasOwnProperty.call(a,n)&&(r=h(a,n),void 0!==r?a[n]=r:delete a[n]);return f.call(t,e,a)}var n;if(e=String(e),k.lastIndex=0,k.test(e)&&(e=e.replace(k,function(t){return"\\u"+("0000"+t.charCodeAt(0).toString(16)).slice(-4)})),/^[\],:{}\s]*$/.test(e.replace(/\\(?:["\\\/bfnrt]|u[0-9a-fA-F]{4})/g,"@").replace(/"[^"\\\n\r]*"|true|false|null|-?\d+(?:\.\d*)?(?:[eE][+\-]?\d+)?/g,"]").replace(/(?:^|:|,)(?:\s*\[)+/g,"")))return n=eval("("+e+")"),"function"==typeof f?h({"":n},""):n;throw new SyntaxError("JSON.parse")})}(),function(){if(!this.localStorage)if(this.globalStorage)try{this.localStorage=this.globalStorage}catch(t){}else{var t,n,r=document.createElement("div");r.style.display="none",document.getElementsByTagName("head")[0].appendChild(r),r.addBehavior&&(r.addBehavior("#default#userdata"),t=this.localStorage={length:0,setItem:function(t,e){r.load("localStorage"),t=n(t),r.getAttribute(t)||this.length++,r.setAttribute(t,e),r.save("localStorage")},getItem:function(t){return r.load("localStorage"),t=n(t),r.getAttribute(t)},removeItem:function(t){r.load("localStorage"),t=n(t),r.removeAttribute(t),r.save("localStorage"),this.length=0},clear:function(){r.load("localStorage");for(var t=0;attr=r.XMLDocument.documentElement.attributes[t++];)r.removeAttribute(attr.name);r.save("localStorage"),this.length=0},key:function(t){return r.load("localStorage"),r.XMLDocument.documentElement.attributes[t]}},n=function(t){return t.replace(/[^-._0-9A-Za-z\xb7\xc0-\xd6\xd8-\xf6\xf8-\u037d\u37f-\u1fff\u200c-\u200d\u203f\u2040\u2070-\u218f]/g,"-")},r.load("localStorage"),t.length=r.XMLDocument.documentElement.attributes.length)}}(),$(document).ready(function(){simpleCart({checkout:{type:paymentOption,email:paypalMail}}),simpleCart.currency(currencyOption),simpleCart({shippingQuantityRate:shippingOption})}),$(document).ready(function(){simpleCart({cartColumns:[{view:"image",attr:"thumb",label:!1},{attr:"name",label:!1},{attr:"price",label:!1,view:"currency"},{attr:"size",label:!1},{view:"decrement",label:!1,text:"<i class='fa fa-minus'></i>"},{attr:"quantity",label:!1},{view:"increment",label:!1,text:"<i class='fa fa-plus'></i>"},{attr:"total",label:!1,view:"currency"},{view:"remove",text:"<i class='fa fa-trash'></i>",label:!1}]})});

//]]>
</script>

<b:if cond='data:view.isMultipleItems'>

<!-- Page Counter - Edit Number Of Post To Show On Each Page -->

<script type='text/javascript'>
var home_page=&quot;/&quot;;
var urlactivepage=location.href;
var postperpage=16;
var numshowpage=2;
var upPageWord =&#39;Previous&#39;;
var downPageWord =&#39;Next&#39;;

//<![CDATA[
eval(function(p,a,c,k,e,r){e=function(c){return(c<a?'':e(parseInt(c/a)))+((c=c%a)>35?String.fromCharCode(c+29):c.toString(36))};if(!''.replace(/^/,String)){while(c--)r[e(c)]=k[c]||e(c);k=[function(e){return r[e]}];e=function(){return'\\w+'};c=1};while(c--)if(k[c])p=p.replace(new RegExp('\\b'+e(c)+'\\b','g'),k[c]);return p}('5 G;5 i;5 b;5 n;1f();x 1g(15){5 6=\'\';H=I(K/2);3(H==K-H){K=H*2+1}J=b-H;3(J<1)J=1;o=I(15/j)+1;3(o-1==15/j)o=o-1;L=J+K-1;3(L>o)L=o;6+="<4 e=\'1y\'>1z "+b+\' 1A \'+o+"</4>";5 16=I(b)-1;3(b>1){3(b==2){3(i=="w"){6+=\'<4 e="1B"><a f="\'+y+\'">\'+M+\'</a></4>\'}c{6+=\'<4 e="k"><a f="/r/s/\'+n+\'?&7-l=\'+j+\'">\'+M+\'</a></4>\'}}c{3(i=="w"){6+=\'<4 e="k"><a f="#" z="N(\'+16+\');A B">\'+M+\'</a></4>\'}c{6+=\'<4 e="k"><a f="#" z="O(\'+16+\');A B">\'+M+\'</a></4>\'}}}1h(5 g=J;g<=L;g++){3(b==g){6+=\'<4 e="1C">\'+g+\'</4>\'}c 3(g==1){3(i=="w"){6+=\'<4 e="k"><a f="\'+y+\'">1</a></4>\'}c{6+=\'<4 e="k"><a f="/r/s/\'+n+\'?&7-l=\'+j+\'">1</a></4>\'}}c{3(i=="w"){6+=\'<4 e="k"><a f="#" z="N(\'+g+\');A B">\'+g+\'</a></4>\'}c{6+=\'<4 e="k"><a f="#" z="O(\'+g+\');A B">\'+g+\'</a></4>\'}}}5 17=I(b)+1;3(b<o){3(i=="w"){6+=\'<4 e="k"><a f="#" z="N(\'+17+\');A B">\'+1i+\'</a></4>\'}c{6+=\'<4 e="k"><a f="#" z="O(\'+17+\');A B">\'+1i+\'</a></4>\'}}5 C=u.1D("C");5 18=u.1E("1F-1G");1h(5 p=0;p<C.P;p++){C[p].1j=6}3(C&&C.P>0){6=\'\'}3(18){18.1j=6}}x 1a(Q){5 R=Q.R;5 1k=I(R.1H$1I.$t,10);1g(1k)}x 1f(){5 d=m;3(d.9("/r/s/")!=-1){3(d.9("?S-7")!=-1){n=d.D(d.9("/r/s/")+14,d.9("?S-7"))}c{n=d.D(d.9("/r/s/")+14,d.9("?&7"))}}3(d.9("?q=")==-1&&d.9(".6")==-1){3(d.9("/r/s/")==-1){i="w";3(m.9("#E=")!=-1){b=m.D(m.9("#E=")+8,m.P)}c{b=1}u.1l("<h T=\\""+y+"U/V/W?7-l=1&X=Y-Z-h&11=1a\\"><\\/h>")}c{i="s";3(d.9("&7-l=")==-1){j=1J}3(m.9("#E=")!=-1){b=m.D(m.9("#E=")+8,m.P)}c{b=1}u.1l(\'<h T="\'+y+\'U/V/W/-/\'+n+\'?X=Y-Z-h&11=1a&7-l=1" ><\\/h>\')}}}x N(F){12=(F-1)*j;G=F;5 13=u.1m(\'1n\')[0];5 v=u.1o(\'h\');v.1p=\'1q/1r\';v.1s("T",y+"U/V/W?1t-1u="+12+"&7-l=1&X=Y-Z-h&11=1b");13.1v(v)}x O(F){12=(F-1)*j;G=F;5 13=u.1m(\'1n\')[0];5 v=u.1o(\'h\');v.1p=\'1q/1r\';v.1s("T",y+"U/V/W/-/"+n+"?1t-1u="+12+"&7-l=1&X=Y-Z-h&11=1b");13.1v(v)}x 1b(Q){1c=Q.R.1K[0];5 1w=1c.1x.$t.D(0,19)+1c.1x.$t.D(1L,1M);5 1d=1N(1w);3(i=="w"){5 1e="/r?S-7="+1d+"&7-l="+j+"#E="+G}c{5 1e="/r/s/"+n+"?S-7="+1d+"&7-l="+j+"#E="+G}1O.f=1e}',62,113,'|||if|span|var|html|max||indexOf||nomerhal|else|thisUrl|class|href|jj|script|jenis|postperpage|showpageNum|results|urlactivepage|lblname1|maksimal|||search|label||document|newInclude|page|function|home_page|onclick|return|false|pageArea|substring|PageNo|numberpage|nopage|nomerkiri|parseInt|mulai|numshowpage|akhir|upPageWord|redirectpage|redirectlabel|length|root|feed|updated|src|feeds|posts|summary|alt|json|in||callback|jsonstart|nBody||banyakdata|prevnomer|nextnomer|blogPager||hitungtotaldata|finddatepost|post|timestamp|alamat|halamanblogger|loophalaman|for|downPageWord|innerHTML|totaldata|write|getElementsByTagName|head|createElement|type|text|javascript|setAttribute|start|index|appendChild|timestamp1|published|showpageOf|Page|of|showpage|showpagePoint|getElementsByName|getElementById|blog|pager|openSearch|totalResults|20|entry|23|29|encodeURIComponent|location'.split('|'),0,{}))
//]]>
</script>
</b:if>

<b:if cond='!data:view.isMultipleItems'>
<script id='main-js' type='text/javascript'>
//<![CDATA[ 

var AJAX_LOADING_IMAGE = '//1.bp.blogspot.com/-Qu3p5sfG0_0/U7-BqkiW-nI/AAAAAAAAIVg/fqpTyUkrFkQ/s1600/ajax-loader.gif';
var CART_CACHE_DURATION = 7; // days
var Feed_URL = '/feeds';

// PLUGINS
function azion_translated_mapper(t){var e=t;return $(azion_easy_text_picker[0]+t+azion_easy_text_picker[1]).each(function(){e=$(this).html()}),e}function azion_thumbnail_handler(){$(azion_easy_text_picker[15]).each(function(){$(this).removeAttr(azion_easy_text_picker[16]),$(this).removeAttr(azion_easy_text_picker[17]);var t=$(this).attr(azion_easy_text_picker[18]);null!=t&&(-1!=t.indexOf(azion_easy_text_picker[19])?(t=t.replace(azion_easy_text_picker[20],azion_easy_text_picker[21]),$(this).after(azion_easy_text_picker[22]+t+azion_easy_text_picker[23]),$(this).remove()):-1!=t.indexOf(azion_easy_text_picker[24])&&-1!=t.indexOf(azion_easy_text_picker[25])&&(t=t.replace(azion_easy_text_picker[26],azion_easy_text_picker[27]),$(this).after(azion_easy_text_picker[28]+t+azion_easy_text_picker[29]),$(this).remove()))})}function azion_call_back_alternative(t){var e,a;"undefined"==azion_easy_text_picker[30]&&azion_easy_text_picker[31],typeof e==azion_easy_text_picker[32]&&(e=150),typeof a==azion_easy_text_picker[33]&&(a=azion_easy_text_picker[34]);var i=new Object;if(i.id=azion_easy_text_picker[35],i.published=azion_easy_text_picker[36],i.cate=new Array,i.title=azion_easy_text_picker[37],i.content=azion_easy_text_picker[38],i.summary=azion_easy_text_picker[39],i.link=azion_easy_text_picker[40],i.reply_label=azion_easy_text_picker[41],i.author=new Object,i.author.name=azion_easy_text_picker[42],i.author.uri=azion_easy_text_picker[43],i.author.avatar=azion_easy_text_picker[44],i.thumbnail=azion_easy_text_picker[45],i.reply_number=0,i.pid=azion_easy_text_picker[46],azion_easy_text_picker[47]in t){var s=t.entry;if(i.id=s.id.$t,page_counter_01=azion_easy_text_picker[48],random_map=i.id.indexOf(page_counter_01),i.id=i.id.substring(random_map+page_counter_01.length),azion_easy_text_picker[49]in s&&(i.published=s.published.$t),azion_easy_text_picker[50]in s)for(level_8=0;level_8<s.category.length;level_8++)i.cate[level_8]=s.category[level_8].term;if(azion_easy_text_picker[51]in s&&(i.title=s.title.$t),azion_easy_text_picker[52]in s&&(i.content=s.content.$t),azion_easy_text_picker[53]in s&&(i.summary=s.summary.$t),i.summary==azion_easy_text_picker[54]&&(i.summary=i.content.replace(/<\S[^>]*>/g,azion_easy_text_picker[55])),i.content==azion_easy_text_picker[56]&&(i.content=i.summary),i.summary.length>e&&(i.summary=i.summary.substring(0,e)+azion_easy_text_picker[57]),azion_easy_text_picker[58]in s)for(level_8=0;level_8<s.link.length;level_8++)s.link[level_8].rel==azion_easy_text_picker[59]&&(i.link=s.link[level_8].href),s.link[level_8].rel==azion_easy_text_picker[60]&&(i.reply_label=s.link[level_8].title);if(a0=s.author[0],azion_easy_text_picker[61]in a0&&(i.author.name=a0.name.$t),azion_easy_text_picker[62]in a0&&(i.author.uri=a0.uri.$t),azion_easy_text_picker[63]in a0&&a0.gd$image.src!=azion_easy_text_picker[64]&&(i.author.avatar=a0.gd$image.src),i.thumbnail=azion_easy_text_picker[65],i.thumbnail==azion_easy_text_picker[66]&&azion_easy_text_picker[67]in s&&(i.thumbnail=s.media$thumbnail.url),i.thumbnail==azion_easy_text_picker[68]&&(i.thumbnail=a),azion_easy_text_picker[69]in s&&(i.reply_number=Number(s.thr$total.$t)),i.reply_label=i.reply_label.replace(i.reply_number+azion_easy_text_picker[70],azion_easy_text_picker[71]),i.reply_to=azion_easy_text_picker[72],i.reply_json=azion_easy_text_picker[73],i.reply_title=azion_easy_text_picker[74],azion_easy_text_picker[75]in s&&(i.reply_to=s[azion_easy_text_picker[76]].href,i.reply_json=s[azion_easy_text_picker[77]].source,i.reply_json=i.reply_json.replace(azion_easy_text_picker[78],azion_easy_text_picker[79]),i.reply_json=i.reply_json+azion_easy_text_picker[80]),azion_easy_text_picker[81]in s)for(level_8=0;level_8<s.gd$extendedProperty.length;level_8++)s.gd$extendedProperty[level_8].name==azion_easy_text_picker[82]&&(i.pid=s.gd$extendedProperty[level_8].value);i.pid=i.pid.replace(azion_easy_text_picker[83],azion_easy_text_picker[84])}return i}function azion_space_write(t,e,a){var i=new Date;i.setDate(i.getDate()+a);i=escape(e)+(null==a?"":azion_easy_text_picker[158]+i.toUTCString())+azion_easy_text_picker[159];return document.cookie=t+azion_easy_text_picker[160]+i,azion_space_send(t)===e}function azion_space_pool(){return!!azion_space_write(azion_easy_text_picker[161],azion_easy_text_picker[162])}function azion_space_send(t){for(var e,a,i=document.cookie.split(azion_easy_text_picker[164]),s=0;s<i.length;s++)if(e=i[s].substr(0,i[s].indexOf(azion_easy_text_picker[165])),a=i[s].substr(i[s].indexOf(azion_easy_text_picker[166])+1),(e=e.replace(/^\s+|\s+$/g,azion_easy_text_picker[167]))==t)return unescape(a);return azion_easy_text_picker[168]}function azion_on_parent(){var t=window.location.href,e=t.indexOf(azion_easy_text_picker[172]);return-1!=e&&(t=t.substring(0,e)),-1!=(e=t.indexOf(azion_easy_text_picker[173]))&&(t=t.substring(0,e)),-1!=(e=t.indexOf(azion_easy_text_picker[174]))&&(t=t.substring(e+3)),(e=t.indexOf(azion_easy_text_picker[175]))==t.length-1&&(t=t.substring(0,e)),t==window.location.hostname}function azion_on_lab(){return-1!=window.location.href.indexOf(azion_easy_text_picker[179])}function azion_on_static(){return-1!=window.location.href.indexOf(azion_easy_text_picker[180])}function azion_on_waiting_list(){var t=window.location.href;return-1!=t.indexOf(azion_easy_text_picker[186])||-1!=t.indexOf(azion_easy_text_picker[187])}function azion_on_checker(){return-1!=window.location.href.indexOf(azion_easy_text_picker[188])}function azion_on_error(){return!azion_on_waiting_list()&&!azion_on_checker()}function azion_box_checker(){try{return window.self!==window.top}catch(t){return!0}}function azion_empty_checker(t){if(t.length)for(var e=0;e<t.length;e++){azion_easy_text_picker[204];if((typeof t[e]!==azion_easy_text_picker[205]?$(t[e]).html():t[e])===azion_easy_text_picker[206])return!0}return!1}function azion_attributes(t){azion_easy_text_picker[207],azion_easy_text_picker[208];var e=azion_easy_text_picker[209];if(t.length)for(var a=0;a<t.length;a++){var i=azion_easy_text_picker[210];(i=typeof t[a]!==azion_easy_text_picker[211]?$(t[a]).html():t[a])&&1<i.length&&!isNaN(i.substring(1))&&(0==i.indexOf(azion_easy_text_picker[212])?i.substring(1):0==i.indexOf(azion_easy_text_picker[213])&&i.substring(1)),i===azion_easy_text_picker[214]&&(e=azion_easy_text_picker[215]+azion_translated_mapper(azion_easy_text_picker[216])+azion_easy_text_picker[217])}return e}azion_easy_text_picker=['.translator i[data-key="','"]',".image-list","id",".widget.Image","","","","h2",".widget-content","img","src",".caption","a","href",".natural-thumbnail img","height","width","src","/s72-c/","/s72-c/","/s1600/",'<img src="','" class="replaced"/>',"youtube.com","/default.","/default.","/mqdefault.",'<img src="','" class="replaced"/>',"undefined","mm/dd/yyyy","undefined","undefined","http://lorempixel.com/300/500/","","","","","","","comments","Anonymous","","http://img1.blogblog.com/img/anon36.png","","","entry","post-","published","category","title","content","summary","","","","...","link","alternate","replies","name","uri","gd$image","http://img1.blogblog.com/img/blank.gif","","","media$thumbnail","","thr$total"," ","","","","","thr$in-reply-to","thr$in-reply-to","thr$in-reply-to","/default/","/summary/","?alt=json-in-script","gd$extendedProperty","blogger.itemClass","pid-","","undefined","mm/dd/yyyy","undefined","undefined","http://lorempixel.com/300/500/","blog-",".comments","","category","","title","","subtitle","Anonymous","","http://img1.blogblog.com/img/anon36.png","name","uri","gd$image","http://img1.blogblog.com/img/blank.gif","entry","post-","","published","category","","title","","content","","summary","","","","...","","comments","link","alternate","replies","Anonymous","","http://img1.blogblog.com/img/anon36.png","name","uri","gd$image","http://img1.blogblog.com/img/blank.gif","","","media$thumbnail","","thr$total"," ","","","","","thr$in-reply-to","thr$in-reply-to","thr$in-reply-to","/default/","/summary/","?alt=json-in-script","","gd$extendedProperty","blogger.itemClass","pid-","","-","dd","mm","yyyy","cookie","; expires=","; path=/","=","test","ok","",";","=","=","","","undefined","","","?","#","://","/","archive.html","/search?updated-min=","/search?","/search/label/","/p/",".html","/cart/","?page=cart","/checkout/","?page=checkout","/wishlist/","/p/wishlist.html","/b/","admin","yes",".item-control",".item-control","display","none","","",".","","",".","#primary",'<div class="wide section" id="blog"><div class="widget Blog" id="Blog1"><div class="blog-posts hfeed"><div class="clear"></div></div></div></div><div class="clear"></div>',"#header-2","","string","!0","","","","","string","_","-","!0",'<div class="property out-of-stock efont">',"Out of stock","</div>",'<div class="property on-sale color-bg efont"><span class="label">',"On sale",'</span><span class="old old-price" data-old="','">','</span><span class="current current-price" data-price="','">',"</span></div>",'<div class="property normal color-bg efont current-price" data-price="','">',"</div>",".blog-posts.hfeed.index .index-post","even","odd","triple","quad","#popular-items .index-post","even","odd","triple","quad","#home-horizon-section-2 .widget","even","odd","triple","quad","span.trans","data-key",".follow-by-email-submit","SUBSCRIBE",".follow-by-email-address","placeholder","Email address...","#header .menu a","_","sub",'<span class="tab"></span>',"#header .menu-toggle","#header .menu","display","none","#header .menu-toggle","#header .menu","display","none","#header .menu-toggle","#header .menu","display","none","#header .menu","#header .menu-toggle","slider","#slider",'<div class="wide inner"></div>',"","","[","]","[","]","","[","]","[","]",'<div class="slide">',"",'<a href="','" class="slide-content pre-title efont white block">',"</a>",'<a href="','" class="slide-content title efont white block">',"</a>",'<a href="','" class="slide-content caption white block">',"</a>",'<a href="','" class="slide-content button efont white color-bg black-hover inb">',"</a>",'<div class="slide-content-wrapper">',"</div>",'<a href="','" class="image block abs"><img alt="slide-image" src="','"/></a>',"</div>",'html[dir="rtl"]',"#bar .tabs .active","#bar .tabs","#bar .arrow","left","px","#bar .inner .tabs","#bar .inner",'<div class="breadcrumb"></div>',"#bar .tabs a","#bar .tabs a.active","active","active",".search-toggle",".search-overlay","#search-form","30%","easeOutBack",".search-overlay",".search-overlay","#search-form","100%","body",".search-overlay","display","none",".search-overlay","#search-form","100%",".index-post",".property",".out-of-stock",".add-to-cart","+ ","Readmore"," +","disabled",".current-price",".add-to-cart","+ ","Add to cart"," +","href",".tabs a",".tabs a","active","active",".latest","#blog","#home-random","#popular-items",".random","#blog","#home-random","#popular-items",".popular","#blog","#home-random","#popular-items",".label-information","_","-","!0","data-count","data-url",'.post-tags a[rel="tag"]',"_","-","!0",".breadcrumb",'<a href="/" class="black color-hover">',"Home",'</a><span class="sep">/</span>','<a href="','?max-results=8" class="black color-hover">',"</a>",'.post-tags a[rel="tag"]',"href","href",'<a href="','?max-results=8" class="black color-hover">','</a><span class="sep">/</span>','<span class="bc-post-title black">404</span>',"title","___","404","title",'<span class="bc-post-title black">',"Archive","</span>",'<span class="bc-post-title black">',"Cart","</span>","title","___","Cart","title",'<span class="bc-post-title black">',"Checkout","</span>","title","___","Checkout","title",'<span class="bc-post-title black">',"Wishlist","</span>","title","___","Wishlist","title","#home-horizon-section .widget.Text .widget-content","##","##",'<span class="icon"><i class="fa fa-','"></i></span>',".post .post-description img","src","src","br","a","br","div.separator","br","div.separator","br","div.separator","a","div.separator",".post-header .desc-image-list","",'<div class="full">','<div class="natural-thumbnail"><img src="','" alt="post-full-image"/></div>','<div class="natural-thumbnail" style="opacity: 0" ><img src="','" alt="post-full-image"/></div>',"</div>",'<div class="thumb">','<a class="natural-thumbnail"><img src="','" alt="post-thumb-image"/></a>','<div class="clear"></div></div>',".post-header .desc-image-list .thumb .natural-thumbnail","img","src",".post-header .desc-image-list .full .natural-thumbnail","opacity","1",".post-header .desc-image-list .full .natural-thumbnail","img","src",".post.hentry .post-header-meta-2",'<span class="price-label">',"Price",":</span>","-",'<span class="inb old-price efont">',"</span>","_",'<span class="inb cur-price efont">',"</span>",'<span class="inb color-bg white efont on-sale">',"On sale","</span>","!0",'<span class="inb white out-of-stock efont">',"Out of stock","</span>","add_to_cart","add_to_wishlist","",",","(",")","(","(",")","",",","(",")","",",","(",")","",",","(",")","",".wishlist-toggle","hide","title","View wishlist",".cart-toggle","hide","title","View cart",".post-header-action-buttons","","data-id",'<div class="action-button-wrapper add-to-cart-button-wrapper rel">','<span class="add-to-cart-up change-cart-counter-button color-hover ptr"><i class="fa fa-angle-up"></i></span>','<span class="add-to-cart-down change-cart-counter-button color-hover ptr"><i class="fa fa-angle-down"></i></span>','<a class="add-to-cart color-bg white black-bg-hover" data-id="','">',"Add",' <span class="counter b">1</span> ',"items to cart",' <i class="fa fa-shopping-cart icon"></i></a>','<div class="clear"></div>',"</div>",'<div class="action-button-wrapper add-to-wishlist-button-wrapper rel">','<a class="add-to-wishlist white-bg black green-bg-hover white-hover" data-id="','">',"Add to Wishlist",' <i class="fa fa-heart"></i></a>','<div class="clear"></div>',"</div>",'<div class="clear"></div>','<div class="shopping-msg"></div>','<div class="clear"></div>',".post-header-action-buttons .change-cart-counter-button",".post-header-action-buttons .add-to-cart .counter",".add-to-cart-up",".post-header-action-buttons .add-to-cart .counter",".cart-toggle",".wishlist-toggle",".number",".fa",'<span class="number color-bg white block abs">',"</span>",".disabled",".counter",".counter","data-id",".counter",".shopping-item.hentry","h1.shopping-title",".shopping-msg",'<i class="fa fa-check"></i> "','" ',"was successfully added to your cart",'. <a href="/?page=cart">',"View cart","</a>",".in-list",'<i class="fa fa-check"></i> ',"Add to cart",".add-to-cart",".add-to-wishlist",".disabled","data-id",".shopping-item","h1.item_name",".shopping-msg",'<i class="fa fa-check"></i> <span style="display:none;">"','"</span> ',"item added to your",' <a href="/p/wishlist.html">',"wishlist.","</a>",'<div class="cart-content white-bg abs right0">\t<div class="cart-list">\t</div>\t<p class="total"><strong>',"Subtotal",':</strong> <span class="amount">','<span class="value">0</span>','</span></p>\t<p class="buttons">\t\t<a href="/?page=cart" class="button viewcart grey-bg black color-bg-hover white-hover inb efont">',"View Cart",'</a>\t\t<a href="/?page=checkout" class="button checkout inb color-bg white black-bg-hover efont">',"Checkout","</a>\t</p></div>",".cart-toggle-wrapper","",".cart-content","/posts/default/","?alt=json-in-script",".cart-content","","_",'<div class="cart-item">\t\t\t\t<a href="','" class="cart-item-thumb">\t\t\t\t<img src="','" alt="cart-item-thumb"></a>\t\t\t\t<div class="cart-text">\t\t\t\t\t<a class="cart-item-title" href="','">','</a>\t\t\t\t\t<span class="quantity"><span class="number">','</span> Ã— <span class="price">','<span class="price-value" data-price="','">',"</span>",'</span></span>\t\t\t\t\t<span class="cart-item-remove" data-id="','" title="',"Remove from cart",'">Ã—</span>\t\t\t\t</div>\t\t\t\t<div class="clear"></div>\t\t\t</div>',".cart-toggle-wrapper .cart-content .cart-list",".cart-toggle-wrapper .cart-content .cart-list .ajax-loader",".cart-toggle-wrapper .cart-content .cart-list .cart-item",".price-value","data-price",".number",".cart-toggle-wrapper .cart-content .total .amount .value",".cart-toggle-wrapper .cart-content .cart-list .cart-item .cart-item-remove","data-id","Can not get item from server!","jsonp","Can not get data from server!",".cart-toggle",".number",".cart-toggle-wrapper .cart-content",".cart-toggle-wrapper .cart-content .cart-list",'<img class="ajax-loader" src="','"/>',".cart-toggle-wrapper .cart-content .total .value","0","",".cart-toggle-wrapper .cart-content",".cart-toggle-wrapper",".disabled",".cart-toggle-wrapper",".disabled",".cart-toggle-wrapper",".cart-content","data-id",'.index-post[data-id="','"]',".index-post",".blog-posts.hfeed",'<div class="empty-wishlist empty-msg">',"The wishlist is empty now","</div>","/posts/default/","?alt=json-in-script","",""," even"," odd"," triple"," quad",'<div class="index-post small shopping-item','" data-id="','">','<a class="natural-thumbnail" href="','">','<img src="','" class="shopping-thumb"/>',"</a>",'<div class="content tcenter">','<h2 class="wishlist-title"><a href="','">',"</a></h2>",'<a class="add-to-cart in-list" data-id="','"><span class="plus-to-list">'," ","</span></a>",'<a class="add-to-cart disabled" href="','"><span class="text black-hover">+ ',"Readmore"," +</span></a>",'<div class="clear"></div>','<a class="remove-from-wishlist" data-id="','"><span class="remove-wishlist">',"Remove from wishlist","</span></a>","</div>",'<div class="clear"></div></div>',".blog-posts.hfeed .ajax-loader",".blog-posts.hfeed .ajax-loader",".blog-posts.hfeed .index-post a.add-to-cart",".blog-posts.hfeed .index-post a.remove-from-wishlist","Can not get item from server!","jsonp","Can not get data from server!","body","wishlist",".blog-posts.hfeed","wishlist-page",".blog-posts.hfeed",'<img class="ajax-loader" src="','"/>',".blog-posts.hfeed",'<div class="empty-wishlist empty-msg">',"The wishlist is empty now","</div>","","body","cart",".blog-posts.hfeed","cart-page",".cart-toggle-wrapper","disabled",".blog-posts.hfeed",'<div class="cart-page-buttons"></div>',".blog-posts.hfeed",'<div class="cart-page-subtotal"></div>',".blog-posts.hfeed",'<div class="cart-page-content"></div>',"/posts/default/","?alt=json-in-script","","_",'<tr class="cart_item" data-id="','">\t\t\t\t\t<td class="product-remove">\t\t\t\t\t\t<a class="remove" title="',"Remove from cart",'" data-id="','">Ã—</a>\t\t\t\t\t</td>\t\t\t\t\t<td class="product-thumbnail">\t\t\t\t\t\t<a href="','"><img src="','"></a>\t\t\t\t\t</td>\t\t\t\t\t<td class="product-name">\t\t\t\t\t\t<a href="','">','</a>\t\t\t\t\t</td>\t\t\t\t\t<td class="product-price">\t\t\t\t\t\t<span class="amount">','<span class="price-value" data-id="','" data-price="','">',"</span>",'</span>\t\t\t\t\t</td>\t\t\t\t\t<td class="product-quantity">\t\t\t\t\t\t<div class="quantity buttons_added"><input type="button" value="-" class="minus" data-id="','"><input type="number" step="1" min="1" name="cart[','][qty]" value="','" class="input-text qty text" size="4"><input type="button" value="+" class="plus" data-id="','"></div>\t\t\t\t\t</td>\t\t\t\t\t<td class="product-subtotal">\t\t\t\t\t\t<span class="amount">','<span class="subtotal-value">',"</span>","</span>\t\t\t\t\t</td>\t\t\t\t</tr>",'<table class="cart-page-table" cellspacing="0"><thead>\t\t\t\t\t\t\t<tr>\t\t\t\t\t\t\t\t<th class="product-remove">&nbsp;</th>\t\t\t\t\t\t\t\t<th class="product-thumbnail">&nbsp;</th>\t\t\t\t\t\t\t\t<th class="product-name">',"Product",'</th>\t\t\t\t\t\t\t\t<th class="product-price">',"Price",'</th>\t\t\t\t\t\t\t\t<th class="product-quantity">',"Quantity",'</th>\t\t\t\t\t\t\t\t<th class="product-subtotal">',"Total","</th>\t\t\t\t\t\t\t</tr>\t\t\t\t\t\t</thead><tbody>","</tbody></table>",".cart-page-content",".cart-page-content .cart_item","data-id",'.price-value[data-id="','"]',"data-price",'input[name="cart[','][qty]"]',".cart-page-subtotal",'<strong class="label">',"Subtotal",':</strong> <span class="subtotal-value">','<span class="value">',"</span>","</span>",".cart-page-buttons",'<a class="update-cart-page inb color-bg white-bg black-bg-hover black white-hover">',"Update cart",'</a> <a class="proceed-checkout inb color-bg white green-bg-hover" href="?page=checkout">',"Procceed checkout","</a>",'.cart_item .product-quantity input[type="button"]',"data-id",'input[name="cart[','][qty]"]',".minus",'input[name="cart[','][qty]"]','input[name="cart[','][qty]"]',".update-cart-page",".cart_item","data-id",'input[name="cart[','][qty]"]',".cart_item .remove","data-id","Can not get item from server!","jsonp","Can not get data from server!","",".cart-page-content","",".cart-page-subtotal","",".cart-page-buttons","",".cart-page-content",'<img class="ajax-loader" src="','"/>',".blog-posts.hfeed",'<div class="empty-cart empty-msg">',"The cart is empty now","</div>","","","","","","","","","","","","","","","","","","","","#ship-to-different-address-checkbox",":checked","","p.validate-required",".billing-fields p.validate-required",'input[type="text"]',"id","_email","@",".","id","_phone","+","id","_postcode","#billing_country","","#billing_first_name","","#billing_last_name","","#billing_company","","#billing_address","","#billing_city","","#billing_postcode","","#billing_email","#billing_phone","#shipping_country","","#shipping_first_name","","#shipping_last_name","","#shipping_company","","#shipping_address","","#shipping_city","","#shipping_postcode","","#order_comments",'.checkout-page .payment-methods input[name="payment_method"][checked="checked"]',"#ship-to-different-address-checkbox",":checked",".checkout-page .contact-form-wrapper",".contact-form-name"," ",".contact-form-email","NEW ORDER",": #","\n","==========================\n","METHOD",":","\n","Billing Address and Shipping Address","Billing Address","\n","-----------------------------------------------------------\n","    ","First Name",": ","\n","    ","Last Name",": ","\n","    ","Company Name",":","\n","    ","Address",": ","\n","    ","Town / City / State",": ","\n","    ","Country",": ","\n","    ","Postcode / Zip",": ","\n","    ","Email",": ","\n","    ","Phone",": ","\n","\n","Shipping Address","\n","-----------------------------------------------------------\n","    ","First Name",": ","\n","    ","Last Name",": ","\n","    ","Company Name",":","\n","    ","Address",": ","\n","    ","Town / City / State",": ","\n","    ","Country",": ","\n","    ","Postcode / Zip",": ","\n","\n","Order Notes","\n","-----------------------------------------------------------\n","\n\n","Order Details","\n","============================================================\n","    ","Product",": ","\n","    ","Price",": ","\n","    ","Quantity",": ","\n","    ","Total",": ","\n","    ","Link",": ","\n","-----------------------------------------------------------\n","Subtotal",": ","\n","-----------------------------------------------------------\n","Shipping",": ","\n","-----------------------------------------------------------\n","Total",": ","\n","-----------------------------------------------------------\n","\n\n\n\n\n ",".contact-form-email-message","#ship-to-different-address-checkbox",":checked","","","p.validate-required",".billing-fields p.validate-required",'input[type="text"]',"id","_email","@",".","id","_phone","+","id","_postcode","style","border","1px solid red","html, body","billing_country","billing_first_name","billing_last_name","billing_company","billing_address","billing_city","billing_postcode","billing_email","billing_phone","Direct Bank Transfer","Cheque Payment","Cash on Delivery","#ship-to-different-address-checkbox",":checked","<p>","Thank you. Your order has been received",'</p>\t\t<ul class="order_details">\t\t\t<li class="order">\t\t\t\t<div class="">',"Order ID",':</div><strong class="color">#','</strong>\t\t\t</li>\t\t\t<li class="date">\t\t\t\t<div class="">MM/DD/YYY:</div><strong>',"/","/",'</strong>\t\t\t</li>\t\t\t<li class="total">\t\t\t\t<div class="">',"Total",':</div><strong><span class="amount">','</span></strong>\t\t\t</li>\t\t\t<li class="method">\t\t\t\t<div class="">',"Payment method",":</div><strong>","</strong>\t\t\t</li>\t\t</ul>","Direct Bank Transfer","<p>","Make your payment directly into our bank account. Please use your Order ID as the payment reference. Your order will not be shipped until the funds have cleared in our account","</p>\t\t\t<h2>","Our Bank Details",'</h2>\t\t\t<h3 class="color">'," - ",'</h3>\t\t\t<ul class="order_details">\t\t\t\t<li class="account_number"><div class="">',"Account Number",':</div><strong class="color">',"</strong></li>",'<li class="sort_code"><div class="">',"Sort Code",":</div><strong>","</strong></li>",'<li class="iban"><div class="">IBAN:</div><strong>',"</strong></li>",'<li class="bic"><div class="">BIC:</div><strong>',"</strong></li>","</ul>","Cheque Payment","<p>","Please send your cheque to",' <span class="color">',", ",", ",", ",", ",", ","</span></p>","<p>","Pay with cash upon delivery.","</p>","<h2>","Order Details",'</h2>\t\t<table class="shop_table order_details">\t\t\t<thead>\t\t\t\t<tr>\t\t\t\t\t<th class="product-name">',"Product",'</th>\t\t\t\t\t<th class="product-total">',"Total",'</th>\t\t\t\t</tr>\t\t\t</thead>\t\t\t<tfoot>\t\t\t\t<tr>\t\t\t\t\t<th scope="row">',"Subtotal",':</th>\t\t\t\t\t<td><span class="amount">','</span></td>\t\t\t\t</tr>\t\t\t\t<tr>\t\t\t\t\t<th scope="row">',"Shipping",":</th>\t\t\t\t\t<td>","Free Shipping",'</td>\t\t\t\t</tr>\t\t\t\t<tr>\t\t\t\t\t<th scope="row">',"Total",':</th>\t\t\t\t\t<td><span class="amount">',"</span></td>\t\t\t\t</tr>\t\t\t</tfoot>\t\t\t<tbody>",'<tr class="order_item">\t\t\t\t<td class="product-name">','<strong class="product-quantity">Ã— ','</strong></td>\t\t\t\t<td class="product-total"><span class="amount">',"</span></td>\t\t\t</tr>","</tbody>\t\t</table>\t\t<header>\t\t\t<h2>","Customer details",'</h2>\t\t</header>\t\t<dl class="customer_details">\t\t\t<dt>',"Email",":</dt>\t\t\t<dd>","</dd><dt>","Phone",":</dt><dd>",'</dd>\t\t</dl>\t\t<div class="col2-set addresses">\t\t\t<div class="col-1 ',"",'">\t\t\t<header class="title">\t\t\t\t<h3>',"Billing Address and Shipping Address","Billing Address","</h3>\t\t\t</header>\t\t\t<address>\t\t\t\t<p>\t\t\t\t\t"," ","<br>\t\t\t\t\t","<br>\t\t\t\t\t","<br>\t\t\t\t\t",", ","\t\t\t\t</p>\t\t\t</address>\t\t</div>",'<div class="col-2">\t\t\t\t<header class="title">\t\t\t\t\t<h3>',"Shipping Address","</h3>\t\t\t\t</header>\t\t\t\t<address>\t\t\t\t\t<p>\t\t\t\t\t\t"," ","<br>\t\t\t\t\t\t","<br>\t\t\t\t\t\t","<br>\t\t\t\t\t\t",", ","\t\t\t\t\t</p>\t\t\t\t</address>\t\t\t</div>",'<div class="clear"></div></div><div class="clear"></div>',".checkout-step-2","PayPal","https://www.paypal.com/cgi-bin/webscr?cmd=_cart","&business=","&currency_code=","&charset=UTF-8","&rm=0","&upload=1","&bn=azion_Cart","&invoice=","&first_name=","&last_name=","&company=","&address1=","&city=","&zip=","&country=","&email=","&night_phone_b=","&day_phone_b=","&handling_cart=","&no_shipping=1","&tax_cart=0","&item_name_","=","&quantity_","=","&amount_","=","#ContactForm1_contact-form-success-message","#ContactForm1_contact-form-success-message",".checkout-step-1",".checkout-step-2","#ContactForm1_contact-form-success-message","#ContactForm1_contact-form-error-message","Blogger server had an unknown error!!",".checkout-step-1",".checkout-step-2","/posts/default/","?alt=json-in-script","","_",'<tr class="cart_item">\t\t\t\t<td class="product-name">',' <strong class="product-quantity">Ã—','</strong></td>\t\t\t\t<td class="product-total"><span class="amount">',"</span></td>\t\t\t</tr>","Free Shipping",'<h3 id="order_review_heading">',"Your Order",'</h3>\t\t\t\t\t<table class="shop_table" cellspacing="0">\t\t\t\t\t\t<thead>\t\t\t\t\t\t\t<tr>\t\t\t\t\t\t\t\t<th class="product-name">',"Product",'</th>\t\t\t\t\t\t\t\t<th class="product-total">',"Total",'</th>\t\t\t\t\t\t\t</tr>\t\t\t\t\t\t</thead>\t\t\t\t\t\t<tfoot>\t\t\t\t\t\t\t<tr class="cart-subtotal">\t\t\t\t\t\t\t\t<th>',"Subtotal",'</th>\t\t\t\t\t\t\t\t<td><span class="amount">','</span></td>\t\t\t\t\t\t\t</tr>\t\t\t\t\t\t\t<tr class="shipping">\t\t\t\t\t\t\t\t<th>',"Shipping and Handling","</th>\t\t\t\t\t\t\t\t<td>\t\t\t\t\t\t\t\t\t",'\t\t\t\t\t\t\t\t</td>\t\t\t\t\t\t\t</tr>\t\t\t\t\t\t\t<tr class="order-total">\t\t\t\t\t\t\t\t<th>',"Total",'</th>\t\t\t\t\t\t\t\t<td><strong><span class="amount">',"</span></strong> </td>\t\t\t\t\t\t\t</tr>\t\t\t\t\t\t</tfoot>\t\t\t\t\t\t<tbody>\t\t\t\t\t\t","\t\t\t\t\t\t</tbody>\t\t\t\t\t</table>",".billing-info",'<ul class="payment_methods methods">','<li class="payment_method_bacs">\t\t\t\t\t\t\t<input id="payment_method_bacs" type="radio" class="input-radio" name="payment_method" value="',"Direct Bank Transfer",'"/>\t\t\t\t\t\t\t<label for="payment_method_bacs">',"Direct Bank Transfer",' </label>\t\t\t\t\t\t\t<div class="payment_box payment_method_bacs"><p>',"Make your payment directly into our bank account. Please use your Order ID as the payment reference. Your order will not be shipped until the funds have cleared in our account",".</p></div>\t\t\t\t\t\t</li>",'<li class="payment_method_cheque">\t\t\t\t\t\t\t<input id="payment_method_cheque" type="radio" class="input-radio" name="payment_method" value="',"Cheque Payment",'"/>\t\t\t\t\t\t\t<label for="payment_method_cheque">',"Cheque Payment",' </label>\t\t\t\t\t\t\t<div class="payment_box payment_method_cheque hide">\t\t\t\t\t\t\t\t<p>',"Please send your cheque to"," ",", ",", ",", ",", ",", ","</p>\t\t\t\t\t\t\t</div>\t\t\t\t\t\t</li>",'<li class="payment_method_cod">\t\t\t\t\t\t\t<input id="payment_method_cod" type="radio" class="input-radio" name="payment_method" value="',"Cash on Delivery",'"/>\t\t\t\t\t\t\t<label for="payment_method_cod">',"Cash on Delivery",' </label>\t\t\t\t\t\t\t<div class="payment_box payment_method_cod hide">\t\t\t\t\t\t\t\t<p>',"Pay with cash upon delivery.","</p>\t\t\t\t\t\t\t</div>\t\t\t\t\t\t</li>",'<li class="payment_method_paypal">\t\t\t\t\t\t\t<input id="payment_method_paypal" type="radio" class="input-radio" name="payment_method" value="PayPal"/>\t\t\t\t\t\t\t<label for="payment_method_paypal">PayPal <div class="inb paypal-img"><span class="pay">Pay</span><span class="pal">Pal</span></div></label>\t\t\t\t\t\t\t<div class="payment_box payment_method_paypal hide">\t\t\t\t\t\t\t\t<p>',"Pay via PayPal; you can pay with your credit card if you have no a PayPal account","</p>\t\t\t\t\t\t\t</div>\t\t\t\t\t\t</li>","</ul>",".checkout-page .payment-methods",'ul.payment_methods li:first input[type="radio"]',"checked","checked",".checkout-step-1 .action-buttons",'<a href="/?page=cart" class="white-bg black color-hover inb button">',"View Cart",'</a> <div class="contact-form-wrapper inb"></div>','#ContactForm1 form[name="contact-form"]',".checkout-page .contact-form-wrapper",'.checkout-page .contact-form-wrapper form[name="contact-form"]','<div class="contact-form-inner"></div>','.checkout-page .contact-form-wrapper form[name="contact-form"]','<div class"button"></div>','.checkout-page .contact-form-wrapper form[name="contact-form"] .contact-form-button-submit','.checkout-page .contact-form-wrapper form[name="contact-form"]','.checkout-page .contact-form-wrapper form[name="contact-form"] .contact-form-button-submit',"color-bg white inb continue button place-order","Place Order",'.checkout-page input[name="payment_method"]',"change","checked",'.checkout-page .payment_methods input[checked="checked"]',"id",".payment_box.","checked","id",".payment_box.","checked","checked","#ContactForm1_contact-form-submit","#ContactForm1_contact-form-submit","Can not get item from server!","jsonp","Can not get data from server!","",".billing-info",'<img class="ajax-loader" src="','"/>','<form name="checkout" method="post" class="checkout" action="">\t<div class="col-1">\t\t<h3>',"Billing Details",'</h3>\t\t<div class="billing-fields">','<p class="address-field update_totals_on_change validate-required" id="billing_country_field">\t\t\t\t\t<label for="billing_country" class="">',"Country",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<select name="billing_country" id="billing_country" class="country_to_state country_select">',"billing_country",'<option value="','"',"",">","</option>",'</select>\t\t\t\t</p><div class="clear"></div>','<p class="form-row form-row-first validate-required" id="billing_first_name_field">\t\t\t\t\t<label for="billing_first_name" class="">',"First Name",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<input type="text" class="input-text " name="billing_first_name" id="billing_first_name" placeholder="" value="',"billing_first_name",'"/>\t\t\t\t</p>','<p class="form-row form-row-last validate-required" id="billing_last_name_field">\t\t\t\t\t<label for="billing_last_name" class="">',"Last Name",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<input type="text" class="input-text " name="billing_last_name" id="billing_last_name" placeholder="" value="',"billing_last_name",'"/>\t\t\t\t</p>','<p class="form-row form-row-wide" id="billing_company_field">\t\t\t\t\t<label for="billing_company" class="">',"Company Name",'</label>\t\t\t\t\t<input type="text" class="input-text " name="billing_company" id="billing_company" placeholder="" value="',"billing_company",'"/>\t\t\t\t</p>','<p class="form-row form-row-wide address-field validate-required" id="billing_address_field">\t\t\t\t\t<label for="billing_address" class="">',"Address",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<input type="text" class="input-text " name="billing_address" id="billing_address" placeholder="" value="',"billing_address",'"/>\t\t\t\t</p>','<p class="form-row form-row-wide address-field validate-required" id="billing_city_field" data-o_class="form-row form-row-wide address-field validate-required">\t\t\t\t\t<label for="billing_city" class="">',"Town / City / State",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<input type="text" class="input-text " name="billing_city" id="billing_city" placeholder="" value="',"billing_city",'"/>\t\t\t\t</p>','<p class="form-row form-row-last address-field validate-required validate-postcode" id="billing_postcode_field" data-o_class="form-row form-row-last address-field validate-required validate-postcode">\t\t\t\t\t<label for="billing_postcode" class="">',"Postcode / Zip",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<input type="text" class="input-text " name="billing_postcode" id="billing_postcode" placeholder="" value="',"billing_postcode",'"/>\t\t\t\t</p>','<p class="form-row form-row-first validate-required validate-email" id="billing_email_field">\t\t\t\t<label for="billing_email" class="">',"Email Address",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t<input type="text" class="input-text " name="billing_email" id="billing_email" placeholder="" value="',"billing_email",'"/>\t\t\t</p>\t\t\t<p class="form-row form-row-last validate-required validate-phone" id="billing_phone_field">\t\t\t\t<label for="billing_phone" class="">',"Phone",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t<input type="text" class="input-text " name="billing_phone" id="billing_phone" placeholder="" value="',"billing_phone",'"/>\t\t\t</p>\t\t<div class="clear"></div></div>\t</div>\t<div class="col-2">\t\t<h3 id="ship-to-different-address">\t\t\t<label for="ship-to-different-address-checkbox" class="checkbox">',"Ship to a different address?",'</label>\t\t\t<input id="ship-to-different-address-checkbox" class="input-checkbox" type="checkbox" name="ship_to_different_address" value="1"/>\t\t</h3>\t\t<div class="hide shipping-fields">','<p class="address-field update_totals_on_change validate-required" id="shipping_country_field">\t\t\t\t\t<label for="shipping_country" class="">',"Country",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<select name="shipping_country" id="shipping_country" class="country_to_state country_select">','<option value="','">',"</option>","</select>\t\t\t\t</p>",'<p class="form-row form-row-first validate-required" id="shipping_first_name_field">\t\t\t\t\t<label for="shipping_first_name" class="">',"First Name",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<input type="text" class="input-text " name="shipping_first_name" id="shipping_first_name" placeholder="" value=""/>\t\t\t\t</p>','<p class="form-row form-row-last validate-required" id="shipping_last_name_field">\t\t\t\t\t<label for="shipping_last_name" class="">',"Last Name",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<input type="text" class="input-text " name="shipping_last_name" id="shipping_last_name" placeholder="" value=""/>\t\t\t\t</p>','<p class="form-row form-row-wide" id="shipping_company_field">\t\t\t\t\t<label for="shipping_company" class="">',"Company Name",'</label>\t\t\t\t\t<input type="text" class="input-text " name="shipping_company" id="shipping_company" placeholder="" value=""/>\t\t\t\t</p>','<p class="form-row form-row-wide address-field validate-required" id="shipping_address_field">\t\t\t\t\t<label for="shipping_address" class="">',"Address",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<input type="text" class="input-text " name="shipping_address" id="shipping_address" placeholder="" value=""/>\t\t\t\t</p>','<p class="form-row form-row-wide address-field validate-required" id="shipping_city_field" data-o_class="form-row form-row-wide address-field validate-required">\t\t\t\t\t<label for="shipping_city" class="">',"Town / City / State",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<input type="text" class="input-text " name="shipping_city" id="shipping_city" placeholder="" value=""/>\t\t\t\t</p>','<p class="form-row form-row-last address-field validate-required validate-postcode" id="shipping_postcode_field" data-o_class="form-row form-row-last address-field validate-required validate-postcode">\t\t\t\t\t<label for="shipping_postcode" class="">',"Postcode / Zip",' <abbr class="required" title="required">*</abbr></label>\t\t\t\t\t<input type="text" class="input-text " name="shipping_postcode" id="shipping_postcode" placeholder="" value=""/>\t\t\t\t</p>','<div class="clear"></div></div>\t\t<p class="form-row notes" id="order_comments_field">\t\t\t<label for="order_comments" class="">',"Order Notes",'</label><textarea name="order_comments" class="input-text " id="order_comments" placeholder="" rows="2"></textarea>\t\t</p>\t</div></form><div class="clear"></div>',"body","checkout",".blog-posts.hfeed","checkout-page",".cart-toggle-wrapper","disabled","a.cart-toggle","href","/?page=cart",".checkout-page",'<div class="checkout-step-1 input-info"><div class="checkout-form">','</div><div class="billing-info"></div><div class="payment-methods"></div><div class="action-buttons"></div>',".checkout-page",'<div class="checkout-step-2 summary-info hide"><img class="ajax-loader" src="','"/></div>',"#ship-to-different-address-checkbox","change",":checked",".shipping-fields",".shipping-fields","#blog .index-post","#home-random",'<img class="ajax_loading_img" src="','"/>',"/posts/summary?alt=json-in-script&max-results=0","/posts/default?alt=json-in-script&max-results=","&start-index=","",""," even"," odd"," triple"," quad",'<div class="index-post small shopping-item','" data-id="','">','<a class="natural-thumbnail" href="','">','<img src="','" class="shopping-thumb"/>',"</a>",'<div class="content tcenter">','<h2 class="b_ shopping-title"><a class="black color-hover" href="','">',"</a></h2>",'<a class="add-to-cart in-list" data-id="','"><span class="text black-hover">+ ',"Add to cart"," +</span></a>",'<a class="add-to-cart disabled" href="','"><span class="text black-hover">+ ',"Readmore"," +</span></a>","</div>",'<div class="clear"></div></div>',"#home-random",'<div class="clear"></div>',"#home-random .index-post a.add-to-cart","jsonp","jsonp","#home-random","#bar .tabs a.random","","#Label1","h2","a","data-href","_","-","!0","/search/label/","?","?","#Label1","collections","rel",'<div class="header"><h2>','<select name="collection-list">','<option value="','">',"</option>","</select></h2>",'<div class="clear"></div></div><div class="clear"></div><div class="body">','<div name="','" class="inner"><div class="collection-content"></div><a href="','?max-results=8" class="more black color-bg-hover white-hover efont ease" style="display: none;">',"View all products of",' <span class="upper">',"</span></a></div>","</div>",'select[name="collection-list"]',"disabled","disabled","/posts/default/-/","?alt=json-in-script&max-results=","",""," even"," odd"," triple"," quad",'<div class="index-post big shopping-item','" data-id="','">','<a class="natural-thumbnail" href="','">','<img src="','" class="shopping-thumb"/>',"</a>",'<div class="content tcenter">','<h2 class="b_ shopping-title"><a class="black color-hover" href="','">',"</a></h2>",'<a class="add-to-cart in-list" data-id="','"><span class="text black-hover">+ ',"Add to cart"," +</span></a>",'<a class="add-to-cart disabled" href="','"><span class="text black-hover">+ ',"Readmore"," +</span></a>","</div>",'<div class="clear"></div></div>','div[name="','"] .collection-content','<div class="clear"></div>','div[name="','"]',"active",'select[name="collection-list"]',"disabled",'div[name="','"]',".more",'div[name="','"] .collection-content .index-post a.add-to-cart',"jsonp","Can not get data from server!",'select[name="collection-list"]',"change","disabled","disabled","#Label1 .body .inner.active","active",'div[name="','"]',"active",'div[name="','"] .collection-content','div[name="','"] .collection-content','<img src="','" class="ajax_loading_img"/>',"/posts/default/-/","?alt=json-in-script&max-results=","",""," even"," odd"," triple"," quad",'<div class="index-post big shopping-item','" data-id="','">','<a class="natural-thumbnail" href="','">','<img src="','" class="shopping-thumb"/>',"</a>",'<div class="content tcenter">','<h2 class="b_ shopping-title"><a class="black color-hover" href="','">',"</a></h2>",'<a class="add-to-cart in-list" data-id="','"><span class="text black-hover">+ ',"Add to cart"," +</span></a>",'<a class="add-to-cart disabled" href="','"><span class="text black-hover">+ ',"Readmore"," +</span></a>","</div>",'<div class="clear"></div></div>','div[name="','"] .collection-content','<div class="clear"></div>','select[name="collection-list"]',"disabled",'div[name="','"]',".more",'div[name="','"] .collection-content .index-post a.add-to-cart',"jsonp","disabled","#Label1","#home-sticky",'<div class="clear"></div>',".post.hentry .post-tags","a","_","-","!0","href","href","?max-results=8",".post.hentry .post-tags","",""," even"," odd"," triple"," quad",'<div class="index-post big shopping-item','" data-id="','">','<a class="natural-thumbnail" href="','">','<img src="','" class="shopping-thumb"/>',"</a>",'<div class="content tcenter">','<h2 class="b_ shopping-title"><a class="black color-hover" href="','">',"</a></h2>",'<a class="add-to-cart in-list" data-id="','"><span class="text black-hover">+ ',"Add to cart"," +</span></a>",'<a class="add-to-cart disabled" href="','"><span class="text black-hover">+ ',"Readmore"," +</span></a>","</div>",'<div class="clear"></div></div>',".post-similar .container","/search/label/","/posts/default/-/","?max-results=0&alt=json-in-script","/posts/default/-/","?max-results=","&start-index=","&alt=json-in-script",".post-similar span.id",".post-similar .container",".post-similar",".post-similar .container .index-post a.add-to-cart","jsonp","jsonp",".comment-thread > ol > li > .comment-block",'<div class="arrow"></div>',".comments .comments-content .comment-thread > .continue","comment-cancel-form","color-bg","black-bg-hover","white","display","none","a","Cancel reply",".comments .continue",".comment-cancel-form","a","comment-reply-link",'.comments .comment .comment-actions a[o="r"]',"comment-reply-link",".comments .comment-reply-link",".comment",".comment-replies",".comment-replybox-thread",".comment-cancel-form",".comment-cancel-form",".comment-cancel-form",".comment-cancel-form","#comment-editor","html, body",'.comments .comment .comment-actions a[o="r"]',".comment-cancel-form","html, body",".blog-posts.hfeed.error_page","p-404","",'<h1 class="title-404">',"PAGE MISSING"," - 404</h1>",'<div class="icon-404 color"><i class="fa fa-circle-o-notch"></i></div>','<div class="msg-1-404">',"Something Went Wrong","</div>",'<div class="msg-2-404">',"This search can help you find what you need","</i></div>","#search-form","#search-form","search-404",".search-toggle","Input keywords and enter ...","#search-form #search-text","#search-form #search-text","blur","","#search-form #search-text","focus",""],azion_thumbnail_handler(),$(window).resize(function(){azion_thumbnail_handler()}),azion_on_waiting_list()&&($(azion_easy_text_picker[201]).html(azion_easy_text_picker[202]),$(azion_easy_text_picker[203]).remove());var short_list_google_search_cate_index=new Array,short_list_google_search_cart_graph=new Array;$(azion_easy_text_picker[361]).each(function(){var t,e=$(this).html();if(e&&1<e.length&&!isNaN(e.substring(1))){if(0==e.indexOf(azion_easy_text_picker[362]))return;if(0==e.indexOf(azion_easy_text_picker[363]))return}e!==azion_easy_text_picker[364]&&(t=short_list_google_search_cate_index.length,short_list_google_search_cate_index[t]=new Object,short_list_google_search_cate_index[t].count=Number($(this).attr(azion_easy_text_picker[365])),short_list_google_search_cate_index[t].url=$(this).attr(azion_easy_text_picker[366]),short_list_google_search_cate_index[t].name=e)}),$(azion_easy_text_picker[367]).each(function(){var t=$(this).html();if(t&&1<t.length&&!isNaN(t.substring(1))){if(0==t.indexOf(azion_easy_text_picker[368]))return void(short_list_google_search_cart_graph[short_list_google_search_cart_graph.length]=t);if(0==t.indexOf(azion_easy_text_picker[369]))return void(short_list_google_search_cart_graph[short_list_google_search_cart_graph.length]=t)}t===azion_easy_text_picker[370]&&(short_list_google_search_cart_graph[short_list_google_search_cart_graph.length]=t)});for(var level_1=0;level_1<short_list_google_search_cate_index.length-1;level_1++)for(var spot_commerce_int_collector,level_8=level_1+1;level_8<short_list_google_search_cate_index.length;level_8++)short_list_google_search_cate_index[level_1].count<short_list_google_search_cate_index[level_8].count&&(spot_commerce_int_collector=short_list_google_search_cate_index[level_1],short_list_google_search_cate_index[level_1]=short_list_google_search_cate_index[level_8],short_list_google_search_cate_index[level_8]=spot_commerce_int_collector);var short_list_google_search_links=!1;$(azion_easy_text_picker[371]).each(function(){var t,e=azion_easy_text_picker[372]+azion_translated_mapper(azion_easy_text_picker[373])+azion_easy_text_picker[374];if(azion_on_lab()){for(var a=window.location.href,i=0;i<short_list_google_search_cate_index.length;i++)if(-1!=a.indexOf(short_list_google_search_cate_index[i].url)){e+=azion_easy_text_picker[375]+short_list_google_search_cate_index[i].url+azion_easy_text_picker[376]+short_list_google_search_cate_index[i].name+azion_easy_text_picker[377];break}}else azion_on_static()||(azion_on_error()?(e+=azion_easy_text_picker[384],t=(t=$(azion_easy_text_picker[385]).html()).replace(azion_easy_text_picker[386],azion_easy_text_picker[387]),$(azion_easy_text_picker[388]).html(t)):azion_on_out_list()?(e+=azion_easy_text_picker[399]+azion_translated_mapper(azion_easy_text_picker[400])+azion_easy_text_picker[401],t=(t=$(azion_easy_text_picker[402]).html()).replace(azion_easy_text_picker[403],azion_translated_mapper(azion_easy_text_picker[404])),$(azion_easy_text_picker[405]).html(t)):azion_on_waiting_list()&&(e+=azion_easy_text_picker[406]+azion_translated_mapper(azion_easy_text_picker[407])+azion_easy_text_picker[408],t=(t=$(azion_easy_text_picker[409]).html()).replace(azion_easy_text_picker[410],azion_translated_mapper(azion_easy_text_picker[411])),$(azion_easy_text_picker[412]).html(t)));$(this).html(e)}),$(azion_easy_text_picker[413]).each(function(){for(var t=$(this).html(),e=0;e<1e3&&t;e++){var a=t.indexOf(azion_easy_text_picker[414]);if(-1==a)break;var i=t.indexOf(azion_easy_text_picker[415],a+2);if(-1==i)break;var s=t.substring(a+2,i),t=t.substring(0,a)+azion_easy_text_picker[416]+s+azion_easy_text_picker[417]+t.substring(i+2)}$(this).html(t)});var gadget_link_objects=new Array;$(azion_easy_text_picker[418]).each(function(){$(this).attr(azion_easy_text_picker[419])&&(gadget_link_objects[gadget_link_objects.length]=$(this).attr(azion_easy_text_picker[420]),$(this).next().each(function(){$(this).is(azion_easy_text_picker[421])&&$(this).remove()}),$(this).parent(azion_easy_text_picker[422]).each(function(){$(this).next().each(function(){$(this).is(azion_easy_text_picker[423])&&$(this).remove()}),$(this).parent(azion_easy_text_picker[424]).each(function(){$(this).next().each(function(){$(this).is(azion_easy_text_picker[425])&&$(this).remove()})})}),$(this).parent(azion_easy_text_picker[426]).each(function(){$(this).next().each(function(){$(this).is(azion_easy_text_picker[427])&&$(this).remove()})}),$(this).parent(azion_easy_text_picker[428]).each(function(){$(this).remove()}),$(this).parent(azion_easy_text_picker[429]).each(function(){$(this).parent(azion_easy_text_picker[430]).each(function(){$(this).remove()}),$(this).remove()}),$(this).remove())}),gadget_link_objects.length&&($(azion_easy_text_picker[431]).html(function(){var t=azion_easy_text_picker[432];t+=azion_easy_text_picker[433];for(var e=0;e<gadget_link_objects.length;e++)t+=0==e?azion_easy_text_picker[434]+gadget_link_objects[e]+azion_easy_text_picker[435]:azion_easy_text_picker[436]+gadget_link_objects[e]+azion_easy_text_picker[437];if(t+=azion_easy_text_picker[438],1<gadget_link_objects.length){t+=azion_easy_text_picker[439];for(e=0;e<gadget_link_objects.length;e++)t+=azion_easy_text_picker[440]+gadget_link_objects[e]+azion_easy_text_picker[441];t+=azion_easy_text_picker[442]}return t}),azion_thumbnail_handler(),$(azion_easy_text_picker[443]).click(function(){$(this).find(azion_easy_text_picker[444]).each(function(){var t=$(this).attr(azion_easy_text_picker[445]);$(azion_easy_text_picker[446]).each(function(){$(this).css(azion_easy_text_picker[447])==azion_easy_text_picker[448]&&$(this).animate({opacity:0},100,function(){$(azion_easy_text_picker[449]).each(function(){t===$(this).find(azion_easy_text_picker[450]).attr(azion_easy_text_picker[451])&&$(this).animate({opacity:1},100)})})})})}));var paypal_early_amount=0,paypal_reject_boolean=!1;$(azion_easy_text_picker[452]).html(function(){for(var t=azion_easy_text_picker[453]+azion_translated_mapper(azion_easy_text_picker[454])+azion_easy_text_picker[455],e=!1,a=0;a<short_list_google_search_cart_graph.length;a++)if(drop_spin_title=short_list_google_search_cart_graph[a],drop_spin_title&&1<drop_spin_title.length&&!isNaN(drop_spin_title.substring(1))&&0==drop_spin_title.indexOf(azion_easy_text_picker[456])){e=!0;break}for(a=0;a<short_list_google_search_cart_graph.length;a++)if(drop_spin_title=short_list_google_search_cart_graph[a],drop_spin_title&&1<drop_spin_title.length&&!isNaN(drop_spin_title.substring(1))&&0==drop_spin_title.indexOf(azion_easy_text_picker[459])){paypal_early_amount=drop_spin_title.substring(1);break}e&&(t+=azion_easy_text_picker[462]+azion_translated_mapper(azion_easy_text_picker[463])+azion_easy_text_picker[464]);for(a=0;a<short_list_google_search_cart_graph.length;a++)if(drop_spin_title=short_list_google_search_cart_graph[a],drop_spin_title&&1<drop_spin_title.length&&!isNaN(drop_spin_title.substring(1))&&drop_spin_title===azion_easy_text_picker[465]){paypal_reject_boolean=!0,t+=azion_easy_text_picker[466]+azion_translated_mapper(azion_easy_text_picker[467])+azion_easy_text_picker[468];break}return t});var spot_commerce_active_list_counter=azion_easy_text_picker[469],spot_commerce_waiting_list_counter=azion_easy_text_picker[470];function azion_gadget_checker(){return!(!azion_space_pool()&&!azion_space_ready())}function azion_package_load(t){var e=new Array,a=azion_easy_text_picker[471];if(azion_space_pool())a=azion_space_send(t);else{if(!azion_space_ready())return!1;a=localStorage.getItem(t)}if(a){a=a.split(azion_easy_text_picker[472]);for(var i=0;i<a.length;i++)a[i]&&-1!=a[i].indexOf(azion_easy_text_picker[473])&&-1!=a[i].indexOf(azion_easy_text_picker[474])&&(idx=e.length,e[idx]=new Object,e[idx].id=a[i].substring(0,a[i].indexOf(azion_easy_text_picker[475])),e[idx].number=Number(a[i].substring(a[i].indexOf(azion_easy_text_picker[476])+1,a[i].indexOf(azion_easy_text_picker[477]))))}return!!e.length&&e}function azion_package_send_out(t,e,a){var i=azion_package_load(t);if(0==i)(i=new Array)[0]=new Object,i[0].id=e,i[0].number=a;else{for(var s=0;s<i.length;s++)if(i[s].id==e){i[s].number+=a;break}s>=i.length&&(idx=i.length,i[idx]=new Object,i[idx].id=e,i[idx].number=a)}for(var r=azion_easy_text_picker[478],s=0;s<i.length;s++)r&&(r+=azion_easy_text_picker[479]),r+=i[s].id+azion_easy_text_picker[480]+i[s].number+azion_easy_text_picker[481];azion_space_pool()?azion_space_write(t,r,CART_CACHE_DURATION):azion_space_ready&&localStorage.setItem(t,r)}function azion_package_empty(t,e){var a=azion_package_load(t);if(a){for(var i=0;i<a.length;i++)if(a[i].id==e){a[i].number=0;break}if(i>=a.length)return!1;if(a.length){for(var s=azion_easy_text_picker[486],i=0;i<a.length;i++)a[i].number&&(s&&(s+=azion_easy_text_picker[487]),s+=a[i].id+azion_easy_text_picker[488]+a[i].number+azion_easy_text_picker[489]);return azion_space_pool()?azion_space_write(t,s,CART_CACHE_DURATION):azion_space_ready&&localStorage.setItem(t,s),!0}}return!1}function azion_package_wipe(t){return azion_space_pool()?(azion_space_write(t,azion_easy_text_picker[490]),!0):!!azion_space_ready&&(localStorage.removeItem(t),!0)}function azion_package_pre_lst(t){var e,a;$(t).is(azion_easy_text_picker[533])||(e=1,$(t).find(azion_easy_text_picker[534]).length&&(e=Number($(t).find(azion_easy_text_picker[535]).text())),(a=$(t).attr(azion_easy_text_picker[536]))&&e&&(azion_package_send_out(spot_commerce_active_list_counter,a,e),azion_tgl_counter(spot_commerce_active_list_counter),$(t).find(azion_easy_text_picker[537]).length&&$(t).parents(azion_easy_text_picker[538]).each(function(){$(this).find(azion_easy_text_picker[539]).each(function(){$(azion_easy_text_picker[540]).html(azion_easy_text_picker[541]+$(this).html()+azion_easy_text_picker[542]+azion_translated_mapper(azion_easy_text_picker[543])+azion_easy_text_picker[544]+azion_translated_mapper(azion_easy_text_picker[545])+azion_easy_text_picker[546])})}),$(t).is(azion_easy_text_picker[547])&&$(t).html(azion_easy_text_picker[548]+azion_translated_mapper(azion_easy_text_picker[549]))))}azion_gadget_checker()&&($(azion_easy_text_picker[491]).removeClass(azion_easy_text_picker[492]).attr(azion_easy_text_picker[493],azion_translated_mapper(azion_easy_text_picker[494])),$(azion_easy_text_picker[495]).removeClass(azion_easy_text_picker[496]).attr(azion_easy_text_picker[497],azion_translated_mapper(azion_easy_text_picker[498]))),$(azion_easy_text_picker[499]).html(function(){var t=azion_easy_text_picker[500],e=$(this).attr(azion_easy_text_picker[501]);return azion_gadget_checker()&&!paypal_reject_boolean&&(paypal_reject_boolean||(t+=azion_easy_text_picker[502],t+=azion_easy_text_picker[503],t+=azion_easy_text_picker[504],t+=azion_easy_text_picker[505]+e+azion_easy_text_picker[506]+azion_translated_mapper(azion_easy_text_picker[507])+azion_easy_text_picker[508]+azion_translated_mapper(azion_easy_text_picker[509])+azion_easy_text_picker[510],t+=azion_easy_text_picker[511],t+=azion_easy_text_picker[512]),t+=azion_easy_text_picker[513],t+=azion_easy_text_picker[514]+e+azion_easy_text_picker[515]+azion_translated_mapper(azion_easy_text_picker[516])+azion_easy_text_picker[517],t+=azion_easy_text_picker[518],t+=azion_easy_text_picker[519],t+=azion_easy_text_picker[520],t+=azion_easy_text_picker[521],t+=azion_easy_text_picker[522]),t}),$(azion_easy_text_picker[523]).click(function(){var t=Number($(azion_easy_text_picker[524]).html());$(this).is(azion_easy_text_picker[525])?t++:1<t&&--t,$(azion_easy_text_picker[526]).html(t)}),$(azion_easy_text_picker[550]).click(function(){azion_package_pre_lst($(this))}),$(azion_easy_text_picker[551]).click(function(){var t;$(this).is(azion_easy_text_picker[552])||(t=$(this).attr(azion_easy_text_picker[553]))&&(azion_package_send_out(spot_commerce_waiting_list_counter,t,1),$(this).parents(azion_easy_text_picker[554]).each(function(){$(this).find(azion_easy_text_picker[555]).each(function(){$(azion_easy_text_picker[556]).html(azion_easy_text_picker[557]+$(this).html()+azion_easy_text_picker[558]+azion_translated_mapper(azion_easy_text_picker[559])+azion_easy_text_picker[560]+azion_translated_mapper(azion_easy_text_picker[561])+azion_easy_text_picker[562])})}))});var list_of_tgl_objects=azion_package_load(spot_commerce_active_list_counter),list_of_tgl_counter=0,list_of_tgl=!1,list_of_tgl_content=azion_easy_text_picker[573],list_of_tgl_spinner=!1;function azion_package_waiting_lst(t){$(t).each(function(){member_card=$(this).attr(azion_easy_text_picker[621]),azion_package_empty(spot_commerce_waiting_list_counter,member_card),$(azion_easy_text_picker[622]+member_card+azion_easy_text_picker[623]).remove(),0==$(azion_easy_text_picker[624]).length&&$(azion_easy_text_picker[625]).prepend(azion_easy_text_picker[626]+azion_translated_mapper(azion_easy_text_picker[627])+azion_easy_text_picker[628])})}function azion_package_waiting_lst_index(){$.get(Feed_URL+azion_easy_text_picker[629]+wtin_lst_pointers[wtin_lst_pointers_record].id+azion_easy_text_picker[630],function(t){var e,a=azion_call_back_alternative(t);a.id?(e=azion_easy_text_picker[631],t=azion_easy_text_picker[632],wtin_lst_pointers_record%2==0?t+=azion_easy_text_picker[633]:t+=azion_easy_text_picker[634],wtin_lst_pointers_record%3==0&&(t+=azion_easy_text_picker[635]),wtin_lst_pointers_record%4==0&&(t+=azion_easy_text_picker[636]),object_format_link=a,e+=azion_easy_text_picker[637]+t+azion_easy_text_picker[638]+object_format_link.id+azion_easy_text_picker[639],e+=azion_easy_text_picker[640]+object_format_link.link+azion_easy_text_picker[641],e+=azion_easy_text_picker[642]+object_format_link.thumbnail+azion_easy_text_picker[643],e+=azion_easy_text_picker[644],e+=azion_easy_text_picker[645],e+=azion_easy_text_picker[646]+object_format_link.link+azion_easy_text_picker[647]+object_format_link.title+azion_easy_text_picker[648],azion_empty_checker(object_format_link.cate)?e+=azion_easy_text_picker[653]+object_format_link.link+azion_easy_text_picker[654]+azion_translated_mapper(azion_easy_text_picker[655])+azion_easy_text_picker[656]:e+=azion_easy_text_picker[649]+object_format_link.id+azion_easy_text_picker[650]+azion_translated_mapper(azion_easy_text_picker[651])+azion_easy_text_picker[652],e+=azion_easy_text_picker[657],e+=azion_easy_text_picker[658]+object_format_link.id+azion_easy_text_picker[659]+azion_translated_mapper(azion_easy_text_picker[660])+azion_easy_text_picker[661],e+=azion_easy_text_picker[662],e+=azion_attributes(object_format_link.cate),e+=azion_easy_text_picker[663],$(azion_easy_text_picker[664]).each(function(){$(e).insertBefore($(this))}),wtin_lst_pointers_record++,wtin_lst_pointers_record<wtin_lst_pointers.length?azion_package_waiting_lst_index():($(azion_easy_text_picker[665]).each(function(){$(this).remove()}),azion_thumbnail_handler(),$(azion_easy_text_picker[666]).click(function(){azion_package_pre_lst($(this))}),$(azion_easy_text_picker[667]).click(function(){azion_package_waiting_lst($(this))}))):azion_box_checker()||alert(azion_easy_text_picker[668])},azion_easy_text_picker[669]).fail(function(){azion_box_checker()||alert(azion_easy_text_picker[670])})}azion_on_waiting_list()&&($(azion_easy_text_picker[671]).addClass(azion_easy_text_picker[672]),$(azion_easy_text_picker[673]).addClass(azion_easy_text_picker[674]),wtin_lst_pointers=azion_package_load(spot_commerce_waiting_list_counter),wtin_lst_pointers_record=0,!1!==wtin_lst_pointers&&wtin_lst_pointers.length?($(azion_easy_text_picker[675]).prepend(azion_easy_text_picker[676]+AJAX_LOADING_IMAGE+azion_easy_text_picker[677]),azion_package_waiting_lst_index()):$(azion_easy_text_picker[678]).prepend(azion_easy_text_picker[679]+azion_translated_mapper(azion_easy_text_picker[680])+azion_easy_text_picker[681]));
//]]>
</script> 
</b:if>

</body>
</html>
```
# Tampilan
![image](https://github.com/riskibowo/Tgs.rpl/assets/115862112/540a974a-59a3-4569-99e0-8b2c0ffd762a)

Tampilan keranjang
<img width="368" alt="image" src="https://github.com/riskibowo/Tgs.rpl/assets/115862112/705533d1-2db0-407e-bd13-a706ad5837c7">

