---
description: 'Last updated: January 8, 2026'
icon: globe-pointer
---

# Caching

#### **Caching Policy**

Weekerp CDN caches transformed images for **up to one year** after the first request.\
When the same request (same URL and parameters) is repeated,\
the cached image is instantly served to maximize delivery speed.

***

#### Cache Duration

* Transformed images are stored on CDN edge servers for **up to 1 year**.
* The same combination of **URL and parameters** always references the same cache.
* After expiration, the first subsequent request automatically regenerates and updates the cache.

***

#### Cache Key Criteria

Cache entries are distinguished based on the **entire request path + parameters**.\
For example, the following two requests generate **separate cache entries**:

```
/image/cat.jpg?w=800
/image/cat.jpg?w=800&fit=cover
```

***

#### Cache Purge

Currently, **no official cache purge feature** is provided.\
However, if you urgently need to remove cached content, please contact [publish-your-docs.md](../getting-started/publish-your-docs.md "mention")

***

#### Versioning (Recommended)

Instead of manually purging cache,\
you can append a **version parameter (`v`)** to the image URL\
to achieve the same effect safely and instantly.

```
/image/cat.jpg?w=800&v=2
```

Changing the `v` value creates a **completely new cache entry**,\
allowing the latest image to be served immediately without touching existing caches.

💡 **Tip:**\
Use a **timestamp** or **build version** for the `v` parameter\
to safely refresh caches on every new release.
