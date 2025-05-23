---
"date": "2025-04-23"
"description": "Python용 Aspose.Slides를 사용하여 PowerPoint에서 SmartArt 그래픽을 만들고 사용자 지정하는 방법을 알아보고, 역동적인 조직도로 프레젠테이션을 향상시켜 보세요."
"title": "Python용 Aspose.Slides를 사용하여 PowerPoint에서 SmartArt를 만들고 사용자 지정하는 방법"
"url": "/ko/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint에서 SmartArt를 만들고 사용자 지정하는 방법

## 소개

프레젠테이션은 조직 구조나 브레인스토밍 세션을 시각적으로 표현하는 데 필수적인 도구입니다. Aspose.Slides for Python을 사용하면 SmartArt 그래픽을 손쉽게 만들고 사용자 지정할 수 있습니다. 이 튜토리얼에서는 PowerPoint 슬라이드에 조직도 SmartArt 그래픽을 추가하는 방법을 안내합니다.

**배울 내용:**
- Python용 Aspose.Slides를 사용하여 PowerPoint에 SmartArt 그래픽을 추가합니다.
- SmartArt 노드의 레이아웃을 사용자 지정합니다.
- 프레젠테이션을 효율적으로 저장하고 내보내세요.

이제 환경 설정을 시작해 보겠습니다!

## 필수 조건

SmartArt 그래픽을 만들기 전에 다음 필수 조건이 충족되는지 확인하세요.

### 필수 라이브러리
- **Python용 Aspose.Slides**: 아직 설치하지 않았다면 pip를 사용하여 이 라이브러리를 설치하세요.

### 환경 설정 요구 사항
- Python이 제대로 설치되어 있어야 합니다(3.x 권장).
- Python 프로그래밍에 대한 기본적인 이해.
- Microsoft PowerPoint에 대해 잘 알고 있으면 도움이 되지만 반드시 필요한 것은 아닙니다.

## Python용 Aspose.Slides 설정

시작하려면 Python 환경에서 Aspose.Slides 라이브러리를 설정하세요.

**Pip 설치:**
```bash
pip install aspose.slides
```

### 라이센스 취득 단계
Aspose는 다양한 라이선스 옵션을 제공합니다.
- **무료 체험**: 임시 라이센스를 다운로드하여 모든 기능을 평가해 보세요.
- **임시 면허**: 단기간 사용을 위한 무료 임시 라이센스를 받으세요.
- **구입**: 장기 프로젝트의 경우 구독 구매를 고려하세요.

### 기본 초기화 및 설정

설치가 완료되면 다음과 같이 Aspose.Slides를 사용하여 Python 스크립트를 초기화하세요.

```python
import aspose.slides as slides

# Presentation 클래스를 초기화합니다. slides.Presentation()을 프레젠테이션으로 지정합니다.
    # SmartArt를 추가하는 코드는 여기에 입력됩니다.
```

## 구현 가이드

이제 Python용 Aspose.Slides를 사용하여 PowerPoint에 SmartArt를 추가하고 사용자 지정하는 프로세스를 살펴보겠습니다.

### SmartArt 그래픽 추가

#### 개요
새 슬라이드를 만들고 조직도 유형 SmartArt 그래픽을 추가합니다.

```python
import aspose.slides as slides

# slides.Presentation()을 프레젠테이션으로 사용하여 프레젠테이션 인스턴스를 만듭니다.
    # 위치(10, 10)에 지정된 치수로 SmartArt를 추가합니다.
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### 매개변수 및 메서드 목적
- **x, y**: 슬라이드에서 SmartArt 그래픽의 위치.
- **너비, 높이**: 적절한 가시성을 위한 치수.
- **레이아웃_타입**: SmartArt 레이아웃의 유형을 지정합니다. 이 경우에는 조직도입니다.

### 조직도 레이아웃 사용자 지정

#### 개요
SmartArt 그래픽의 첫 번째 노드를 사용자 지정하려면 레이아웃을 LEFT_HANGING으로 설정합니다.

```python
# 첫 번째 노드를 왼쪽에 매달린 레이아웃으로 설정합니다.
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### 주요 구성 옵션 설명
- **조직도 레이아웃 유형**노드가 표시되는 방식을 결정하여 가독성과 미적 매력을 향상시킵니다.

### 프레젠테이션 저장

마지막으로, 프레젠테이션을 지정된 디렉토리에 저장합니다.

```python
# SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\를 사용하여 프레젠테이션을 저장합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}