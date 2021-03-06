---
layout: post
title: LinkedIn/Facebook loading issue using jQuery Mobile
published_at: 2013-01-14
tags:
  - Technology
  - jQuery
---

If you're trying to add LinkedIn/Facebook to your mobile site, and are using jQuery Mobile, you might get a 302 redirect error.  Similar to this:

```
Completed 302 Found in 1084ms (ActiveRecord: 0.0ms)
```

This error doesn't help much.

The problem is that jQuery Mobile is treating the link as an AJAX navigation request, though you don't want that.

All you have to do is place a `rel="external"`, `data-ajax="false"` or any `target` property in the link to disable AJAX navigation.

http://jquerymobile.com/demos/1.1.0/docs/pages/page-links.html

Before:
```
<a href="http://api.linkedin...">Login via LinkedIn</a>
```

After:
```
<a href="http://api.linkedin..." rel="external">Login via LinkedIn</a>
```
