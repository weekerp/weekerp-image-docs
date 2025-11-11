---
icon: copy
---

# 범용 파일 API

`/file` 엔드포인트는 별도의 맞춤형 API를 사용하지 않고도\
정적 파일(PDF, MP4, ZIP 등)을 Weekerp CDN을 통해 안정적으로 서빙할 수 있도록 제공합니다.

이 API는 이미지, 비디오, 문서 등 **모든 파일 타입**에 공통적으로 적용됩니다.

```
https://cdn.weekerp.com/file/{source}/file.pdf
```



<table><thead><tr><th width="189.4285888671875">설명</th><th>예시 URL</th></tr></thead><tbody><tr><td>PDF 파일 서빙</td><td><code>https://cdn.weekerp.com/file/docs/guide.pdf</code></td></tr><tr><td>MP4 비디오 서빙</td><td><code>https://cdn.weekerp.com/file/media/example.mp4</code></td></tr><tr><td>ZIP 아카이브</td><td><code>https://cdn.weekerp.com/file/backup/site.zip</code></td></tr></tbody></table>
