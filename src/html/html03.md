---
layout: home
---
# HTML 03강
이미지 파일을 사용하여 홈페이지에 적용하는 방법에 대해서 알아 봅니다.

이미지테그

## 이미지의 선택
이미지의 포맷과 파일의 용량등을 같이 고려하여 선택하여야 합니다.

* 전송속도
이미지를 사용하면 전송속도에 민감합니다. 
이를 위해서 섬네일 이미지를 사용하기도 합니다.


* 이미지 타입
다양한 포맷의 이미지를 사용할 수 있습니다.
GIF, JPG, PNG 으로 파일을 사용할 수 있습니다.
작은 용량으로 우수한 화질을 유지할 수 있는 압축을 제공합니다.

- 투명배경
gif와 png는 투명 배경을 사용할 수 있습니다.


압축률
gif, png는 무손실 압축을 지원하며, jpg의 경우 약간의 화질을 손상하면서 높은 압축률을 제공합니다.
gif는 256 컬러를 지원, 에니메이션 지원 가능
png는 투루칼러 지원.


* GIF (graphic interchange format)
작은 크기의 이미지를 유지 할 수 있습니다.
투명이미지와 에니메이션을 지원합니다. 단점은 256 색만 표현이 가능합니다.

* JPG/JPEG (Joint Photographic Expert Group)
손실 압축
사진을 표현할때 적합합니다. 섬세한 색상과 명암을 표현할 수 있습니다.
색상수가 많은 이미지에 적절합니다.

* PNG
원본을 상태를 유지하면서 무손실 압축을 적용합니다.
interlaced 기능을 적용하여 이미지를 처리합니다. 저해상도에서 고해상도 변화되면서 화면에 출력됩니다.

## 이미지 삽입
html에 이미지를 삽입할때 `img` 테그를 사용합니다. img는 images의 약자 입니다.
img는 속성을 가지고 있습니다.

* src : 이미지 경로
* width : 가로폭
* height : 높이폭
* alt : 대체 텍스트
* title : 마우스 호버스 설명글 출력
* align : 위치정렬 (left/right/top/middle/bottom)
* border : 외각테두리


## 경로
정상적으로 이미지룰 출력하기 위해서는 올바른 경로를 선택하는 것이 중요합니다.
src 속성은 source의 약자 입니다. 

이미지는 `상대경로`와 `절대경로`로 사용합니다.

```html
<img src="파일명" />
```

## 이미지의 크기
이미지의 가로(width), 세로의 크기를 조정할 수 있습니다.
크기를 변경하는 속성은 실제 파일의 크기가 변경되는 것이 아니다. 단지, 화면에 보여지는 크기가 변경되는 것입니다.

실제 파일의 물리적 크기를 변경하기 위해서는 별도의 그래픽 도구를 사용해야 합니다.

보여지는 이미지의 크기를 수정할때는 `비율`도 같이 계산해야 합니다.

작은 이미지를 크게 보이도록 표시를 변경하는 경우에는 깨져 보일 수도 있습니다.


## Alt
Alt는 alternative의 약자 입니다.
시각 장애인의 경우 브라우저에서 이미지를 텍스트로 대체하여 출력하게 됩니다.
시각 장애인용 사이트를 제작할 때는 반드시 alt 속성을 이용하여 작성을 해야 한다.

alt 오류
이미지의 경로, 네트워크 오류등으로 정상적으로 이미지를 출력하지 못할 경우 x 상자와 함께 alt 텍스트도 같이 표시됩니다.
즉, 이미지의 읽기 오류가 발생되었을 경우 alt 텍스트도 같이 표시되는 문제가 있습니다.



## title
title은 도움말 텍스트입니다. 마우스 호버 상태일때 출력 합니다.
title 속성은 이지지 외에 a / span/ td 테그등에도 사용을 할 수 있습니다.


## 이미지 배치하기
align 속성을 이용하여 이미지의 위치를 배치할 수 있습니다.

* left
* right

* top
* middle
* bottom


## 테두리
이미지의 테두리 선을 설정합니다.
외각선을 제거할때에는 0 값을 지정하면 됩니다. 하지만, html로 설정된 테두리는 검생색으로 다른 색으로 변경할 수 없다.

테두리의 색상을 변경하기 위해서는 `스타일시트`를 이용하여야 한다.
스타일 시트는 다음과 같이 사용할 수 있습니다.

```css
style="border-style:스타일; border-color:색상; border-width:굵기"
```

외각성속성(border-style)
* dashed :
* dotted : 점선 으로 표시합니다.
* double : 이중선으로 표시합니다.
* solid : 실선으로 출력합니다.
* inset : 들어가 있는 모습
* outset : 튀어나온 모습


border-width
* thin
* medium
* thick
* 숫자값


border-color
* 색상명
* 색상값(hexa code)


## 속성 추가하기
* alt
* title


## FIGURE
이미지, 코드, 텍스트등을 하나로 묶어서 표현할 수 있습니다. 하나의 블럭으로 처리하여 요소들간의 관계를 명합하게 구조화 합니다.

```html
<figure>
    <figcaption>HTML5</figcaption>
    <img src="이미지" />
</figure>
```

figcaption 은 ir8 이하버전에서는 지원하지 않습니다. ie9, firefox,오페라, 크롬, 사파리등에서만 지원 됩니다.


## 대체이미지
사이트를 만들때 적절한 이미지가 준비가 되어있으면 좋겠지만, 
아직 이미지가 없는 경우 임시 이미지가 필요 합니다.

`placehold.it` 사이트는 대체할 수 있는 이미지를 제공합니다.

```html
<img src="http://placehold.it/200x200">
```

## 배경이미지
html 문서내에 배경이미지를 적용합니다.

* 테그로 사용하기
html5 이전의 버전의 경우 background 속성을 사용할 수 있습니다.

```html
<body background="배경이미지">
```

* css 적용
HTML5의 경우 css를 이용하여 배경이미지를 적용합니다.

```html
<body style="background-image:url(배경이미지);">
```

배경은 지정한 이미지를 패턴으로 사용하여 배치를 합니다.
패턴 반복을 처리합니다.
`background-repeat:repeat`

반복 순서 정의
* 가로 반복만 허용
`background-repeat:repeat-x`

* 세로 반복만 허용
`background-repeat:repeat-y`

* 반복금지
`background-repeat:no-repeat`


## 배경이미지 위치
배경의 위치를 지정할때에는 no-repeat을 먼저 설정합니다.

```
background-position:center center;
```

또는 

```
background-position:세로위치px 가로위치px;
```


## 배경이미지 고정
기본적으로 배경이미지는 스크롤 하게 되면 페이지의 위치와 함께 이동합니다.

`background-attachment: fixed`

지정한 위치의 배경이미지가 고정됩니다.



## 이미지경로

경로란 파일의 위치를 명확하게 지정하는 것을 말합니다.

### 상대경로
이미지가 제대로 보이지 않는 경우 정확한 파일의 경로가 설정되어 있지 않는 경우가 대부분 입니다.

상대경로란?
현재의 html 문서를 기반으로 경로를 지정하는 것입니다.

* `./파일명` 현재 문서와 동일한 위치
* `./폴더명/파일명` 현재 문서의 `폴더명` 하위 위치
* `../파일명` 현재 문서의 상위 폴더위치



절대경로란?
파일의 위치를 전체로 표시합니다.

* 절대위치 루트(/)
* 외부 url



