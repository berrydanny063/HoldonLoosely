
<!doctype html>
<html lang="en-US">
<head><meta charset="UTF-8"><script>if(navigator.userAgent.match(/MSIE|Internet Explorer/i)||navigator.userAgent.match(/Trident\/7\..*?rv:11/i)){var href=document.location.href;if(!href.match(/[?&]nowprocket/)){if(href.indexOf("?")==-1){if(href.indexOf("#")==-1){document.location.href=href+"?nowprocket=1"}else{document.location.href=href.replace("#","?nowprocket=1#")}}else{if(href.indexOf("#")==-1){document.location.href=href+"&nowprocket=1"}else{document.location.href=href.replace("#","&nowprocket=1#")}}}}</script><script>class RocketLazyLoadScripts{constructor(){this.triggerEvents=["keydown","mousedown","mousemove","touchmove","touchstart","touchend","wheel"],this.userEventHandler=this._triggerListener.bind(this),this.touchStartHandler=this._onTouchStart.bind(this),this.touchMoveHandler=this._onTouchMove.bind(this),this.touchEndHandler=this._onTouchEnd.bind(this),this.clickHandler=this._onClick.bind(this),this.interceptedClicks=[],window.addEventListener("pageshow",(e=>{this.persisted=e.persisted})),window.addEventListener("DOMContentLoaded",(()=>{this._preconnect3rdParties()})),this.delayedScripts={normal:[],async:[],defer:[]},this.allJQueries=[]}_addUserInteractionListener(e){document.hidden?e._triggerListener():(this.triggerEvents.forEach((t=>window.addEventListener(t,e.userEventHandler,{passive:!0}))),window.addEventListener("touchstart",e.touchStartHandler,{passive:!0}),window.addEventListener("mousedown",e.touchStartHandler),document.addEventListener("visibilitychange",e.userEventHandler))}_removeUserInteractionListener(){this.triggerEvents.forEach((e=>window.removeEventListener(e,this.userEventHandler,{passive:!0}))),document.removeEventListener("visibilitychange",this.userEventHandler)}_onTouchStart(e){"HTML"!==e.target.tagName&&(window.addEventListener("touchend",this.touchEndHandler),window.addEventListener("mouseup",this.touchEndHandler),window.addEventListener("touchmove",this.touchMoveHandler,{passive:!0}),window.addEventListener("mousemove",this.touchMoveHandler),e.target.addEventListener("click",this.clickHandler),this._renameDOMAttribute(e.target,"onclick","rocket-onclick"))}_onTouchMove(e){window.removeEventListener("touchend",this.touchEndHandler),window.removeEventListener("mouseup",this.touchEndHandler),window.removeEventListener("touchmove",this.touchMoveHandler,{passive:!0}),window.removeEventListener("mousemove",this.touchMoveHandler),e.target.removeEventListener("click",this.clickHandler),this._renameDOMAttribute(e.target,"rocket-onclick","onclick")}_onTouchEnd(e){window.removeEventListener("touchend",this.touchEndHandler),window.removeEventListener("mouseup",this.touchEndHandler),window.removeEventListener("touchmove",this.touchMoveHandler,{passive:!0}),window.removeEventListener("mousemove",this.touchMoveHandler)}_onClick(e){e.target.removeEventListener("click",this.clickHandler),this._renameDOMAttribute(e.target,"rocket-onclick","onclick"),this.interceptedClicks.push(e),e.preventDefault(),e.stopPropagation(),e.stopImmediatePropagation()}_replayClicks(){window.removeEventListener("touchstart",this.touchStartHandler,{passive:!0}),window.removeEventListener("mousedown",this.touchStartHandler),this.interceptedClicks.forEach((e=>{e.target.dispatchEvent(new MouseEvent("click",{view:e.view,bubbles:!0,cancelable:!0}))}))}_renameDOMAttribute(e,t,n){e.hasAttribute&&e.hasAttribute(t)&&(event.target.setAttribute(n,event.target.getAttribute(t)),event.target.removeAttribute(t))}_triggerListener(){this._removeUserInteractionListener(this),"loading"===document.readyState?document.addEventListener("DOMContentLoaded",this._loadEverythingNow.bind(this)):this._loadEverythingNow()}_preconnect3rdParties(){let e=[];document.querySelectorAll("script[type=rocketlazyloadscript]").forEach((t=>{if(t.hasAttribute("src")){const n=new URL(t.src).origin;n!==location.origin&&e.push({src:n,crossOrigin:t.crossOrigin||"module"===t.getAttribute("data-rocket-type")})}})),e=[...new Map(e.map((e=>[JSON.stringify(e),e]))).values()],this._batchInjectResourceHints(e,"preconnect")}async _loadEverythingNow(){this.lastBreath=Date.now(),this._delayEventListeners(),this._delayJQueryReady(this),this._handleDocumentWrite(),this._registerAllDelayedScripts(),this._preloadAllScripts(),await this._loadScriptsFromList(this.delayedScripts.normal),await this._loadScriptsFromList(this.delayedScripts.defer),await this._loadScriptsFromList(this.delayedScripts.async);try{await this._triggerDOMContentLoaded(),await this._triggerWindowLoad()}catch(e){}window.dispatchEvent(new Event("rocket-allScriptsLoaded")),this._replayClicks()}_registerAllDelayedScripts(){document.querySelectorAll("script[type=rocketlazyloadscript]").forEach((e=>{e.hasAttribute("src")?e.hasAttribute("async")&&!1!==e.async?this.delayedScripts.async.push(e):e.hasAttribute("defer")&&!1!==e.defer||"module"===e.getAttribute("data-rocket-type")?this.delayedScripts.defer.push(e):this.delayedScripts.normal.push(e):this.delayedScripts.normal.push(e)}))}async _transformScript(e){return await this._littleBreath(),new Promise((t=>{const n=document.createElement("script");[...e.attributes].forEach((e=>{let t=e.nodeName;"type"!==t&&("data-rocket-type"===t&&(t="type"),n.setAttribute(t,e.nodeValue))})),e.hasAttribute("src")?(n.addEventListener("load",t),n.addEventListener("error",t)):(n.text=e.text,t());try{e.parentNode.replaceChild(n,e)}catch(e){t()}}))}async _loadScriptsFromList(e){const t=e.shift();return t?(await this._transformScript(t),this._loadScriptsFromList(e)):Promise.resolve()}_preloadAllScripts(){this._batchInjectResourceHints([...this.delayedScripts.normal,...this.delayedScripts.defer,...this.delayedScripts.async],"preload")}_batchInjectResourceHints(e,t){var n=document.createDocumentFragment();e.forEach((e=>{if(e.src){const i=document.createElement("link");i.href=e.src,i.rel=t,"preconnect"!==t&&(i.as="script"),e.getAttribute&&"module"===e.getAttribute("data-rocket-type")&&(i.crossOrigin=!0),e.crossOrigin&&(i.crossOrigin=e.crossOrigin),n.appendChild(i)}})),document.head.appendChild(n)}_delayEventListeners(){let e={};function t(t,n){!function(t){function n(n){return e[t].eventsToRewrite.indexOf(n)>=0?"rocket-"+n:n}e[t]||(e[t]={originalFunctions:{add:t.addEventListener,remove:t.removeEventListener},eventsToRewrite:[]},t.addEventListener=function(){arguments[0]=n(arguments[0]),e[t].originalFunctions.add.apply(t,arguments)},t.removeEventListener=function(){arguments[0]=n(arguments[0]),e[t].originalFunctions.remove.apply(t,arguments)})}(t),e[t].eventsToRewrite.push(n)}function n(e,t){let n=e[t];Object.defineProperty(e,t,{get:()=>n||function(){},set(i){e["rocket"+t]=n=i}})}t(document,"DOMContentLoaded"),t(window,"DOMContentLoaded"),t(window,"load"),t(window,"pageshow"),t(document,"readystatechange"),n(document,"onreadystatechange"),n(window,"onload"),n(window,"onpageshow")}_delayJQueryReady(e){let t=window.jQuery;Object.defineProperty(window,"jQuery",{get:()=>t,set(n){if(n&&n.fn&&!e.allJQueries.includes(n)){n.fn.ready=n.fn.init.prototype.ready=function(t){e.domReadyFired?t.bind(document)(n):document.addEventListener("rocket-DOMContentLoaded",(()=>t.bind(document)(n)))};const t=n.fn.on;n.fn.on=n.fn.init.prototype.on=function(){if(this[0]===window){function e(e){return e.split(" ").map((e=>"load"===e||0===e.indexOf("load.")?"rocket-jquery-load":e)).join(" ")}"string"==typeof arguments[0]||arguments[0]instanceof String?arguments[0]=e(arguments[0]):"object"==typeof arguments[0]&&Object.keys(arguments[0]).forEach((t=>{delete Object.assign(arguments[0],{[e(t)]:arguments[0][t]})[t]}))}return t.apply(this,arguments),this},e.allJQueries.push(n)}t=n}})}async _triggerDOMContentLoaded(){this.domReadyFired=!0,await this._littleBreath(),document.dispatchEvent(new Event("rocket-DOMContentLoaded")),await this._littleBreath(),window.dispatchEvent(new Event("rocket-DOMContentLoaded")),await this._littleBreath(),document.dispatchEvent(new Event("rocket-readystatechange")),await this._littleBreath(),document.rocketonreadystatechange&&document.rocketonreadystatechange()}async _triggerWindowLoad(){await this._littleBreath(),window.dispatchEvent(new Event("rocket-load")),await this._littleBreath(),window.rocketonload&&window.rocketonload(),await this._littleBreath(),this.allJQueries.forEach((e=>e(window).trigger("rocket-jquery-load"))),await this._littleBreath();const e=new Event("rocket-pageshow");e.persisted=this.persisted,window.dispatchEvent(e),await this._littleBreath(),window.rocketonpageshow&&window.rocketonpageshow({persisted:this.persisted})}_handleDocumentWrite(){const e=new Map;document.write=document.writeln=function(t){const n=document.currentScript,i=document.createRange(),r=n.parentElement;let o=e.get(n);void 0===o&&(o=n.nextSibling,e.set(n,o));const s=document.createDocumentFragment();i.setStart(s,0),s.appendChild(i.createContextualFragment(t)),r.insertBefore(s,o)}}async _littleBreath(){Date.now()-this.lastBreath>45&&(await this._requestAnimFrame(),this.lastBreath=Date.now())}async _requestAnimFrame(){return document.hidden?new Promise((e=>setTimeout(e))):new Promise((e=>requestAnimationFrame(e)))}static run(){const e=new RocketLazyLoadScripts;e._addUserInteractionListener(e)}}RocketLazyLoadScripts.run();</script>
	
		<meta name="viewport" content="width=device-width, initial-scale=1">
	<link rel="profile" href="https://gmpg.org/xfn/11">
	<meta name='robots' content='index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1' />

<!-- Google Tag Manager for WordPress by gtm4wp.com -->
<script data-cfasync="false" data-pagespeed-no-defer>
	var gtm4wp_datalayer_name = "dataLayer";
	var dataLayer = dataLayer || [];
</script>
<!-- End Google Tag Manager for WordPress by gtm4wp.com -->
	<!-- This site is optimized with the Yoast SEO Premium plugin v19.7 (Yoast SEO v19.14) - https://yoast.com/wordpress/plugins/seo/ -->
	<title>Hold on Loosely - Boundless</title><link rel="preload" as="style" href="https://fonts.googleapis.com/css?family=Montserrat%3A100%2C100italic%2C200%2C200italic%2C300%2C300italic%2C400%2C400italic%2C500%2C500italic%2C600%2C600italic%2C700%2C700italic%2C800%2C800italic%2C900%2C900italic&#038;display=swap" /><link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Montserrat%3A100%2C100italic%2C200%2C200italic%2C300%2C300italic%2C400%2C400italic%2C500%2C500italic%2C600%2C600italic%2C700%2C700italic%2C800%2C800italic%2C900%2C900italic&#038;display=swap" media="print" onload="this.media='all'" /><noscript><link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Montserrat%3A100%2C100italic%2C200%2C200italic%2C300%2C300italic%2C400%2C400italic%2C500%2C500italic%2C600%2C600italic%2C700%2C700italic%2C800%2C800italic%2C900%2C900italic&#038;display=swap" /></noscript>
	<link rel="canonical" href="https://www.boundless.org/blog/hold-on-loosely/" />
	<meta property="og:locale" content="en_US" />
	<meta property="og:type" content="article" />
	<meta property="og:title" content="Hold on Loosely" />
	<meta property="og:description" content="If you’re as ancient as me, you might remember the band 38 SPECIAL. (Some of you are nodding; most of you are going, &#8220;Who?&#8221;). One of the group&#8217;s biggest hits was a song about a certain mistake guys make. “Hold on Loosely” counseled over-eager suitors not to let romantic enthusiasm smother a relationship. “So hold [&hellip;]" />
	<meta property="og:url" content="https://www.boundless.org/blog/hold-on-loosely/" />
	<meta property="og:site_name" content="Boundless" />
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:label1" content="Est. reading time" />
	<meta name="twitter:data1" content="4 minutes" />
	<script type="application/ld+json" class="yoast-schema-graph">{"@context":"https://schema.org","@graph":[{"@type":"WebPage","@id":"https://www.boundless.org/blog/hold-on-loosely/","url":"https://www.boundless.org/blog/hold-on-loosely/","name":"Hold on Loosely - Boundless","isPartOf":{"@id":"https://www.boundless.org/#website"},"datePublished":"2011-11-07T20:47:00+00:00","dateModified":"2011-11-07T20:47:00+00:00","breadcrumb":{"@id":"https://www.boundless.org/blog/hold-on-loosely/#breadcrumb"},"inLanguage":"en-US","potentialAction":[{"@type":"ReadAction","target":["https://www.boundless.org/blog/hold-on-loosely/"]}]},{"@type":"BreadcrumbList","@id":"https://www.boundless.org/blog/hold-on-loosely/#breadcrumb","itemListElement":[{"@type":"ListItem","position":1,"name":"Blog Posts","item":"https://www.boundless.org/blog/"},{"@type":"ListItem","position":2,"name":"Hold on Loosely"}]},{"@type":"WebSite","@id":"https://www.boundless.org/#website","url":"https://www.boundless.org/","name":"Boundless","description":"Find your place. Focus your future.","publisher":{"@id":"https://www.boundless.org/#organization"},"potentialAction":[{"@type":"SearchAction","target":{"@type":"EntryPoint","urlTemplate":"https://www.boundless.org/?s={search_term_string}"},"query-input":"required name=search_term_string"}],"inLanguage":"en-US"},{"@type":"Organization","@id":"https://www.boundless.org/#organization","name":"Boundless","url":"https://www.boundless.org/","logo":{"@type":"ImageObject","inLanguage":"en-US","@id":"https://www.boundless.org/#/schema/logo/image/","url":"https://www.boundless.org/wp-content/uploads/2019/08/Boundless_Logo_2CR_RGB@2x.png","contentUrl":"https://www.boundless.org/wp-content/uploads/2019/08/Boundless_Logo_2CR_RGB@2x.png","width":614,"height":148,"caption":"Boundless"},"image":{"@id":"https://www.boundless.org/#/schema/logo/image/"}}]}</script>
	<!-- / Yoast SEO Premium plugin. -->


<link href='https://fonts.gstatic.com' crossorigin rel='preconnect' />
<link rel="alternate" type="application/rss+xml" title="Boundless &raquo; Feed" href="https://www.boundless.org/feed/" />
<link rel="alternate" type="application/rss+xml" title="Boundless &raquo; Comments Feed" href="https://www.boundless.org/comments/feed/" />
<link rel="alternate" type="application/rss+xml" title="Boundless &raquo; Hold on Loosely Comments Feed" href="https://www.boundless.org/blog/hold-on-loosely/feed/" />
<style>
img.wp-smiley,
img.emoji {
	display: inline !important;
	border: none !important;
	box-shadow: none !important;
	height: 1em !important;
	width: 1em !important;
	margin: 0 0.07em !important;
	vertical-align: -0.1em !important;
	background: none !important;
	padding: 0 !important;
}
</style>
	<link rel='stylesheet' id='mci-footnotes-jquery-tooltips-pagelayout-none-css' href='https://www.boundless.org/wp-content/plugins/footnotes/css/footnotes-jqttbrpl0.min.css?ver=2.7.3' media='all' />
<link rel='stylesheet' id='wp-block-library-css' href='https://www.boundless.org/wp-includes/css/dist/block-library/style.min.css?ver=6.1.1' media='all' />
<link rel='stylesheet' id='mediaelement-css' href='https://www.boundless.org/wp-includes/js/mediaelement/mediaelementplayer-legacy.min.css?ver=4.2.17' media='all' />
<link rel='stylesheet' id='wp-mediaelement-css' href='https://www.boundless.org/wp-includes/js/mediaelement/wp-mediaelement.min.css?ver=6.1.1' media='all' />
<link rel='stylesheet' id='view_editor_gutenberg_frontend_assets-css' href='https://www.boundless.org/wp-content/plugins/wp-views/public/css/views-frontend.css?ver=3.6.5' media='all' />
<style id='view_editor_gutenberg_frontend_assets-inline-css'>
.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default > span.wpv-sort-list,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default .wpv-sort-list-item {border-color: #cdcdcd;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default .wpv-sort-list-item a {color: #444;background-color: #fff;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default a:hover,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default a:focus {color: #000;background-color: #eee;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default .wpv-sort-list-item.wpv-sort-list-current a {color: #000;background-color: #eee;}
.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default > span.wpv-sort-list,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default .wpv-sort-list-item {border-color: #cdcdcd;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default .wpv-sort-list-item a {color: #444;background-color: #fff;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default a:hover,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default a:focus {color: #000;background-color: #eee;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default .wpv-sort-list-item.wpv-sort-list-current a {color: #000;background-color: #eee;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey > span.wpv-sort-list,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey .wpv-sort-list-item {border-color: #cdcdcd;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey .wpv-sort-list-item a {color: #444;background-color: #eeeeee;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey a:hover,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey a:focus {color: #000;background-color: #e5e5e5;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey .wpv-sort-list-item.wpv-sort-list-current a {color: #000;background-color: #e5e5e5;}
.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default > span.wpv-sort-list,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default .wpv-sort-list-item {border-color: #cdcdcd;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default .wpv-sort-list-item a {color: #444;background-color: #fff;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default a:hover,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default a:focus {color: #000;background-color: #eee;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-default .wpv-sort-list-item.wpv-sort-list-current a {color: #000;background-color: #eee;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey > span.wpv-sort-list,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey .wpv-sort-list-item {border-color: #cdcdcd;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey .wpv-sort-list-item a {color: #444;background-color: #eeeeee;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey a:hover,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey a:focus {color: #000;background-color: #e5e5e5;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-grey .wpv-sort-list-item.wpv-sort-list-current a {color: #000;background-color: #e5e5e5;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-blue > span.wpv-sort-list,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-blue .wpv-sort-list-item {border-color: #0099cc;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-blue .wpv-sort-list-item a {color: #444;background-color: #cbddeb;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-blue a:hover,.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-blue a:focus {color: #000;background-color: #95bedd;}.wpv-sort-list-dropdown.wpv-sort-list-dropdown-style-blue .wpv-sort-list-item.wpv-sort-list-current a {color: #000;background-color: #95bedd;}
</style>
<link rel='stylesheet' id='classic-theme-styles-css' href='https://www.boundless.org/wp-includes/css/classic-themes.min.css?ver=1' media='all' />
<style id='global-styles-inline-css'>
body{--wp--preset--color--black: #000000;--wp--preset--color--cyan-bluish-gray: #abb8c3;--wp--preset--color--white: #ffffff;--wp--preset--color--pale-pink: #f78da7;--wp--preset--color--vivid-red: #cf2e2e;--wp--preset--color--luminous-vivid-orange: #ff6900;--wp--preset--color--luminous-vivid-amber: #fcb900;--wp--preset--color--light-green-cyan: #7bdcb5;--wp--preset--color--vivid-green-cyan: #00d084;--wp--preset--color--pale-cyan-blue: #8ed1fc;--wp--preset--color--vivid-cyan-blue: #0693e3;--wp--preset--color--vivid-purple: #9b51e0;--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple: linear-gradient(135deg,rgba(6,147,227,1) 0%,rgb(155,81,224) 100%);--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan: linear-gradient(135deg,rgb(122,220,180) 0%,rgb(0,208,130) 100%);--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange: linear-gradient(135deg,rgba(252,185,0,1) 0%,rgba(255,105,0,1) 100%);--wp--preset--gradient--luminous-vivid-orange-to-vivid-red: linear-gradient(135deg,rgba(255,105,0,1) 0%,rgb(207,46,46) 100%);--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray: linear-gradient(135deg,rgb(238,238,238) 0%,rgb(169,184,195) 100%);--wp--preset--gradient--cool-to-warm-spectrum: linear-gradient(135deg,rgb(74,234,220) 0%,rgb(151,120,209) 20%,rgb(207,42,186) 40%,rgb(238,44,130) 60%,rgb(251,105,98) 80%,rgb(254,248,76) 100%);--wp--preset--gradient--blush-light-purple: linear-gradient(135deg,rgb(255,206,236) 0%,rgb(152,150,240) 100%);--wp--preset--gradient--blush-bordeaux: linear-gradient(135deg,rgb(254,205,165) 0%,rgb(254,45,45) 50%,rgb(107,0,62) 100%);--wp--preset--gradient--luminous-dusk: linear-gradient(135deg,rgb(255,203,112) 0%,rgb(199,81,192) 50%,rgb(65,88,208) 100%);--wp--preset--gradient--pale-ocean: linear-gradient(135deg,rgb(255,245,203) 0%,rgb(182,227,212) 50%,rgb(51,167,181) 100%);--wp--preset--gradient--electric-grass: linear-gradient(135deg,rgb(202,248,128) 0%,rgb(113,206,126) 100%);--wp--preset--gradient--midnight: linear-gradient(135deg,rgb(2,3,129) 0%,rgb(40,116,252) 100%);--wp--preset--duotone--dark-grayscale: url('#wp-duotone-dark-grayscale');--wp--preset--duotone--grayscale: url('#wp-duotone-grayscale');--wp--preset--duotone--purple-yellow: url('#wp-duotone-purple-yellow');--wp--preset--duotone--blue-red: url('#wp-duotone-blue-red');--wp--preset--duotone--midnight: url('#wp-duotone-midnight');--wp--preset--duotone--magenta-yellow: url('#wp-duotone-magenta-yellow');--wp--preset--duotone--purple-green: url('#wp-duotone-purple-green');--wp--preset--duotone--blue-orange: url('#wp-duotone-blue-orange');--wp--preset--font-size--small: 13px;--wp--preset--font-size--medium: 20px;--wp--preset--font-size--large: 36px;--wp--preset--font-size--x-large: 42px;--wp--preset--spacing--20: 0.44rem;--wp--preset--spacing--30: 0.67rem;--wp--preset--spacing--40: 1rem;--wp--preset--spacing--50: 1.5rem;--wp--preset--spacing--60: 2.25rem;--wp--preset--spacing--70: 3.38rem;--wp--preset--spacing--80: 5.06rem;}:where(.is-layout-flex){gap: 0.5em;}body .is-layout-flow > .alignleft{float: left;margin-inline-start: 0;margin-inline-end: 2em;}body .is-layout-flow > .alignright{float: right;margin-inline-start: 2em;margin-inline-end: 0;}body .is-layout-flow > .aligncenter{margin-left: auto !important;margin-right: auto !important;}body .is-layout-constrained > .alignleft{float: left;margin-inline-start: 0;margin-inline-end: 2em;}body .is-layout-constrained > .alignright{float: right;margin-inline-start: 2em;margin-inline-end: 0;}body .is-layout-constrained > .aligncenter{margin-left: auto !important;margin-right: auto !important;}body .is-layout-constrained > :where(:not(.alignleft):not(.alignright):not(.alignfull)){max-width: var(--wp--style--global--content-size);margin-left: auto !important;margin-right: auto !important;}body .is-layout-constrained > .alignwide{max-width: var(--wp--style--global--wide-size);}body .is-layout-flex{display: flex;}body .is-layout-flex{flex-wrap: wrap;align-items: center;}body .is-layout-flex > *{margin: 0;}:where(.wp-block-columns.is-layout-flex){gap: 2em;}.has-black-color{color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-color{color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-color{color: var(--wp--preset--color--white) !important;}.has-pale-pink-color{color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-color{color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-color{color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-color{color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-color{color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-color{color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-color{color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-color{color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-color{color: var(--wp--preset--color--vivid-purple) !important;}.has-black-background-color{background-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-background-color{background-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-background-color{background-color: var(--wp--preset--color--white) !important;}.has-pale-pink-background-color{background-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-background-color{background-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-background-color{background-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-background-color{background-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-background-color{background-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-background-color{background-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-background-color{background-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-background-color{background-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-background-color{background-color: var(--wp--preset--color--vivid-purple) !important;}.has-black-border-color{border-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-border-color{border-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-border-color{border-color: var(--wp--preset--color--white) !important;}.has-pale-pink-border-color{border-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-border-color{border-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-border-color{border-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-border-color{border-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-border-color{border-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-border-color{border-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-border-color{border-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-border-color{border-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-border-color{border-color: var(--wp--preset--color--vivid-purple) !important;}.has-vivid-cyan-blue-to-vivid-purple-gradient-background{background: var(--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple) !important;}.has-light-green-cyan-to-vivid-green-cyan-gradient-background{background: var(--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan) !important;}.has-luminous-vivid-amber-to-luminous-vivid-orange-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange) !important;}.has-luminous-vivid-orange-to-vivid-red-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-orange-to-vivid-red) !important;}.has-very-light-gray-to-cyan-bluish-gray-gradient-background{background: var(--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray) !important;}.has-cool-to-warm-spectrum-gradient-background{background: var(--wp--preset--gradient--cool-to-warm-spectrum) !important;}.has-blush-light-purple-gradient-background{background: var(--wp--preset--gradient--blush-light-purple) !important;}.has-blush-bordeaux-gradient-background{background: var(--wp--preset--gradient--blush-bordeaux) !important;}.has-luminous-dusk-gradient-background{background: var(--wp--preset--gradient--luminous-dusk) !important;}.has-pale-ocean-gradient-background{background: var(--wp--preset--gradient--pale-ocean) !important;}.has-electric-grass-gradient-background{background: var(--wp--preset--gradient--electric-grass) !important;}.has-midnight-gradient-background{background: var(--wp--preset--gradient--midnight) !important;}.has-small-font-size{font-size: var(--wp--preset--font-size--small) !important;}.has-medium-font-size{font-size: var(--wp--preset--font-size--medium) !important;}.has-large-font-size{font-size: var(--wp--preset--font-size--large) !important;}.has-x-large-font-size{font-size: var(--wp--preset--font-size--x-large) !important;}
.wp-block-navigation a:where(:not(.wp-element-button)){color: inherit;}
:where(.wp-block-columns.is-layout-flex){gap: 2em;}
.wp-block-pullquote{font-size: 1.5em;line-height: 1.6;}
</style>
<link rel='stylesheet' id='fotf-elementor-extension-css' href='https://www.boundless.org/wp-content/plugins/fotf-elementor-forms-extension/src/public/css/fotf-elementor-extension-public.css?ver=21.2.3' media='all' />
<link rel='stylesheet' id='hello-elementor-css' href='https://www.boundless.org/wp-content/themes/hello-elementor/style.min.css?ver=2.6.1' media='all' />
<link rel='stylesheet' id='hello-elementor-child-css' href='https://www.boundless.org/wp-content/themes/hello-theme-child-master/style.css?ver=1.0.0' media='all' />
<link rel='stylesheet' id='hello-elementor-theme-style-css' href='https://www.boundless.org/wp-content/themes/hello-elementor/theme.min.css?ver=2.6.1' media='all' />
<link rel='stylesheet' id='elementor-icons-css' href='https://www.boundless.org/wp-content/plugins/elementor/assets/lib/eicons/css/elementor-icons.min.css?ver=5.17.0' media='all' />
<link rel='stylesheet' id='elementor-frontend-legacy-css' href='https://www.boundless.org/wp-content/plugins/elementor/assets/css/frontend-legacy.min.css?ver=3.10.0' media='all' />
<link rel='stylesheet' id='elementor-frontend-css' href='https://www.boundless.org/wp-content/plugins/elementor/assets/css/frontend.min.css?ver=3.10.0' media='all' />
<link rel='stylesheet' id='elementor-post-29643-css' href='https://www.boundless.org/wp-content/uploads/elementor/css/post-29643.css?ver=1673627595' media='all' />
<link rel='stylesheet' id='elementor-pro-css' href='https://www.boundless.org/wp-content/plugins/elementor-pro/assets/css/frontend.min.css?ver=3.10.1' media='all' />
<link rel='stylesheet' id='elementor-global-css' href='https://www.boundless.org/wp-content/uploads/elementor/css/global.css?ver=1673627596' media='all' />
<link rel='stylesheet' id='elementor-post-29667-css' href='https://www.boundless.org/wp-content/uploads/elementor/css/post-29667.css?ver=1673627596' media='all' />
<link rel='stylesheet' id='elementor-post-26385-css' href='https://www.boundless.org/wp-content/uploads/elementor/css/post-26385.css?ver=1673627596' media='all' />
<link rel='stylesheet' id='elementor-post-26624-css' href='https://www.boundless.org/wp-content/uploads/elementor/css/post-26624.css?ver=1673627599' media='all' />

<link rel='stylesheet' id='elementor-icons-shared-0-css' href='https://www.boundless.org/wp-content/plugins/elementor/assets/lib/font-awesome/css/fontawesome.min.css?ver=5.15.3' media='all' />
<link rel='stylesheet' id='elementor-icons-fa-solid-css' href='https://www.boundless.org/wp-content/plugins/elementor/assets/lib/font-awesome/css/solid.min.css?ver=5.15.3' media='all' />
<link rel='stylesheet' id='elementor-icons-fa-brands-css' href='https://www.boundless.org/wp-content/plugins/elementor/assets/lib/font-awesome/css/brands.min.css?ver=5.15.3' media='all' />
<link rel="preconnect" href="https://fonts.gstatic.com/" crossorigin><script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/wp-views/vendor/toolset/common-es/public/toolset-common-es-frontend.js?ver=164000' id='toolset-common-es-frontend-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/jquery/jquery.min.js?ver=3.6.1' id='jquery-core-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/jquery/jquery-migrate.min.js?ver=3.3.2' id='jquery-migrate-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/footnotes/js/jquery.tools.min.js?ver=1.2.7.redacted.2' id='mci-footnotes-jquery-tools-js'></script>
<script id='fotf-elementor-extension-js-extra'>
var fotfSeFieldSettings = {"organization_name":{"type":"text","name":"Organization Name*","label":"Organization Name","placeholder":"Organization Name","required":true,"pattern":"\/^[a-zA-Z0-9\\s'.-]{1,70}$\/","pattern_modifiers":"","maxlength":70,"title":"Please use between 1-70 characters.\n\t\tPlease use only alphabet, apostrophe, hyphen, space and period.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"organization_name","account_type":"organization"},"organization_confirm_email":{"type":"email","name":"Organization Email Address Confirmation","label":"Organization Confirm Email","placeholder":"example@domain.com","required":false,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":null,"error_msg":"Provided email addresses don't match","default_value":"","custom_post_type_id":null,"html_element_id":"organization_confirm_email","account_type":"organization"},"organization_state":{"type":"text","name":"Organization State","label":"Organization State\/Province","placeholder":"Enter 2 digit state or province abbreviation","required":false,"pattern":"\/^[a-zA-Z]{2}$\/","pattern_modifiers":"","maxlength":2,"title":"Please enter 2-digit abbreviation of the state or province.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"organization_state","account_type":"organization"},"organization_email_address":{"type":"email","name":"Organization Email Address**","label":"Organization Email Address","placeholder":"example@domain.com","required":true,"pattern":"\/^[+\\^'_\\.0-9a-zA-Z-]+@[a-zA-Z0-9]+([\\-\\.]{1}[a-zA-Z0-9]+)*\\.[a-zA-Z]{2,}$\/","pattern_modifiers":"","maxlength":null,"title":"Must meet email standard format.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"organization_email_address","account_type":"organization"},"organization_country_codes":{"type":"select","name":"Organization Country*","label":"Organization Country","placeholder":null,"required":true,"pattern":"\/^([a-zA-Z]{2}|[a-zA-Z]{2}-[0-9])$\/","pattern_modifiers":"","maxlength":null,"title":"Select a country from the selection","error_msg":null,"default_value":"US","custom_post_type_id":"fotf_countrycode","account_type":"organization","html_element_id":"organization_country_codes","mapped_value":"Country"},"organization_zip_code":{"type":"text","name":"Organization Zip Code","label":"Organization Zip Code","placeholder":"12345-1234","required":false,"pattern":"\/^[0-9]{5}(?:-[0-9]{4})?$\/","pattern_modifiers":"","maxlength":null,"title":"Valid zip code formats only.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"organization_zip_code","account_type":"organization"},"organization_phone":{"type":"text","name":"Organization Phone Number**","label":"Organization Phone Number","placeholder":"555-555-5555","required":false,"pattern":"\/[0-9()#&+*-=. ]+\/","pattern_modifiers":"","maxlength":null,"title":"Area code, followed by your 7-digit phone number, cell phone preferred. For international, up to 15 digits.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"organization_phone","account_type":"organization","phone_util":{}},"church_denomination":{"type":"select","name":"Church Denomination","label":"Church Denomination","placeholder":"Make a selection...","required":false,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":"Please select an option","error_msg":null,"default_value":"","custom_post_type_id":"fotf_church_denom","account_type":"organization","html_element_id":"church_denomination"},"organization_city":{"type":"text","name":"Organization City","label":"Organization City","placeholder":"Enter the city","required":false,"pattern":"\/^[A-Za-z-\\s\\\/\\)\\(`\\.\"']{1,20}$\/","pattern_modifiers":"","maxlength":20,"title":"No more than 20 characters.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"organization_city","account_type":"organization"},"contact_phone":{"type":"tel","name":"Contact Phone Number**","label":"Contact Phone Number","placeholder":"5555555555","required":false,"pattern":"\/^(\\d{1,15})$\/","pattern_modifiers":"","maxlength":null,"title":"Area code, followed by your 7-digit phone number, cell phone preferred. Numbers only, no dashes or other separator. For international, up to 15 digits.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"contact_phone","account_type":"contact"},"contact_email_address":{"type":"email","name":"Contact Email Address**","label":"Contact Email Address","placeholder":"example@domain.com","required":true,"pattern":"\/^[+\\^'_\\.0-9a-zA-Z-]+@[a-zA-Z0-9]+([\\-\\.]{1}[a-zA-Z0-9]+)*\\.[a-zA-Z]{2,}$\/","pattern_modifiers":"","maxlength":null,"title":"Must meet email standard format.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"contact_email_address","account_type":"contact"},"contact_title":{"type":"select","name":"Contact Title","label":"Contact Title","placeholder":"Contact Title","required":false,"pattern":null,"pattern_modifiers":"","maxlength":7,"title":"Please select a contact title","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"contact_title","account_type":"contact","options":"Mr.|Mr.\nMrs.|Mrs.\nMs.|Ms.\nMiss|Miss\nDr.|Dr.\nRev.|Rev.\nPastor|Pastor"},"contact_last_name":{"type":"text","name":"Contact Last Name*","label":"Contact Last Name","placeholder":"Contact Last Name","required":true,"pattern":"\/^[a-zA-Z\\s'.-]{1,20}$\/","pattern_modifiers":"","maxlength":20,"title":"Please use between 1-20 characters.\n\t\tPlease use only alphabet, apostrophe, hyphen, space and period.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"contact_last_name","account_type":"contact"},"contact_suffix":{"type":"text","name":"Contact Suffix","label":"Contact Suffix","placeholder":"Contact Suffix","required":false,"pattern":"\/^[a-zA-Z\\s'.-]{1,20}$\/","pattern_modifiers":"","maxlength":20,"title":"Please use between 1-20 characters.\n\t\tPlease use only alphabet, apostrophe, hyphen, space and period.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"contact_suffix","account_type":"contact"},"contact_type":{"type":"select","name":"Contact Type","label":"Contact Type","placeholder":"Select contact type...","required":false,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":"Select a contact type from the options below","error_msg":null,"default_value":"","custom_post_type_id":"fotf_contact_type","html_element_id":"contact_type","account_type":"contact","multiple":false},"contact_first_name":{"type":"text","name":"Contact First Name*","label":"Contact First Name","placeholder":"Contact First Name","required":true,"pattern":"\/^[a-zA-Z\\s'.-]{1,20}$\/","pattern_modifiers":"","maxlength":20,"title":"Please use between 1-20 characters.\n\t\tPlease use only alphabet, apostrophe, hyphen, space and period.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"contact_first_name","account_type":"contact"},"contact_ministry_role":{"type":"select","name":"Contact Ministry Role","label":"Contact Ministry Role","placeholder":"Select ministry role...","required":false,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":"Select a ministry role from the options below","error_msg":null,"default_value":"","custom_post_type_id":"fotf_ministry_role","account_type":"contact","html_element_id":"contact_ministry_role","multiple":false},"church_services_offered":{"type":"checkbox","name":"Church Services Offered","label":"Church Services Offered","placeholder":"Make a selection...","required":false,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":"Please select an option","error_msg":null,"default_value":"","custom_post_type_id":"fotf_church_service","account_type":"organization","html_element_id":"church_services_offered"},"organization_type":{"type":["select","hidden"],"name":"Organization Type*","label":"Organization Type","placeholder":"Make a selection...","required":true,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":"Please select an option","error_msg":null,"default_value":"","custom_post_type_id":"fotf_org_type","account_type":"organization","html_element_id":"organization_type"},"organization_address":{"type":"text","name":"Organization Address**","label":"Organization Address","placeholder":"Street Address or P.O. Box","required":false,"pattern":"\/^.{2,70}$\/","pattern_modifiers":"","maxlength":70,"title":"Please use between 2-70 characters; Please use only alphabet, numbers, apostrophe, hyphen, space and period.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"organization_address","account_type":"organization"},"organization_address_line_two":{"type":"text","name":"Organization Address Line 2 (Inside US)","label":"","placeholder":"Organization Address Line 2 [OPTIONAL] - i.e Apartment, suite, unit, building, floor, etc...","required":false,"pattern":"\/^.{2,70}$\/","pattern_modifiers":"","maxlength":70,"title":"Please use between 2-70 characters; Please use only alphabet, numbers, apostrophe, hyphen, space and period.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"organization_address_line_two","account_type":"organization"},"church_size":{"type":"select","name":"Church Size","label":"Church Size","placeholder":"Make a selection...","required":false,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":"Please select an option","error_msg":null,"default_value":"","custom_post_type_id":"fotf_church_size","account_type":"organization","html_element_id":"church_size"},"organization_phone_Extension":{"type":"text","name":"Organization Phone Number Extension","label":"Organization Phone Number Extension","placeholder":"1234","required":false,"pattern":"\/[0-9]+\/","pattern_modifiers":"","maxlength":null,"title":"Only numbers are accepted. ","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"organization_phone_Extension","account_type":"organization"},"phone":{"type":"tel","name":"Phone Number","label":"Phone Number","placeholder":"5555555555","required":false,"pattern":"\/^(\\d{1,15})$\/","pattern_modifiers":"","maxlength":null,"title":"Area code, followed by your 7-digit phone number, cell phone preferred. Numbers only, no dashes or other separator. For international, up to 15 digits.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"phone","account_type":"individual"},"birthdate":{"type":"date","name":"Birthdate","label":"Birthdate","placeholder":"yyyy-mm-dd","required":false,"pattern":"\/(^([12]\\d{3}-(0[1-9]|1[0-2])-([0][1-9]|[12]\\d|3[01]))$|^(0[1-9]|1[0-2])\\\/([0][1-9]|[12]\\d|3[01])\\\/([12]\\d{3})$)\/","pattern_modifiers":"","maxlength":null,"title":"Format must be entered in yyyy-mm-dd or mm\/dd\/yyyy format. The date cannot be a future date, or before 01\/01\/1900","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"birthdate","account_type":"individual","min":"1900-01-01"},"confirm_email":{"type":"email","name":"Email Address Confirmation","label":"Confirm Email","placeholder":"example@domain.com","required":false,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":null,"error_msg":"Provided email addresses don't match","default_value":"","custom_post_type_id":null,"html_element_id":"confirm_email","account_type":"individual"},"ad_hoc":{"type":["text","textarea","radio","select","checkbox","acceptance","number"],"name":"Ad Hoc","label":null,"placeholder":null,"required":false,"pattern":"\/^.{0,8000}$\/","pattern_modifiers":"s","maxlength":null,"title":"All characters allowed.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"ad_hoc","account_type":"individual"},"City":{"type":"text","name":"City","label":"City","placeholder":"Enter the city","required":false,"pattern":"\/^[A-Za-z-\\s\\\/\\)\\(`\\.\"']{1,20}$\/","pattern_modifiers":"","maxlength":20,"title":"No more than 20 characters.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"City","account_type":"individual"},"State":{"type":"text","name":"State","label":"State\/Province","placeholder":"Enter 2 digit state or province abbreviation","required":false,"pattern":"\/^[a-zA-Z]{2}$\/","pattern_modifiers":"","maxlength":2,"title":"Please enter 2-digit abbreviation of the state or province.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"State","account_type":"individual"},"last_name":{"type":"text","name":"Last Name*","label":"Last Name","placeholder":"Last Name","required":true,"pattern":"\/^[a-zA-Z\\s'.-]{1,20}$\/","pattern_modifiers":"","maxlength":20,"title":"Please use between 1-20 characters.\n\t\tPlease use only alphabet, apostrophe, hyphen, space and period.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"last_name","account_type":"individual"},"email_address":{"type":"email","name":"Email Address*","label":"Email Address","placeholder":"example@domain.com","required":true,"pattern":"\/^[+\\^'_\\.0-9a-zA-Z-]+@[a-zA-Z0-9]+([\\-\\.]{1}[a-zA-Z0-9]+)*\\.[a-zA-Z]{2,}$\/","pattern_modifiers":"","maxlength":null,"title":"Must meet email standard format.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"email_address","account_type":"individual"},"address":{"type":"text","name":"Address","label":"Address","placeholder":"Street Address or P.O. Box","required":false,"pattern":"\/^.{2,70}$\/","pattern_modifiers":"","maxlength":70,"title":"Please use between 2-70 characters; Please use only alphabet, numbers, apostrophe, hyphen, space and period.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"address","account_type":"individual"},"zip_code":{"type":"text","name":"Zip Code","label":"Zip Code","placeholder":"12345-1234","required":false,"pattern":"\/^[0-9]{5}(?:-[0-9]{4})?$\/","pattern_modifiers":"","maxlength":null,"title":"Valid zip code formats only.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"zip_code","account_type":"individual"},"age_verification":{"type":"acceptance","name":"13 or Over Age Verification","label":"Age Verification","placeholder":null,"required":true,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":"You must be age 13 or older. Please confirm by checking box.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"age_verification","account_type":"individual","acceptance_text":"Are you 13 years of age or older?"},"marital_status":{"type":"select","name":"Marital Status","label":"Marital Status","placeholder":null,"required":false,"pattern":"\/^(BLENDED|DIVORCED|LIVWPRTNR|MARRIED|REMARRIED|SEPARATED|SINGLE|WIDOWED)$\/","pattern_modifiers":"","maxlength":null,"title":"Select Your Marital Status","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"marital_status","account_type":"individual","options":" | \nBlended|BLENDED\nDivorced|DIVORCED\nLiving With Partner|LIVWPRTNR\nMarried|MARRIED\nRemarried|REMARRIED\nSeparated|SEPARATED\nSingle|SINGLE\nWidowed|WIDOWED"},"gender":{"type":"select","name":"Gender","label":"Gender","placeholder":"M","required":false,"pattern":"\/^(M|F)$\/","pattern_modifiers":"","maxlength":1,"title":"Must select M or F.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"gender","account_type":"individual","options":" | \nMale|M\nFemale|F"},"year_started_in_ministry":{"type":"text","name":"Year Started In Ministry","label":"Year Started In Ministry","placeholder":"1999","required":false,"pattern":"\/^(1919|19[2-9][0-9]|20[0-9][0-9]|21[0-1][0-9])$\/","pattern_modifiers":"","maxlength":null,"title":"Year must be between 1919 and 2119","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"year_started_in_ministry","account_type":"individual"},"long_comment":{"type":"textarea","name":"Comment","label":"Comment","placeholder":"Enter comment here","required":false,"pattern":"\/^.{0,8000}$\/","pattern_modifiers":"s","maxlength":8000,"title":"Comment must be less than 8000 characters","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"long_comment","account_type":"individual"},"country_codes":{"type":"select","name":"Country*","label":"Country","placeholder":null,"required":true,"pattern":"\/^([a-zA-Z]{2}|[a-zA-Z]{2}-[0-9])$\/","pattern_modifiers":"","maxlength":null,"title":"Select a country from the selection","error_msg":null,"default_value":"US","custom_post_type_id":"fotf_countrycode","account_type":"individual","html_element_id":"country_codes","mapped_value":"Country"},"ministry_role":{"type":"select","name":"Ministry Role","label":"Ministry Role","placeholder":"Select ministry role...","required":false,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":"Select a ministry role from the options below","error_msg":null,"default_value":"","custom_post_type_id":"fotf_ministry_role","account_type":"individual","html_element_id":"ministry_role","multiple":false},"first_name":{"type":"text","name":"First Name*","label":"First Name","placeholder":"First Name","required":true,"pattern":"\/^[a-zA-Z\\s'.-]{1,20}$\/","pattern_modifiers":"","maxlength":20,"title":"Please use between 1-20 characters.\n\t\tPlease use only alphabet, apostrophe, hyphen, space and period.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"first_name","account_type":"individual"},"child_ages":{"type":"checkbox","name":"Child Ages","label":"Child Ages","placeholder":"Select ages of your children:","required":true,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":"Select ages of your children from the options below","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"child_ages","account_type":"individual","multiple":true,"options":"No Children|-1\nLess than 1 year old|0\n1 year old|1\n2 years old|2\n3 years old|3\n4 years old|4\n5 years old|5\n6 years old|6\n7 years old|7\n8 years old|8\n9 years old|9\n10 years old|10\n11 years old|11\n12 years old|12\n13 years old|13\n14 years old|14\n15 years old|15\n16 years old|16\n17 years old|17\n18 years old|18\nOver 18 years old|99"},"magazine_subscription":{"subscription_code":null,"price_code":null,"type":"acceptance","name":"Magazine Subscription","label":"Magazine Subscription","placeholder":null,"required":false,"pattern":null,"pattern_modifiers":"","maxlength":null,"title":"Would you like a free magazine subscription? Please confirm by checking box.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"magazine_subscription","account_type":"individual","acceptance_text":"Would you like a free magazine subscription?"},"address_line_two":{"type":"text","name":"Address Line 2 (Inside US)","label":"","placeholder":"Address Line 2 [OPTIONAL] - i.e Apartment, suite, unit, building, floor, etc...","required":false,"pattern":"\/^.{2,70}$\/","pattern_modifiers":"","maxlength":70,"title":"Please use between 2-70 characters; Please use only alphabet, numbers, apostrophe, hyphen, space and period.","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"address_line_two","account_type":"individual"},"phone_type":{"type":"select","name":"Phone Number Type","label":"Phone Number Type","placeholder":null,"required":false,"pattern":"\/^(HOME|BUS|CELL)$\/","pattern_modifiers":"","maxlength":null,"title":"Select The Phone Number Type","error_msg":null,"default_value":"","custom_post_type_id":null,"html_element_id":"phone_type","account_type":"individual","options":" | \nHome|HOME\nBusiness|BUS\nMobile|CELL"}};
</script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/fotf-elementor-forms-extension/src/public/js/public-bundle.js?ver=21.2.3' id='fotf-elementor-extension-js'></script>
<link rel="https://api.w.org/" href="https://www.boundless.org/wp-json/" /><link rel="EditURI" type="application/rsd+xml" title="RSD" href="https://www.boundless.org/xmlrpc.php?rsd" />
<link rel="wlwmanifest" type="application/wlwmanifest+xml" href="https://www.boundless.org/wp-includes/wlwmanifest.xml" />
<link rel='shortlink' href='https://www.boundless.org/?p=11904' />
<link rel="alternate" type="application/json+oembed" href="https://www.boundless.org/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fwww.boundless.org%2Fblog%2Fhold-on-loosely%2F" />
<link rel="alternate" type="text/xml+oembed" href="https://www.boundless.org/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fwww.boundless.org%2Fblog%2Fhold-on-loosely%2F&#038;format=xml" />
		<meta property="fb:pages" content="136231928822" />
		
<!-- Google Tag Manager for WordPress by gtm4wp.com -->
<!-- GTM Container placement set to automatic -->
<script data-cfasync="false" data-pagespeed-no-defer type="text/javascript">
	var dataLayer_content = {"pagePostType":"blog","pagePostType2":"single-blog","pageCategory":["spiritual-growth"],"instantArticle":false};
	dataLayer.push( dataLayer_content );
</script>
<script type="rocketlazyloadscript" data-cfasync="false">
(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'//www.googletagmanager.com/gtm.'+'js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-WHJ6VC');
</script>
<!-- End Google Tag Manager -->
<!-- End Google Tag Manager for WordPress by gtm4wp.com --><script type="rocketlazyloadscript" src="//player.ooyala.com/core/391e099a718f4a62b44c78f97f85ecde"></script> <script type="rocketlazyloadscript"> window.addEventListener("load",function(){ var c={script:false,link:false}; function ls(s) { if(!['script','link'].includes(s)||c[s]){return;}c[s]=true; var d=document,f=d.getElementsByTagName(s)[0],j=d.createElement(s); if(s==='script'){j.async=true;j.src='https://www.boundless.org/wp-content/plugins/wp-views/vendor/toolset/blocks/public/js/frontend.js?v=1.6.4';}else{ j.rel='stylesheet';j.href='https://www.boundless.org/wp-content/plugins/wp-views/vendor/toolset/blocks/public/css/style.css?v=1.6.4';} f.parentNode.insertBefore(j, f); }; function ex(){ls('script');ls('link')} window.addEventListener("scroll", ex, {once: true}); if (('IntersectionObserver' in window) && ('IntersectionObserverEntry' in window) && ('intersectionRatio' in window.IntersectionObserverEntry.prototype)) { var i = 0, fb = document.querySelectorAll("[class^='tb-']"), o = new IntersectionObserver(es => { es.forEach(e => { o.unobserve(e.target); if (e.intersectionRatio > 0) { ex();o.disconnect();}else{ i++;if(fb.length>i){o.observe(fb[i])}} }) }); if (fb.length) { o.observe(fb[i]) } } }) </script>
	<noscript>
		<link rel="stylesheet" href="https://www.boundless.org/wp-content/plugins/wp-views/vendor/toolset/blocks/public/css/style.css">
	</noscript><link rel="icon" href="https://www.boundless.org/wp-content/uploads/2018/08/cropped-favicon-1-32x32.png" sizes="32x32" />
<link rel="icon" href="https://www.boundless.org/wp-content/uploads/2018/08/cropped-favicon-1-192x192.png" sizes="192x192" />
<link rel="apple-touch-icon" href="https://www.boundless.org/wp-content/uploads/2018/08/cropped-favicon-1-180x180.png" />
<meta name="msapplication-TileImage" content="https://www.boundless.org/wp-content/uploads/2018/08/cropped-favicon-1-270x270.png" />
		<style id="wp-custom-css">
			/* Global Styles */
body {
	font-family:'Montserrat',Helvetica,Arial,Lucida,sans-serif;
}

p {
  line-height: 1.7em;
}

ul {
	margin-bottom: 0.9em;
}

h1,h2,h3,h4,h5,h6 {
	font-weight:600;
	line-height:1.2;
}

a {
	color:#2ad2c9;
}

a:hover {
	color:#2ad2c9;
	text-decoration:underline;
}

.elementor-26384 .elementor-element.elementor-element-383b4846 > .elementor-container {
	height: 113px;
}
.elementor-button {
	background-color:#2ad2c9;
	border:none;
}

.elementor-button:hover {
	text-decoration:underline;
}

/** Header **/
.elementor-search-form__container {
	flex-direction:row-reverse;
	height: 24px;
}

/*-- Navigation --*/
.elementor-nav-menu--main .elementor-nav-menu a {
	-webkit-transition:.1s;
	-o-transition:.1s;
	transition:.1s;
}

.elementor-nav-menu--main .elementor-nav-menu li {
	position:relative;
}

.mainnav a:hover,.mainnav a:active,.mainnav li.current-menu-item {
	font-weight:600;
}

.mainnav .elementor-nav-menu--main .elementor-nav-menu > li:hover:after {
	font-family:"Font Awesome 5 Free";
	position:absolute;
	color:#51BAB1;
	font-weight:600;
	font-size:16px;
	top:4px;
	right:4px;
	transform:rotate(45deg);
	content:'\f077';
}

.mainnav .elementor-nav-menu--main .elementor-nav-menu > li.current-menu-item:after {
	font-family:"Font Awesome 5 Free";
	position:absolute;
	color:#51BAB1;
	font-weight:600;
	font-size:16px;
	top:4px;
	right:4px;
	transform:rotate(45deg);
	content:'\f077';
}

.mainnav ul.elementor-nav-menu--dropdown a,ul.elementor-nav-menu--dropdown a:focus,ul.elementor-nav-menu--dropdown a:hover {
	text-shadow:none;
	border-left:0 solid transparent;
}

/** Footer **/
.donate-btn a {
	display:inline-block;
	background-color:#de7c00;
	padding:3px 6px!important;
	margin-left:20px;
}

.newsletter-cta:before {
	content:"";
	position:absolute;
	bottom:0;
	left:0;
	width:65px;
	height:60px;
	border-left:solid 4px #51BAB1;
	border-bottom:solid 4px #51BAB1;
}

.newsletter-cta:after {
	content:"";
	position:absolute;
	top:0;
	right:0;
	width:65px;
	height:60px;
	border-right:solid 4px #51BAB1;
	border-top:solid 4px #51BAB1;
}

.signup-btn {
	margin-bottom:1rem;
}

.footersm .elementor-social-icon:not(:last-child) {
	margin:0 50px 20px;
}

.elementor-social-icon:last-child {
	margin:0 50px 20px;
}

/* Blog */
.blog-meta-author {
	color:#9B9B9B;
	font-weight:300;
	font-size:.875rem;
}

.blog-meta-author span a {
	color:#9B9B9B;
	text-transform:uppercase;
	font-weight:300;
}

.blog-meta-date {
	color:#9B9B9B;
	font-weight:300;
}

.article-category {
	color:#fff;
	background-color:#2ad2c9;
	font-size:.875rem;
	font-weight:600;
	margin:0 1px;
	padding:3px 6px;
}

.article-category:first-child {
	margin:1px 1px 1px 0;
}

.article-category:hover {
	color:#fff;
}

.article-category.life-with-others {
	background-color:#2AD2C9!important;
}

/*-- Blog Author --*/
.bio-box {
	padding:20px;
	background:#F0F0F0;
	overflow:auto;
	margin:20px 0;
}

.bio-box h3 {
	margin:0 10px 0 0;
	color:#425563;
	font-size:26px;
	letter-spacing:1.5px;
	font-weight:600!important;
}

.bio-box .bio-photo {
	margin:10px 0;
	padding-right:20px;
	width:30%;
	display:inline-block;
	float:left;
	max-width:100%;
}

.bio-box .bio-desc {
	width:70%;
	float:right;
}

.bio-box .bio-desc span.name {
	color:#9B9B9B;
	font-size:20px;
	display:block;
	margin-top:10px;
	margin-bottom:10px;
	text-transform:uppercase;
}

.bio-box .bio-desc span.name a {
	color:#9B9B9B;
}

.bio-box .bio-desc span.name a:hover {
	text-decoration:underline;
}

.bio-box .bio-desc p {
	font-size:14px;
	color:#4A4A4A;
	line-height:1.5;
}

/* Articles */
#featured-category-article .article {
	height:395px;
	background-size:cover;
	background-position:center center;
	border:none;
	padding:17px 0;
}

#featured-category-article .article .post-content-box {
	bottom:0;
	position:absolute;
	width:100%;
}

#featured-category-article .article .article-details {
	border:none;
	background:rgba(24,30,35,0.85);
	padding:26px 18px;
	color:#fff;
	background:-webkit-gradient(linear,left top,left bottom,from(transparent),color-stop(90%,black));
	background:linear-gradient(to bottom,transparent 0%,black 90%);
	filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000',endColorstr='#000000',GradientType=0);
}

#featured-category-article .article .article-details .post-ctgys span {
	padding:0 6px;
	line-height:1.3;
}

#featured-category-article .article .article-details .post-ctgys {
	margin:0 0 5px;
}

.article-details.faith .post-ctgys a,.article-details.faith .post-ctgys span {
	background-color:#FFB500;
}

    .post-ctgys a.article-category.relationships, .post-ctgys a.article-category.dating, .post-ctgys a.article-category.marriage-prep, .post-ctgys a.article-category.life-with-others, .post-ctgys span.article-category.relationships, .post-ctgys span.article-category.dating, .post-ctgys span.article-category.marriage-prep, .post-ctgys span.article-category.life-with-others {
      background-color: #2AD2C9; }
    .post-ctgys a.article-category.adulthood, .post-ctgys a.article-category.being-single, .post-ctgys a.article-category.sexuality, .post-ctgys a.article-category.personal-growth, .post-ctgys a.article-category.career-finances, .post-ctgys span.article-category.adulthood, .post-ctgys span.article-category.being-single, .post-ctgys span.article-category.sexuality, .post-ctgys span.article-category.personal-growth, .post-ctgys span.article-category.career-finances {
      background-color: #DC582A; }
    .post-ctgys a.article-category.faith, .post-ctgys a.article-category.church, .post-ctgys a.article-category.ministry-service, .post-ctgys a.article-category.sharing-your-faith, .post-ctgys a.article-category.spiritual-growth, .post-ctgys span.article-category.faith, .post-ctgys span.article-category.church, .post-ctgys span.article-category.ministry-service, .post-ctgys span.article-category.sharing-your-faith, .post-ctgys span.article-category.spiritual-growth {
      background-color: #FFB500; }


.post-ctgys a,.post-ctgys span {
	display:inline-block;
	color:#fff!important;
	font-size:14px;
	line-height:1;
	font-weight:700;
	padding:3px 5px;
}

#featured-category-article .article .article-details h3.entry-title {
	padding-bottom:0;
}

#featured-category-article .article .article-details h3.entry-title a {
	font-size:30px;
	font-weight:600;
	color:#fff;
}

.post-content h1,.post-content .entry-title {
	font-size:36px;
	font-weight:700;
}

.post-content h1,.post-content .entry-title a:hover {
	text-decoration:none;
}

.article-details .post-authors,.article-details .post-authors a {
	text-transform:uppercase!important;
	font-size:16px!important;
	color:#9B9B9B!important;
}

#featured-category-article .article .article-details .post-excerpt {
	font-size:.875rem;
}

#featured-category-article .article .article-details .post-excerpt p {
	line-height:1.275;
}

.elementor-widget-image .elementor-image > a, .elementor-widget-image .elementor-image figure > a {
	display: block;
}

/*.article-details.faith {
    border-color: #FFB500;
}
.article-details {
    border: solid 2px #51BAB1;
    height: 100%;
}*/
/* Masonry Grid */
.grid-sizer {
		width:48%;
}

.grid-item {
	width:48%;
	margin-bottom:4%;
}

.gutter-sizer {
	width:4%;
}
#related-content article {
	margin-bottom: 4%
}
#post-grid .page-load-status {
	display:none;
	padding-top:20px;
	border-top:1px solid #DDD;
	text-align:center;
	color:#777;
}

#related-content article,
#post-grid article.blog {
	background-color:#F6F6F6;
	font-family:Montserrat,Helvetica,sans-serif;
}

.archive #post-grid article.blog .header {
	position:relative;
}
#related-content article .article-image,
.archive #post-grid article.blog .header a {
	position:relative;
	display:block;
	line-height:0
}

.archive .header {
	width:100%;
	padding:0;
}

#post-grid article.blog {
	background-color:#F6F6F6;
}

#post-grid article {
	background-size:cover;
	background-repeat:no-repeat;
	background-position:center center;
}

.grid-item article {
	margin-bottom:0;
}

#post-grid article.blog .header a img {
	-o-object-fit:cover;
	object-fit:cover;
	height:225px;
}

#related-content article .article-content,
#post-grid article.blog .post-content {
	padding:10px;
}

#post-grid article.blog .post-authors {
	color:#9B9B9B;
	font-size:.75rem;
	line-height:1.7em;
}

#post-grid article.blog .post-authors a {
	color:#9B9B9B;
	font-size:.75rem;
}

#related-content article .article-content h3,
#post-grid article.blog h2.post-title {
	line-height:1.1;
	font-weight:700;
	margin-bottom:.5rem;
	margin-top:0
}

#related-content article .article-content h3 a,
#post-grid article.blog h2.post-title a {
	color:#333F48;
	font-size:1.675rem!important;
}

#related-content article .article-content p,
#post-grid article.blog .excerpt p {
	padding:0;
	line-height:1.7em;
	margin:0
}

.et_pb_extra_overlay {
	z-index:3;
	position:absolute;
	top:0;
	left:0;
	display:block;
	background:rgba(0,0,0,.3);
	width:100%;
	height:100%;
	opacity:0;
	transition:.3s ease;
}

.et_pb_extra_overlay:hover {
	opacity:1;
}

.et_pb_extra_overlay:before {
	font-family:"Font Awesome 5 Free";
	content:'\f055';
	position:absolute;
	color:#fff;
/*background-color: #fff;
    border-radius: 50%;*/
	padding:10px;
	top:50%;
	left:50%;
	display:inline-block;
	transition:.3s ease;
	-webkit-transform:translate(-50%,-50%);
	transform:translate(-50%,-50%);
	font-size:24px;
	line-height:24px;
}

.elementor-widget-theme-post-content hr,
.blog-post-content hr {
  border: none; 
  margin: 1em 0 2em;
}

.elementor-widget-theme-post-content hr::before,
.blog-post-content hr::before {
  content: '***';
  display: block;
  text-align: center; }
  
/**** Ajax loading ***/
.loader-ellips {
	font-size:20px;
/* change size here */
	position:relative;
	width:4em;
	height:1em;
	margin:10px auto;
	border-bottom:none;
}

.loader-ellips__dot {
	display:block;
	width:1em;
	height:1em;
	border-radius:.5em;
	background:#2ad2c9;
/* change color here */
	position:absolute;
	animation-duration:.5s;
	animation-timing-function:ease;
	animation-iteration-count:infinite;
}

.loader-ellips__dot:nth-child(1),.loader-ellips__dot:nth-child(2) {
	left:0;
}

.loader-ellips__dot:nth-child(3) {
	left:1.5em;
}

.loader-ellips__dot:nth-child(4) {
	left:3em;
}

@keyframes reveal {
	from {
		transform:scale(0.001);
	}
	
	to {
		transform:scale(1);
	}
}

@keyframes slide {
	to {
		transform:translateX(1.5em);
	}
}

.loader-ellips__dot:nth-child(1) {
	animation-name:reveal;
}

.loader-ellips__dot:nth-child(2),.loader-ellips__dot:nth-child(3) {
	animation-name:slide;
}

.loader-ellips__dot:nth-child(4) {
	animation-name:reveal;
	animation-direction:reverse;
}

/* Articles */
#post-grid article a:hover {
	text-decoration:none;
}

#post-grid article.article {
	padding:10px;
	background-color:#F4F4F4;
	position:relative;
	min-height:270px;
}

#post-grid article.article:before {
	content:'';
	position:absolute;
	top:0;
	left:0;
	width:100%;
	height:100%;
	background-color:rgba(0,0,0,0.49);
	z-index:0;
}

#post-grid article.article .post-content {
	padding:10px;
	position:absolute;
	bottom:0;
	left:0;
	width:100%;
}

#post-grid article.article h2.post-title {
	line-height:1.1;
	font-size:1.675rem!important;
}

#post-grid article .post-ctgys {
	margin:0 0 10px;
}

#post-grid article.relationships .post-ctgys span {
	background-color:#2AD2C9;
}

#post-grid article.adulthood .post-ctgys span {
	background-color:#DC582A;
}

#post-grid article.faith .post-ctgys span {
	background-color:#FFB500;
}

#post-grid article.article h2.post-title a {
	color:#fff;
	font-size:1.675rem!important;
}

#post-grid article.article .post-authors {
	color:#9B9B9B;
	font-size:.75rem;
}

#post-grid article.article .post-authors a {
	color:#9B9B9B;
	font-size:.75rem;
}

/* Podcasts */
.podcast-episode a:hover {
	text-decoration:none;
}

.podcast-episode.inbox {
	background-image:url(/wp-content/uploads/2019/08/BG-Inbox-Segment.jpg);
}

.podcast-episode.roundtable {
	background-image:url(/wp-content/uploads/2019/08/BG-Roundtable-Segment-mobile.jpg);
}

.podcast-episode.culture {
	background-image:url(/wp-content/uploads/2019/08/BG-Culture-Segment.jpg);
}

.podcast-episode {
	width:100%;
	position:relative;
	text-align:center;
	padding:25px 15px;
	color:#fff;
	background-size:cover;
	background-position:center center;
	background-image:url(/wp-content/uploads/2019/08/podcast-image1.jpg);
	height:100%;
	display:-ms-flexbox;
	display:-webkit-flex;
	display:flex;
	-webkit-flex-direction:column;
	-ms-flex-direction:column;
	flex-direction:column;
	-webkit-flex-wrap:nowrap;
	-ms-flex-wrap:nowrap;
	flex-wrap:nowrap;
	-webkit-justify-content:space-between;
	-ms-flex-pack:justify;
	justify-content:space-between;
	-webkit-align-content:stretch;
	-ms-flex-line-pack:stretch;
	align-content:stretch;
	-webkit-align-items:flex-start;
	-ms-flex-align:start;
	align-items:flex-start;
	margin-bottom:0;
}

.podcast-episode:after {
  background: rgba(0,0,0,0.5);
  position:absolute;
	top:0;
	left:0;
	right:0;
	bottom:0;
	content:"";
	z-index:0;
}

.podcast-episode .show-logo {
	position:relative;
	z-index:1;
	margin:0 10px 40px;
	max-width:270px;
}

@media only screen and (min-width: 480px) {
	.podcast-episode .show-logo {
		margin:0 auto 40px;
	}
}

.podcast-episode .episode-details {
	align-self:flex-end;
	position:relative;
	z-index:1;
	width:100%;
}

.podcast-episode .episode-details .episode-date {
	text-transform:uppercase;
	font-size:14px;
}

.podcast-episode .episode-details .post-title {
	font-size:30px;
	color:#fff!important;
	font-weight:700;
}

.podcast-episode .episode-details .post-title a {
	color:#fff!important;
}

.podcast-episode .episode-details .segment-type {
	font-weight:700;
	text-transform:uppercase;
	color:#FFB500;
	margin-bottom:30px;
}

.podcast-episode .episode-details .episode-link {
	margin:8px 0 1.6em;
}

.listen-now span {
	font-weight:600;
	text-transform:uppercase;
}

.elementor-button.elementor-size-xs,.elementor-button.elementor-size-sm {
	border-radius:0;
	text-decoration:none;
}
.podcast-episode-details{
    color:#fff;
}
.podcast-episode-details h1.episode-title {
	color: #fff !important;
	font-size: 36px;
	font-weight: bold
}
.podcast-episode-details .episode-guests {
	font-style: italic
}
.podcast-episode-details .episode-guests .ep-guests-list {
	display: inline;
	margin: 0;
	padding: 0;
	list-style-type: none
}
.podcast-episode-details .episode-guests .ep-guests-list li {
	display: inline
}
.podcast-episode-details .episode-guests .ep-guests-list li:after {
	content: ", "
}
.podcast-episode-details .episode-guests .ep-guests-list li:last-of-type:after {
	content: none
}
.podcast-episode-details .episode-guests .js-wpv-view-layout .js-wpv-view-layout {
	display: inline
}
.podcast-episode-details .episode-guests .js-wpv-view-layout .js-wpv-view-layout:last-child .separator:last-child {
	display: none
}
.podcast-episode-details .episode-text {
	margin-top: 1em
}
.podcast-episode-details .episode-text .episode-time {
	float: left;
	display: inline;
	margin: 0
}
.podcast-episode-details .episode-download {
	text-align: center
}
.segment-time, .episode-time {
	float: left;
	display: inline;
	margin: 0
}
/* Featured Content - Podcast */

.podcast-episode-featured-content {
    background-color: #51bab1;
  /*  padding: 0 30px 30px 30px!important;
    margin-top: 40px;*/
    color: #fff!important;
}
.podcast-episode-featured-content h2, .podcast-episode-featured-content a {
    color: #fff!important;
}

.podcast-episode-featured-content .featured-product-image {
    display: block;
    text-align: center;
    margin: 0 auto;
}
.podcast-episode-featured-content p {
    line-height: 1.7em;
}
.podcast-episode-featured-content h2{
    color: #fff!important;
}
.podcast-episode-featured-content a {
    color: #fff!important;
    text-decoration: underline;
}
.podcast-episode-featured-content a.button {
    color: #ffffff;
    border: 2px solid #fff;
    background-color: transparent;
    font-size: 15px;
    padding: 8px 24px;    
    transition: background-color .3s ease-in-out;
    margin-top: 10px;
    text-decoration: none;   
}
.podcast-episode-featured-content a.button:hover {
    background-color: #2ad2c9;
    text-decoration: none;
}

@media only screen and (min-width: 768px) {
    .podcast-episode-featured-content .featured-product-image {
        float: left!important;
        padding-right: 30px!important;
    }    
}

.podcast-segments-list .section-title, .podcast-segment-list .section-title {
	margin: 1em 0
}


.podcast-episode-segment {
	background-color: #EFEFEF;
	padding: 30px;
	margin-bottom: 30px
}
.podcast-episode-segment .segment-type {
	color: #9B9B9B;
	text-transform: uppercase
}
.podcast-episode-segment h2 {
	font-size: 26px
}
.podcast-episode-segment .episode-guests {
	font-style: italic
}
.podcast-episode-segment .episode-guests p .separator:last-child {
	display: none
}
.podcast-episode-segment .segment-guests {
	font-style: italic
}
.podcast-episode-segment .segment-excerpt {
	margin-top: 1em
}
.podcast-episode-segment .episode-download {
	text-align: center
}
.podcast-episode-segment .episode-link a {
  margin: 20px 0;
  padding: 20px;
  color: #ffffff;
  background-color: #51BAB1;
  display: inline-block;
}
.et-db article.single-podcast-episode #et-boc .et_pb_row {
	width: 100%;
	padding: 0
}
.oo-player-container .oo-small .oo-action-icon span.oo-icon, .oo-player-container .oo-small .oo-action-icon-pause.oo-animate-pause {
	font-size: 50px !important
}
.oo-player-container .oo-xsmall .oo-action-icon span.oo-icon, .oo-player-container .oo-xsmall .oo-action-icon-pause.oo-animate-pause {
	font-size: 30px !important
}
.episodePlayer {
	width: 100%;
	padding-top: 17%;
	position: relative;
	margin: 10px 0
}
.episodePlayer .oo-player-container {
	height: 100% !important;
	width: 100%;
	max-width: 100% !important;
	min-width: 0 !important;
	top: 0;
	left: 0;
	position: absolute;
	overflow: hidden
}
.episodePlayer .oo-player-container button {
	background: none !important
}
.episodePlayer .oo-player-container .oo-player {
	display: block;
	position: absolute;
	bottom: 0;
	padding: 0 !important
}
.episodePlayer .oo-player-container .oo-player .oo-state-screen-poster {
	background: none !important
}
.episodePlayer .oo-player-container .oo-player .oo-state-screen-info {
	display: none !important
}
.episode-list .et_pb_section .et_pb_row {
	margin: 0;
	padding: 0;
	width: 100%
}
.episode-list .post-title {
	font-size: 26px;
	font-weight: 700;
	padding: 0
}
.episode-list .episode-date {
	text-transform: uppercase;
	font-size: .875rem;
	color: #9B9B9B
}
.episode-list .post-excerpt {
	text-align: left;
	margin: 10px 0;
	font-size: .875rem;
}
.episode-list .episode-link {
	margin: 8px 0 1.6em
}
.episode-list .episode-link a:hover {
	text-decoration: underline
}
.podcast-episode-segment {
    background-color: #EFEFEF;
    padding: 30px;
    margin-bottom: 30px;
}
.podcast-episode-segment .segment-type {
    color: #9B9B9B;
    text-transform: uppercase;
    font-weight: 400;
}
.podcast-episode-segment h2 {
    font-size: 26px;
    color:#333f48;
}
.podcast-episode-segment .episode-guests {
    font-style: italic;
}
.podcast-episode-segment .segment-excerpt {
    margin-top: 0;
}

#featured-full-width-article {
	background-repeat:no-repeat;
	background-position:center;
	background-size:cover;
}
#featured-full-width-article .elementor-row {
	justify-content: flex-end;
}
#featured-full-width-article .elementor-column {
	-webkit-flex-direction:row-reverse;
	-ms-flex-direction:row-reverse;
	flex-direction:row-reverse;
}

#featured-full-width-article .article {
	background-size:cover;
	background-position:center center;
	border:none;
	padding:17px;
/* 980px Breakpoint */
}

@media only screen and (min-width: 980px) {
	#featured-full-width-article .article {
		width:50%;
		padding:17px 0 17px 50px;
        min-width: 480px;
	}
}

#featured-full-width-article .article .article-details {
	border:none;
	background:rgba(24,30,35,0.85);
	padding:26px 18px;
	color:#fff;
}

#featured-full-width-article .article .article-details h2 {
	font-size:36px;
	font-weight:600;
}

#featured-full-width-article .article .article-details h2 a {
	font-size:36px;
	color:#fff;
}

#featured-full-width-article .article .article-details h3 {
	font-size:20px;
	font-weight:400;
}

#featured-full-width-article .article .article-details h3 a {
	color:#9B9B9B;
}

#featured-full-width-article .article .article-details h6 {
	font-size:14px;
	font-weight:400;
	color:#fff;
	text-transform:uppercase;
	margin:0 0 10px;
}

#featured-full-width-article .article .article-details h6 a {
	display:inline-block;
	color:#fff;
	font-size:16px;
	font-weight:700;
	padding:3px 5px;
	text-decoration:none;
}

#featured-full-width-article .related-content {
	margin-top:1em;
	padding:15px;
	border:solid 3px #FFB500;
}

#featured-full-width-article .related-content .js-wpv-view-layout:last-child hr {
	display:none;
}

#featured-full-width-article .related-content h6 {
	font-size:14px;
	font-weight:400;
	color:#fff;
	text-transform:uppercase;
}

#featured-full-width-article .related-content hr {
	background:#FFB500;
	border:none;
	height:3px;
	margin:10px 0;
}

#featured-full-width-article .related-content p {
	margin:0;
	font-weight:700;
}

#featured-full-width-article .related-content a:hover {
	text-decoration:underline;
}

#featured-full-width-article .related-content a.post-title-link {
	color:#fff;
}

.article-details {
	border:solid 2px #51BAB1;
	height:100%;
}

.article-details.relationships {
	border-color:#2AD2C9;
}

.article-details.relationships .post-ctgys a,.article-details.relationships .post-ctgys span {
	background-color:#2AD2C9;
}

.article-details.relationships .post-title a:hover {
	color:#2AD2C9;
}

.article-details.adulthood {
	border-color:#DC582A;
}

.article-details.adulthood .post-ctgys a,.article-details.adulthood .post-ctgys span {
	background-color:#DC582A;
}

.article-details.adulthood .post-title a:hover {
	color:#DC582A;
}

.article-details.faith {
	border-color:#FFB500;
}

.article-details.faith .post-ctgys a,.article-details.faith .post-ctgys span {
	background-color:#FFB500;
}

.article-details.faith .post-title a:hover {
	color:#FFB500;
}

.article-details .pad {
	padding:10px;
}

.article-details h3.post-title {
	font-size:26px;
	font-weight:600;
}

.article-details h3.post-title a {
	font-size:26px;
	color:#333F48;
}

.article-details .post-authors a {
	text-transform:uppercase!important;
	font-size:16px!important;
	color:#9B9B9B!important;
}

.article-details .post-authors a:hover {
	text-decoration:underline;
}

.post-ctgys {
	margin:0 0 10px;
}

.post-ctgys a,.post-ctgys span {
	display:inline-block;
	color:#fff;
	font-size:14px;
	line-height:1;
	font-weight:700;
	padding:3px 5px;
}

body.archive.category .archive-page-title .elementor-heading-title {
	background-size:auto 50%;
	background-repeat:no-repeat;
	background-position:right top;
	padding-right:40px;
	display:inline-block;
}

.category-relationships .archive-page-title .elementor-heading-title {
	background-image:url(/wp-content/uploads/2019/08/Relationships_Icon-1.png);
}

.category-adulthood .archive-page-title .elementor-heading-title {
	background-image:url(/wp-content/uploads/2019/08/Adulthood_Icon-1.png);
}

.category-faith .archive-page-title .elementor-heading-title {
	background-image:url(/wp-content/uploads/2019/08/Faith_Icon-1.png);
}

body.category-relationships .article-details .post-ctgys a,body.category-relationships .article-details .post-ctgys span {
	background-color:#2AD2C9;
}

body.category-relationships .article-details .post-title a:hover {
	color:#2AD2C9;
}

body.category-adulthood .article-details .post-ctgys a,body.category-adulthood .article-details .post-ctgys span {
	background-color:#DC582A;
}

body.category-adulthood .article-details .post-title a:hover {
	color:#DC582A;
}

body.category-faith .article-details .post-ctgys a,body.category-faith .article-details .post-ctgys span {
	background-color:#FFB500;
}

body.category-faith .article-details .post-title a:hover {
	color:#FFB500;
}

.post-ctgys {
	margin:0 0 10px;
}

.post-ctgys a,.post-ctgys span {
	display:inline-block;
	color:#fff!important;
	font-size:14px;
	line-height:1;
	font-weight:700;
	padding:3px 5px;
}

.lt_grid-container {
	display:grid;
	height:100%;
	grid-template-columns:1.35fr 0.65fr;
	grid-template-rows:1fr 1fr;
	grid-template-areas:"first second" "first third";
/* 768px Breakpoint (Tablet) */
}

@media all and (-ms-high-contrast: none) {
	.lt_grid-container {
		display:-ms-grid;
		-ms-grid-columns:1.35fr 0.65fr;
		-ms-grid-rows:1fr 1fr;
	}
	
	.lt_grid-container > div:nth-child(1) {
		-ms-grid-row:1;
		-ms-grid-row-span:2;
		-ms-grid-column:1;
		-ms-grid-column-span:1;
	}
	
	.lt_grid-container > div:nth-child(2) {
		-ms-grid-row:1;
		-ms-grid-row-span:1;
		-ms-grid-column:2;
		-ms-grid-column-span:1;
	}
	
	.lt_grid-container > div:nth-child(3) {
		-ms-grid-row:2;
		-ms-grid-row-span:1;
		-ms-grid-column:2;
		-ms-grid-column-span:1;
	}
}

@media only screen and (max-width: 768px) {
	.lt_grid-container {
		display:block;
	}
}

.lt_grid-container .article {
	background-size:cover;
	background-position:center center;
	display:grid;
	position:relative;
}

.lt_grid-container .article:after {
/* Permalink - use to edit and share this gradient: http://colorzilla.com/gradient-editor/#000000+0,000000+100&0+0,0.5+100 */
	background:-moz-linear-gradient(top,rgba(0,0,0,0) 0%,rgba(0,0,0,0.5) 100%);
/* FF3.6-15 */
	background:-webkit-linear-gradient(top,rgba(0,0,0,0) 0%,rgba(0,0,0,0.5) 100%);
/* Chrome10-25,Safari5.1-6 */
	background:linear-gradient(to bottom,rgba(0,0,0,0) 0%,rgba(0,0,0,0.5) 100%);
/* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
	filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000',endColorstr='#80000000',GradientType=0);
/* IE6-9 */
	position:absolute;
	top:0;
	left:0;
	right:0;
	bottom:0;
	content:"";
	z-index:0;
}

.lt_grid-container .article .article-details {
	align-self:end;
	border:none;
	padding:30% 10px 10px;
	position:relative;
	z-index:1;
	height:auto;
}

.lt_grid-container .article .article-details h2.post-title {
	font-size:20px;
	font-weight:600;
	color:#fff;
}

.lt_grid-container .article .article-details h2.post-title a {
	font-size:20px;
	color:#fff;
}

.lt_grid-container .article .article-details .post-excerpt {
	display:none;
}

.lt_grid-container > div:first-child {
	grid-area:first;
}

.lt_grid-container > div:first-child .article-details {
	padding:50% 30px 30px;
/* 768px Breakpoint (Tablet) */
}

@media only screen and (max-width: 768px) {
	.lt_grid-container > div:first-child .article-details {
		padding:50% 10px 10px;
	}
}

.lt_grid-container > div:first-child .article-details h2.post-title {
	font-size:30px;
}

.lt_grid-container > div:first-child .article-details h2.post-title a {
	font-size:30px;
}

.lt_grid-container > div:first-child .article-details .post-excerpt {
	display:block;
	color:#fff;
}

.lt_grid-container > div:nth-child(2) {
	grid-area:second;
}

.lt_grid-container > div:nth-child(3) {
	grid-area:third;
}

@media only screen and (max-width: 980px) {
	.podcast-episode {
		margin-bottom:20px;
	}
}

.podcast-episode.roundtable {
	background-image:url(/wp-content/uploads/2019/08/BG-Roundtable-Segment.png);
/* 1024px Breakpoint (Desktop) */
}

@media only screen and (max-width: 1024px) {
	.podcast-episode.roundtable {
		background-image:url(/wp-content/uploads/2019/08/BG-Roundtable-Segment-mobile.jpg);
	}
}

.podcast-episode.culture {
	background-image:url(/wp-content/uploads/2019/08/BG-Culture-Segment.jpg);
}

.podcast-episode.inbox {
	background-image:url(/wp-content/uploads/2019/08/BG-Inbox-Segment.jpg);
}

.podcast-episode.nobgimg {
	background-image:none!important;
	background-color:#333F48;
}

.podcast-episode.nobgimg:after {
	display:none;
}

.podcast-episode .episode-details {
	align-self:flex-end;
	position:relative;
	z-index:1;
	width:100%;
}

.podcast-episode .episode-details .post-title {
	font-size:30px;
	color:#fff!important;
	font-weight:700;
}

.podcast-episode .episode-details .post-title a {
	color:#fff!important;
}

.podcast-episode .episode-details .episode-date {
	text-transform:uppercase;
	font-size:14px;
}

.podcast-episode .episode-details .segment-type {
	font-weight:700;
	text-transform:uppercase;
	color:#FFB500;
	margin-bottom:30px;
}

.podcast-episode .episode-details .post-excerpt {
	text-align:left;
	margin:10px 0;
}

.podcast-episode .episode-details .episode-link {
	margin:8px 0 1.6em;
}

.podcast-episode .episode-details .episode-link a:hover {
	text-decoration:underline;
}

.blog-post {
	display:block;
	clear:both;
}

.blog-post img {
	width:100%;
}

.blog-post .post-details {
	margin:0 0 20px;
}

@media only screen and (min-width: 480px) {
	.blog-post img {
		width:50%;
		float:left;
		margin:0 0 20px;
	}
	
	.blog-post .post-details {
		width:50%;
		float:left;
		padding-left:20px;
	}
}

.blog-post .post-details .post-title {
	font-size:26px;
	margin:0 0 15px;
	padding:0;
}

.blog-post .post-details .post-title a {
	font-size:26px;
	color:#333F48;
}

.blog-post .post-details .post-date {
	font-size:16px;
	color:#9B9B9B;
	margin:15px 0;
}

.blog-post .post-details .post-date .js-wpv-view-layout {
	display:inline;
}

.blog-post .post-details .post-date span {
	text-transform:uppercase;
}

.blog-post .post-details .post-date span a {
	color:#9B9B9B;
}

.blog-post .post-details .post-excerpt {
	margin:0;
}

.socials {
	margin:0;
	padding:0;
}

.socials li {
	float:left;
	width:33.33%;
	overflow:hidden;
	margin-bottom:.7em;
	border:none;
}

.socials li a {
	display:block;
	text-align:center;
}

.socials li a i {
	background-color:#2AD2C9;
	border-radius:100%;
	padding:9px 0;
	width:42px;
	height:42px;
	font-size:24px;
}

.socials li a span {
	display:block;
	font-size:10px;
	text-transform:uppercase;
	font-weight:600;
}

.socials.no-text li a span {
	display:none;
}

article.single-post-module .post-ctgys a {
	background-color:#2AD2C9;
	color:#fff;
	display:inline;
	padding:3px 6px;
}

article.single-post-module .post-ctgys a.relationships,article.single-post-module .post-ctgys a.adulthood,article.single-post-module .post-ctgys a.faith,article.single-post-module .post-ctgys a.uncategorized {
	display:none;
}

article-detail-head .post-meta, article.single-post-module .post-meta {
	color:#9B9B9B;
	font-size:14px;
	margin-bottom:1.6em;
}

.article-detail-head .post-meta,
article.single-post-module .post-meta .js-wpv-view-layout {
	display:inline;
}

.article-detail-head .post-meta,
.article-detail-head .post-meta a, 
article.single-post-module .post-meta a {
	color:#9B9B9B;
	text-transform:uppercase;
}

.article-detail-head .post-meta a:hover,
article.single-post-module .post-meta a:hover {
	text-decoration:underline;
}

article.single-post-module .post-excerpt {
	font-size:18px;
	font-style:italic;
	margin:0 0 1.6em;
}

.elementor-post-navigation span.elementor-post-navigation__link__next, .elementor-post-navigation span.elementor-post-navigation__link__prev {
    display: block;
}
.elementor-widget-post-navigation .post-navigation__prev--title, .elementor-widget-post-navigation .post-navigation__next--title {
    display: block;
}
.elementor-widget-post-navigation .post-navigation__prev--label,
.elementor-widget-post-navigation .post-navigation__next--label {
    font-weight: normal;
    font-style: normal;
    text-transform: uppercase;
    text-decoration: none;
    background-color: #2ad2c9;
    color: #ffffff;
    padding: 10px 12px;
    font-size: 16px;
    display: inline-block;
}
.elementor-widget-post-navigation .post-navigation__prev--label:before {
    font-family: "Font Awesome 5 Free";
    content: "\f104";
    margin-right: 5px;
		font-weight: 600;
}
.elementor-widget-post-navigation .post-navigation__prev--label:hover:before {
		margin-right: 10px;
	transition: all 150ms ease-in-out;
}
.elementor-widget-post-navigation .post-navigation__next--label:after {
    font-family: "Font Awesome 5 Free";
    content: "\f105";
    margin-left: 5px;
		font-weight: 600;
}
.elementor-widget-post-navigation .post-navigation__next--label:hover:after {
		margin-left: 10px;
	transition: all 150ms ease-in-out;
}
.gigya-share-widget td {
	vertical-align: top !important;
}
.gig-button-text.gig-share-button-text {
	
}
.gigya-share-widget table tbody > tr > td, .gigya-share-widget table tbody > tr > th {
	background-color: transparent;
}
.person-socials a {
  padding: 0;
  margin: 0;
  display: block;
}
.person-socials a:before {
    margin-right: 5px;
}
.person-socials a[title="Website"]:before {
    font-family: "Font Awesome 5 Free";
    content: "\f35d";
}
.person-socials a[title="Facebook"]:before {
    font-family: "Font Awesome 5 Brands";
    content: "\f09a";
}
.person-socials a[title="Twitter"]:before {
    font-family: "Font Awesome 5 Brands";
    content: "\f099";
}
.person-socials a[title="Instagram"]:before {
    font-family: "Font Awesome 5 Brands";
    content: "\f16d";
}

blockquote {
    border-left: 5px solid;
    margin: 20px 0 30px;
    padding-left: 20px;
    font-size: 15px;
    font-weight: 700;
}
blockquote, q {
    quotes: none;
}

.topics-dd{
    color: #fff;
}
.topics-dd h5{
    font-family: Montserrat;
    font-size: 1.5rem;
    text-transform: uppercase;
    font-weight: 600;
    letter-spacing: 1.2px
}
.topics-dd select {
		position:relative;
    font-family: Montserrat;
    font-weight: 600;
    color: #ffffff!important;
    height: 50px;
    margin: 15px 0px;
    outline: 0;
    
	    background: url("/wp-content/uploads/2019/09/chevron-down-.png") 90% 50% no-repeat; 
	background-size: 8%;
	background-color: rgba(0,0,0,.05);
    border: 0;
    border-radius: 3px;
    box-shadow: none;
    box-sizing: border-box;
    padding: 10px 12px;
    color: rgba(0,0,0,.6);
   transition: .3s ease;
    -moz-appearance: none;
    -webkit-appearance: none;
    appearance: none;
}
/* body select.select_box option */ 
.topics-dd select option { 
    padding: 0 4px; 
		color:#000;
} 
/* for IE and Edge */ 
.topics-dd select::-ms-expand { 
    display: none; 
} 
.topics-dd select:disabled::-ms-expand { 
    background: #f60; 
}
.gig-comments-container {
    width: 100% !important;
    max-width: 100%;
    margin-top: 30px !important;
}		</style>
		
<style type="text/css" media="all">
.footnotes_reference_container {margin-top: 24px !important; margin-bottom: 0px !important;}
.footnote_container_prepare > p {border-bottom: 1px solid #aaaaaa !important;}
.footnote_tooltip { font-size: 13px !important; color: #000000 !important; background-color: #ffffff !important; border-width: 1px !important; border-style: solid !important; border-color: #cccc99 !important; -webkit-box-shadow: 2px 2px 11px #666666; -moz-box-shadow: 2px 2px 11px #666666; box-shadow: 2px 2px 11px #666666; max-width: 450px !important;}


</style>
</head>
<body class="blog-template-default single single-blog postid-11904 wp-custom-logo elementor-default elementor-template-full-width elementor-kit-29643 elementor-page-26624">

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;" ><defs><filter id="wp-duotone-dark-grayscale"><feColorMatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 " /><feComponentTransfer color-interpolation-filters="sRGB" ><feFuncR type="table" tableValues="0 0.498039215686" /><feFuncG type="table" tableValues="0 0.498039215686" /><feFuncB type="table" tableValues="0 0.498039215686" /><feFuncA type="table" tableValues="1 1" /></feComponentTransfer><feComposite in2="SourceGraphic" operator="in" /></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;" ><defs><filter id="wp-duotone-grayscale"><feColorMatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 " /><feComponentTransfer color-interpolation-filters="sRGB" ><feFuncR type="table" tableValues="0 1" /><feFuncG type="table" tableValues="0 1" /><feFuncB type="table" tableValues="0 1" /><feFuncA type="table" tableValues="1 1" /></feComponentTransfer><feComposite in2="SourceGraphic" operator="in" /></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;" ><defs><filter id="wp-duotone-purple-yellow"><feColorMatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 " /><feComponentTransfer color-interpolation-filters="sRGB" ><feFuncR type="table" tableValues="0.549019607843 0.988235294118" /><feFuncG type="table" tableValues="0 1" /><feFuncB type="table" tableValues="0.717647058824 0.254901960784" /><feFuncA type="table" tableValues="1 1" /></feComponentTransfer><feComposite in2="SourceGraphic" operator="in" /></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;" ><defs><filter id="wp-duotone-blue-red"><feColorMatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 " /><feComponentTransfer color-interpolation-filters="sRGB" ><feFuncR type="table" tableValues="0 1" /><feFuncG type="table" tableValues="0 0.278431372549" /><feFuncB type="table" tableValues="0.592156862745 0.278431372549" /><feFuncA type="table" tableValues="1 1" /></feComponentTransfer><feComposite in2="SourceGraphic" operator="in" /></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;" ><defs><filter id="wp-duotone-midnight"><feColorMatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 " /><feComponentTransfer color-interpolation-filters="sRGB" ><feFuncR type="table" tableValues="0 0" /><feFuncG type="table" tableValues="0 0.647058823529" /><feFuncB type="table" tableValues="0 1" /><feFuncA type="table" tableValues="1 1" /></feComponentTransfer><feComposite in2="SourceGraphic" operator="in" /></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;" ><defs><filter id="wp-duotone-magenta-yellow"><feColorMatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 " /><feComponentTransfer color-interpolation-filters="sRGB" ><feFuncR type="table" tableValues="0.780392156863 1" /><feFuncG type="table" tableValues="0 0.949019607843" /><feFuncB type="table" tableValues="0.352941176471 0.470588235294" /><feFuncA type="table" tableValues="1 1" /></feComponentTransfer><feComposite in2="SourceGraphic" operator="in" /></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;" ><defs><filter id="wp-duotone-purple-green"><feColorMatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 " /><feComponentTransfer color-interpolation-filters="sRGB" ><feFuncR type="table" tableValues="0.650980392157 0.403921568627" /><feFuncG type="table" tableValues="0 1" /><feFuncB type="table" tableValues="0.447058823529 0.4" /><feFuncA type="table" tableValues="1 1" /></feComponentTransfer><feComposite in2="SourceGraphic" operator="in" /></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;" ><defs><filter id="wp-duotone-blue-orange"><feColorMatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 " /><feComponentTransfer color-interpolation-filters="sRGB" ><feFuncR type="table" tableValues="0.0980392156863 1" /><feFuncG type="table" tableValues="0 0.662745098039" /><feFuncB type="table" tableValues="0.847058823529 0.419607843137" /><feFuncA type="table" tableValues="1 1" /></feComponentTransfer><feComposite in2="SourceGraphic" operator="in" /></filter></defs></svg>
<!-- GTM Container placement set to automatic -->
<!-- Google Tag Manager (noscript) -->
				<noscript><iframe src="https://www.googletagmanager.com/ns.html?id=GTM-WHJ6VC" height="0" width="0" style="display:none;visibility:hidden" aria-hidden="true"></iframe></noscript>
<!-- End Google Tag Manager (noscript) -->
<a class="skip-link screen-reader-text" href="#content">
	Skip to content</a>

		<div data-elementor-type="header" data-elementor-id="29667" class="elementor elementor-29667 elementor-location-header">
					<div class="elementor-section-wrap">
								<header class="elementor-section elementor-top-section elementor-element elementor-element-328df026 elementor-section-content-middle elementor-section-height-min-height page-header elementor-section-boxed elementor-section-height-default elementor-section-items-middle" data-id="328df026" data-element_type="section" data-settings="{&quot;background_background&quot;:&quot;classic&quot;}">
						<div class="elementor-container elementor-column-gap-no">
							<div class="elementor-row">
					<div class="elementor-column elementor-col-50 elementor-top-column elementor-element elementor-element-2bfe0d60" data-id="2bfe0d60" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-6c157bd elementor-hidden-desktop elementor-hidden-tablet elementor-widget elementor-widget-image" data-id="6c157bd" data-element_type="widget" data-widget_type="image.default">
				<div class="elementor-widget-container">
								<div class="elementor-image">
													<a href="https://www.boundless.org/">
							<img width="601" height="107" src="https://www.boundless.org/wp-content/uploads/2020/02/Boundless_Logo_NoTag_WHITE.png" class="attachment-medium_large size-medium_large wp-image-29668" alt="" loading="lazy" srcset="https://www.boundless.org/wp-content/uploads/2020/02/Boundless_Logo_NoTag_WHITE.png 601w, https://www.boundless.org/wp-content/uploads/2020/02/Boundless_Logo_NoTag_WHITE-300x53.png 300w" sizes="(max-width: 601px) 100vw, 601px" />								</a>
														</div>
						</div>
				</div>
				<div class="elementor-element elementor-element-5556c567 elementor-hidden-phone elementor-widget elementor-widget-theme-site-logo elementor-widget-image" data-id="5556c567" data-element_type="widget" data-widget_type="theme-site-logo.default">
				<div class="elementor-widget-container">
								<div class="elementor-image">
													<a href="https://www.boundless.org">
							<img width="614" height="148" src="https://www.boundless.org/wp-content/uploads/2019/08/Boundless_Logo_2CR_RGB@2x.png" class="attachment-full size-full wp-image-26520" alt="" loading="lazy" srcset="https://www.boundless.org/wp-content/uploads/2019/08/Boundless_Logo_2CR_RGB@2x.png 614w, https://www.boundless.org/wp-content/uploads/2019/08/Boundless_Logo_2CR_RGB@2x-300x72.png 300w" sizes="(max-width: 614px) 100vw, 614px" />								</a>
														</div>
						</div>
				</div>
						</div>
					</div>
		</div>
				<div class="elementor-column elementor-col-50 elementor-top-column elementor-element elementor-element-6a7125ed" data-id="6a7125ed" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-3c41474f elementor-widget__width-initial elementor-widget-tablet__width-auto elementor-widget-mobile__width-initial elementor-search-form--skin-classic elementor-search-form--button-type-icon elementor-search-form--icon-search elementor-widget elementor-widget-search-form" data-id="3c41474f" data-element_type="widget" data-settings="{&quot;skin&quot;:&quot;classic&quot;}" data-widget_type="search-form.default">
				<div class="elementor-widget-container">
					<form class="elementor-search-form" role="search" action="https://www.boundless.org" method="get">
									<div class="elementor-search-form__container">
								<input placeholder="" class="elementor-search-form__input" type="search" name="s" title="Search" value="">
													<button class="elementor-search-form__submit" type="submit" title="Search" aria-label="Search">
													<i aria-hidden="true" class="fas fa-search"></i>							<span class="elementor-screen-only">Search</span>
											</button>
											</div>
		</form>
				</div>
				</div>
				<div class="elementor-element elementor-element-6fb3f125 elementor-widget-tablet__width-auto elementor-widget elementor-widget-image" data-id="6fb3f125" data-element_type="widget" data-widget_type="image.default">
				<div class="elementor-widget-container">
								<div class="elementor-image">
													<a href="https://www.focusonthefamily.com/" target="_blank" rel="nofollow">
							<img src="https://www.boundless.org/wp-content/uploads/2019/08/FOTF_TypeStretch_1CR_White@2x-2.png" title="FOTF_TypeStretch_1CR_White@2x.png" alt="FOTF_TypeStretch_1CR_White@2x.png" loading="lazy" />								</a>
														</div>
						</div>
				</div>
				<div class="elementor-element elementor-element-8326616 elementor-nav-menu__align-left mobilenav elementor-nav-menu--stretch elementor-widget-mobile__width-initial elementor-absolute elementor-hidden-desktop elementor-widget-tablet__width-initial elementor-widget__width-initial elementor-nav-menu--dropdown-tablet elementor-nav-menu__text-align-aside elementor-nav-menu--toggle elementor-nav-menu--burger elementor-widget elementor-widget-nav-menu" data-id="8326616" data-element_type="widget" data-settings="{&quot;layout&quot;:&quot;vertical&quot;,&quot;full_width&quot;:&quot;stretch&quot;,&quot;_position&quot;:&quot;absolute&quot;,&quot;submenu_icon&quot;:{&quot;value&quot;:&quot;&lt;i class=\&quot;fas fa-angle-down\&quot;&gt;&lt;\/i&gt;&quot;,&quot;library&quot;:&quot;fa-solid&quot;},&quot;toggle&quot;:&quot;burger&quot;}" data-widget_type="nav-menu.default">
				<div class="elementor-widget-container">
						<nav migration_allowed="1" migrated="0" class="elementor-nav-menu--main elementor-nav-menu__container elementor-nav-menu--layout-vertical e--pointer-none">
				<ul id="menu-1-8326616" class="elementor-nav-menu sm-vertical"><li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-has-children menu-item-29673"><a href="https://www.boundless.org/category/relationships/" class="elementor-item">Relationships</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29682"><a href="https://www.boundless.org/category/relationships/" class="elementor-sub-item">All Relationships</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29674"><a href="https://www.boundless.org/category/relationships/dating/" class="elementor-sub-item">Dating</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29676"><a href="https://www.boundless.org/category/relationships/marriage-prep/" class="elementor-sub-item">Marriage Prep</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29675"><a href="https://www.boundless.org/category/relationships/life-with-others/" class="elementor-sub-item">Life With Others</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-has-children menu-item-29677"><a href="https://www.boundless.org/category/adulthood/" class="elementor-item">Adulthood</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29683"><a href="https://www.boundless.org/category/adulthood/" class="elementor-sub-item">All Adulthood</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29684"><a href="https://www.boundless.org/category/adulthood/being-single/" class="elementor-sub-item">Being Single</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29687"><a href="https://www.boundless.org/category/adulthood/sexuality/" class="elementor-sub-item">Sexuality</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29686"><a href="https://www.boundless.org/category/adulthood/personal-growth/" class="elementor-sub-item">Personal Growth</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29685"><a href="https://www.boundless.org/category/adulthood/career-finances/" class="elementor-sub-item">Career and Finances</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor menu-item-has-children menu-item-29679"><a href="https://www.boundless.org/category/faith/" class="elementor-item">Faith</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor menu-item-29691"><a href="https://www.boundless.org/category/faith/" class="elementor-sub-item">Faith</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29688"><a href="https://www.boundless.org/category/faith/church/" class="elementor-sub-item">Church</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29689"><a href="https://www.boundless.org/category/faith/ministry-service/" class="elementor-sub-item">Ministry and Service</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29690"><a href="https://www.boundless.org/category/faith/sharing-your-faith/" class="elementor-sub-item">Sharing Your Faith</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor current-menu-parent current-blog-parent menu-item-29680"><a href="https://www.boundless.org/category/faith/spiritual-growth/" class="elementor-sub-item">Spiritual Growth</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-has-children menu-item-29694"><a href="https://www.boundless.org/blog/" class="elementor-item">Blog</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29695"><a href="https://www.boundless.org/blog/" class="elementor-sub-item">All Topics</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29681"><a href="https://www.boundless.org/category/news/" class="elementor-sub-item">In the News</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29692"><a href="https://www.boundless.org/category/announcements/" class="elementor-sub-item">Announcements</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-has-children menu-item-29696"><a href="https://www.boundless.org/podcast/" class="elementor-item">Podcast</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29697"><a href="https://www.boundless.org/podcast/" class="elementor-sub-item">All Episodes</a></li>
	<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-29698"><a href="https://www.boundless.org/about-the-show/" class="elementor-sub-item">About the Show</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29699"><a href="https://ambassadoradvertising.com/station-map/?program=143" class="elementor-sub-item">On the Radio</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29700"><a href="https://www.boundless.org/contact/" class="elementor-sub-item">Contact the Show</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29701"><a href="https://itunes.apple.com/podcast/the-boundless-show/id272731921?mt=2" class="elementor-sub-item">iTunes</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29702"><a href="https://open.spotify.com/show/21Y1yTX2SfndMyeS5ksOTj?si=ab_jP4sMQkOsdQQBVZKUtw" class="elementor-sub-item">Spotify</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29703"><a href="http://feeds.feedburner.com/boundless/podcast" class="elementor-item">RSS</a></li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29704"><a href="https://store.focusonthefamily.com/focus-featured/boundless" class="elementor-item">Shop</a></li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29705"><a href="https://donate.focusonthefamily.com/boundless-donation-page#refcd=95404" class="elementor-item elementor-item-anchor">Donate</a></li>
</ul>			</nav>
					<div class="elementor-menu-toggle" role="button" tabindex="0" aria-label="Menu Toggle" aria-expanded="false">
			<i aria-hidden="true" role="presentation" class="elementor-menu-toggle__icon--open eicon-menu-bar"></i><i aria-hidden="true" role="presentation" class="elementor-menu-toggle__icon--close eicon-close"></i>			<span class="elementor-screen-only">Menu</span>
		</div>
					<nav class="elementor-nav-menu--dropdown elementor-nav-menu__container" aria-hidden="true">
				<ul id="menu-2-8326616" class="elementor-nav-menu sm-vertical"><li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-has-children menu-item-29673"><a href="https://www.boundless.org/category/relationships/" class="elementor-item" tabindex="-1">Relationships</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29682"><a href="https://www.boundless.org/category/relationships/" class="elementor-sub-item" tabindex="-1">All Relationships</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29674"><a href="https://www.boundless.org/category/relationships/dating/" class="elementor-sub-item" tabindex="-1">Dating</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29676"><a href="https://www.boundless.org/category/relationships/marriage-prep/" class="elementor-sub-item" tabindex="-1">Marriage Prep</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29675"><a href="https://www.boundless.org/category/relationships/life-with-others/" class="elementor-sub-item" tabindex="-1">Life With Others</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-has-children menu-item-29677"><a href="https://www.boundless.org/category/adulthood/" class="elementor-item" tabindex="-1">Adulthood</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29683"><a href="https://www.boundless.org/category/adulthood/" class="elementor-sub-item" tabindex="-1">All Adulthood</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29684"><a href="https://www.boundless.org/category/adulthood/being-single/" class="elementor-sub-item" tabindex="-1">Being Single</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29687"><a href="https://www.boundless.org/category/adulthood/sexuality/" class="elementor-sub-item" tabindex="-1">Sexuality</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29686"><a href="https://www.boundless.org/category/adulthood/personal-growth/" class="elementor-sub-item" tabindex="-1">Personal Growth</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29685"><a href="https://www.boundless.org/category/adulthood/career-finances/" class="elementor-sub-item" tabindex="-1">Career and Finances</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor menu-item-has-children menu-item-29679"><a href="https://www.boundless.org/category/faith/" class="elementor-item" tabindex="-1">Faith</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor menu-item-29691"><a href="https://www.boundless.org/category/faith/" class="elementor-sub-item" tabindex="-1">Faith</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29688"><a href="https://www.boundless.org/category/faith/church/" class="elementor-sub-item" tabindex="-1">Church</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29689"><a href="https://www.boundless.org/category/faith/ministry-service/" class="elementor-sub-item" tabindex="-1">Ministry and Service</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29690"><a href="https://www.boundless.org/category/faith/sharing-your-faith/" class="elementor-sub-item" tabindex="-1">Sharing Your Faith</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor current-menu-parent current-blog-parent menu-item-29680"><a href="https://www.boundless.org/category/faith/spiritual-growth/" class="elementor-sub-item" tabindex="-1">Spiritual Growth</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-has-children menu-item-29694"><a href="https://www.boundless.org/blog/" class="elementor-item" tabindex="-1">Blog</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29695"><a href="https://www.boundless.org/blog/" class="elementor-sub-item" tabindex="-1">All Topics</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29681"><a href="https://www.boundless.org/category/news/" class="elementor-sub-item" tabindex="-1">In the News</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-29692"><a href="https://www.boundless.org/category/announcements/" class="elementor-sub-item" tabindex="-1">Announcements</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-has-children menu-item-29696"><a href="https://www.boundless.org/podcast/" class="elementor-item" tabindex="-1">Podcast</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29697"><a href="https://www.boundless.org/podcast/" class="elementor-sub-item" tabindex="-1">All Episodes</a></li>
	<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-29698"><a href="https://www.boundless.org/about-the-show/" class="elementor-sub-item" tabindex="-1">About the Show</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29699"><a href="https://ambassadoradvertising.com/station-map/?program=143" class="elementor-sub-item" tabindex="-1">On the Radio</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29700"><a href="https://www.boundless.org/contact/" class="elementor-sub-item" tabindex="-1">Contact the Show</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29701"><a href="https://itunes.apple.com/podcast/the-boundless-show/id272731921?mt=2" class="elementor-sub-item" tabindex="-1">iTunes</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29702"><a href="https://open.spotify.com/show/21Y1yTX2SfndMyeS5ksOTj?si=ab_jP4sMQkOsdQQBVZKUtw" class="elementor-sub-item" tabindex="-1">Spotify</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29703"><a href="http://feeds.feedburner.com/boundless/podcast" class="elementor-item" tabindex="-1">RSS</a></li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29704"><a href="https://store.focusonthefamily.com/focus-featured/boundless" class="elementor-item" tabindex="-1">Shop</a></li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-29705"><a href="https://donate.focusonthefamily.com/boundless-donation-page#refcd=95404" class="elementor-item elementor-item-anchor" tabindex="-1">Donate</a></li>
</ul>			</nav>
				</div>
				</div>
						</div>
					</div>
		</div>
								</div>
					</div>
		</header>
				<nav class="elementor-section elementor-top-section elementor-element elementor-element-22cfe6f9 elementor-hidden-tablet elementor-hidden-phone elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-id="22cfe6f9" data-element_type="section" data-settings="{&quot;background_background&quot;:&quot;classic&quot;,&quot;sticky&quot;:&quot;top&quot;,&quot;sticky_on&quot;:[],&quot;sticky_offset&quot;:0,&quot;sticky_effects_offset&quot;:0}">
							<div class="elementor-background-overlay"></div>
							<div class="elementor-container elementor-column-gap-no">
							<div class="elementor-row">
					<nav class="elementor-column elementor-col-50 elementor-top-column elementor-element elementor-element-6bbeade6 elementor-hidden-tablet elementor-hidden-phone" data-id="6bbeade6" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-5cc28e08 elementor-nav-menu__align-left mainnav elementor-hidden-phone elementor-nav-menu--dropdown-mobile elementor-hidden-tablet elementor-nav-menu__text-align-aside elementor-nav-menu--toggle elementor-nav-menu--burger elementor-widget elementor-widget-nav-menu" data-id="5cc28e08" data-element_type="widget" data-settings="{&quot;submenu_icon&quot;:{&quot;value&quot;:&quot;&lt;i class=\&quot;\&quot;&gt;&lt;\/i&gt;&quot;,&quot;library&quot;:&quot;&quot;},&quot;layout&quot;:&quot;horizontal&quot;,&quot;toggle&quot;:&quot;burger&quot;}" data-widget_type="nav-menu.default">
				<div class="elementor-widget-container">
						<nav migration_allowed="1" migrated="0" class="elementor-nav-menu--main elementor-nav-menu__container elementor-nav-menu--layout-horizontal e--pointer-none">
				<ul id="menu-1-5cc28e08" class="elementor-nav-menu"><li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-has-children menu-item-19289"><a href="https://www.boundless.org/category/relationships/" class="elementor-item">Relationships</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="show-mobile menu-item menu-item-type-taxonomy menu-item-object-category menu-item-21411"><a href="https://www.boundless.org/category/relationships/" class="elementor-sub-item">All Relationships</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19298"><a href="https://www.boundless.org/category/relationships/dating/" class="elementor-sub-item">Dating</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19299"><a href="https://www.boundless.org/category/relationships/marriage-prep/" class="elementor-sub-item">Marriage Prep</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19300"><a href="https://www.boundless.org/category/relationships/life-with-others/" class="elementor-sub-item">Life With Others</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-37036"><a href="https://www.focusonthefamily.com/marriage/boundless-guides-to-marrying-well/" class="elementor-sub-item">Guides to Marrying Well</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-has-children menu-item-19302"><a href="https://www.boundless.org/category/adulthood/" class="elementor-item">Adulthood</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="show-mobile menu-item menu-item-type-taxonomy menu-item-object-category menu-item-21412"><a href="https://www.boundless.org/category/adulthood/" class="elementor-sub-item">All Adulthood</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19303"><a href="https://www.boundless.org/category/adulthood/being-single/" class="elementor-sub-item">Being Single</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19304"><a href="https://www.boundless.org/category/adulthood/sexuality/" class="elementor-sub-item">Sexuality</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19305"><a href="https://www.boundless.org/category/adulthood/personal-growth/" class="elementor-sub-item">Personal Growth</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19306"><a href="https://www.boundless.org/category/adulthood/career-finances/" class="elementor-sub-item">Career and Finances</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor menu-item-has-children menu-item-26610"><a href="https://www.boundless.org/category/faith/" class="elementor-item">Faith</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor menu-item-26615"><a href="https://www.boundless.org/category/faith/" class="elementor-sub-item">All Faith</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-26612"><a href="https://www.boundless.org/category/faith/church/" class="elementor-sub-item">Church</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-26613"><a href="https://www.boundless.org/category/faith/ministry-service/" class="elementor-sub-item">Ministry and Service</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-26614"><a href="https://www.boundless.org/category/faith/sharing-your-faith/" class="elementor-sub-item">Sharing Your Faith</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor current-menu-parent current-blog-parent menu-item-26611"><a href="https://www.boundless.org/category/faith/spiritual-growth/" class="elementor-sub-item">Spiritual Growth</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-post_type_archive menu-item-object-blog menu-item-has-children menu-item-19314"><a href="https://www.boundless.org/blog/" class="elementor-item">Blog</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-post_type_archive menu-item-object-blog menu-item-19315"><a href="https://www.boundless.org/blog/" class="elementor-sub-item">All Topics</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19317"><a href="https://www.boundless.org/category/news/" class="elementor-sub-item">In the News</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19318"><a href="https://www.boundless.org/category/announcements/" class="elementor-sub-item">Announcements</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-post_type_archive menu-item-object-podcast menu-item-has-children menu-item-19406"><a href="https://www.boundless.org/podcast/" class="elementor-item">Podcast</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21449"><a href="/podcast/" class="elementor-sub-item">All Episodes</a></li>
	<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-20056"><a href="https://www.boundless.org/about-the-show/" class="elementor-sub-item">About the Show</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21450"><a target="_blank" rel="noopener" href="https://ambassadoradvertising.com/station-map/?program=143" class="elementor-sub-item">On the Radio</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21451"><a href="/contact/" class="elementor-sub-item">Contact the Show</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21454"><a target="_blank" rel="noopener" href="https://itunes.apple.com/podcast/the-boundless-show/id272731921?mt=2" class="elementor-sub-item">iTunes</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21455"><a target="_blank" rel="noopener" href="https://open.spotify.com/show/21Y1yTX2SfndMyeS5ksOTj?si=ab_jP4sMQkOsdQQBVZKUtw" class="elementor-sub-item">Spotify</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21456"><a target="_blank" rel="noopener" href="http://feeds.feedburner.com/boundless/podcast" class="elementor-sub-item">RSS</a></li>
</ul>
</li>
</ul>			</nav>
					<div class="elementor-menu-toggle" role="button" tabindex="0" aria-label="Menu Toggle" aria-expanded="false">
			<i aria-hidden="true" role="presentation" class="elementor-menu-toggle__icon--open eicon-menu-bar"></i><i aria-hidden="true" role="presentation" class="elementor-menu-toggle__icon--close eicon-close"></i>			<span class="elementor-screen-only">Menu</span>
		</div>
					<nav class="elementor-nav-menu--dropdown elementor-nav-menu__container" aria-hidden="true">
				<ul id="menu-2-5cc28e08" class="elementor-nav-menu"><li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-has-children menu-item-19289"><a href="https://www.boundless.org/category/relationships/" class="elementor-item" tabindex="-1">Relationships</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="show-mobile menu-item menu-item-type-taxonomy menu-item-object-category menu-item-21411"><a href="https://www.boundless.org/category/relationships/" class="elementor-sub-item" tabindex="-1">All Relationships</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19298"><a href="https://www.boundless.org/category/relationships/dating/" class="elementor-sub-item" tabindex="-1">Dating</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19299"><a href="https://www.boundless.org/category/relationships/marriage-prep/" class="elementor-sub-item" tabindex="-1">Marriage Prep</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19300"><a href="https://www.boundless.org/category/relationships/life-with-others/" class="elementor-sub-item" tabindex="-1">Life With Others</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-37036"><a href="https://www.focusonthefamily.com/marriage/boundless-guides-to-marrying-well/" class="elementor-sub-item" tabindex="-1">Guides to Marrying Well</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-has-children menu-item-19302"><a href="https://www.boundless.org/category/adulthood/" class="elementor-item" tabindex="-1">Adulthood</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="show-mobile menu-item menu-item-type-taxonomy menu-item-object-category menu-item-21412"><a href="https://www.boundless.org/category/adulthood/" class="elementor-sub-item" tabindex="-1">All Adulthood</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19303"><a href="https://www.boundless.org/category/adulthood/being-single/" class="elementor-sub-item" tabindex="-1">Being Single</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19304"><a href="https://www.boundless.org/category/adulthood/sexuality/" class="elementor-sub-item" tabindex="-1">Sexuality</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19305"><a href="https://www.boundless.org/category/adulthood/personal-growth/" class="elementor-sub-item" tabindex="-1">Personal Growth</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19306"><a href="https://www.boundless.org/category/adulthood/career-finances/" class="elementor-sub-item" tabindex="-1">Career and Finances</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor menu-item-has-children menu-item-26610"><a href="https://www.boundless.org/category/faith/" class="elementor-item" tabindex="-1">Faith</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor menu-item-26615"><a href="https://www.boundless.org/category/faith/" class="elementor-sub-item" tabindex="-1">All Faith</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-26612"><a href="https://www.boundless.org/category/faith/church/" class="elementor-sub-item" tabindex="-1">Church</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-26613"><a href="https://www.boundless.org/category/faith/ministry-service/" class="elementor-sub-item" tabindex="-1">Ministry and Service</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-26614"><a href="https://www.boundless.org/category/faith/sharing-your-faith/" class="elementor-sub-item" tabindex="-1">Sharing Your Faith</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor current-menu-parent current-blog-parent menu-item-26611"><a href="https://www.boundless.org/category/faith/spiritual-growth/" class="elementor-sub-item" tabindex="-1">Spiritual Growth</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-post_type_archive menu-item-object-blog menu-item-has-children menu-item-19314"><a href="https://www.boundless.org/blog/" class="elementor-item" tabindex="-1">Blog</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-post_type_archive menu-item-object-blog menu-item-19315"><a href="https://www.boundless.org/blog/" class="elementor-sub-item" tabindex="-1">All Topics</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19317"><a href="https://www.boundless.org/category/news/" class="elementor-sub-item" tabindex="-1">In the News</a></li>
	<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19318"><a href="https://www.boundless.org/category/announcements/" class="elementor-sub-item" tabindex="-1">Announcements</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-post_type_archive menu-item-object-podcast menu-item-has-children menu-item-19406"><a href="https://www.boundless.org/podcast/" class="elementor-item" tabindex="-1">Podcast</a>
<ul class="sub-menu elementor-nav-menu--dropdown">
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21449"><a href="/podcast/" class="elementor-sub-item" tabindex="-1">All Episodes</a></li>
	<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-20056"><a href="https://www.boundless.org/about-the-show/" class="elementor-sub-item" tabindex="-1">About the Show</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21450"><a target="_blank" rel="noopener" href="https://ambassadoradvertising.com/station-map/?program=143" class="elementor-sub-item" tabindex="-1">On the Radio</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21451"><a href="/contact/" class="elementor-sub-item" tabindex="-1">Contact the Show</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21454"><a target="_blank" rel="noopener" href="https://itunes.apple.com/podcast/the-boundless-show/id272731921?mt=2" class="elementor-sub-item" tabindex="-1">iTunes</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21455"><a target="_blank" rel="noopener" href="https://open.spotify.com/show/21Y1yTX2SfndMyeS5ksOTj?si=ab_jP4sMQkOsdQQBVZKUtw" class="elementor-sub-item" tabindex="-1">Spotify</a></li>
	<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-21456"><a target="_blank" rel="noopener" href="http://feeds.feedburner.com/boundless/podcast" class="elementor-sub-item" tabindex="-1">RSS</a></li>
</ul>
</li>
</ul>			</nav>
				</div>
				</div>
						</div>
					</div>
		</nav>
				<div class="elementor-column elementor-col-50 elementor-top-column elementor-element elementor-element-1170015 elementor-hidden-phone elementor-hidden-tablet" data-id="1170015" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-42974300 elementor-align-right shopbtn elementor-widget__width-auto elementor-widget elementor-widget-button" data-id="42974300" data-element_type="widget" data-widget_type="button.default">
				<div class="elementor-widget-container">
					<div class="elementor-button-wrapper">
			<a href="https://store.focusonthefamily.com/young-adult/" target="_blank" rel="nofollow" class="elementor-button-link elementor-button elementor-size-sm" role="button" id="shop-btn">
						<span class="elementor-button-content-wrapper">
							<span class="elementor-button-icon elementor-align-icon-left">
				<i aria-hidden="true" class="fas fa-shopping-basket"></i>			</span>
						<span class="elementor-button-text">shop</span>
		</span>
					</a>
		</div>
				</div>
				</div>
				<div class="elementor-element elementor-element-26bf81de donatebtn elementor-widget__width-auto elementor-hidden-tablet elementor-hidden-phone elementor-widget elementor-widget-button" data-id="26bf81de" data-element_type="widget" data-widget_type="button.default">
				<div class="elementor-widget-container">
					<div class="elementor-button-wrapper">
			<a href="https://donate.focusonthefamily.com/boundless-donation-page?refcd=95404&#038;linktarget=_blank" target="_blank" rel="nofollow" class="elementor-button-link elementor-button elementor-size-xs" role="button" id="donate-btn">
						<span class="elementor-button-content-wrapper">
						<span class="elementor-button-text">donate</span>
		</span>
					</a>
		</div>
				</div>
				</div>
						</div>
					</div>
		</div>
								</div>
					</div>
		</nav>
				<section class="elementor-section elementor-top-section elementor-element elementor-element-11840541 elementor-section-height-min-height elementor-section-content-middle elementor-hidden-tablet elementor-hidden-phone elementor-section-boxed elementor-section-height-default elementor-section-items-middle" data-id="11840541" data-element_type="section" data-settings="{&quot;background_background&quot;:&quot;classic&quot;}">
						<div class="elementor-container elementor-column-gap-default">
							<div class="elementor-row">
					<div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-2df3d7bc elementor-hidden-phone" data-id="2df3d7bc" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-6b023a7e elementor-nav-menu--dropdown-none elementor-widget elementor-widget-nav-menu" data-id="6b023a7e" data-element_type="widget" data-settings="{&quot;submenu_icon&quot;:{&quot;value&quot;:&quot;&lt;i class=\&quot;\&quot;&gt;&lt;\/i&gt;&quot;,&quot;library&quot;:&quot;&quot;},&quot;layout&quot;:&quot;horizontal&quot;}" data-widget_type="nav-menu.default">
				<div class="elementor-widget-container">
						<nav migration_allowed="1" migrated="0" class="elementor-nav-menu--main elementor-nav-menu__container elementor-nav-menu--layout-horizontal e--pointer-none">
				<ul id="menu-1-6b023a7e" class="elementor-nav-menu"><li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-19325"><a href="https://www.boundless.org/about-us/" class="elementor-item">About Us</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-19326"><a href="https://www.boundless.org/meet-the-team/" class="elementor-item">Meet the Team</a></li>
</ul>			</nav>
						<nav class="elementor-nav-menu--dropdown elementor-nav-menu__container" aria-hidden="true">
				<ul id="menu-2-6b023a7e" class="elementor-nav-menu"><li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-19325"><a href="https://www.boundless.org/about-us/" class="elementor-item" tabindex="-1">About Us</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-19326"><a href="https://www.boundless.org/meet-the-team/" class="elementor-item" tabindex="-1">Meet the Team</a></li>
</ul>			</nav>
				</div>
				</div>
						</div>
					</div>
		</div>
								</div>
					</div>
		</section>
							</div>
				</div>
				<div data-elementor-type="single" data-elementor-id="26624" class="elementor elementor-26624 elementor-location-single post-11904 blog type-blog status-publish hentry category-spiritual-growth">
					<div class="elementor-section-wrap">
								<section class="elementor-section elementor-top-section elementor-element elementor-element-9f5dd4a elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-id="9f5dd4a" data-element_type="section">
						<div class="elementor-container elementor-column-gap-default">
							<div class="elementor-row">
					<div class="elementor-column elementor-col-66 elementor-top-column elementor-element elementor-element-6650cc0 article-detail-head" data-id="6650cc0" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-18bf02f post-ctgys elementor-widget elementor-widget-toolset-view" data-id="18bf02f" data-element_type="widget" data-widget_type="toolset-view.default">
				<div class="elementor-widget-container">
			
	
	
	
      
		<a href="https://www.boundless.org/category/faith/spiritual-growth/" class="spiritual-growth article-category">Spiritual Growth</a>
      
	
	
	
	
		</div>
				</div>
				<div class="elementor-element elementor-element-26d619a elementor-widget elementor-widget-theme-post-title elementor-page-title elementor-widget-heading" data-id="26d619a" data-element_type="widget" data-widget_type="theme-post-title.default">
				<div class="elementor-widget-container">
			<h1 class="elementor-heading-title elementor-size-default">Hold on Loosely</h1>		</div>
				</div>
				<section class="elementor-section elementor-inner-section elementor-element elementor-element-9ad8559 elementor-section-full_width post-meta elementor-section-height-default elementor-section-height-default" data-id="9ad8559" data-element_type="section">
						<div class="elementor-container elementor-column-gap-no">
							<div class="elementor-row">
					<div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-099f44c" data-id="099f44c" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-6896e8a elementor-align-left elementor-widget__width-auto elementor-widget elementor-widget-post-info" data-id="6896e8a" data-element_type="widget" data-widget_type="post-info.default">
				<div class="elementor-widget-container">
					<ul class="elementor-inline-items elementor-icon-list-items elementor-post-info">
								<li class="elementor-icon-list-item elementor-repeater-item-741bd26 elementor-inline-item" itemprop="datePublished">
													<span class="elementor-icon-list-text elementor-post-info__item elementor-post-info__item--type-date">
										November 7, 2011					</span>
								</li>
				<li class="elementor-icon-list-item elementor-repeater-item-add8fd0 elementor-inline-item">
										<span class="elementor-icon-list-icon">
								<i aria-hidden="true" class="far fa-tags"></i>							</span>
									<span class="elementor-icon-list-text elementor-post-info__item elementor-post-info__item--type-custom">
										by					</span>
								</li>
				</ul>
				</div>
				</div>
				<div class="elementor-element elementor-element-b808831 elementor-widget__width-auto elementor-widget elementor-widget-toolset-view" data-id="b808831" data-element_type="widget" data-widget_type="toolset-view.default">
				<div class="elementor-widget-container">
			<a href="https://www.boundless.org/people/adam-holz/">Adam Holz</a>		</div>
				</div>
						</div>
					</div>
		</div>
								</div>
					</div>
		</section>
						</div>
					</div>
		</div>
				<div class="elementor-column elementor-col-33 elementor-top-column elementor-element elementor-element-ad2c0c8" data-id="ad2c0c8" data-element_type="column">
			<div class="elementor-column-wrap">
							<div class="elementor-widget-wrap">
								</div>
					</div>
		</div>
								</div>
					</div>
		</section>
				<section class="elementor-section elementor-top-section elementor-element elementor-element-c57884a elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-id="c57884a" data-element_type="section">
						<div class="elementor-container elementor-column-gap-default">
							<div class="elementor-row">
					<article class="elementor-column elementor-col-66 elementor-top-column elementor-element elementor-element-64a8e12 single-post-module" data-id="64a8e12" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-89a138a elementor-widget elementor-widget-theme-post-content" data-id="89a138a" data-element_type="widget" data-widget_type="theme-post-content.default">
				<div class="elementor-widget-container">
			<p><body></p>
<p>If you’re as ancient as me, you might remember the band 38 SPECIAL. (Some of you are nodding; most of you are going, &#8220;Who?&#8221;). One of the group&#8217;s biggest hits was a song about a certain mistake guys make.</p>
<p>“Hold on Loosely” counseled over-eager suitors not to let romantic enthusiasm smother a relationship. “So hold on loosely,” the chorus instructed, “But don’t let go/If you cling too tightly/You’re gonna lose control.”</p>
<p>Now I know there have been <em>plenty</em> of conversations on Boundless lamenting some guys’ tendency not to pursue. But there’s also a subset of guys out there who have the <em>opposite</em> problem. We might call them “over-pursuers.”</p>
<p>I was one of those guys.</p>
<p>I wanted to be married from birth. My parents were married young. I thought it&#8217;d work that way for me, too. When I was 18, I figured I’d be married after college, and I wanted to be done having kids by my mid-20s. If you’d have told me at 18 that it would be another <em>16 years</em> before I got married, well, sometimes it’s better if we don’t know the future.</p>
<p>I didn&#8217;t get married quickly, but it wasn&#8217;t for lack of trying. Between my senior year of college and the time my wife and I tied the knot, I think I pursued about 30 different women. OK, it was 34. I have the journals to prove it. That probably sounds like an outrageous number, but it works out to about one every three months. Out of those initiatives, I had exactly <em>one</em> relationship that lasted longer than three dates. A couple of times, for the record, I decided not to pursue someone further; but most of the time, I was the rejectee. The one receiving the delightful “Let’s be friends” chat. </p>
<p>I was <em>so</em> eager. I couldn’t stop projecting <em>way</em> into the future. And checking potential mates against my “list.” Pondering Myers-Briggs compatibility. And you know what? It scared the women TO DEATH. Why? Because I was too intense. I didn’t know how to be casual. Cling too tightly? Check. Lose control? Got the T-shirt.</p>
<p>So, if you’re an over-pursuer like I was, what should you do? (And though I&#8217;m writing to guys here, these ideas might apply to over-eager women, too.)  </p>
<p><strong>Go easy on your passionate self</strong>. More than once I lamented, <em>God did You make me this way? Why do I want this so much? Why do I keep making the same mistakes?</em> As I asked those questions, I slowly came to grips with the reality that God had made me a passionate person, and that was OK.</p>
<p><strong>Trust God with your desires</strong>. Obviously, that&#8217;s excruciating at times. But keep talking to God. Keep pouring out your heart to Him. It’s so easy after rejection to flirt with the lie that He has it in for us. Resist the impulse to get angry (at Him and at all women everywhere) and to shut down emotionally — a road that leads to bitterness. Tell Him you’re angry and hurt, definitely. But keep talking to Him.</p>
<p><strong>Give new relational possibilities room to breathe</strong>. This one is hard. But, as much as you can help it, <em>don’t</em> rush to define things as quickly as you <em>possibly</em> can with the next person who catches your interest. With my wife, I tried to initiate a “defining the relationship” talk on our third date. (And that was <em>progress</em> compared to the poor women forced to respond to me trying to define the relationship on the <em>first</em> date. Trust me — I got definition.) She told me, matter-of-factly, that she didn’t have enough information yet to define anything. Our first date was May 20 that year (2003), and it wasn’t until our fifth (Sept. 17) that she concluded she was interested. It was a long process for her, and it pert&#8217; near <em>killed</em> me. But giving things space to breathe made the relationship possible.  </p>
<p><strong>Don’t jump into the emotional deep end</strong>. When we’re over-eager, it’s so easy to go too deep, too fast. Been there. But if you start talking about cherished hopes or fears or struggles on your first or second date, it screams, &#8220;I’m desperate!&#8221; As much as most women say that they want emotional intimacy, they <em>also</em> want some mystery. Mystery opens the door to possibility. Too much emotional stuff too soon will absolutely snuff that flickering mystery flame.</p>
<p><strong>Give yourself space after rejection.</strong> Getting shot down hurts. Afterward, you need space to talk to God, to take the edge off the rawness. Jumping back into the fray immediately is generally a bad idea. The only thing worse than getting rejected once is getting rejected two or three times in, say, a month or so. (Been there. Ouch.)</p>
<p><strong>But don’t give up! </strong>That said, dropping out of the game never seemed to me a very viable alternative. After all, if you quit pursuing, how’s it ever going to happen? That was my mindset, anyway, and on try No. 35, God <em>finally</em> answered my prayers.</p>
<p>So, get back on the horse and try again (when the time is right). Then again, maybe I don’t have to tell over-pursuers that.</p>
<p><script>class RocketElementorAnimation{constructor(){this.deviceMode=document.createElement("span"),this.deviceMode.id="elementor-device-mode",this.deviceMode.setAttribute("class","elementor-screen-only"),document.body.appendChild(this.deviceMode)}_detectAnimations(){let t=getComputedStyle(this.deviceMode,":after").content.replace(/"/g,"");this.animationSettingKeys=this._listAnimationSettingsKeys(t),document.querySelectorAll(".elementor-invisible[data-settings]").forEach(t=>{const e=t.getBoundingClientRect();if(e.bottom>=0&&e.top<=window.innerHeight)try{this._animateElement(t)}catch(t){}})}_animateElement(t){const e=JSON.parse(t.dataset.settings),i=e._animation_delay||e.animation_delay||0,n=e[this.animationSettingKeys.find(t=>e[t])];if("none"===n)return void t.classList.remove("elementor-invisible");t.classList.remove(n),this.currentAnimation&&t.classList.remove(this.currentAnimation),this.currentAnimation=n;let s=setTimeout(()=>{t.classList.remove("elementor-invisible"),t.classList.add("animated",n),this._removeAnimationSettings(t,e)},i);window.addEventListener("rocket-startLoading",function(){clearTimeout(s)})}_listAnimationSettingsKeys(t="mobile"){const e=[""];switch(t){case"mobile":e.unshift("_mobile");case"tablet":e.unshift("_tablet");case"desktop":e.unshift("_desktop")}const i=[];return["animation","_animation"].forEach(t=>{e.forEach(e=>{i.push(t+e)})}),i}_removeAnimationSettings(t,e){this._listAnimationSettingsKeys().forEach(t=>delete e[t]),t.dataset.settings=JSON.stringify(e)}static run(){const t=new RocketElementorAnimation;requestAnimationFrame(t._detectAnimations.bind(t))}}document.addEventListener("DOMContentLoaded",RocketElementorAnimation.run);</script></body></p>
		</div>
				</div>
				<section class="elementor-section elementor-inner-section elementor-element elementor-element-6c31b55 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-id="6c31b55" data-element_type="section">
						<div class="elementor-container elementor-column-gap-default">
							<div class="elementor-row">
					<div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-562a0d6" data-id="562a0d6" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-e3b7b4a elementor-widget elementor-widget-heading" data-id="e3b7b4a" data-element_type="widget" data-widget_type="heading.default">
				<div class="elementor-widget-container">
			<h4 class="elementor-heading-title elementor-size-default">Share This Post:</h4>		</div>
				</div>
				<div class="elementor-element elementor-element-506c761 elementor-share-buttons--view-icon elementor-share-buttons--skin-minimal elementor-share-buttons--shape-circle elementor-share-buttons--align-center elementor-grid-0 elementor-share-buttons--color-official elementor-widget elementor-widget-share-buttons" data-id="506c761" data-element_type="widget" data-widget_type="share-buttons.default">
				<div class="elementor-widget-container">
					<div class="elementor-grid">
								<div class="elementor-grid-item">
						<div
							class="elementor-share-btn elementor-share-btn_facebook"
							role="button"
							tabindex="0"
							aria-label="Share on facebook"
						>
															<span class="elementor-share-btn__icon">
								<i class="fab fa-facebook" aria-hidden="true"></i>							</span>
																				</div>
					</div>
									<div class="elementor-grid-item">
						<div
							class="elementor-share-btn elementor-share-btn_twitter"
							role="button"
							tabindex="0"
							aria-label="Share on twitter"
						>
															<span class="elementor-share-btn__icon">
								<i class="fab fa-twitter" aria-hidden="true"></i>							</span>
																				</div>
					</div>
									<div class="elementor-grid-item">
						<div
							class="elementor-share-btn elementor-share-btn_pinterest"
							role="button"
							tabindex="0"
							aria-label="Share on pinterest"
						>
															<span class="elementor-share-btn__icon">
								<i class="fab fa-pinterest" aria-hidden="true"></i>							</span>
																				</div>
					</div>
									<div class="elementor-grid-item">
						<div
							class="elementor-share-btn elementor-share-btn_linkedin"
							role="button"
							tabindex="0"
							aria-label="Share on linkedin"
						>
															<span class="elementor-share-btn__icon">
								<i class="fab fa-linkedin" aria-hidden="true"></i>							</span>
																				</div>
					</div>
						</div>
				</div>
				</div>
						</div>
					</div>
		</div>
								</div>
					</div>
		</section>
				<div class="elementor-element elementor-element-84f1933 elementor-widget elementor-widget-toolset-view" data-id="84f1933" data-element_type="widget" data-widget_type="toolset-view.default">
				<div class="elementor-widget-container">
			


<div id="wpv-view-layout-22208-CPID11904" class="js-wpv-view-layout js-wpv-layout-responsive js-wpv-view-layout-22208-CPID11904" data-viewnumber="22208-CPID11904" data-pagination="{&quot;id&quot;:22208,&quot;query&quot;:&quot;normal&quot;,&quot;type&quot;:&quot;disabled&quot;,&quot;effect&quot;:&quot;fade&quot;,&quot;duration&quot;:&quot;500&quot;,&quot;speed&quot;:&quot;5&quot;,&quot;pause_on_hover&quot;:&quot;disabled&quot;,&quot;stop_rollover&quot;:&quot;false&quot;,&quot;cache_pages&quot;:&quot;enabled&quot;,&quot;preload_images&quot;:&quot;enabled&quot;,&quot;preload_pages&quot;:&quot;enabled&quot;,&quot;preload_reach&quot;:&quot;1&quot;,&quot;spinner&quot;:&quot;builtin&quot;,&quot;spinner_image&quot;:&quot;https://www.boundless.org/wp-content/plugins/wp-views/embedded/res/img/ajax-loader.gif&quot;,&quot;callback_next&quot;:&quot;&quot;,&quot;manage_history&quot;:&quot;enabled&quot;,&quot;has_controls_in_form&quot;:&quot;disabled&quot;,&quot;infinite_tolerance&quot;:&quot;0&quot;,&quot;max_pages&quot;:0,&quot;page&quot;:1,&quot;base_permalink&quot;:&quot;/blog/hold-on-loosely/?wpv_view_count=22208-CPID11904&amp;wpv_paged=WPV_PAGE_NUM&quot;,&quot;loop&quot;:{&quot;type&quot;:&quot;&quot;,&quot;name&quot;:&quot;&quot;,&quot;data&quot;:[],&quot;id&quot;:0}}" data-permalink="/blog/hold-on-loosely/?wpv_view_count=22208-CPID11904">

	
	
	
		
<div class="bio-box">
  <h3>About the Author</h3>
  <div class="bio-photo"><img loading="lazy" width="150" height="150" src="https://www.boundless.org/wp-content/uploads/2018/08/adam-holz-cropped-150x150.jpg" class="attachment-thumbnail size-thumbnail wp-post-image" alt="Adam Holz" decoding="async" srcset="https://www.boundless.org/wp-content/uploads/2018/08/adam-holz-cropped-150x150.jpg 150w, https://www.boundless.org/wp-content/uploads/2018/08/adam-holz-cropped.jpg 222w" sizes="(max-width: 150px) 100vw, 150px" /></div>
  <div class="bio-desc"><span class="name"><a href="https://www.boundless.org/people/adam-holz/">Adam Holz</a></span><p><strong>Adam R. Holz</strong> has served as an editor and writer for <em>Plugged In</em> for 15 years. He also spent a decade working for The Navigators, mostly as associate editor for <em>Discipleship Journal</em>. Adam is the author of the NavPress Bible Study “Beating Busyness.” Adam and his wife, Jennifer, have three children and enjoy watching movies, playing board games and playing music together.</p>
</div>
</div>

	
	
	
	
</div>		</div>
				</div>
						</div>
					</div>
		</article>
				<div class="elementor-column elementor-col-33 elementor-top-column elementor-element elementor-element-f46a4c1" data-id="f46a4c1" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-5539223 elementor-hidden-desktop elementor-hidden-tablet elementor-hidden-mobile elementor-widget elementor-widget-heading" data-id="5539223" data-element_type="widget" data-widget_type="heading.default">
				<div class="elementor-widget-container">
			<h2 class="elementor-heading-title elementor-size-medium">Related Content</h2>		</div>
				</div>
				<div class="elementor-element elementor-element-5c4e537 elementor-widget elementor-widget-wp-widget-text" data-id="5c4e537" data-element_type="widget" data-widget_type="wp-widget-text.default">
				<div class="elementor-widget-container">
						<div class="textwidget"><div id="related-content">
<h2 style="font-size: 1.2rem; margin-top: 0;">Related Content</h2>
<article>
<div class="article-image"><img width="300" height="170" src="https://www.boundless.org/wp-content/uploads/2011/07/naassom-azevedo-4lrj6z4nRfo-unsplash-scaled-e1635885254356-300x170.jpg" class="attachment-medium size-medium wp-post-image" alt="" decoding="async" loading="lazy" srcset="https://www.boundless.org/wp-content/uploads/2011/07/naassom-azevedo-4lrj6z4nRfo-unsplash-scaled-e1635885254356-300x170.jpg 300w, https://www.boundless.org/wp-content/uploads/2011/07/naassom-azevedo-4lrj6z4nRfo-unsplash-scaled-e1635885254356-1024x579.jpg 1024w, https://www.boundless.org/wp-content/uploads/2011/07/naassom-azevedo-4lrj6z4nRfo-unsplash-scaled-e1635885254356-768x435.jpg 768w, https://www.boundless.org/wp-content/uploads/2011/07/naassom-azevedo-4lrj6z4nRfo-unsplash-scaled-e1635885254356-1536x869.jpg 1536w, https://www.boundless.org/wp-content/uploads/2011/07/naassom-azevedo-4lrj6z4nRfo-unsplash-scaled-e1635885254356.jpg 1707w" sizes="(max-width: 300px) 100vw, 300px" /></div>
<div class="article-content">
<div class="elementor-widget-heading">
<h3><a href="https://www.boundless.org/blog/whats-the-deal-with-fasting/">What&#8217;s the Deal With Fasting?</a></h3>
</div>
<p><small><strong>January 17, 2023</strong></small></p>
<p>Fasting isn&#8217;t just about going without food; it&#8217;s about connecting with the Creator in a deeper way.</p>
</p></div>
</article>
<article>
<div class="article-image"><img width="300" height="200" src="https://www.boundless.org/wp-content/uploads/2018/04/clem-onojeghuo-143466-unsplash-300x200.jpg" class="attachment-medium size-medium wp-post-image" alt="old hard-back books" decoding="async" loading="lazy" srcset="https://www.boundless.org/wp-content/uploads/2018/04/clem-onojeghuo-143466-unsplash-300x200.jpg 300w, https://www.boundless.org/wp-content/uploads/2018/04/clem-onojeghuo-143466-unsplash-768x512.jpg 768w, https://www.boundless.org/wp-content/uploads/2018/04/clem-onojeghuo-143466-unsplash-1024x682.jpg 1024w, https://www.boundless.org/wp-content/uploads/2018/04/clem-onojeghuo-143466-unsplash.jpg 1280w" sizes="(max-width: 300px) 100vw, 300px" /></div>
<div class="article-content">
<div class="elementor-widget-heading">
<h3><a href="https://www.boundless.org/blog/love-your-story-even-the-hard-chapters/">Love Your Story, Even the Hard Chapters</a></h3>
</div>
<p><small><strong>January 11, 2023</strong></small></p>
<p>We&#8217;re all stories written by God. But it’s easy to hate parts of your story. Maybe your story isn’t panning out the way you expected it to.</p>
</p></div>
</article>
<article>
<div class="article-image"><img width="300" height="202" src="https://www.boundless.org/wp-content/uploads/2018/11/jamie-street-382722-unsplash-1-300x202.jpg" class="attachment-medium size-medium wp-post-image" alt="person holding compass outside" decoding="async" loading="lazy" srcset="https://www.boundless.org/wp-content/uploads/2018/11/jamie-street-382722-unsplash-1-300x202.jpg 300w, https://www.boundless.org/wp-content/uploads/2018/11/jamie-street-382722-unsplash-1-768x517.jpg 768w, https://www.boundless.org/wp-content/uploads/2018/11/jamie-street-382722-unsplash-1-1024x690.jpg 1024w, https://www.boundless.org/wp-content/uploads/2018/11/jamie-street-382722-unsplash-1-1080x727.jpg 1080w, https://www.boundless.org/wp-content/uploads/2018/11/jamie-street-382722-unsplash-1.jpg 1280w" sizes="(max-width: 300px) 100vw, 300px" /></div>
<div class="article-content">
<div class="elementor-widget-heading">
<h3><a href="https://www.boundless.org/faith/how-to-be-discerning/">How to Be Discerning</a></h3>
</div>
<p><small><strong>January 9, 2023</strong></small></p>
<p>Learning discernment is more than adhering to a list of approved behaviors or having a “sixth sense” about a situation. Here is how you can be discerning.</p>
</p></div>
</article>
<article>
<div class="article-image"><img width="300" height="169" src="https://www.boundless.org/wp-content/uploads/2023/01/fb-graphic-4-300x169.png" class="attachment-medium size-medium wp-post-image" alt="" decoding="async" loading="lazy" srcset="https://www.boundless.org/wp-content/uploads/2023/01/fb-graphic-4-300x169.png 300w, https://www.boundless.org/wp-content/uploads/2023/01/fb-graphic-4-1024x576.png 1024w, https://www.boundless.org/wp-content/uploads/2023/01/fb-graphic-4-768x432.png 768w, https://www.boundless.org/wp-content/uploads/2023/01/fb-graphic-4.png 1280w" sizes="(max-width: 300px) 100vw, 300px" /></div>
<div class="article-content">
<div class="elementor-widget-heading">
<h3><a href="https://www.boundless.org/blog/when-the-pain-wont-stop/">When the Pain Won&#8217;t Stop</a></h3>
</div>
<p><small><strong>January 3, 2023</strong></small></p>
<p>It’s easy to accept that good can come out of suffering—unless you’re the one who’s suffering. It&#8217;s much harder to praise God when the pain won&#8217;t stop.</p>
</p></div>
</article>
<article>
<div class="article-image"><img width="300" height="169" src="https://www.boundless.org/wp-content/uploads/2018/09/star-300x169.jpg" class="attachment-medium size-medium wp-post-image" alt="lit up star leaning against a wall" decoding="async" loading="lazy" srcset="https://www.boundless.org/wp-content/uploads/2018/09/star-300x169.jpg 300w, https://www.boundless.org/wp-content/uploads/2018/09/star-768x432.jpg 768w, https://www.boundless.org/wp-content/uploads/2018/09/star-1024x576.jpg 1024w, https://www.boundless.org/wp-content/uploads/2018/09/star-1080x608.jpg 1080w, https://www.boundless.org/wp-content/uploads/2018/09/star.jpg 1280w" sizes="(max-width: 300px) 100vw, 300px" /></div>
<div class="article-content">
<div class="elementor-widget-heading">
<h3><a href="https://www.boundless.org/faith/spiritual-growth/why-i-dont-have-to-make-a-name-for-myself/">Why I Don’t Have to Make a Name for Myself</a></h3>
</div>
<p><small><strong>December 30, 2022</strong></small></p>
<p>I wanted to make a name for myself. But I&#8217;ve learned I’m made for something greater than fame and expanding my own influence.</p>
</p></div>
</article>
<article>
<div class="article-image"><img width="300" height="169" src="https://www.boundless.org/wp-content/uploads/2022/12/fb-graphic-1-300x169.png" class="attachment-medium size-medium wp-post-image" alt="" decoding="async" loading="lazy" srcset="https://www.boundless.org/wp-content/uploads/2022/12/fb-graphic-1-300x169.png 300w, https://www.boundless.org/wp-content/uploads/2022/12/fb-graphic-1-1024x576.png 1024w, https://www.boundless.org/wp-content/uploads/2022/12/fb-graphic-1-768x432.png 768w, https://www.boundless.org/wp-content/uploads/2022/12/fb-graphic-1.png 1280w" sizes="(max-width: 300px) 100vw, 300px" /></div>
<div class="article-content">
<div class="elementor-widget-heading">
<h3><a href="https://www.boundless.org/blog/hope-for-the-despairing/">Hope for the Despairing</a></h3>
</div>
<p><small><strong>December 20, 2022</strong></small></p>
<p>Feeling in the “depths of despair” doesn’t mean you’re turning your back on God; it can mean you are turning your face toward Him.</p>
</p></div>
</article>
</div>
</div>
				</div>
				</div>
						</div>
					</div>
		</div>
								</div>
					</div>
		</section>
				<section class="elementor-section elementor-top-section elementor-element elementor-element-755ad23 elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-id="755ad23" data-element_type="section">
						<div class="elementor-container elementor-column-gap-default">
							<div class="elementor-row">
					<div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-17138bc" data-id="17138bc" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-f3d4ed2 elementor-widget elementor-widget-post-navigation" data-id="f3d4ed2" data-element_type="widget" data-widget_type="post-navigation.default">
				<div class="elementor-widget-container">
					<div class="elementor-post-navigation">
			<div class="elementor-post-navigation__prev elementor-post-navigation__link">
				<a href="https://www.boundless.org/blog/wedding-prices-and-marital-success/" rel="prev"><span class="elementor-post-navigation__link__prev"><span class="post-navigation__prev--label">Previous</span><span class="post-navigation__prev--title">Wedding Prices and Marital Success</span></span></a>			</div>
						<div class="elementor-post-navigation__next elementor-post-navigation__link">
				<a href="https://www.boundless.org/blog/a-wink-and-a-smile/" rel="next"><span class="elementor-post-navigation__link__next"><span class="post-navigation__next--label">Next</span><span class="post-navigation__next--title">A Wink and a Smile</span></span></a>			</div>
		</div>
				</div>
				</div>
						</div>
					</div>
		</div>
								</div>
					</div>
		</section>
							</div>
				</div>
				<div data-elementor-type="footer" data-elementor-id="26385" class="elementor elementor-26385 elementor-location-footer">
					<div class="elementor-section-wrap">
								<section class="elementor-section elementor-top-section elementor-element elementor-element-4ea40d14 elementor-section-content-middle elementor-reverse-mobile elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-id="4ea40d14" data-element_type="section" data-settings="{&quot;background_background&quot;:&quot;classic&quot;}">
						<div class="elementor-container elementor-column-gap-extended">
							<div class="elementor-row">
					<div class="elementor-column elementor-col-33 elementor-top-column elementor-element elementor-element-26a7556b" data-id="26a7556b" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-752b44c2 elementor-widget elementor-widget-shortcode" data-id="752b44c2" data-element_type="widget" data-widget_type="shortcode.default">
				<div class="elementor-widget-container">
					<div class="elementor-shortcode">		<div data-elementor-type="section" data-elementor-id="26379" class="elementor elementor-26379 elementor-location-footer">
					<div class="elementor-section-wrap">
								<section class="elementor-section elementor-top-section elementor-element elementor-element-383d47aa elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-id="383d47aa" data-element_type="section" data-settings="{&quot;background_background&quot;:&quot;classic&quot;}">
						<div class="elementor-container elementor-column-gap-default">
							<div class="elementor-row">
					<div class="elementor-column elementor-col-50 elementor-top-column elementor-element elementor-element-25c609e2" data-id="25c609e2" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-1f55eaf1 elementor-widget elementor-widget-image" data-id="1f55eaf1" data-element_type="widget" data-widget_type="image.default">
				<div class="elementor-widget-container">
								<div class="elementor-image">
													<a href="https://www.boundless.org/">
							<img width="196" height="224" src="https://www.boundless.org/wp-content/uploads/2019/08/Boundless_Icon_1CR_White@2x-1.png" class="attachment-medium size-medium wp-image-26377" alt="" loading="lazy" />								</a>
														</div>
						</div>
				</div>
				<div class="elementor-element elementor-element-622df55e elementor-widget elementor-widget-image" data-id="622df55e" data-element_type="widget" data-widget_type="image.default">
				<div class="elementor-widget-container">
								<div class="elementor-image">
													<a href="https://www.focusonthefamily.com/" target="_blank">
							<img width="234" height="100" src="https://www.boundless.org/wp-content/uploads/2019/08/FOTF-Logo@2x-1.png" class="attachment-medium size-medium wp-image-26378" alt="" loading="lazy" />								</a>
														</div>
						</div>
				</div>
						</div>
					</div>
		</div>
				<div class="elementor-column elementor-col-50 elementor-top-column elementor-element elementor-element-5b3be89a" data-id="5b3be89a" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-4d8f0120 footer-menu elementor-nav-menu--dropdown-mobile elementor-nav-menu__text-align-aside elementor-widget elementor-widget-nav-menu" data-id="4d8f0120" data-element_type="widget" data-settings="{&quot;layout&quot;:&quot;vertical&quot;,&quot;submenu_icon&quot;:{&quot;value&quot;:&quot;&lt;i class=\&quot;\&quot;&gt;&lt;\/i&gt;&quot;,&quot;library&quot;:&quot;&quot;}}" data-widget_type="nav-menu.default">
				<div class="elementor-widget-container">
						<nav migration_allowed="1" migrated="0" class="elementor-nav-menu--main elementor-nav-menu__container elementor-nav-menu--layout-vertical e--pointer-none">
				<ul id="menu-1-4d8f0120" class="elementor-nav-menu sm-vertical"><li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19330"><a href="https://www.boundless.org/category/relationships/" class="elementor-item">Relationships</a></li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19331"><a href="https://www.boundless.org/category/adulthood/" class="elementor-item">Adulthood</a></li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor menu-item-19332"><a href="https://www.boundless.org/category/faith/" class="elementor-item">Faith</a></li>
<li class="menu-item menu-item-type-post_type_archive menu-item-object-blog menu-item-19333"><a href="https://www.boundless.org/blog/" class="elementor-item">Blog</a></li>
<li class="menu-item menu-item-type-post_type_archive menu-item-object-podcast menu-item-19407"><a href="https://www.boundless.org/podcast/" class="elementor-item">Podcast</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-19337"><a href="https://www.boundless.org/about-us/" class="elementor-item">About Us</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-19338"><a href="https://www.boundless.org/contact/" class="elementor-item">Contact</a></li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-37108"><a href="https://link.focusonthefamily.com/email/other/emailPage.html?site=Boundless" class="elementor-item">Email Preferences</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-19339"><a href="https://www.boundless.org/legal/" class="elementor-item">Legal</a></li>
<li class="external donate-btn menu-item menu-item-type-custom menu-item-object-custom menu-item-19340"><a target="_blank" rel="noopener" href="https://donate.focusonthefamily.com/boundless-donation-page#refcd=95404" class="elementor-item elementor-item-anchor">Donate</a></li>
</ul>			</nav>
						<nav class="elementor-nav-menu--dropdown elementor-nav-menu__container" aria-hidden="true">
				<ul id="menu-2-4d8f0120" class="elementor-nav-menu sm-vertical"><li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19330"><a href="https://www.boundless.org/category/relationships/" class="elementor-item" tabindex="-1">Relationships</a></li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category menu-item-19331"><a href="https://www.boundless.org/category/adulthood/" class="elementor-item" tabindex="-1">Adulthood</a></li>
<li class="menu-item menu-item-type-taxonomy menu-item-object-category current-blog-ancestor menu-item-19332"><a href="https://www.boundless.org/category/faith/" class="elementor-item" tabindex="-1">Faith</a></li>
<li class="menu-item menu-item-type-post_type_archive menu-item-object-blog menu-item-19333"><a href="https://www.boundless.org/blog/" class="elementor-item" tabindex="-1">Blog</a></li>
<li class="menu-item menu-item-type-post_type_archive menu-item-object-podcast menu-item-19407"><a href="https://www.boundless.org/podcast/" class="elementor-item" tabindex="-1">Podcast</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-19337"><a href="https://www.boundless.org/about-us/" class="elementor-item" tabindex="-1">About Us</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-19338"><a href="https://www.boundless.org/contact/" class="elementor-item" tabindex="-1">Contact</a></li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-37108"><a href="https://link.focusonthefamily.com/email/other/emailPage.html?site=Boundless" class="elementor-item" tabindex="-1">Email Preferences</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-19339"><a href="https://www.boundless.org/legal/" class="elementor-item" tabindex="-1">Legal</a></li>
<li class="external donate-btn menu-item menu-item-type-custom menu-item-object-custom menu-item-19340"><a target="_blank" rel="noopener" href="https://donate.focusonthefamily.com/boundless-donation-page#refcd=95404" class="elementor-item elementor-item-anchor" tabindex="-1">Donate</a></li>
</ul>			</nav>
				</div>
				</div>
						</div>
					</div>
		</div>
								</div>
					</div>
		</section>
							</div>
				</div>
		</div>
				</div>
				</div>
						</div>
					</div>
		</div>
				<div class="elementor-column elementor-col-66 elementor-top-column elementor-element elementor-element-1ad91876" data-id="1ad91876" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<section class="elementor-section elementor-inner-section elementor-element elementor-element-bf4493a newsletter-cta elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-id="bf4493a" data-element_type="section">
						<div class="elementor-container elementor-column-gap-wide">
							<div class="elementor-row">
					<div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-2df5bfc" data-id="2df5bfc" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-6f07edf elementor-widget elementor-widget-image" data-id="6f07edf" data-element_type="widget" data-widget_type="image.default">
				<div class="elementor-widget-container">
								<div class="elementor-image">
												<img width="504" height="46" src="https://www.boundless.org/wp-content/uploads/2018/08/boundless_newsletter.png" class="attachment-large size-large wp-image-19425" alt="" loading="lazy" srcset="https://www.boundless.org/wp-content/uploads/2018/08/boundless_newsletter.png 504w, https://www.boundless.org/wp-content/uploads/2018/08/boundless_newsletter-300x27.png 300w" sizes="(max-width: 504px) 100vw, 504px" />														</div>
						</div>
				</div>
						</div>
					</div>
		</div>
								</div>
					</div>
		</section>
				<div class="elementor-element elementor-element-a2ee61c elementor-align-center elementor-widget elementor-widget-button" data-id="a2ee61c" data-element_type="widget" data-widget_type="button.default">
				<div class="elementor-widget-container">
					<div class="elementor-button-wrapper">
			<a href="https://www.boundless.org/boundless-email-sign-up/" class="elementor-button-link elementor-button elementor-size-sm" role="button">
						<span class="elementor-button-content-wrapper">
						<span class="elementor-button-text"><i class="fas fa-envelope" aria-hidden="true"></i> Sign Up</span>
		</span>
					</a>
		</div>
				</div>
				</div>
				<section class="elementor-section elementor-inner-section elementor-element elementor-element-199a9d6 elementor-section-content-middle elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-id="199a9d6" data-element_type="section">
						<div class="elementor-container elementor-column-gap-default">
							<div class="elementor-row">
					<div class="elementor-column elementor-col-100 elementor-inner-column elementor-element elementor-element-769ffb3" data-id="769ffb3" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-0ba940e elementor-widget elementor-widget-heading" data-id="0ba940e" data-element_type="widget" data-widget_type="heading.default">
				<div class="elementor-widget-container">
			<h4 class="elementor-heading-title elementor-size-default">Follow Us</h4>		</div>
				</div>
				<div class="elementor-element elementor-element-454ef05 elementor-shape-circle elementor-widget__width-auto elementor-grid-0 e-grid-align-center elementor-widget elementor-widget-social-icons" data-id="454ef05" data-element_type="widget" data-widget_type="social-icons.default">
				<div class="elementor-widget-container">
					<div class="elementor-social-icons-wrapper elementor-grid">
							<span class="elementor-grid-item">
					<a class="elementor-icon elementor-social-icon elementor-social-icon-facebook-f elementor-repeater-item-eff48a4" href="http://www.facebook.com/boundless.org" target="_blank" rel="nofollow">
						<span class="elementor-screen-only">Facebook-f</span>
						<i class="fab fa-facebook-f"></i>					</a>
				</span>
							<span class="elementor-grid-item">
					<a class="elementor-icon elementor-social-icon elementor-social-icon-youtube elementor-repeater-item-6fc0bd5" href="https://www.youtube.com/user/boundlessvid" target="_blank" rel="nofollow">
						<span class="elementor-screen-only">Youtube</span>
						<i class="fab fa-youtube"></i>					</a>
				</span>
					</div>
				</div>
				</div>
				<div class="elementor-element elementor-element-6df3124 elementor-shape-circle elementor-widget__width-auto elementor-grid-0 e-grid-align-center elementor-widget elementor-widget-social-icons" data-id="6df3124" data-element_type="widget" data-widget_type="social-icons.default">
				<div class="elementor-widget-container">
					<div class="elementor-social-icons-wrapper elementor-grid">
							<span class="elementor-grid-item">
					<a class="elementor-icon elementor-social-icon elementor-social-icon-apple elementor-repeater-item-fd13982" href="https://itunes.apple.com/podcast/the-boundless-show/id272731921?mt=2" target="_blank" rel="nofollow">
						<span class="elementor-screen-only">Apple</span>
						<i class="fab fa-apple"></i>					</a>
				</span>
							<span class="elementor-grid-item">
					<a class="elementor-icon elementor-social-icon elementor-social-icon-instagram elementor-repeater-item-5d3dfeb" href="https://www.instagram.com/boundlessteam/" target="_blank" rel="nofollow">
						<span class="elementor-screen-only">Instagram</span>
						<i class="fab fa-instagram"></i>					</a>
				</span>
							<span class="elementor-grid-item">
					<a class="elementor-icon elementor-social-icon elementor-social-icon-envelope elementor-repeater-item-0a57acb" href="/contact/">
						<span class="elementor-screen-only">Envelope</span>
						<i class="fas fa-envelope"></i>					</a>
				</span>
					</div>
				</div>
				</div>
						</div>
					</div>
		</div>
								</div>
					</div>
		</section>
						</div>
					</div>
		</div>
								</div>
					</div>
		</section>
				<section class="elementor-section elementor-top-section elementor-element elementor-element-5d519d69 elementor-section-content-middle elementor-section-boxed elementor-section-height-default elementor-section-height-default" data-id="5d519d69" data-element_type="section" data-settings="{&quot;background_background&quot;:&quot;classic&quot;}">
						<div class="elementor-container elementor-column-gap-no">
							<div class="elementor-row">
					<div class="elementor-column elementor-col-100 elementor-top-column elementor-element elementor-element-2414e05f" data-id="2414e05f" data-element_type="column">
			<div class="elementor-column-wrap elementor-element-populated">
							<div class="elementor-widget-wrap">
						<div class="elementor-element elementor-element-48e9c18 elementor-widget elementor-widget-heading" data-id="48e9c18" data-element_type="widget" id="footer-bottom" data-widget_type="heading.default">
				<div class="elementor-widget-container">
			<p class="elementor-heading-title elementor-size-default">© 2022 <a href="https://www.focusonthefamily.com/" title="Focus on the Family">Focus on the Family</a></p>		</div>
				</div>
				<div class="elementor-element elementor-element-4847d7e elementor-widget elementor-widget-html" data-id="4847d7e" data-element_type="widget" data-widget_type="html.default">
				<div class="elementor-widget-container">
				<script type="rocketlazyloadscript" data-rocket-type='text/javascript' src='/wp-content/plugins/gigya/features/comments/gigya_comments.js?ver=5.2.2'></script>
		</div>
				</div>
						</div>
					</div>
		</div>
								</div>
					</div>
		</section>
							</div>
				</div>
		

<script type="rocketlazyloadscript" data-rocket-type="text/javascript">
const wpvViewHead = document.getElementsByTagName( "head" )[ 0 ];
const wpvViewExtraCss = document.createElement( "style" );
wpvViewExtraCss.textContent = '<!--[if IE 7]><style>.wpv-pagination { *zoom: 1; }</style><![endif]-->';
wpvViewHead.appendChild( wpvViewExtraCss );
</script>
<link rel='stylesheet' id='elementor-icons-fa-regular-css' href='https://www.boundless.org/wp-content/plugins/elementor/assets/lib/font-awesome/css/regular.min.css?ver=5.15.3' media='all' />
<link rel='stylesheet' id='elementor-post-26379-css' href='https://www.boundless.org/wp-content/uploads/elementor/css/post-26379.css?ver=1673627598' media='all' />
<link rel='stylesheet' id='e-animations-css' href='https://www.boundless.org/wp-content/plugins/elementor/assets/lib/animations/animations.min.css?ver=3.10.0' media='all' />
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/jquery/ui/core.min.js?ver=1.13.2' id='jquery-ui-core-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/jquery/ui/tooltip.min.js?ver=1.13.2' id='jquery-ui-tooltip-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/duracelltomi-google-tag-manager/js/gtm4wp-form-move-tracker.js?ver=1.16.2' id='gtm4wp-form-move-tracker-js'></script>
<script type="rocketlazyloadscript" id='rocket-browser-checker-js-after'>
"use strict";var _createClass=function(){function defineProperties(target,props){for(var i=0;i<props.length;i++){var descriptor=props[i];descriptor.enumerable=descriptor.enumerable||!1,descriptor.configurable=!0,"value"in descriptor&&(descriptor.writable=!0),Object.defineProperty(target,descriptor.key,descriptor)}}return function(Constructor,protoProps,staticProps){return protoProps&&defineProperties(Constructor.prototype,protoProps),staticProps&&defineProperties(Constructor,staticProps),Constructor}}();function _classCallCheck(instance,Constructor){if(!(instance instanceof Constructor))throw new TypeError("Cannot call a class as a function")}var RocketBrowserCompatibilityChecker=function(){function RocketBrowserCompatibilityChecker(options){_classCallCheck(this,RocketBrowserCompatibilityChecker),this.passiveSupported=!1,this._checkPassiveOption(this),this.options=!!this.passiveSupported&&options}return _createClass(RocketBrowserCompatibilityChecker,[{key:"_checkPassiveOption",value:function(self){try{var options={get passive(){return!(self.passiveSupported=!0)}};window.addEventListener("test",null,options),window.removeEventListener("test",null,options)}catch(err){self.passiveSupported=!1}}},{key:"initRequestIdleCallback",value:function(){!1 in window&&(window.requestIdleCallback=function(cb){var start=Date.now();return setTimeout(function(){cb({didTimeout:!1,timeRemaining:function(){return Math.max(0,50-(Date.now()-start))}})},1)}),!1 in window&&(window.cancelIdleCallback=function(id){return clearTimeout(id)})}},{key:"isDataSaverModeOn",value:function(){return"connection"in navigator&&!0===navigator.connection.saveData}},{key:"supportsLinkPrefetch",value:function(){var elem=document.createElement("link");return elem.relList&&elem.relList.supports&&elem.relList.supports("prefetch")&&window.IntersectionObserver&&"isIntersecting"in IntersectionObserverEntry.prototype}},{key:"isSlowConnection",value:function(){return"connection"in navigator&&"effectiveType"in navigator.connection&&("2g"===navigator.connection.effectiveType||"slow-2g"===navigator.connection.effectiveType)}}]),RocketBrowserCompatibilityChecker}();
</script>
<script id='rocket-preload-links-js-extra'>
var RocketPreloadLinksConfig = {"excludeUris":"\/(?:.+\/)?feed(?:\/(?:.+\/?)?)?$|\/(?:.+\/)?embed\/|\/(index\\.php\/)?wp\\-json(\/.*|$)|\/refer\/|\/go\/|\/recommend\/|\/recommends\/","usesTrailingSlash":"1","imageExt":"jpg|jpeg|gif|png|tiff|bmp|webp|avif|pdf|doc|docx|xls|xlsx|php","fileExt":"jpg|jpeg|gif|png|tiff|bmp|webp|avif|pdf|doc|docx|xls|xlsx|php|html|htm","siteUrl":"https:\/\/www.boundless.org","onHoverDelay":"100","rateThrottle":"3"};
</script>
<script type="rocketlazyloadscript" id='rocket-preload-links-js-after'>
(function() {
"use strict";var r="function"==typeof Symbol&&"symbol"==typeof Symbol.iterator?function(e){return typeof e}:function(e){return e&&"function"==typeof Symbol&&e.constructor===Symbol&&e!==Symbol.prototype?"symbol":typeof e},e=function(){function i(e,t){for(var n=0;n<t.length;n++){var i=t[n];i.enumerable=i.enumerable||!1,i.configurable=!0,"value"in i&&(i.writable=!0),Object.defineProperty(e,i.key,i)}}return function(e,t,n){return t&&i(e.prototype,t),n&&i(e,n),e}}();function i(e,t){if(!(e instanceof t))throw new TypeError("Cannot call a class as a function")}var t=function(){function n(e,t){i(this,n),this.browser=e,this.config=t,this.options=this.browser.options,this.prefetched=new Set,this.eventTime=null,this.threshold=1111,this.numOnHover=0}return e(n,[{key:"init",value:function(){!this.browser.supportsLinkPrefetch()||this.browser.isDataSaverModeOn()||this.browser.isSlowConnection()||(this.regex={excludeUris:RegExp(this.config.excludeUris,"i"),images:RegExp(".("+this.config.imageExt+")$","i"),fileExt:RegExp(".("+this.config.fileExt+")$","i")},this._initListeners(this))}},{key:"_initListeners",value:function(e){-1<this.config.onHoverDelay&&document.addEventListener("mouseover",e.listener.bind(e),e.listenerOptions),document.addEventListener("mousedown",e.listener.bind(e),e.listenerOptions),document.addEventListener("touchstart",e.listener.bind(e),e.listenerOptions)}},{key:"listener",value:function(e){var t=e.target.closest("a"),n=this._prepareUrl(t);if(null!==n)switch(e.type){case"mousedown":case"touchstart":this._addPrefetchLink(n);break;case"mouseover":this._earlyPrefetch(t,n,"mouseout")}}},{key:"_earlyPrefetch",value:function(t,e,n){var i=this,r=setTimeout(function(){if(r=null,0===i.numOnHover)setTimeout(function(){return i.numOnHover=0},1e3);else if(i.numOnHover>i.config.rateThrottle)return;i.numOnHover++,i._addPrefetchLink(e)},this.config.onHoverDelay);t.addEventListener(n,function e(){t.removeEventListener(n,e,{passive:!0}),null!==r&&(clearTimeout(r),r=null)},{passive:!0})}},{key:"_addPrefetchLink",value:function(i){return this.prefetched.add(i.href),new Promise(function(e,t){var n=document.createElement("link");n.rel="prefetch",n.href=i.href,n.onload=e,n.onerror=t,document.head.appendChild(n)}).catch(function(){})}},{key:"_prepareUrl",value:function(e){if(null===e||"object"!==(void 0===e?"undefined":r(e))||!1 in e||-1===["http:","https:"].indexOf(e.protocol))return null;var t=e.href.substring(0,this.config.siteUrl.length),n=this._getPathname(e.href,t),i={original:e.href,protocol:e.protocol,origin:t,pathname:n,href:t+n};return this._isLinkOk(i)?i:null}},{key:"_getPathname",value:function(e,t){var n=t?e.substring(this.config.siteUrl.length):e;return n.startsWith("/")||(n="/"+n),this._shouldAddTrailingSlash(n)?n+"/":n}},{key:"_shouldAddTrailingSlash",value:function(e){return this.config.usesTrailingSlash&&!e.endsWith("/")&&!this.regex.fileExt.test(e)}},{key:"_isLinkOk",value:function(e){return null!==e&&"object"===(void 0===e?"undefined":r(e))&&(!this.prefetched.has(e.href)&&e.origin===this.config.siteUrl&&-1===e.href.indexOf("?")&&-1===e.href.indexOf("#")&&!this.regex.excludeUris.test(e.href)&&!this.regex.images.test(e.href))}}],[{key:"run",value:function(){"undefined"!=typeof RocketPreloadLinksConfig&&new n(new RocketBrowserCompatibilityChecker({capture:!0,passive:!0}),RocketPreloadLinksConfig).init()}}]),n}();t.run();
}());
</script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor-pro/assets/lib/smartmenus/jquery.smartmenus.min.js?ver=1.0.1' id='smartmenus-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor-pro/assets/js/webpack-pro.runtime.min.js?ver=3.10.1' id='elementor-pro-webpack-runtime-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor/assets/js/webpack.runtime.min.js?ver=3.10.0' id='elementor-webpack-runtime-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor/assets/js/frontend-modules.min.js?ver=3.10.0' id='elementor-frontend-modules-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/dist/vendor/regenerator-runtime.min.js?ver=0.13.9' id='regenerator-runtime-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/dist/vendor/wp-polyfill.min.js?ver=3.15.0' id='wp-polyfill-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/dist/hooks.min.js?ver=4169d3cf8e8d95a3d6d5' id='wp-hooks-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/dist/i18n.min.js?ver=9e794f35a71bb98672ae' id='wp-i18n-js'></script>
<script type="rocketlazyloadscript" id='wp-i18n-js-after'>
wp.i18n.setLocaleData( { 'text direction\u0004ltr': [ 'ltr' ] } );
</script>
<script type="rocketlazyloadscript" id='elementor-pro-frontend-js-before'>
var ElementorProFrontendConfig = {"ajaxurl":"https:\/\/www.boundless.org\/wp-admin\/admin-ajax.php","nonce":"b8338a4e8c","urls":{"assets":"https:\/\/www.boundless.org\/wp-content\/plugins\/elementor-pro\/assets\/","rest":"https:\/\/www.boundless.org\/wp-json\/"},"shareButtonsNetworks":{"facebook":{"title":"Facebook","has_counter":true},"twitter":{"title":"Twitter"},"linkedin":{"title":"LinkedIn","has_counter":true},"pinterest":{"title":"Pinterest","has_counter":true},"reddit":{"title":"Reddit","has_counter":true},"vk":{"title":"VK","has_counter":true},"odnoklassniki":{"title":"OK","has_counter":true},"tumblr":{"title":"Tumblr"},"digg":{"title":"Digg"},"skype":{"title":"Skype"},"stumbleupon":{"title":"StumbleUpon","has_counter":true},"mix":{"title":"Mix"},"telegram":{"title":"Telegram"},"pocket":{"title":"Pocket","has_counter":true},"xing":{"title":"XING","has_counter":true},"whatsapp":{"title":"WhatsApp"},"email":{"title":"Email"},"print":{"title":"Print"}},"facebook_sdk":{"lang":"en_US","app_id":""},"lottie":{"defaultAnimationUrl":"https:\/\/www.boundless.org\/wp-content\/plugins\/elementor-pro\/modules\/lottie\/assets\/animations\/default.json"}};
</script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor-pro/assets/js/frontend.min.js?ver=3.10.1' id='elementor-pro-frontend-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor/assets/lib/waypoints/waypoints.min.js?ver=4.0.2' id='elementor-waypoints-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor/assets/lib/swiper/swiper.min.js?ver=5.3.6' id='swiper-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor/assets/lib/share-link/share-link.min.js?ver=3.10.0' id='share-link-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor/assets/lib/dialog/dialog.min.js?ver=4.9.0' id='elementor-dialog-js'></script>
<script type="rocketlazyloadscript" id='elementor-frontend-js-before'>
var elementorFrontendConfig = {"environmentMode":{"edit":false,"wpPreview":false,"isScriptDebug":false},"i18n":{"shareOnFacebook":"Share on Facebook","shareOnTwitter":"Share on Twitter","pinIt":"Pin it","download":"Download","downloadImage":"Download image","fullscreen":"Fullscreen","zoom":"Zoom","share":"Share","playVideo":"Play Video","previous":"Previous","next":"Next","close":"Close"},"is_rtl":false,"breakpoints":{"xs":0,"sm":480,"md":768,"lg":1025,"xl":1440,"xxl":1600},"responsive":{"breakpoints":{"mobile":{"label":"Mobile","value":767,"default_value":767,"direction":"max","is_enabled":true},"mobile_extra":{"label":"Mobile Extra","value":880,"default_value":880,"direction":"max","is_enabled":false},"tablet":{"label":"Tablet","value":1024,"default_value":1024,"direction":"max","is_enabled":true},"tablet_extra":{"label":"Tablet Extra","value":1200,"default_value":1200,"direction":"max","is_enabled":false},"laptop":{"label":"Laptop","value":1366,"default_value":1366,"direction":"max","is_enabled":false},"widescreen":{"label":"Widescreen","value":2400,"default_value":2400,"direction":"min","is_enabled":false}}},"version":"3.10.0","is_static":false,"experimentalFeatures":{"e_hidden_wordpress_widgets":true,"theme_builder_v2":true,"kit-elements-defaults":true,"page-transitions":true,"notes":true,"e_scroll_snap":true},"urls":{"assets":"https:\/\/www.boundless.org\/wp-content\/plugins\/elementor\/assets\/"},"settings":{"page":[],"editorPreferences":[]},"kit":{"global_image_lightbox":"yes","active_breakpoints":["viewport_mobile","viewport_tablet"],"lightbox_enable_counter":"yes","lightbox_enable_fullscreen":"yes","lightbox_enable_zoom":"yes","lightbox_enable_share":"yes","lightbox_title_src":"title","lightbox_description_src":"description"},"post":{"id":11904,"title":"Hold%20on%20Loosely%20-%20Boundless","excerpt":"","featuredImage":false}};
</script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor/assets/js/frontend.min.js?ver=3.10.0' id='elementor-frontend-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor-pro/assets/js/preloaded-elements-handlers.min.js?ver=3.10.1' id='pro-preloaded-elements-handlers-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor/assets/js/preloaded-modules.min.js?ver=3.10.0' id='preloaded-modules-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/elementor-pro/assets/lib/sticky/jquery.sticky.min.js?ver=3.10.1' id='e-sticky-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/jquery/ui/datepicker.min.js?ver=1.13.2' id='jquery-ui-datepicker-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/jquery/ui/mouse.min.js?ver=1.13.2' id='jquery-ui-mouse-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/jquery/ui/slider.min.js?ver=1.13.2' id='jquery-ui-slider-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/jquery/jquery.ui.touch-punch.js?ver=0.2.2' id='jquery-touch-punch-js'></script>
<script type="rocketlazyloadscript" id='mediaelement-core-js-before'>
var mejsL10n = {"language":"en","strings":{"mejs.download-file":"Download File","mejs.install-flash":"You are using a browser that does not have Flash player enabled or installed. Please turn on your Flash player plugin or download the latest version from https:\/\/get.adobe.com\/flashplayer\/","mejs.fullscreen":"Fullscreen","mejs.play":"Play","mejs.pause":"Pause","mejs.time-slider":"Time Slider","mejs.time-help-text":"Use Left\/Right Arrow keys to advance one second, Up\/Down arrows to advance ten seconds.","mejs.live-broadcast":"Live Broadcast","mejs.volume-help-text":"Use Up\/Down Arrow keys to increase or decrease volume.","mejs.unmute":"Unmute","mejs.mute":"Mute","mejs.volume-slider":"Volume Slider","mejs.video-player":"Video Player","mejs.audio-player":"Audio Player","mejs.captions-subtitles":"Captions\/Subtitles","mejs.captions-chapters":"Chapters","mejs.none":"None","mejs.afrikaans":"Afrikaans","mejs.albanian":"Albanian","mejs.arabic":"Arabic","mejs.belarusian":"Belarusian","mejs.bulgarian":"Bulgarian","mejs.catalan":"Catalan","mejs.chinese":"Chinese","mejs.chinese-simplified":"Chinese (Simplified)","mejs.chinese-traditional":"Chinese (Traditional)","mejs.croatian":"Croatian","mejs.czech":"Czech","mejs.danish":"Danish","mejs.dutch":"Dutch","mejs.english":"English","mejs.estonian":"Estonian","mejs.filipino":"Filipino","mejs.finnish":"Finnish","mejs.french":"French","mejs.galician":"Galician","mejs.german":"German","mejs.greek":"Greek","mejs.haitian-creole":"Haitian Creole","mejs.hebrew":"Hebrew","mejs.hindi":"Hindi","mejs.hungarian":"Hungarian","mejs.icelandic":"Icelandic","mejs.indonesian":"Indonesian","mejs.irish":"Irish","mejs.italian":"Italian","mejs.japanese":"Japanese","mejs.korean":"Korean","mejs.latvian":"Latvian","mejs.lithuanian":"Lithuanian","mejs.macedonian":"Macedonian","mejs.malay":"Malay","mejs.maltese":"Maltese","mejs.norwegian":"Norwegian","mejs.persian":"Persian","mejs.polish":"Polish","mejs.portuguese":"Portuguese","mejs.romanian":"Romanian","mejs.russian":"Russian","mejs.serbian":"Serbian","mejs.slovak":"Slovak","mejs.slovenian":"Slovenian","mejs.spanish":"Spanish","mejs.swahili":"Swahili","mejs.swedish":"Swedish","mejs.tagalog":"Tagalog","mejs.thai":"Thai","mejs.turkish":"Turkish","mejs.ukrainian":"Ukrainian","mejs.vietnamese":"Vietnamese","mejs.welsh":"Welsh","mejs.yiddish":"Yiddish"}};
</script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/mediaelement/mediaelement-and-player.min.js?ver=4.2.17' id='mediaelement-core-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/mediaelement/mediaelement-migrate.min.js?ver=6.1.1' id='mediaelement-migrate-js'></script>
<script id='mediaelement-js-extra'>
var _wpmejsSettings = {"pluginPath":"\/wp-includes\/js\/mediaelement\/","classPrefix":"mejs-","stretching":"responsive"};
</script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/mediaelement/wp-mediaelement.min.js?ver=6.1.1' id='wp-mediaelement-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/underscore.min.js?ver=1.13.4' id='underscore-js'></script>
<script id='wp-util-js-extra'>
var _wpUtilSettings = {"ajax":{"url":"\/wp-admin\/admin-ajax.php"}};
</script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/wp-util.min.js?ver=6.1.1' id='wp-util-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/backbone.min.js?ver=1.4.1' id='backbone-js'></script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-includes/js/mediaelement/wp-playlist.min.js?ver=6.1.1' id='wp-playlist-js'></script>
<script id='views-blocks-frontend-js-extra'>
var wpv_pagination_local = {"front_ajaxurl":"https:\/\/www.boundless.org\/wp-admin\/admin-ajax.php","calendar_image":"https:\/\/www.boundless.org\/wp-content\/plugins\/wp-views\/embedded\/res\/img\/calendar.gif","calendar_text":"Select date","datepicker_min_date":null,"datepicker_max_date":null,"datepicker_min_year":"1582","datepicker_max_year":"3000","resize_debounce_tolerance":"100","datepicker_style_url":"https:\/\/www.boundless.org\/wp-content\/plugins\/types\/vendor\/toolset\/toolset-common\/toolset-forms\/css\/wpt-jquery-ui\/jquery-ui-1.11.4.custom.css","wpmlLang":""};
</script>
<script type="rocketlazyloadscript" src='https://www.boundless.org/wp-content/plugins/wp-views/public/js/views-frontend.js?ver=3.6.5' id='views-blocks-frontend-js'></script>

</body>
</html>

<!-- This website is like a Rocket, isn't it? Performance optimized by WP Rocket. Learn more: https://wp-rocket.me -->
