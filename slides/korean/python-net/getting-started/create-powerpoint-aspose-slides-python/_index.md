---
"date": "2025-04-23"
"description": "Aspose.Slides for Python을 사용하여 PowerPoint 프레젠테이션을 자동화하는 방법을 알아보세요. 이 가이드에서는 설정, 슬라이드 생성, 도형 추가, 프레젠테이션 저장 방법을 손쉽게 설명합니다."
"title": "Python용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션 만들기 - 완벽한 가이드"
"url": "/ko/python-net/getting-started/create-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션을 만들고 저장하는 방법

## 소개

Python을 사용하여 PowerPoint 프레젠테이션 제작을 자동화하고 싶으신가요? 보고서, 슬라이드쇼 또는 기타 프레젠테이션 자료를 프로그래밍 방식으로 제작할 때 이 작업을 숙달하면 상당한 시간을 절약할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Python을 사용하여 새 PowerPoint 프레젠테이션을 만들고, 도형(선 등)을 추가하고, 손쉽게 저장하는 방법을 안내합니다.

**배울 내용:**
- Aspose.Slides를 사용하기 위한 환경을 설정하는 방법.
- Python으로 PowerPoint 프레젠테이션을 만드는 과정.
- 프로그래밍 방식으로 슬라이드에 모양 추가하기.
- 프레젠테이션을 간편하게 저장하세요.

코딩을 시작할 준비를 위해 먼저 필수 조건을 살펴보겠습니다!

## 필수 조건

시작하기에 앞서 다음 사항이 있는지 확인하세요.

1. **필수 라이브러리**: 다음이 필요합니다. `aspose.slides` 이 튜토리얼을 위한 라이브러리입니다.
2. **파이썬 버전**: Python 3.x를 권장합니다(Aspose.Slides와의 호환성을 보장하세요).
3. **환경 설정**:
   - 원하는 경우 Python을 설치하고 가상 환경을 설정하세요.

4. **지식 전제 조건**:
   - Python 프로그래밍에 대한 기본적인 이해.
   - Python에서 파일을 처리하는 데 익숙함.

설정이 준비되었으니 Python용 Aspose.Slides를 설치해 보겠습니다.

## Python용 Aspose.Slides 설정

### 설치

pip를 통해 Aspose.Slides를 쉽게 설치할 수 있습니다.

```bash
pip install aspose.slides
```

### 라이센스 취득 단계

Aspose.Slides는 무료 평가판, 임시 라이선스 및 구매 옵션을 제공합니다.
- **무료 체험**: 제한 없이 라이브러리의 기능을 테스트합니다.
- **임시 면허**: 로컬 컴퓨터에서 평가 목적으로 이것을 얻으세요.
- **구입**: 장기적인 상업적 사용을 위해.

방문하다 [Aspose 구매](https://purchase.aspose.com/buy) 이러한 옵션을 살펴보세요. 라이선스를 취득한 후 코드에서 설정할 수 있습니다.

```python
import aspose.slides as slides

# 라이선스 적용(.lic 파일이 있다고 가정)
license = slides.License()
license.set_license("path_to_your_licence_file.lic")
```

## 구현 가이드

이제 프레젠테이션을 만들고 저장하는 방법을 살펴보겠습니다.

### 새로운 프레젠테이션 만들기

이 튜토리얼의 핵심은 Python을 사용하여 처음부터 PowerPoint 프레젠테이션을 만드는 방법을 보여주는 것입니다.

#### 개요

우리는 초기화로 시작할 것입니다 `Presentation` 프레젠테이션 파일을 나타내는 객체입니다.

```python
import aspose.slides as slides

# 프레젠테이션 파일을 나타내는 Presentation 객체를 인스턴스화합니다.\with slides.Presentation()을 프레젠테이션으로 사용합니다.
    # 첫 번째 슬라이드를 가져옵니다(Aspose.Slides에서 추가된 기본 슬라이드)
slide = presentation.slides[0]

    # 슬라이드에 선 유형의 자동 도형 추가
slide.shapes.add_auto_shape(slides.ShapeType.LINE, 50, 150, 300, 0)

    # PPTX 형식으로 프레젠테이션을 저장합니다.
presentation.save("YOUR_OUTPUT_DIRECTORY/create_new_presentation_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}