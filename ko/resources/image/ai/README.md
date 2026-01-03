---
description: '최종 수정일: 2026-01-03'
icon: head-side-gear
---

# AI 쿼리

### **AI 쿼리 (AI Query)**

이미지를 대화체로 조작할 수 있는 ai 쿼리입니다.

ai 쿼리를 사용하면 요청에 맞는 형태로 이미지를 가공하여 전달합니다.



#### **`ai`**

#### **설명**

AI 쿼리는 입력한 자연어 요청을 내부적으로 처리가능한 변환 명령으로 변환합니다.



#### 형식

```
?ai={prompt}
```



#### **예시**

dog.jpg?`ai=사이즈를 절반으로 줄여줘`

dog.jpg?`ai=이미지 오른쪽으로 회전`

<table><thead><tr><th width="283.28564453125">요청</th><th>추론 </th><th>결과 (예상)</th></tr></thead><tbody><tr><td><code>dog.jpg?ai=사이즈를 절반으로 줄여줘</code></td><td>300x400으로 리사이즈</td><td><code>dog.jpg?w=300&#x26;h=400</code></td></tr><tr><td><code>dog.jpg?ai=이미지 오른쪽으로 회전</code></td><td>이미지 우측으로90도 회전</td><td><code>dog.jpg?rotate=90</code></td></tr></tbody></table>

{% hint style="info" %}
AI는 실수를 할 수 있습니다.&#x20;
{% endhint %}



### AI 쿼리 동작

#### **요청의 일관성**

AI는 일반적으로 호출 시점에 따라 결과가 달라질 수 있습니다. 하지만 위커프는 **동일한 AI 요청에 대해 동일한 변경 응답을 보장**하여 이미지가 임의로 변경되지 않습니다. 자세한 사안은 [consistency.md](consistency.md "mention") 페이지를 참고하세요.

#### **캐싱**

캐싱 정책은 [cache.md](../../cache.md "mention") 문서와 동일하게 적용됩니다. AI 응답을 바꾸고 싶다면 요청을 버전업하여 캐시 키를 분리할 수 있습니다.

* 예: `?ai=사이즈를 절반으로 줄여줘-v1`

#### **요금**

요금은 **AI 변환이 실제 수행될 때 1회** 발생합니다. 이후 동일 요청은 캐싱 처리되어 **추가 AI 실행 없이** 응답됩니다.\
단위당 비용 및 자세한 정책은 [overview.md](../../../billing/overview.md "mention") 페이지를  참고하세요.

#### **디버깅**

AI가 내부적으로 어떤 변환을 수행했는지 확인하고 싶다면 [debugging.md](debugging.md "mention") 페이지를 참고하세요.





