---
description: 'Last updated: January 8, 2026'
icon: head-side-gear
---

# AI Query

### **AI Query**

AI Query lets you transform images using natural-language prompts.

When you include the `ai` query parameter, Weekerp interprets your request and applies the appropriate transformations.



#### **`ai`**

#### **D**escription

`ai` converts your natural-language prompt into executable transformation commands behind the scenes.



#### Format

```
?ai={prompt}
```



#### **E**xamples

dog.jpg?`ai=reduce the size by half`

dog.jpg?`ai=rotate the image to the right`

<table><thead><tr><th width="374.53564453125">Request</th><th>Interpreted as</th><th>Result (expected)</th></tr></thead><tbody><tr><td><code>dog.jpg?ai=reduce the size by half</code></td><td>Resize to 300×400</td><td><code>dog.jpg?w=300&#x26;h=400</code></td></tr><tr><td><code>dog.jpg?ai=rotate the image to the right</code></td><td>Rotate 90° clockwise</td><td><code>dog.jpg?rotate=90</code></td></tr></tbody></table>

{% hint style="info" %}
AI can make mistakes.
{% endhint %}



### How AI Query works

#### Request Consistency

AI는 일반적으로 호출 시점에 따라 결과가 달라질 수 있습니다. 하지만 위커프는 **동일한 AI 요청에 대해 동일한 변경 응답을 보장**하여 이미지가 임의로 변경되지 않습니다. 자세한 사안은 [Broken link](/broken/pages/Zin1DmsB2uASYZTYkr0x "mention") 페이지를 참고하세요.

AI outputs can vary depending on timing. However, **Weekerp guarantees deterministic results for the same AI prompt**, so your images won’t change unpredictably. See the **Request Consistency** page for details.

#### **캐싱**

캐싱 정책은 [Broken link](/broken/pages/ZVrOaHlrYeJ1A4y7jUkE "mention") 문서와 동일하게 적용됩니다. AI 응답을 바꾸고 싶다면 요청을 버전업하여 캐시 키를 분리할 수 있습니다.

* 예: `?ai=사이즈를 절반으로 줄여줘-v1`

#### **요금**

요금은 **AI 변환이 실제 수행될 때 1회** 발생합니다. 이후 동일 요청은 캐싱 처리되어 **추가 AI 실행 없이** 응답됩니다.\
단위당 비용 및 자세한 정책은 [Broken link](/broken/pages/rM6B1WheEGNhpcFAyLLq "mention") 페이지를  참고하세요.

#### **디버깅**

AI가 내부적으로 어떤 변환을 수행했는지 확인하고 싶다면 [Broken link](/broken/pages/68CFtVBsAMfEPtXlvjUd "mention") 페이지를 참고하세요.
