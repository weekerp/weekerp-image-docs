---
description: '최종 수정일: 2026-01-05'
icon: arrows-rotate
---

# 흑백 변환

### 흑백 변환 (Grayscale)

이미지를 **흑백(그레이스케일)** 로 변환할 수 있습니다.

썸네일 톤 통일, 분위기 연출, 콘텐츠 강조(컬러 대비) 등에 유용합니다.



### `grayscale`

**설명**

이미지를 흑백(black & white)으로 변환합니다.



**형식**

```
?grayscale=true
```



**지원 값**

* `true | false`
* `true`일 때만 적용됩니다. (미지정/false면 적용 없음)



**예시**

| 요청                                      | 결과                        |
| --------------------------------------- | ------------------------- |
| `?grayscale=true`                       | 흑백으로 변환                   |
| `?width=600&format=webp&grayscale=true` | 600px 리사이즈 + WebP 변환 + 흑백 |

***

### 함께 사용하기



*   `format`, `width` 같은 변환 옵션과 같이 써도 자연스럽게 동작합니다.

    예: `?width=600&format=webp&grayscale=true`

{% hint style="info" %}
컬러 버전과 흑백 버전을 섞어 쓰면 “강조해야 하는 콘텐츠만 컬러”로 연출할 수 있습니다.
{% endhint %}



