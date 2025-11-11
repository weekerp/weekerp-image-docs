---
icon: arrows-rotate-reverse
---

# 리사이징 방식 조절

### 리사이징 방식 조절 (Fit & Position)

이미지 크기를 지정할 때, `fit`과 `position` 옵션을 함께 사용하면 **비율 유지 방식**과 **자르기 기준점**을 세밀하게 제어할 수 있습니다.



#### `fit`

**설명**\
요청한 `width`·`height`에 맞춰 이미지를 어떻게 배치할지 정의합니다.\
즉, **“이미지를 영역에 어떻게 맞출지”** 결정하는 옵션입니다.

**형식**

```
?fit={type}
```

**지원 값**

<table><thead><tr><th width="123.28564453125">값</th><th width="373.142822265625">설명</th><th>특징</th></tr></thead><tbody><tr><td><code>cover</code></td><td>영역을 가득 채우되 넘치는 부분은 잘라냄</td><td>썸네일·배너용</td></tr><tr><td><code>contain</code></td><td>이미지 전체가 보이도록 축소 (여백 허용)</td><td>원본 비율 유지</td></tr><tr><td><code>fill</code></td><td>비율 무시하고 영역을 정확히 채움</td><td>왜곡 가능</td></tr><tr><td><code>inside</code></td><td>요청 크기 안쪽에서 최대 크기로 조정</td><td>확대 제한</td></tr><tr><td><code>outside</code></td><td>요청 크기 바깥까지 포함하도록 확장</td><td>축소 제한</td></tr></tbody></table>

#### 예시

| 요청                         | 결과               |
| -------------------------- | ---------------- |
| `?w=400&h=400&fit=cover`   | 정사각형으로 잘라냄       |
| `?w=400&h=400&fit=contain` | 여백 포함, 이미지 전체 표시 |
| `?w=800&h=400&fit=fill`    | 비율 무시하고 강제 맞춤    |



#### `position`

**설명**\
`fit=cover`와 같이 이미지 일부가 잘릴 때,\
**어느 부분을 기준으로 유지할지** 결정합니다.

**형식**

```
?position={direction}
```

**지원 값**

| 값        | 설명          |
| -------- | ----------- |
| `centre` | 중앙 기준 (기본값) |
| `top`    | 상단 기준       |
| `bottom` | 하단 기준       |
| `left`   | 좌측 기준       |
| `right`  | 우측 기준       |

**예시**

| 요청                                       | 결과          |
| ---------------------------------------- | ----------- |
| `?w=400&h=400&fit=cover&position=top`    | 위쪽 기준으로 자름  |
| `?w=400&h=400&fit=cover&position=bottom` | 아래쪽 기준으로 자름 |



#### 함께 사용하기

`fit`과 `position`은 함께 사용할 때 가장 유용합니다.

```txt
?w=400&h=400&fit=cover&position=top
```

* `fit=cover`: 정사각형 영역을 꽉 채움
* `position=top`: 상단 기준으로 잘림

***

> 💡 **Tip:**
>
> * `fit`을 지정하지 않으면 기본값(일반적으로 `cover`)이 적용됩니다.
> * `position`은 `fit=cover`일 때만 효과가 있습니다.

