---
"date": "2025-04-24"
"description": "Aspose.Slides for Python을 사용하여 도형에 그림자 효과를 추가하여 PowerPoint 프레젠테이션을 더욱 돋보이게 하는 방법을 알아보세요. 단계별 가이드를 따라 슬라이드를 더욱 돋보이게 만들어 보세요."
"title": "Aspose.Slides Python을 사용하여 PowerPoint에서 도형에 그림자 효과 추가"
"url": "/ko/python-net/shapes-text/aspose-slides-python-shadow-effects-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Python을 사용하여 PowerPoint에서 도형에 그림자 효과 추가
## 소개
Python과 강력한 Aspose.Slides 라이브러리를 사용하여 도형에 시각적으로 매력적인 그림자 효과를 추가하여 PowerPoint 프레젠테이션을 더욱 돋보이게 하세요. 이 튜토리얼에서는 프로그래밍 방식으로 동적 그림자를 적용하여 심미성과 참여도를 모두 향상시키는 방법을 안내합니다.

**배울 내용:**
- Python용 Aspose.Slides 설정
- Python을 사용하여 새로운 PowerPoint 프레젠테이션 만들기
- Aspose.Slides를 사용하여 모양 추가 및 그림자 효과 적용
- 프레젠테이션 조작 시 성능 최적화

시작하기에 앞서, 이 튜토리얼을 따라하는 데 필요한 모든 것이 준비되어 있는지 확인하세요.

## 필수 조건
이 튜토리얼을 성공적으로 완료하려면 다음 사항이 있는지 확인하세요.
- **Python용 Aspose.Slides**: 라이브러리를 설치하려면 다음을 확인하세요. [Aspose 공식 출시 페이지](https://releases.aspose.com/slides/python-net/).
- **파이썬 환경**: Python(버전 3.x 권장)이 제대로 설치되어 있어야 합니다.
- **기본 지식**: 기본적인 Python 프로그래밍과 외부 라이브러리 처리에 익숙하면 도움이 됩니다.

## Python용 Aspose.Slides 설정
프로젝트에서 Aspose.Slides를 사용하려면 다음 단계를 따르세요.

### 설치
pip를 통해 라이브러리를 설치하려면 다음 명령을 실행하세요.
```bash
pip install aspose.slides
```

### 라이센스 취득
임시 면허 취득을 고려하세요 [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/) 평가 목적 외에도 광범위하게 사용할 수 있습니다. 체험 기간 동안 모든 기능을 사용할 수 있습니다.

### 기본 초기화 및 설정
라이브러리를 Python 스크립트로 가져옵니다.
```python
import aspose.slides as slides

# slides.Presentation()을 pres로 사용하여 프레젠테이션 객체를 초기화합니다.
    # 프레젠테이션을 조작하는 코드는 여기에 있습니다.
```

## 구현 가이드
이 섹션에서는 Aspose.Slides를 사용하여 PowerPoint에서 도형에 그림자 효과를 추가하는 방법을 안내합니다.

### 모양에 그림자 효과 추가
그림자를 적용하여 슬라이드의 시각적 매력을 높여 보세요. 방법은 다음과 같습니다.

#### 1단계: 새 프레젠테이션 만들기
슬라이드와 도형 작업을 위한 새로운 프레젠테이션 객체를 초기화합니다.
```python
with slides.Presentation() as pres:
    # 프레젠테이션 작업
```

#### 2단계: 첫 번째 슬라이드에 액세스
일반적으로 인덱스 0에서 첫 번째 슬라이드에 접근합니다.
```python
slide = pres.slides[0]
```

#### 3단계: 사각형 유형의 자동 모양 추가
좌표와 크기 매개변수를 사용하여 슬라이드에 사각형 모양을 추가합니다.
```python
auto_shape = slide.shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 150, 75, 150, 50
)
```

#### 4단계: 사각형 모양에 텍스트 프레임 추가
텍스트 상자로 기능하려면 모양에 텍스트 프레임을 삽입하세요.
```python
auto_shape.add_text_frame("Aspose TextBox")
```

#### 5단계: 그림자 표시에 대한 채우기 비활성화
그림자가 방해 없이 보이도록 채우기가 적용되지 않았는지 확인하세요.
```python
auto_shape.fill_format.fill_type = slides.FillType.NO_FILL
```

#### 6단계: 바깥쪽 그림자 효과 활성화 및 구성
그림자 효과를 활성화하고 속성을 구성합니다.
```python
# 그림자 효과 활성화
auto_shape.effect_format.enable_outer_shadow_effect()

# 그림자 속성 구성
shadow = auto_shape.effect_format.outer_shadow_effect
shadow.blur_radius = 4.0
shadow.direction = 45
shadow.distance = 3
shadow.rectangle_align = slides.RectangleAlignment.TOP_LEFT
shadow.shadow_color.preset_color = slides.PresetColor.BLACK
```

#### 7단계: 프레젠테이션 저장
지정된 출력 디렉토리에 프레젠테이션을 파일로 저장합니다.
```python
pres.save("YOUR_OUTPUT_DIRECTORY/text_ShadowEffects_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}