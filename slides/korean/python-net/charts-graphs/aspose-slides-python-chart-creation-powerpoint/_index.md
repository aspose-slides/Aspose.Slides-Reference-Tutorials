---
"date": "2025-04-23"
"description": "Aspose.Slides for Python을 사용하여 PowerPoint에서 차트를 만들고 조작하는 방법을 알아보세요. 역동적인 데이터 시각화로 프레젠테이션을 더욱 풍성하게 만들어 보세요."
"title": "Python용 Aspose.Slides를 사용하여 PowerPoint에서 차트 만들기 마스터하기"
"url": "/ko/python-net/charts-graphs/aspose-slides-python-chart-creation-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint에서 차트 만들기 마스터하기

## 소개

데이터 기반 차트를 완벽하게 통합하여 프레젠테이션을 더욱 효과적으로 만들고 싶으신가요? 역동적인 시각화를 만드는 것은 흔한 과제이지만, 다음과 같은 적절한 도구를 사용하면 **Python용 Aspose.Slides**, 어렵지 않습니다. 이 튜토리얼은 PowerPoint 슬라이드에서 차트를 만들고 조작하는 방법을 안내하며, 차트 데이터의 행과 열을 전환하는 데 중점을 둡니다.

### 배울 내용:
- Python에 Aspose.Slides를 설치하고 설정하는 방법.
- PowerPoint 슬라이드에서 클러스터형 막대형 차트를 만드는 방법.
- 차트 데이터의 행과 열을 쉽게 전환합니다.
- 실제 적용 및 성능 고려 사항.

이 강력한 기능을 활용할 수 있도록 환경을 설정하는 방법을 알아보겠습니다!

## 필수 조건

시작하기에 앞서 다음 사항이 있는지 확인하세요.

### 필수 라이브러리
- **Python용 Aspose.Slides**: 이 튜토리얼을 따르려면 22.10 버전 이상이 필요합니다.
  

### 환경 설정 요구 사항
- Python 개발 환경(버전 3.7 이상 권장).
- Python 프로그래밍에 대한 기본적인 이해.

Aspose.Slides를 처음 사용하시는 분이라면 걱정하지 마세요. 설치 과정을 단계별로 안내해 드리겠습니다!

## Python용 Aspose.Slides 설정

시작하려면 다음을 설치하세요. **Aspose.Slides** pip를 사용합니다. 터미널이나 명령 프롬프트를 열고 다음을 실행합니다.

```bash
pip install aspose.slides
```

### 라이센스 취득 단계

Aspose는 제한된 기능의 무료 체험판을 제공합니다. 모든 기능을 사용하려면 라이선스를 구매하거나 임시 라이선스를 요청하세요.
- **무료 체험**: 최신 버전을 다운로드하여 기능을 살펴보세요.
- **임시 면허**방문하다 [Aspose의 임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/) 단기적인 해결책을 위해서.
- **구입**모든 기능을 사용할 준비가 되었다면 다음으로 이동하세요. [Aspose 구매 페이지](https://purchase.aspose.com/buy).

### 기본 초기화 및 설정

설치가 완료되면 Python 스크립트에서 Aspose.Slides를 초기화합니다.

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # 여기에 코드를 입력하세요
```

이는 작업할 기본 프레젠테이션 객체를 설정합니다.

## 구현 가이드

이제 설정이 끝났으니 차트를 만들고 조작하는 방법을 알아보겠습니다.

### 클러스터형 막대형 차트 만들기

#### 개요
군집 막대형 차트는 여러 범주의 데이터를 비교하는 데 매우 유용합니다. 첫 번째 슬라이드의 위치(100, 100)에 400x300 크기의 군집 막대형 차트를 추가해 보겠습니다.

```python
import aspose.slides as slides
from aspose.slides import Presentation, SaveFormat

with Presentation() as pres:
    # 클러스터형 막대형 차트 추가
    chart = pres.slides[0].shapes.add_chart(
        slides.charts.ChartType.CLUSTERED_COLUMN,
        100, 100, 400, 300
    )
```

#### 설명
- **차트 유형.클러스터형_열**: 차트의 유형을 지정합니다.
- **위치 및 차원**: 위치는 (100, 100), 크기는 400x300입니다.

### 행과 열 전환

#### 개요
행과 열을 전환하면 데이터에 대한 새로운 관점을 얻을 수 있습니다. Aspose.Slides를 사용하면 이를 간편하게 수행할 수 있습니다. `switch_row_column()`.

```python
# 차트 데이터의 행과 열을 전환합니다
cchart.chart_data.switch_row_column()
```

이 방법은 데이터를 재구성하여 다양한 맥락에서 해석 가능성을 높여줍니다.

### 프레젠테이션 저장

#### 개요
차트를 변경한 후 프레젠테이션을 저장하세요.

```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_switching_rows_and_columns_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}