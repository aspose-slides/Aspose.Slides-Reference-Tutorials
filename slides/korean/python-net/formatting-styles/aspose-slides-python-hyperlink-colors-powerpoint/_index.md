---
"date": "2025-04-23"
"description": "Aspose.Slides for Python을 사용하여 PowerPoint 프레젠테이션의 하이퍼링크 색상을 사용자 지정하는 방법을 알아보세요. 개인화된 링크 스타일로 슬라이드를 효율적으로 꾸며보세요."
"title": "Python용 Aspose.Slides를 사용하여 PowerPoint에서 하이퍼링크 색상을 설정하는 방법"
"url": "/ko/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint에서 하이퍼링크 색상을 설정하는 방법

## 소개

Aspose.Slides for Python을 사용하면 하이퍼링크 색상을 사용자 지정하여 PowerPoint 프레젠테이션의 시각적 매력을 간편하게 향상시킬 수 있습니다. 이 가이드에서는 Python을 사용하여 슬라이드에 특정 색상으로 하이퍼링크를 설정하는 방법을 안내합니다.

**배울 내용:**
- PowerPoint에서 텍스트 모양 내에 하이퍼링크 색상을 설정하는 방법.
- 시각적으로 매력적인 프레젠테이션을 만드는 데 필요한 단계입니다.
- 이러한 사용자 정의를 용이하게 하는 Python용 Aspose.Slides의 주요 기능입니다.

시작하기에 앞서 필요한 전제 조건을 살펴보겠습니다.

## 필수 조건

시작하기 전에 다음 사항이 환경 준비에 필요한지 확인하세요.
- **라이브러리 및 버전:** 설치하다 `aspose.slides` 라이브러리. Python이 컴퓨터에 설치되어 있는지 확인하세요.
- **환경 설정 요구 사항:** 이 튜토리얼에서는 Windows, Mac 또는 Linux에서 Python이 기본적으로 설정되어 있다고 가정합니다.
- **지식 전제 조건:** Python 프로그래밍에 익숙하면 도움이 됩니다.

## Python용 Aspose.Slides 설정

Python에서 Aspose.Slides를 사용하려면 pip를 통해 패키지를 설치하세요.

```bash
pip install aspose.slides
```

**라이센스 취득 단계:**
- **무료 체험:** 평가판을 다운로드하세요 [Aspose의 릴리스 페이지](https://releases.aspose.com/slides/python-net/).
- **임시 면허:** 임시 라이센스를 요청하세요 [구매 페이지](https://purchase.aspose.com/temporary-license/) 확장된 접근을 위해.
- **구입:** 제한 없이 기능을 완전히 잠금 해제하려면 라이선스 구매를 고려하세요. [Aspose 구매 페이지](https://purchase.aspose.com/buy).

**기본 초기화:**
설치하고 라이선스를 받은 후 스크립트에 Aspose.Slides를 가져옵니다.

```python
import aspose.slides as slides
```

## 구현 가이드

이 섹션에서는 PowerPoint 프레젠테이션 내에서 하이퍼링크 색상을 설정하는 방법을 안내합니다.

### 하이퍼링크 색상 설정 기능

#### 개요

Python용 Aspose.Slides를 사용하여 텍스트 모양에 포함된 하이퍼링크의 색상을 사용자 지정하세요. 이렇게 하면 가독성과 시각적 매력이 향상됩니다.

##### 1단계: 새 프레젠테이션 만들기

프레젠테이션 인스턴스를 만듭니다.

```python
with slides.Presentation() as presentation:
    # 여기에 코드를 입력하세요
```

##### 2단계: 텍스트가 있는 도형 추가

첫 번째 슬라이드에 사각형 모양을 추가하고 하이퍼링크가 포함된 텍스트를 삽입합니다.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### 3단계: 하이퍼링크 속성 설정

하이퍼링크를 지정하고 색상을 설정합니다. `hyperlink_click` 속성은 링크를 클릭했을 때 어디로 이동해야 하는지 지정합니다.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# 하이퍼링크의 색상 소스를 부분 형식으로 설정하고 채우기 유형과 색상을 정의합니다.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### 4단계: 프레젠테이션 저장

프레젠테이션을 지정된 디렉토리에 저장합니다.

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}