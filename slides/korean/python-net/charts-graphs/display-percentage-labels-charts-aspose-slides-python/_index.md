---
"date": "2025-04-22"
"description": "Aspose.Slides for Python을 사용하여 PowerPoint 프레젠테이션의 차트에 백분율 레이블을 손쉽게 표시하는 방법을 알아보세요. 데이터 시각화 향상에 매우 유용합니다."
"title": "Aspose.Slides for Python을 사용하여 차트에 백분율 레이블을 표시하는 방법 - 종합 가이드"
"url": "/ko/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 차트에 백분율 레이블을 표시하는 방법

## 소개

프레젠테이션과 보고서에서 데이터를 효과적으로 시각화하는 것은 매우 중요합니다. 특히 비율이나 분포를 명확하게 강조하고 싶을 때 더욱 그렇습니다. 하지만 차트에 비율을 직접 표시해야 한다면 어떨까요? 이 종합 가이드에서는 다음과 같은 방법을 안내해 드립니다. **Python용 Aspose.Slides** 차트에 백분율 값을 레이블로 손쉽게 표시하는 방법.

### 배울 내용:
- Python용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에 차트를 만들고 포함하는 방법.
- 차트에 데이터 포인트를 백분율 레이블로 표시합니다.
- PowerPoint 프레젠테이션을 효율적으로 저장하고 관리합니다.

데이터에 통찰력 있는 시각적 요소를 추가할 준비가 되셨나요? 코드 작업을 시작하기 전에 먼저 필요한 사항을 살펴보겠습니다!

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.
- **Python용 Aspose.Slides**: 이 라이브러리는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고 조작하는 데 필수적입니다.
- **파이썬 환경**: Python 프로그래밍과 환경 설정에 대한 기본적인 이해.
- **PIP 패키지 관리자**: Aspose.Slides를 설치하는 데 사용됩니다.

## Python용 Aspose.Slides 설정

Aspose.Slides를 사용하려면 먼저 설치해야 합니다.

```bash
pip install aspose.slides
```

### 라이센스 취득 단계:
무료 체험판을 시작하거나 임시 라이선스를 구매하여 Aspose.Slides의 모든 기능을 사용해 보세요. 장기간 사용하려면 구독을 고려해 보세요.

#### 기본 초기화 및 설정

설치가 완료되면 다음과 같이 프레젠테이션 환경을 초기화합니다.

```python
import aspose.slides as slides

# 프레젠테이션 객체를 초기화합니다
def create_presentation():
    with slides.Presentation() as presentation:
        # 여기에 코드를 입력하세요
```

## 구현 가이드

이제 설정이 끝났으니 차트에 백분율을 표시하는 방법을 알아보겠습니다.

### 차트 만들기 및 데이터 추가

#### 개요
각 데이터 포인트에 대한 백분율 레이블이 있는 쌓인 막대형 차트를 만들어서 보는 사람이 한눈에 정확한 비율을 볼 수 있도록 하겠습니다.

##### 1단계: 슬라이드에 차트 추가

```python
# 프레젠테이션의 첫 번째 슬라이드에 액세스하세요
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # 쌓인 막대형 차트 추가
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

이 코드 조각은 첫 번째 슬라이드에 기본 차트를 추가합니다. `add_chart` 이 방법은 차트의 유형과 위치, 크기를 지정합니다.

##### 2단계: 범주별 총 값 계산

```python
def calculate_totals(chart):
    total_for_category = []
    # 각 카테고리의 모든 시리즈에 대한 값을 합산합니다.
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

이 루프는 백분율 계산에 중요한, 시리즈 전체의 모든 데이터 포인트의 합계를 계산합니다.

#### 백분율 레이블 설정

##### 3단계: 시리즈 데이터 포인트 구성

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # 필수적이지 않은 정보를 숨기려면 기본 레이블 옵션을 설정하세요.
        series.labels.default_data_label_format.show_legend_key = False
        
        # 백분율 레이블을 계산하고 설정합니다.
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # 백분율 값을 사용하여 텍스트 부분을 만듭니다.
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # 기존 레이블을 지우고 새로운 백분율 레이블을 추가합니다.
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # 다른 데이터 레이블 요소 숨기기
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

이 세그먼트는 각 데이터 포인트를 처리하여 전체에서 차지하는 비율을 계산하고 이를 레이블로 지정합니다.

### 프레젠테이션 저장

```python
def save_presentation(presentation, output_directory):
    # 수정된 프레젠테이션을 저장하세요
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}