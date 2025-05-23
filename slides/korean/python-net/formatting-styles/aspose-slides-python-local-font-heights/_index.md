---
"date": "2025-04-24"
"description": "Python용 Aspose.Slides를 사용하여 로컬 글꼴 높이를 설정하여 텍스트를 사용자 정의하고 프레젠테이션의 시각적 매력을 향상시키는 방법을 알아보세요."
"title": "Python용 Aspose.Slides를 사용하여 프레젠테이션에서 로컬 글꼴 높이 설정"
"url": "/ko/python-net/formatting-styles/aspose-slides-python-local-font-heights/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 프레젠테이션에서 로컬 글꼴 높이 설정

오늘날 프레젠테이션 중심의 세상에서 슬라이드 맞춤 제작은 필수적입니다. 투자자를 대상으로 프레젠테이션을 하든, 컨퍼런스에서 프레젠테이션을 하든, 프레젠테이션 방식은 무엇을 발표하느냐만큼이나 중요할 수 있습니다. 바로 여기서 **Python용 Aspose.Slides** 시각적으로 멋진 프레젠테이션을 쉽게 만들 수 있는 도구를 제공합니다. 이 튜토리얼에서는 Aspose.Slides를 사용하여 텍스트 프레임 내에서 로컬 글꼴 높이를 설정하는 방법을 안내합니다. 이 기능은 핵심 메시지를 돋보이게 해줍니다.

## 당신이 배울 것
- 단일 텍스트 프레임 내에서 다양한 글꼴 높이를 설정하는 방법.
- Aspose.Slides에서 텍스트 프레임을 만들고 조작하는 단계입니다.
- Python과 Aspose.Slides를 사용하여 프레젠테이션을 최적화하는 모범 사례.

프레젠테이션 맞춤화를 시작하기 전에 필수 조건을 알아보겠습니다!

### 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- **Python용 Aspose.Slides**: PowerPoint 슬라이드를 조작하는 데 필요한 기본 라이브러리입니다. 설치 및 설정에 대해서는 곧 다루겠습니다.
- **파이썬 환경**: Python 프로그래밍에 대한 기본적인 이해가 필수적입니다.
- **개발 설정**: 환경(예: IDE 또는 텍스트 편집기)이 Python을 지원하는지 확인하세요.

### Python용 Aspose.Slides 설정
#### 설치
시작하려면 Aspose.Slides 라이브러리를 설치해야 합니다. pip를 사용하여 쉽게 설치할 수 있습니다.
```bash
pip install aspose.slides
```
이 명령을 사용하면 시스템에 최신 버전의 Aspose.Slides를 다운로드하고 설치할 수 있습니다.

#### 라이센스 취득
모든 기능을 사용하려면 라이센스를 취득하는 것이 좋습니다.
- **무료 체험**: 무료 체험판을 통해 모든 기능을 탐색해 보세요.
- **임시 면허**: 평가에 더 많은 시간이 필요하다면 임시 면허를 신청하세요.
- **구입**: 장기간 사용하려면 라이선스 구매를 고려하세요.

라이브러리를 설치하고 라이선스를 취득한 후 스크립트에서 Aspose.Slides를 초기화합니다.
```python
import aspose.slides as slides

# 해당되는 경우 여기에 라이센스 코드로 초기화하세요.
```
이제 Python용 Aspose.Slides를 설정하는 방법을 다루었으니, 핵심 기능을 구현하는 방법으로 넘어가겠습니다.

## 구현 가이드
### 텍스트 프레임에서 로컬 글꼴 높이 설정
이 기능을 사용하면 단일 프레임 내의 텍스트 일부를 사용자 지정할 수 있어 프레젠테이션의 특정 부분을 강조하는 데 적합합니다.
#### 개요
로컬에서 글꼴 높이를 수정하면 전체 레이아웃을 변경하지 않고도 핵심 문구나 섹션에 주의를 끌 수 있습니다. 이 튜토리얼에서는 단락 내 다양한 부분에 서로 다른 높이를 설정하는 방법을 다룹니다.
#### 구현 단계
##### 1단계: 프레젠테이션 초기화 및 모양 추가
새 프레젠테이션을 만들고 텍스트가 들어갈 모양을 추가하여 시작하세요.
```python
def set_local_font_height_values():
    with slides.Presentation() as pres:
        # 첫 번째 슬라이드에 사각형 모양 추가
        new_shape = pres.slides[0].shapes.add_auto_shape(
            slides.ShapeType.RECTANGLE, 100, 100, 400, 75, False)
```
여기서는 지정된 좌표와 치수를 갖는 직사각형 모양을 추가합니다.
##### 2단계: 텍스트 프레임 만들기
다음으로, 새로 추가된 모양 내에 빈 텍스트 프레임을 만듭니다.
```python
        # 빈 텍스트 프레임 만들기
        new_shape.add_text_frame("")
        new_shape.text_frame.paragraphs[0].portions.clear()
```
기존 부분을 지우면 사용자 정의 텍스트를 추가할 수 있는 깨끗한 상태가 유지됩니다.
##### 3단계: 텍스트 부분 추가 및 사용자 지정
문단에 두 개의 서로 다른 텍스트 부분을 추가한 다음, 해당 부분의 글꼴 높이를 사용자 지정하세요.
```python
        # 높이가 다른 텍스트 부분 추가
        portion0 = slides.Portion("Sample text with first portion")
        portion1 = slides.Portion(" and second portion.")
        
        new_shape.text_frame.paragraphs[0].portions.add(portion0)
        new_shape.text_frame.paragraphs[0].portions.add(portion1)

        # 글꼴 높이 설정
        pres.default_text_style.get_level(0).default_portion_format.font_height = 24
        new_shape.text_frame.paragraphs[0].paragraph_format.default_portion_format.font_height = 40
        
        new_shape.text_frame.paragraphs[0].portions[0].portion_format.font_height = 55
        new_shape.text_frame.paragraphs[0].portions[1].portion_format.font_height = 18
```
그만큼 `font_height` 매개변수는 각 부분의 시각적 두드러짐을 설정하는 데 중요합니다.
##### 4단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 저장합니다.
```python
        # 지정된 디렉토리에 저장
        pres.save("YOUR_OUTPUT_DIRECTORY/text_SetLocalFontHeightValues_out.pptx", slides.export.SaveFormat.PPTX)
```
### 실제 응용 프로그램
1. **핵심 포인트 강조**: 다양한 글꼴 높이를 사용하여 비즈니스 제안서의 중요한 요소를 강조합니다.
2. **시각적 계층 구조 만들기**슬라이드 텍스트 내에서 제목과 부제목을 구별하여 가독성을 높입니다.
3. **맞춤형 학습 자료**: 학생 참여를 높이기 위해 교육 콘텐츠를 맞춤화합니다.

### 성능 고려 사항
- **텍스트 관리 최적화**: 성능을 향상시키려면 문단당 부분의 수를 최소화하세요.
- **리소스 사용**: 특히 대용량 프레젠테이션을 다룰 때 메모리 사용량을 모니터링합니다.
- **효율적인 메모리 관리**: 사용 후 프레젠테이션을 즉시 닫아 리소스를 확보하세요.

## 결론
축하합니다! Aspose.Slides for Python을 사용하여 로컬 글꼴 높이를 설정하는 방법을 완벽하게 익히셨습니다. 이 기술을 활용하면 청중의 요구에 맞춰 더욱 역동적이고 매력적인 프레젠테이션을 제작할 수 있습니다.

### 다음 단계
- 색상, 스타일 등 다른 텍스트 사용자 지정을 실험해 보세요.
- Aspose.Slides를 다른 데이터 소스나 애플리케이션과 통합하는 방법을 살펴보세요.

시도해 볼 준비가 되셨나요? 다음 프레젠테이션 프로젝트에 이 기술들을 구현해 보세요!

## FAQ 섹션
**질문 1: Python용 Aspose.Slides를 사용하여 높이와 함께 글꼴 색상을 변경할 수 있나요?**
A1: 네, 글꼴 색상과 높이를 모두 수정할 수 있습니다. `portion_format` 속성.

**질문 2: Aspose.Slides에 대한 임시 라이선스를 신청하려면 어떻게 해야 하나요?**
A2: 지침에 따라 임시 면허를 신청하세요. [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/).

**질문 3: 글꼴 높이를 설정할 때 흔히 발생하는 문제는 무엇인가요?**
A3: 유효한 문단 내에 부분이 있는지 확인하고 올바른 좌표 값을 확인하세요.

**질문 4: Aspose.Slides는 모든 Python 버전과 호환됩니까?**
A4: 호환성을 위해 Python 3.6 이상 버전을 사용하는 것이 좋습니다.

**질문 5: 여러 슬라이드에서 텍스트 프레임을 자동으로 생성하려면 어떻게 해야 하나요?**
A5: 루프를 사용하여 슬라이드 컬렉션을 반복하고 텍스트 프레임 사용자 지정 코드를 적용합니다.

## 자원
- **선적 서류 비치**: 자세한 API 참조는 다음을 방문하세요. [Aspose 문서](https://reference.aspose.com/slides/python-net/).
- **다운로드**: 최신 릴리스를 여기에서 받으세요 [Aspose 다운로드](https://releases.aspose.com/slides/python-net/).
- **구입**: 라이센스를 구매하려면 다음으로 이동하세요. [Aspose 구매 페이지](https://purchase.aspose.com/buy).
- **무료 체험**: 무료 체험판으로 시작하세요 [Aspose 무료 체험판](https://releases.aspose.com/slides/python-net/).
- **지원하다**: 질문이나 지원이 필요하면 다음을 방문하세요. [Aspose 포럼](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}