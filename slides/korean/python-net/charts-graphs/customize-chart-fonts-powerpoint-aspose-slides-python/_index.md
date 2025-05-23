---
"date": "2025-04-22"
"description": "Aspose.Slides를 Python과 함께 사용하여 PowerPoint 프레젠테이션의 차트 글꼴을 사용자 지정하는 방법을 알아보세요. 자세한 단계와 실제 적용 사례는 이 가이드를 참조하세요."
"title": "Python용 Aspose.Slides를 사용하여 PowerPoint에서 차트 글꼴을 사용자 지정하는 방법"
"url": "/ko/python-net/charts-graphs/customize-chart-fonts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint에서 차트 글꼴을 사용자 지정하는 방법

## 소개
Python을 사용하여 PowerPoint 프레젠테이션 차트의 시각적인 매력을 향상시키고 싶으신가요? 여러분만 그런 것이 아닙니다! 많은 개발자들이 프로그래밍 방식으로 차트 글꼴을 사용자 정의하려고 할 때 어려움을 겪습니다. 이 가이드에서는 PowerPoint에서 차트의 글꼴 속성을 설정하는 방법을 안내합니다. **Python용 Aspose.Slides**이러한 기술을 익히면 시각적으로 매력적이고 전문적인 슬라이드를 손쉽게 만들 수 있습니다.

이 튜토리얼에서는 다음 내용을 다룹니다.
- Python용 Aspose.Slides 설정
- 차트 글꼴을 간편하게 사용자 지정
- 귀하의 프로젝트에 대한 실용적인 응용 프로그램

모든 것을 준비했는지 확인하여 시작해 보겠습니다!

### 필수 조건
시작하기에 앞서, 다음과 같은 전제 조건이 충족되었는지 확인하세요.
1. **파이썬 환경**: Python이 설치되어 있는지 확인하세요(버전 3.6 이상).
2. **Python용 Aspose.Slides**: PowerPoint 파일을 조작하려면 이 라이브러리가 필요합니다.
3. **기본 지식**: Python 프로그래밍에 대한 지식과 라이브러리 작업에 대한 기본적인 이해가 도움이 됩니다.

## Python용 Aspose.Slides 설정
시작하려면 다음을 설치해야 합니다. `aspose.slides` pip를 사용하는 라이브러리:

```bash
pip install aspose.slides
```

### 라이센스 취득 단계
- **무료 체험**: 무료 평가판을 다운로드하세요 [Aspose 공식 사이트](https://releases.aspose.com/slides/python-net/).
- **임시 면허**: 보다 광범위한 테스트를 위해 해당 기관을 통해 임시 라이센스를 취득하십시오. [구매 페이지](https://purchase.aspose.com/temporary-license/).
- **구입**: 귀하의 요구 사항에 도구가 매우 유용하다고 생각되면 다음에서 전체 라이센스를 구매하는 것을 고려하십시오. [Aspose 구매 사이트](https://purchase.aspose.com/buy).

설치하고 라이선스를 받은 후 Python에서 Aspose.Slides를 초기화합니다.

```python
import aspose.slides as slides

# slides.Presentation()을 pres로 사용하여 Presentation 객체를 초기화합니다.
    # 여기에 코드를 입력하세요
```

## 구현 가이드
이 섹션에서는 차트 글꼴 속성을 단계별로 설정하는 방법을 살펴보겠습니다.

### 클러스터형 막대형 차트 추가
먼저, 프레젠테이션에 클러스터형 막대형 차트를 추가해 보겠습니다.

```python
# 지정된 위치와 크기에 클러스터형 막대형 차트를 추가합니다.
chart = pres.slides[0].shapes.add_chart(
    slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 500, 400
)
```
**설명**: 이 스니펫은 프레젠테이션의 첫 번째 슬라이드에 새 차트를 추가합니다. `add_chart` 이 방법을 사용하려면 차트 유형과 슬라이드에서의 위치 및 크기를 지정해야 합니다.

### 글꼴 속성 설정
다음으로, 차트 내 텍스트의 글꼴 높이를 설정해 보겠습니다.

```python
# 차트의 텍스트에 대한 글꼴 높이를 설정합니다.
chart.text_format.portion_format.font_height = 20
```
**설명**: 이 줄은 차트 내 모든 텍스트 부분의 글꼴 크기를 조정합니다. `font_height` 속성은 포인트 단위로 지정되며, 디자인 요구 사항에 맞게 이 값을 조정할 수 있습니다.

### 데이터 레이블 표시
가독성을 높이기 위해 데이터 레이블에 값을 표시합니다.

```python
# 첫 번째 시리즈의 데이터 레이블에 값을 표시합니다.
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```
**설명**: 이 설정은 첫 번째 계열의 각 데이터 포인트가 해당 값을 표시하도록 합니다. 특히 정확한 정보를 한눈에 전달하는 데 유용합니다.

### 프레젠테이션 저장
마지막으로, 원하는 위치에 프레젠테이션을 저장합니다.

```python
# 프레젠테이션을 지정된 출력 디렉토리에 저장합니다.
pres.save(
    "YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_chart_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}