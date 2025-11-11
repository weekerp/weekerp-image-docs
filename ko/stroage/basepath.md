# BasePath 설정

`BasePath`는 버킷 내에서 **리소스의 루트 경로(root directory)** 를 지정하는 옵션입니다.\
즉, CDN이 파일을 불러올 때 기준이 되는 **최상위 디렉터리 경로**를 정의합니다.

#### 예시

다음과 같이 버킷에 파일이 저장되어 있다고 가정합니다.

```
/dog.jpg
/assets/cat.png
```



이 경우, BasePath는 아래 두 가지 방식으로 설정할 수 있습니다.

<table><thead><tr><th width="131.71429443359375">설정 값</th><th>설명</th></tr></thead><tbody><tr><td><code>/</code></td><td><p>버킷의 루트 디렉터리를 기준으로 모든 파일에 접근합니다.</p><p><br>위커프사용  예: <code>https://cdn.weekerp.com/image/mysource/</code><strong><code>dog.jpg</code></strong></p></td></tr><tr><td><code>/assets</code></td><td><p><code>assets</code> 폴더를 루트로 지정합니다.</p><p><br>위커프사용  예: <code>https://cdn.weekerp.com/image/mysource/</code><strong><code>dog.jpg</code></strong></p></td></tr><tr><td><code>/</code></td><td><code>assets</code> 폴더를 루트로 지정하지 않은 경우<br><br>위커프사용  예: <code>https://cdn.weekerp.com/image/mysource/assets/</code><strong><code>cat.jpg</code></strong></td></tr></tbody></table>

***



#### 참고

* BasePath는 각 Source(버킷)마다 개별로 지정할 수 있습니다.
*   설정된 BasePath는 CDN 요청 시 자동으로 경로 앞에 추가됩니다.

    ```
    https://cdn.weekerp.com/image/{source}/{basePath}/cat.png
    ```
* 루트(`/`)로 설정할 경우, 모든 경로를 그대로 불러옵니다.



