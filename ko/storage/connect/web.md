---
description: 전체 설정까지 5분
icon: browser
---

# Web Proxy

위커프 API를 이용하기 위해 WEB Proxy 방법을 안내합니다.

Web에 업로드된 이미지를 위커프와 연결합니다.



#### 연결에 필요한 정보

위커프가 이미지에 접근할 수 있도록 하기 위해 다음 정보를 입력해야 합니다:

* URL



#### 1. 웹 프록시의 이해

1.  사용자는 위커프 CDN 주소로 이미지를 요청합니다.

    예: `https://cdn.weekerp.com/image/{alias}/dog.jpg`
2.  위커프는 `{alias}`에 연결된 **Target URL(원본 서버)** 로 이미지를 요청합니다.

    예: `https://raw.githubusercontent.com/weekerp/test-assets/main` + `/dog.jpg`
3.  원본 서버는 이미지 파일을 응답합니다.

    예: `https://raw.githubusercontent.com/weekerp/test-assets/main/dog.jpg`
4. 위커프는 그 응답을 가공하여 사용자에게 전달하고 동시에 1년간 캐시합니다.
5. 이후 동일한 요청은 캐시 응답으로 원본 요청없이 사용자에게 빠르게 전달됩니다.



{% hint style="info" %}
WEB PROXY는 **버킷/키 같은 클라우드 자격증명 없이** “이미 공개된 URL”만 있으면 연결됩니다.
{% endhint %}

원본 서버 접근에 자격 증명이 필요한 경우, Custom Headers로 인증 헤더(예: `Authorization`)를 추가해 요청할 수 있습니다.

Custom Headers는 현재 위커프 콘솔에서 직접 설정할 수는 없습니다. 다만 내부적으로는 기능이 준비되어 있으니, 필요하시면 (문의링크)로 문의해 주세요.



#### 2. 연결 예시 (타겟 서버 : Github Repo)

* Github Repository 에 이미지와 영상을 업로드 함
* Github는 Url을 통해 해당 리소스에 접근할 수 있음



#### 3. 저장소 정보

깃허브를 사용한 이미지 저장소는 다음과 같습니다.

`https://raw.githubusercontent.com/weekerp/test-assets/main`

{% embed url="https://github.com/weekerp/test-assets" %}



#### 4. 저장 파일 예시

하위에는 4개의 파일이 있습니다.

<figure><img src="../../.gitbook/assets/4 (3).png" alt=""><figcaption></figcaption></figure>



#### 5. 공개된 이미지 정보

이미지는 다음과 같이 접속 가능한 상태여야 합니다.

[https://raw.githubusercontent.com/weekerp/test-assets/main/dog.jpg](https://raw.githubusercontent.com/weekerp/test-assets/main/dog.jpg)



#### 6. 다음과 같은 정보가 준비되어 있어야 합니다.

1. Target Url (Step #5)



#### 7. 위커프 접속 후 우측 상단 Add Source 클릭

1. 위커프 접속
2. Source 탭 클릭 후
3. Add Source 클릭

<figure><img src="../../.gitbook/assets/7 (2).png" alt=""><figcaption></figcaption></figure>



#### 8. Static via WEB Proxy 선택

<figure><img src="../../.gitbook/assets/8 (2).png" alt=""><figcaption></figcaption></figure>



#### 9. 연결 정보 입력

1. Target Url 입력
2. (필요시) Base Path 설정

<figure><img src="../../.gitbook/assets/9 (2).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
BasePath는 원본 요청의 루트 디렉터리를 설정합니다.
{% endhint %}

파일을 아래와 같이 보관하고 있는 경우 basePath는 / 혹은 /assets 으로 설정할 수 있습니다.

* /dog.jpg
* /assets/cat.png



**요청 예시**

* `cdn.weekerp.com/image/{alias}/dog.jpg`

**원본 요청**

* BasePath 설정 : https://static.example.com/**`assets`**/dog.jpg
* BasePath 미 설정 : https://static.example.com/dog.jpg

자세한 사안은 [basepath.md](../basepath.md "mention")을 참고해주세요.



#### 10. 소스 별칭(alias) 입력

1. 사용할 별칭 입력
2. 별칭을 생성

<figure><img src="../../.gitbook/assets/10.png" alt=""><figcaption></figcaption></figure>



#### 11. 생성된 데이터 소스 확인

<figure><img src="../../.gitbook/assets/11 (2).png" alt=""><figcaption></figcaption></figure>



#### 다음과 같이 사용하세요.

cdn.weekerp.com/<mark style="color:red;">`image`</mark>/`weekerp-assets`/dog.jpg

cdn.weekerp.com/<mark style="color:red;">`image`</mark>/`weekerp-assets`/dog.jpg?ai=Rotate the image to the right

cdn.weekerp.com/<mark style="color:red;">`video`</mark>/`weekerp-assets`/test-video.mp4



모든 설정을 완료했습니다.

일반적으로 모든 글로벌 환경에 연결을 전파하는데 까지는 5\~10 분 소요됩니다.
