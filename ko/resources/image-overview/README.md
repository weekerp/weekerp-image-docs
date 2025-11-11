---
icon: image-landscape
---

# 이미지 API

#### 이미지 처리 (Image Processing)

Weekerp Image API는 URL 파라미터만으로 다음과 같은 처리를 제공합니다.

* 리사이즈 (width / height / size)
* 포맷 변환 (JPEG, PNG, WebP, AVIF 등)
* 품질 조정 (quality)
* 리사이즈 전략 (fit)
* 포지션 지정 (position)

모든 처리는 요청 시점에 수행되며 **최초 1회 요청 시 변환된 결과가 CDN 엣지에 캐싱됩니다.**\
이후 동일한 요청은 캐시에서 바로 송신됩니다.\


캐싱된 이미지를동일한 파라미터로 재요청하는 경우, **이미 변환된 캐시 이미지가 즉시 반환되어 지연 없이 응답합니다.**

> 자세한 사항은  [cache.md](../cache.md "mention") 문서를 참고해주세요.

#### 기본 요청 형식

```
https://cdn.weekerp.com/image/{source}/{path/to/image}.{ext}?{options}
```

***

#### 예시

<table><thead><tr><th width="283.7142333984375">설명</th><th>요청 URL</th></tr></thead><tbody><tr><td>너비 800px, 비율 자동 조정</td><td><code>https://cdn.weekerp.com/image/demo/photo.jpg?w=800</code></td></tr><tr><td>400×400 정사각형으로 리사이즈</td><td><code>https://cdn.weekerp.com/image/demo/photo.jpg?w=400&#x26;h=400&#x26;fit=cover</code></td></tr><tr><td>70% 품질로 압축</td><td><code>https://cdn.weekerp.com/image/demo/photo.jpg?w=1200&#x26;q=70</code></td></tr></tbody></table>

#### 옵션

<table><thead><tr><th width="121.28558349609375">옵션</th><th width="131.4285888671875">별칭 (Alias)</th><th width="245.8572998046875">설명</th><th>예시</th></tr></thead><tbody><tr><td><strong>size</strong></td><td><code>size</code>, <code>s</code></td><td>width/height 일괄 지정</td><td><code>"800x600"</code></td></tr><tr><td><strong>width</strong></td><td><code>width</code>, <code>w</code></td><td>가로(px) 지정</td><td><code>number</code> → <code>800</code></td></tr><tr><td><strong>height</strong></td><td><code>height</code>, <code>h</code></td><td>세로(px) 지정</td><td><code>number</code> → <code>600</code></td></tr><tr><td><strong>format</strong></td><td><code>format</code>, <code>f</code></td><td>출력 포맷 지정</td><td><code>'webp'</code>, <code>'avif'</code>, <code>'jpg'</code>, <code>'png'</code>, <code>'gif'</code>, <code>'tiff'</code>, <code>'svg'</code></td></tr><tr><td><strong>quality</strong></td><td><code>quality</code>, <code>q</code></td><td>압축 품질(1~100)</td><td><code>number</code> → <code>80</code></td></tr><tr><td><strong>fit</strong></td><td><code>fit</code></td><td>리사이즈 방식</td><td><code>'cover'</code>, <code>'contain'</code>, <code>'fill'</code>, <code>'inside'</code>, <code>'outside'</code></td></tr><tr><td><strong>position</strong></td><td><code>position</code>, <code>p</code></td><td>잘림 기준 위치</td><td><code>'centre'</code>, <code>'top'</code>, <code>'bottom'</code>, <code>'left'</code>, <code>'right'</code></td></tr></tbody></table>

#### 참고

* 원본 이미지는 변경되지 않습니다.
* 변환된 이미지는 CDN 캐시에 저장되어 동일 요청 시 즉시 서빙됩니다.
* 기본 응답 포맷은 원본 확장자를 기준으로 하며, `f` 파라미터를 사용해 WebP, AVIF 등의 포맷으로 변환할 수 있습니다.

예: `https://cdn.weekerp.com/image/demo/photo.jpg?w=800&f=webp`

***

#### 권장사항

* 최대 응답 크기는 **1MB**를 권장합니다. (현재 베타 버전 제한, 즉각 처리요청 help@weekerp.com)
* 너무 큰 원본 이미지는 CDN 처리 과정에서 변환 실패가 발생할 수 있습니다.
* 필요 시 고용량 이미지는 `/file` 엔드포인트를 통해 직접 서빙하는 것을 권장합니다.





