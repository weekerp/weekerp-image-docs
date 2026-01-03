---
description: '최종 수정일: 2026-01-03'
icon: copy
---

# 범용 파일 API

#### 범용 파일 처리 (File Processing)

Weekerp File API는 별도의 맞춤형 API를 사용하지 않고도\
정적 파일(PDF, MP4, ZIP, CSS 등)을 Weekerp CDN을 통해 안정적으로 서빙할 수 있도록 제공합니다.

모든 처리는 요청 시점에 수행되며 **최초 1회 요청 시 변환된 결과가 CDN 엣지에 캐싱됩니다.**\
이후 동일한 요청은 캐시에서 바로 송신됩니다.<br>

캐싱된 비디오를 동일한 파라미터로 재요청하는 경우, **이미 변환된 캐시 비디오가 즉시 반환되어 지연 없이 응답합니다.**

> 자세한 사항은  [cache.md](cache.md "mention") 문서를 참고해주세요.

#### 기본 요청 형식

```
https://cdn.weekerp.com/file/{source}/{path/to/video}.{ext}?{options}
```

<table><thead><tr><th width="189.4285888671875">설명</th><th>예시 URL</th></tr></thead><tbody><tr><td>PDF 파일 서빙</td><td><code>https://cdn.weekerp.com/file/docs/guide.pdf</code></td></tr><tr><td>MP4 비디오 서빙</td><td><code>https://cdn.weekerp.com/file/media/example.mp4</code></td></tr><tr><td>ZIP 아카이브</td><td><code>https://cdn.weekerp.com/file/backup/site.zip</code></td></tr></tbody></table>



#### 필요한 기능이 있어요.

{% hint style="info" %}
pdf, json, css 파일등 특별한 파일의처리가 필요하신경우 빠르게 지원할 수 있습니다.\
기능 추가를 요청하시면 위커프 팀은 최우선으로 반영하여 처리합니다.
{% endhint %}

[feature.md](../quick/feature.md "mention")에서 기능 추가를 요청하세요.



