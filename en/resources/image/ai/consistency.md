---
description: 'Last updated: January 8, 2026'
icon: circle-1
---

# Request consistency

### Request Consistency

Request Consistency stores the **initially resolved transformation interpretation** and reuses it for subsequent identical requests, so the output image won’t change unexpectedly—even after a **cache miss** or **cache expiration**.

Weekerp provides Request Consistency to prevent “accidental variation,” where the output could differ from one request to another simply because the AI interpretation changes.

***

### Why do we need this?

Request Consistency is mainly needed in two situations:



#### 1) For images that rarely change

Weekerp caches images for a long time by default (e.g., up to **1 year**).

This is very effective for assets such as company logos, official certification marks, or security badges—files that almost never change. However, when the cache **expires** or a **cache miss** occurs, Weekerp may fetch the original asset again and re-run the AI transformation.



If the user provided an open-ended prompt like:

```
?ai=change the image to a reddish tone
```

the AI could produce a different result when it re-interprets the request (due to model state, interpretation differences, etc.).



#### 2) When the same image is requested from different countries/regions

Weekerp serves cached images from the edge location closest to the user whenever possible.

In a global environment, cache states differ by region (edge). In some regions, there may be no cached result (a cache miss), so Weekerp fetches the original asset and runs the AI transformation from scratch.

If AI interpretation is not guaranteed to be consistent, the same URL could produce different outputs depending on the user’s country/region.



***

### What We Guarantee

Weekerp guarantees identical output when all of the following are the same:

* The **same original image**
* The **same `ai` prompt** (must be an identical string)
* The **same transformation options/parameters** (if any)

In other words, repeatedly requesting the same URL will not cause the output to drift or change “slightly” over time.

{% hint style="info" %}
“Same `ai` prompt” means the string must match exactly. Differences in spacing or wording may be treated as a different request.
{% endhint %}



***

### Versioning

If you intentionally want a different result, add a version suffix to the prompt.

Example:

```
?ai=change the image to a reddish tone-v2
```



