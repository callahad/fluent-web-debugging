# Performance

***

### Compared to Desktop

1. Worse Network
2. Slower CPU
3. Less RAM

***

### ORLY?

![](slides/images/craptops.jpg)

***

### Compared to Desktop

1. Same engines
2. No old IE
3. Hardware acceleration

***

### Webviews?

* UIWebView didn't use Safari's JIT.
* WKWebView (iOS 8) does.

http://developer.telerik.com/featured/why-ios-8s-wkwebview-is-a-big-deal-for-hybrid-development/

***

> You __are not__ exempt from mobile testing.

Note: More headroom on desktop leads to more headroom on mobile. Relative costs of operations are similar; just worried about scaling factor.

---

## Measuring Performance

You can't debug what you can't measure

***

### Areas of Measurement

1. Network Performance
2. Frames Per Second
3. Memory Usage

---

## Network Performance

More from Mike later, but...

***

### What do we care about?

1. Time until something appears.
2. Time until the page is interactive.

> Hack the first to get better __perceived speed__.

Note: Script tag at end of body, cache headers, etc.

***

![](slides/images/facebook-shell.png)

***

### Network Perf Tools

1. Get to know your Network Panel
2. http://webpagetest.org
3. https://developers.google.com/speed/pagespeed/insights/

***

![](slides/images/netperf-chrome.png)

***

![](slides/images/netperf-webpagetest.png)

***

![](slides/images/netperf-pagespeed.png)

***

### Obsolete Practices

1. Domain sharding
2. Concatenating sources
3. Combining images into sprites

Thanks, SPDY and HTTP/2!

---

## Framerate Performance

60 FPS means 16 ms per frame

***

### Rendering Stages

1. Recalculate Styles
2. Reflow / Layout
3. Paint
4. Composite

Reflows and Paints are most expensive.

***

![](slides/images/compositing-aerotwist.jpg)

_Illustration by Paul Lewis, <br> From his blog post [Pixels are Expensive](http://aerotwist.com/blog/pixels-are-expensive/)._

***

### Creating layers

```css
.foo {
    will-change: transform, opacity; /* New goodness */
    transform: translateZ(0); /* Old hack for Safari */
}
```

***

### Trivia: Selector Performance

No. | Type       | Example
--- | ---------- | -------
1.  | Identifier | `#id`
2.  | Class      | `.class`
3.  | Tag        | `div`
4.  | Sibling    | `a + i`
5.  | Descendant | `ul > li`
6.  | Universal  | `*`
7.  | Attribute  | `input[type="text"]`
8.  | Pseudo     | `a:hover`

Note: Right to left matching! Also, adding / removing classes is fast.

***

### Layout Thrashing, Part 1

```javascript
var h1 = element1.clientHeight;          // Read
element1.style.height = (h1 * 2) + 'px'; // Write (invalidates)

var h2 = element2.clientHeight;          // Read (forces reflow)
element2.style.height = (h2 * 2) + 'px'; // Write (invalidates)

var h3 = element3.clientHeight;          // Read (forces reflow)
element3.style.height = (h3 * 2) + 'px'; // Write (invalidates)

// Document reflows at end of frame
```

_From Wilson Page's [blog](http://wilsonpage.co.uk/preventing-layout-thrashing/)_

***

### Layout Thrashing, Part 2

```javascript
// Read
var h1 = element1.clientHeight;
var h2 = element2.clientHeight;
var h3 = element3.clientHeight;

// Write (invalidates layout)
element1.style.height = (h1 * 2) + 'px';
element2.style.height = (h2 * 2) + 'px';
element3.style.height = (h3 * 2) + 'px';

// Document reflows at end of frame
```

_From Wilson Page's [blog](http://wilsonpage.co.uk/preventing-layout-thrashing/)_

***

![](slides/images/layout-thrashing.png)

***

### Need even more? Virtualize.

- [React](https://facebook.github.io/react/)
- [Mithril](https://lhorie.github.io/mithril/)
- [virtual-dom](https://github.com/Matt-Esch/virtual-dom)

***

### Animations

Demos!

---

## Memory Performance

Heaps of leaks

***

Let's just do some demos here, too.
