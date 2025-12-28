---
description: 전체 설정까지 10분
icon: google
---

# GCP GCS

위커프 API를 이용하기 위해 GCP 스토리지에 연결하는 방법을 안내합니다.

자격 증명을 발급하고 발급받은 자격 증명을 위커프에 등록하는 전체 과정을 포함합니다.



#### 연결에 필요한 정보

위커프가 이미지에 접근할 수 있도록 하기 위해 다음 정보를 입력해야 합니다:

* GCP Crendential Json file
  * Client email
  * private key
* Bucket name



#### 자격증명 얻기 (GCP)

GCP에 익숙하지 않다면, Weekerp에서 버킷의 이미지를 읽을 수 있도록

**읽기 전용 서비스 계정(Service Account)** 을 새로 만드는 것을 추천합니다.

1. GCP 관리 콘솔 접속 → **Service Accounts → Create service account**
2. Service account 이름 입력 (예: `weekerp-cdn-reader`) → **Create and Continue**
3. 권한(Role) 설정 → **Storage Object Viewer** 검색/선택 → **Done**
4. 생성한 Service account 선택 → **Keys 탭 → Add Key → Create new key → JSON → Create**
5. 다운로드된 **JSON 키 파일** 저장 (외부 유출 금지)
6. GCP 관리 콘솔 → **Buckets**에서 연결할 **Bucket name** 확인
7. Weekerp 접속 → **Sources → Add Source → Google Cloud Storage (GCS)**
8. Weekerp에 **Bucket name 입력 + JSON 키 파일 업로드** → **Next**
9. **Alias 입력 후 생성**하면 소스가 추가됩니다



#### 아래는 이미지로 나타낸 가이드 문서입니다.



#### 1. GCP 관리 콘솔에서 “Service Accounts” 검색

<figure><img src="../../.gitbook/assets/1 (3).png" alt=""><figcaption></figcaption></figure>



#### 2. “Create service account” 클릭

<figure><img src="../../.gitbook/assets/2 (3).png" alt=""><figcaption></figcaption></figure>



#### 3. Service account 생성

1. “weekerp-cdn-reader” 입력 (변경 가능)
2. Create and Continue 버튼 클릭

<figure><img src="../../.gitbook/assets/3 (2).png" alt=""><figcaption></figcaption></figure>



#### 4. 생성한 account에 Permissions 부여, Role 드롭다운 클릭

<figure><img src="../../.gitbook/assets/4 (2).png" alt=""><figcaption></figcaption></figure>



#### 5. Storage Object Viewer 검색 후 권한 부여

1. Storage Object Viewer 검색
2. 최상단 Storage Object Viewer 클릭

<figure><img src="../../.gitbook/assets/5 (1).png" alt=""><figcaption></figcaption></figure>



#### 6. account에 Permissions 부여 완료

1. Done 버튼 클릭

<figure><img src="../../.gitbook/assets/6 (4).png" alt=""><figcaption></figcaption></figure>



#### 7. 생성한 account 확인 및 상세 정보 확인

1. 생성한 account 확인
2. 생성한 account 명칭 클릭

<figure><img src="../../.gitbook/assets/7 (1).png" alt=""><figcaption></figcaption></figure>



#### 8. 키(JSON) 생성

1. 상단 Key 탭 클릭
2. 하위 Add Key 버튼 클릭
3. 드롭다운 메뉴중 “Create new key” 클릭

<figure><img src="../../.gitbook/assets/8 (1).png" alt=""><figcaption></figcaption></figure>



#### 9. 키 타입 설정

1. JSON 클릭
2. 우측 하단 Create 버튼 클릭

<figure><img src="../../.gitbook/assets/9 (1).png" alt=""><figcaption></figcaption></figure>



#### 10. 다운로드된 키 파일(.json) 확인

json 파일 다운로드 이후 다음과 같은 키가 발급됩니다. (외부 유출 금지)

```json
{
  "type": "service_account",
  "project_id": "weekerp-cdn-test",
  "private_key_id": "4e393a5fe31bfa11fecb5eae0d47d4603fe681d5",
  "private_key": "-----BEGIN PRIVATE KEY-----\\nMIIEvgIBADANBgkqhkiG9w0BAQEFAASCBKgwggSkAgEAAoIBAQCWuvmrL083KrOK\\nJW/IH/GX3rBmOjfWneJb4jFCQadoQFChtTW9TUJCwtFpSGOSJ6wmIJSNG2QJWuIn\\nnTKeAKnAGQsFA2ezlSkfjUZ2mOx+6CZidZhIQIsTvVqjp2LJf+SM+oeRFwVEIgiJ\\n4bzjtxra1HAeAjR9AeSxQBvJDc2SXBXpUznDS8nD3Z/52M4A66+WAAOwqCWPey4l\\n17ahHE6vN9BBAi5puTBa1Q/YJt7O8ELH6KJA4MbYqenvJmTIQImQeDb+gcGzb1Ka\\n3hVyn4uU4G89mTMMtWPAINu9jU9Q2sX2xrFuzMDDRlpmABbVtH29sZzn2TpkvJdp\\nT/J+h6z3AgMBAAECggEAFc7TlKrxoR+yfkhQVfoZMEnt57yAm7KYL4cYbWemWvUD\\nNYJMVik5bwNU3RC2J01KIPIRzCCsZpYZpnWd/zJFXR/CcmU9ucPZAVGlYj9Z6Dqa\\nYyB0ee+sr5xz4r2zE0hHvwX4W0ujXWo3JgvdEm1Jm2OlHRJgmb2OYv7NhldS6Nvk\\n+4z5jrH+SYNyIRqOSh1y+tWNIjPLzRqt6lH1vP6f8lcTp7ESDYeN15JvB6QuStU1\\nKUDSMZpiq7G071nQrFNrXEKZhK9PWa1/7bnGLe+oIL3rjQUqdm7a9mFmRcdRAmVZ\\nQA2JWjleCMKRBiq1cEZTdCMgpm92lgWGBOLcIFEmEQKBgQDPJ9Twl7plkXuLrtvo\\nyFE4ycUfnGrB7Uki0ozcdkfOdJVr9v6DJvqTeWn1P8zgtO/MlHj0uuu4/4QiVd1d\\n2ldzwlN+AibXZdo6ZOqdDthSd7oWAaRB+Lp/WuL+yQSZ0zvr0B1AmNet+bW2Raer\\nqof86/9FAoUJHRl/1euBQ/XLqwKBgQC6RT9Lm+TYJEwO4N18SWdMnlF2au8X58ji\\nbDA653xoAybYvXC/+rkfQMUL9bvWR0PL0+p7Zw4nw8Eqi/tTHYiMA3CKWgSE3rQZ\\neT1Ja47nBxBPU83cn74pbKElYy9gZi0XBZgtggbHBqxmxBJXUz76PviSfpHGiqT7\\nG7YO+fR35QKBgQC7H//6VRTLKt+vDgUYAdtcsOaf52uIQhAOpKMZgr7af/V50WOW\\nlV9EWCieoUMwuEDlTDj22OKV+johye5tGQ5mQuOor8jmSdsXZJGJzh8aX4x41ILM\\nFSJiaHckL/E4Atfd6+CAuZAaV7cNL16Gc0Tj80pjzCLgWKjwEQzrd7hQgQKBgC8n\\nBGTRa9bDKXXCuo6RzlJ46Uo+u5OjmximJndizf1OfvDy063lfCNLNBZY+Fm/5Iue\\nc4cViWHLjgSFNvPNUBmRbVW4f9hav+CK7la9oYkeIqTSJBSrY2n9E7XxK7cNZnCj\\ne+hZN/n92HqTO8lbS1/xvN7op2JJCoZ+d1HHOHl5AoGBAMMinfkr73SU2kuOIzwI\\nBXtpY6s/O4CaCoFHM5sTkXzYs8++rtwMbMGfkRSxKTwW3Qi5Nl1+GIUP+Ke8y/kn\\n7XYb2WDTmJpKOyRcp8nwVtO2il6iPqZvyjI/5yj+MeZxuKPwE8v/PqThlUSFK6/x\\nKquzm/b2ZXFh52bmn1Po6tsb\\n-----END PRIVATE KEY-----\\n",
  "client_email": "weekerp-cdn-reader@weekerp-cdn-test.iam.gserviceaccount.com",
  "client_id": "109823219863817160893",
  "auth_uri": "<https://accounts.google.com/o/oauth2/auth>",
  "token_uri": "<https://oauth2.googleapis.com/token>",
  "auth_provider_x509_cert_url": "<https://www.googleapis.com/oauth2/v1/certs>",
  "client_x509_cert_url": "<https://www.googleapis.com/robot/v1/metadata/x509/weekerp-cdn-reader%40weekerp-cdn-test.iam.gserviceaccount.com>",
  "universe_domain": "googleapis.com"
}

```



#### 11. GCP 관리 콘솔에서 Buckets 검색 (버킷 이름 확인)

<figure><img src="../../.gitbook/assets/11 (1).png" alt=""><figcaption></figcaption></figure>



#### 12. 버킷 이름(Bucket name) 확인

1. weekerp-test-2 확인 (예시)

<figure><img src="../../.gitbook/assets/12 (1).png" alt=""><figcaption></figcaption></figure>



#### 13. 다음과 같은 정보가 준비되어 있어야 합니다.

1. Crendential Json file (Step #10)
2. Bucket name : (Step #12)



#### 14. 위커프 접속 후 우측 상단 Add Source 클릭

1. 위커프 접속
2. Source 탭 클릭 후
3. Add Source 클릭

<figure><img src="../../.gitbook/assets/14 (1).png" alt=""><figcaption></figcaption></figure>

![image.png](attachment:723b0ba7-b34a-4b4c-af8a-9d37b718dbb8:image.png)

#### 15. Google Cloud Storage 선택

<figure><img src="../../.gitbook/assets/15 (1).png" alt=""><figcaption></figcaption></figure>

![image.png](attachment:03ebaadb-3563-422a-9173-24afb19913e8:image.png)

#### 16. 자격증명 정보 입력

1. Bucket name 입력
2. JSON 파일 업로드

<figure><img src="../../.gitbook/assets/16 (1).png" alt=""><figcaption></figcaption></figure>

![Frame 7.png](attachment:e75720cd-cc2a-420f-a29c-a798a84aed8f:Frame_7.png)





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



#### 17. 입력 정보 확인

1. 입력 정보 확인
2. Next 버튼 클릭

<figure><img src="../../.gitbook/assets/17 (1).png" alt=""><figcaption></figcaption></figure>

![image.png](attachment:dd65b12a-9086-4e91-9f04-92429af41bf2:image.png)

#### 18. 소스 별칭(alias) 입력

1. 사용할 별칭 입력
2. 별칭을 생성

<figure><img src="../../.gitbook/assets/18 (2).png" alt=""><figcaption></figcaption></figure>

![image.png](attachment:b8c17ea6-cade-447f-af48-28095e9b2359:image.png)

#### 19. 생성된 데이터 소스 확인

<figure><img src="../../.gitbook/assets/19 (1).png" alt=""><figcaption></figcaption></figure>

![image.png](attachment:b512cd7d-3a62-43ac-bbe6-c99394488c84:image.png)



#### 다음과 같이 사용하세요.

cdn.weekerp.com/<mark style="color:red;">`image`</mark>/`weekerp-assets`/dog.jpg

cdn.weekerp.com/<mark style="color:red;">`image`</mark>/`weekerp-assets`/dog.jpg?ai=Rotate the image to the right

cdn.weekerp.com/<mark style="color:red;">`video`</mark>/`weekerp-assets`/test-video.mp4



모든 설정을 완료했습니다.

일반적으로 모든 글로벌 환경에 연결을 전파하는데 까지는 5\~10 분 소요됩니다.

