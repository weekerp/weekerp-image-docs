# Source Connection

**Connect a Source**\
Define the source from which Weekerp CDN will fetch files.\
A source refers to the location where original (origin) resources such as images, videos, or files are stored.

\
Weekerp supports not only cloud storage but also existing web servers via a **Web Proxy** connection.\
You can create and manage multiple sources as needed.

***

#### Supported Data Source Types

<table><thead><tr><th width="154.714111328125">Type</th><th>Description</th><th>Docs</th></tr></thead><tbody><tr><td><strong>AWS S3</strong></td><td>Connect an existing S3 bucket.</td><td><a data-mention href="aws.md">aws.md</a></td></tr><tr><td><strong>GCP GCS</strong></td><td>Connect a GCP Storage bucket.</td><td><a data-mention href="gcp.md">gcp.md</a></td></tr><tr><td><strong>Azure Blob</strong></td><td>Connect an Azure Blob container.</td><td><a data-mention href="azure.md">azure.md</a></td></tr><tr><td><strong>Web Proxy</strong></td><td>Cache external image URLs in a proxy form.</td><td><a data-mention href="web.md">web.md</a></td></tr></tbody></table>

***

#### Management

* Multiple sources can be created.
* Each source can be modified, disabled, or deleted as needed.
* All sources are automatically synchronized with the connected CDN paths.

***

#### Examples

* Register separate S3 buckets as sources for each region.
* Connect an existing image server as a Web Proxy to apply CDN without additional uploads.
* Add a separate GCS bucket as a source for testing environments.

{% hint style="info" %}
A **Source** in Weekerp Image, Video, and File APIs serves as the origin data for each resource.\
All CDN requests are processed based on the connected sources.
{% endhint %}

