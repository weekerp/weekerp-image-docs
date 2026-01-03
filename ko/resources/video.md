---
description: '최종 수정일: 2026-01-03'
icon: video
---

# 비디오 API

#### 비디오 처리 (Video Processing)

Weekerp Video API는 별도의 맞춤형 API를 사용하지 않고도\
Weekerp CDN을 통해 안정적으로 서빙할 수 있도록 제공합니다.

모든 처리는 요청 시점에 수행되며 **최초 1회 요청 시 변환된 결과가 CDN 엣지에 캐싱됩니다.**\
이후 동일한 요청은 캐시에서 바로 송신됩니다.<br>

캐싱된 비디오를 동일한 파라미터로 재요청하는 경우, **이미 변환된 캐시 비디오가 즉시 반환되어 지연 없이 응답합니다.**

> 자세한 사항은  [cache.md](cache.md "mention") 문서를 참고해주세요.

#### 기본 요청 형식

```
https://cdn.weekerp.com/video/{source}/{path/to/video}.{ext}?{options}
```



#### 필요한 기능이 있어요.

{% hint style="info" %}
스트리밍 등 비디오 포맷에 맞는 지원은 지원예정에 있습니다.&#x20;\
기능 추가를 요청하시면 위커프 팀은 최우선으로 반영하여 처리합니다.
{% endhint %}

[feature.md](../quick/feature.md "mention")에서 기능 추가를 요청하세요.



