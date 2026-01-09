---
description: 'Last updated: January 8, 2026'
icon: video
---

# Video API

#### Video Processing

The Weekerp Video API lets you reliably serve videos through the Weekerp CDN **without building a custom API**. All processing is performed **on request**, and the transformed result is cached at the **CDN edge** on the first request.\
Subsequent identical requests are served directly from cache.

When you request a cached video again with the same parameters, the already-transformed cached video is returned immediately for a low-latency response.<br>

> For more details, see the [cache.md](cache.md "mention") documentation.

#### Basic request format

```
https://cdn.weekerp.com/video/{source}/{path/to/video}.{ext}?{options}
```



#### Roadmap / Feature requests

{% hint style="info" %}
Some features (such as streaming and other format-specific video support) are planned and will be added in a future update.&#x20;

If you request a feature, the Weekerp team will prioritize it and implement it as soon as possible.
{% endhint %}

Request new features here: [feature.md](../getting-started/feature.md "mention")&#x20;
