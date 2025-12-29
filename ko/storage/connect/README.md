# 소스 연결

#### 소스(Source) 연결

Weekerp CDN에서 파일을 불러올 **소스(Source)** 를 정의합니다.\
소스는 이미지·비디오·파일 등의 **원본(origin)** 이 저장된 위치를 의미합니다.

Weekerp는 클라우드 저장소뿐만 아니라,\
기존에 운영 중인 웹 서버를 **Web Proxy** 형태로도 연결할 수 있습니다.\
필요에 따라 여러 개의 소스를 생성하고 관리할 수 있습니다.



#### 지원되는 데이터 소스 유형

<table><thead><tr><th width="139.85711669921875">구분</th><th width="401.142822265625">설명</th><th>문서</th></tr></thead><tbody><tr><td>AWS S3</td><td>기존 S3 버킷을 연결합니다.</td><td><a href="aws.md">AWS 연결 가이드</a></td></tr><tr><td>GCP GCS</td><td>GCP Storage 버킷을 연결합니다.</td><td><a href="gcp.md">GCP 연결 가이드</a></td></tr><tr><td>Azure Blob</td><td>Azure Blob Container를 연결합니다.</td><td><a href="azure.md">Azure 연결 가이드</a></td></tr><tr><td>Web Proxy</td><td>외부 이미지 URL을 프록시 형태로 캐싱합니다.</td><td><a href="web.md">Web Proxy 가이드</a></td></tr></tbody></table>



#### 관리

* 소스는 **여러 개 생성**할 수 있습니다.
* 필요 시 **수정, 비활성화, 삭제**가 가능합니다.
* 각 소스는 연결된 CDN 경로와 자동으로 동기화됩니다.



#### 사용 예시

* 국가별 리전에 따라 다른 S3 버킷을 소스로 등록
* 기존 이미지 서버를 Web Proxy로 연결해 별도 업로드 없이 CDN 적용
* 테스트 환경용 GCS 버킷을 별도 소스로 추가 등록



{% hint style="info" %}
소스(Source)는 Weekerp Image, Video, File API에서 **리소스의 원본 데이터**로 사용됩니다.\
모든 CDN 요청은 연결된 소스를 기반으로 처리됩니다.
{% endhint %}





