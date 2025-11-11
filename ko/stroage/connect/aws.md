---
icon: aws
---

# AWS S3

위커프 CDN과 S3를 연결하는 과정에 대한 가이드에요.

IAM 계정을 발급하고 위커프에 등록하는 과정이에요.



#### 연결에 필요한 정보

위커프가 이미지에 접근할 수 있도록 하기 위해 다음 정보를 입력해야 합니다:

* Access Key ID
* Secret Access Key
* Bucket 이름



#### 자격 증명 얻기

AWS에 익숙하지 않다면, Weekerp 에서 이미지를 접근할 수 있도록&#x20;

**전용 IAM 사용자**를 새로 만드는 것을 추천합니다.



1. **Amazon IAM (Identity and Access Management)** 콘솔을 엽니다.
2. **Users ⟶ Create user** 로 이동합니다.
3. “Programmatic access(프로그래밍 방식 접근)” 옵션을 반드시 활성화합니다.
4. **Permissions(권한)** 탭에서 “Attach existing policies directly(기존 정책 직접 연결)”을 선택합니다.
5. “AmazonS3ReadOnlyAccess”라는 정책을 검색하고 선택합니다.
6. 절차를 완료하면 필요한 Access Key와 Secret Key를 받을 수 있습니다.
7. 이후 [**Weekerp 로그인**](https://weekerp.com/space/callback)
8. **Sources ⟶ Add Source ⟶ Amazon S3** 로 이동합니다.
9. 위에서 얻은 자격 증명 정보를 입력하면 됩니다.



#### 아래는 이미지로 나타낸 가이드 문서입니다.

#### 1. AWS 관리 콘솔, IAM 검색

<figure><img src="../../.gitbook/assets/1.png" alt=""><figcaption></figcaption></figure>



#### 2.  좌측  네비게이션바 User 탭 클릭 후 Create User 클릭

1. 좌측 네비게이션 바 User 탭 클릭
2. 우측 하단 Create user 클릭

<div data-full-width="true"><figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure></div>



#### 3. user name 입력 후 다음버튼 클릭

1. weekerp-cdn-reader 입력
2. 다음버튼 클릭

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>



#### 4. 정책연결

1. `AmazonS3ReadOnlyAccess` 검색
2. 검색 결과 클릭
3. 다음 버튼 클릭

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>



> 직접 정책을 연결하고 싶은경우 아래와 같은 권한이 필요합니다.

```json
{
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:ListBucket",
        "s3:GetBucketLocation"
      ],
      "Resource": [
        "arn:aws:s3:::my-bucket/*",
        "arn:aws:s3:::my-bucket"
      ]
    }
  ]
}
```





#### 5. 생성결과 확인

1. 생성결과 확인
2. View User 클릭

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>



#### 6. 유저 상세화면 중 Security Credentials 탭 클릭

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

ㅡ

#### 7. 스크롤 후 하단 Create access Key 클릭

1. 아래로 스크롤
2. Create Access Key 클릭릭

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>



#### 8. Description 추가 후 키 생성

1. Description tag value 입력
2. Create Access Key 클릭릭

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>



#### 9. 결과 확인 및 CSV 파일 다운로드

1. 키 확인
2. (권장) CSV 파일 다운로드드

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

&#x20;

#### 10. 위커프 접속 후 우측 상단 Add Source 클릭

1. [위커프 접속](https://weekerp.com/space/callback)
2. Source 탭 클릭 후
3. Add Source 클릭

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>



#### 11. 발급한 정보 입력

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
BasePath는 버킷에 루트 디렉터리를 설정합니다.
{% endhint %}



* /dog.jpg
* /assets/cat.png

위와 같이 파일을 보관하고 있는 경우

basePath는 /(root) 혹은 /assets 으로 설정할 수 있습니다.



#### 12. 고유의 식별자 입력

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
고유의 식별자를 통해 CDN을 이용할 수 있습니다.



https://cdn.weekerp.com/image/**`{unique-identifier}`**/dog.jpg?s=200x200
{% endhint %}



#### 13. 생성된 CDN 확인

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>



모든 설정을 완료했습니다.

일반적으로 모든 글로벌 환경에 연결을 전파하는데 까지는 5\~10 분 소요됩니다.





