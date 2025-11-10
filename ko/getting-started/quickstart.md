---
description: This is the guide you need to get started with weekerp.
icon: bullseye-arrow
---

# 빠른 시작 가이드

#### 1️⃣계정 생성

1. [weekerp](https://weekerp.com/space/callback)에 접속합니다.
2. 구글로그인을 선택합니다.



#### 2️⃣저장소 연결

다음 중 한 곳에 이미지가 저장되어 있어야 합니다.

* 클라우드 저장소
* 내 웹 서버



리소스의 원본(Origin)은 아래 중 하나를 선택할 수 있습니다.

<table><thead><tr><th width="139.85711669921875">구분</th><th width="401.142822265625">설명</th><th>문서</th></tr></thead><tbody><tr><td>AWS S3</td><td>기존 S3 버킷을 연결합니다.</td><td><a href="../basics/images-and-media.md">AWS 연결 가이드</a></td></tr><tr><td>GCP GCS</td><td>GCP Storage 버킷을 연결합니다.</td><td><a href="../basics/interactive-blocks.md">GCP 연결 가이드</a></td></tr><tr><td>Azure Blob</td><td>Azure Blob Container를 연결합니다.</td><td><a href="../stroage/azure.md">Azure 연결 가이드</a></td></tr><tr><td>Web Proxy</td><td>외부 이미지 URL을 프록시 형태로 캐싱합니다.</td><td><a href="../stroage/web.md">Web Proxy 가이드</a></td></tr></tbody></table>

저장소는 여러 개 생성할 수 있으며, 언제든 수정, 삭제가 가능합니다.



### 3️⃣ 이미지 CDN 적용하기

연결된 이미지를 다음처럼 불러올 수 있습니다.

```html
<img src="https://cdn.weekerp.com/image/{workspace}/example.jpg?w=800&q=80" />
```

* `source` : 고유의 데이터 소스입니다.
* `w`: 변경하고자 하는 이미지 너비
* `q`: 품질 (1\~100)
* `f`: 포맷 변환 (jpg, webp 등)

{% hint style="info" %}
최초리사이징 이후에는 모든 이미지는 캐싱처리되어 전세계 빠른 응답을 보장합니다.
{% endhint %}



#### 4️⃣ 빌링 구독

위커프는 종량제 청구방식을 따릅니다.

여기에서 자세히 확인하실 수 있습니다.

:arrow\_right: [요금관련 가이드 확인하기](../billing/overview.md)

