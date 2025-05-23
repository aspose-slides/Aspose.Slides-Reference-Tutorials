---
"date": "2025-04-23"
"description": "Aspose.Slides for Python을 사용하여 PowerPoint에서 사각형 도형을 자동으로 만들고 서식을 지정하는 방법을 알아보세요. 손쉽게 프레젠테이션 실력을 향상시켜 보세요."
"title": "Python용 Aspose.Slides를 사용하여 PowerPoint에서 사각형 모양 자동화"
"url": "/ko/python-net/shapes-text/automate-rectangle-shapes-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint에서 사각형 모양을 만들고 서식을 지정하는 방법
## 소개
PowerPoint 프레젠테이션에 사용자 지정 도형을 빠르게 추가해야 하는데 자동화 기능이 부족해서 어려움을 겪어 본 적이 있나요? 슬라이드마다 사각형을 직접 서식 지정하는 데 지치셨다면, 이 튜토리얼이 해결책이 될 것입니다. "Aspose.Slides for Python"을 활용하여 단 몇 줄의 코드만으로 사각형 도형을 추가하고 스타일을 지정하는 작업을 자동화해 보겠습니다. 이 가이드를 마치면 다음 기능을 완벽하게 익힐 수 있습니다.
- 프로그래밍 방식으로 사각형 모양 만들기
- 색상 및 선 스타일과 같은 서식 옵션 적용
- 프레젠테이션을 간편하게 저장하세요
슬라이드 제작 과정을 어떻게 바꿀 수 있는지 자세히 알아보겠습니다!
### 필수 조건
코딩을 시작하기 전에 다음 사항을 준비하세요.
- **파이썬** 귀하의 컴퓨터에 설치되어 있어야 합니다(버전 3.6 이상 권장)
- **Python용 Aspose.Slides** PowerPoint 프레젠테이션을 조작할 수 있는 라이브러리
- Python 프로그래밍 개념에 대한 기본적인 이해와 pip를 사용하여 패키지를 설치하는 것에 대한 익숙함
## Python용 Aspose.Slides 설정
### 설치
Aspose.Slides 패키지를 설치하려면 터미널이나 명령 프롬프트를 열고 다음을 실행하세요.
```bash
pip install aspose.slides
```
이 명령은 PyPI에서 Python용 Aspose.Slides의 최신 버전을 가져와서 설치합니다.
### 라이센스 취득
Aspose.Slides는 상용 제품이지만, 무료 평가판 라이선스를 사용하여 시작할 수 있습니다. 라이선스를 구매하는 방법은 다음과 같습니다.
1. **무료 체험:** 방문하다 [Aspose 무료 체험판](https://releases.aspose.com/slides/python-net/) 평가에 등록하세요.
2. **임시 면허:** 제한 없이 보다 광범위한 테스트를 원하시면 임시 라이센스를 요청하세요. [임시 면허 페이지](https://purchase.aspose.com/temporary-license/).
3. **구입:** 라이브로 전환할 준비가 되면 다음을 통해 라이센스를 구매하세요. [Aspose 구매 페이지](https://purchase.aspose.com/buy).
라이선스를 취득한 후에는 문서에 따라 프로젝트에 라이선스를 적용하세요.
### 기본 초기화
Python에서 Aspose.Slides를 초기화하는 방법은 다음과 같습니다.
```python
import aspose.slides as slides
\# 프레젠테이션 클래스 초기화
with slides.Presentation() as pres:
    print("Presentation is ready!")
```
이 스니펫은 새로운 프레젠테이션을 설정하고 조작할 준비가 되었는지 확인합니다.
## 구현 가이드
### 사각형 모양 만들기
#### 개요
이 섹션에서는 Python용 Aspose.Slides를 사용하여 PowerPoint 슬라이드에 사각형 모양을 추가하는 방법에 대해 중점적으로 살펴보겠습니다.
#### 모양을 만드는 단계
1. **프레젠테이션을 열거나 만드세요:**
   ```python
   import aspose.slides as slides
   
   with slides.Presentation() as pres:
       # 여기에 사각형을 추가합니다
   ```
2. **슬라이드에 접근하세요:**
   모양을 추가하려는 첫 번째 슬라이드를 검색합니다.
   ```python
   slide = pres.slides[0]
   ```
3. **사각형 모양 추가:**
   사용하세요 `add_auto_shape` 슬라이드에 사각형을 만드는 방법입니다.
   ```python
   shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 150, 50)
   ```
   - 매개변수: `ShapeType.RECTANGLE`, x-위치(50), y-위치(150), 너비(150), 높이(50).
### 사각형 서식 지정
#### 개요
다음으로, 채우기 색과 선 스타일을 포함하여 사각형 모양에 서식을 적용해 보겠습니다.
#### 서식 지정 단계
1. **채우기 색상:**
   사각형의 배경에 특정 색상으로 단색 채우기를 설정합니다.
   ```python
   shape.fill_format.fill_type = slides.FillType.SOLID
   shape.fill_format.solid_fill_color.color = drawing.Color.chocolate
   ```
2. **선 스타일:**
   사각형의 선을 사용자 지정하고 색상과 너비를 설정합니다.
   ```python
   shape.line_format.fill_format.fill_type = slides.FillType.SOLID
   shape.line_format.fill_format.solid_fill_color.color = drawing.Color.black
   shape.line_format.width = 5
   ```
3. **프레젠테이션 저장:**
   마지막으로 프레젠테이션을 파일로 저장합니다.
   ```python
   pres.save("YOUR_OUTPUT_DIRECTORY/shapes_formatted_rectangle_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}