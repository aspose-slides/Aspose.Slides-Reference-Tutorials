---
"date": "2025-04-23"
"description": "Python용 Aspose.Slides를 사용하여 동적 차트로 PowerPoint 프레젠테이션을 개선하는 방법을 알아보세요. 이 단계별 가이드를 따라 클러스터형 세로 막대형 차트를 효과적으로 만들고, 관리하고, 서식을 지정하세요."
"title": "Python용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에서 차트 만들기 및 서식 지정"
"url": "/ko/python-net/charts-graphs/create-charts-presentation-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에서 차트 만들기 및 서식 지정

## 소개

오늘날 데이터 중심 사회에서 시각적으로 매력적인 차트를 프레젠테이션에 통합하는 것은 효과적인 커뮤니케이션에 필수적입니다. 데이터 분석가, 프로젝트 관리자, 비즈니스 전문가 등 누구에게나 동적 차트는 메시지를 크게 향상시킬 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Python을 사용하여 클러스터형 세로 막대형 차트를 만들고 서식을 지정하는 방법을 안내하며, 이를 통해 PowerPoint 슬라이드를 손쉽게 개선할 수 있습니다.

**배울 내용:**
- Python용 Aspose.Slides를 설치하고 설정하는 방법
- 새 프레젠테이션을 만들고 클러스터형 막대형 차트를 추가합니다.
- 차트 내에서 데이터 시리즈 및 범주 관리
- 더 나은 시각화를 위해 시리즈 데이터를 채우고 형식을 지정합니다.

프레젠테이션을 더욱 풍성하게 만들 준비가 되셨나요? Aspose.Slides를 활용하여 매력적인 차트를 만드는 방법을 살펴보겠습니다.

## 필수 조건

시작하기에 앞서 다음 사항이 있는지 확인하세요.

- **Python 설치됨:** 버전 3.6 이상을 권장합니다.
- **Python 패키지용 Aspose.Slides:** pip를 사용하여 이 패키지를 설치하세요.
- **파이썬 프로그래밍에 대한 기본 지식:** Python 구문과 파일 처리에 익숙하면 도움이 됩니다.

## Python용 Aspose.Slides 설정

시작하려면 Aspose.Slides 라이브러리를 설치해야 합니다. 이 강력한 도구를 사용하면 Python에서 PowerPoint 프레젠테이션을 쉽게 만들고 조작할 수 있습니다.

### 설치

다음 명령을 실행하여 패키지를 설치하세요.

```bash
pip install aspose.slides
```

### 라이센스 취득

Aspose는 모든 기능을 제한 없이 체험해 볼 수 있는 무료 체험판 라이선스를 제공합니다. 다음 단계에 따라 라이선스를 받으세요.

1. 방문하다 [Aspose 무료 체험판](https://releases.aspose.com/slides/python-net/) 체험판 패키지를 다운로드하세요.
2. 또는 다음을 통해 임시 라이센스를 요청하세요. [임시 면허 페이지](https://purchase.aspose.com/temporary-license/).

라이선스 파일을 받으면 Python 스크립트에서 초기화하세요.

```python
from aspose.slides import License

# Aspose.Slides 라이선스 설정
license = License()
license.set_license("path/to/your/license/file.lic")
```

## 구현 가이드

이 과정을 차트 만들기, 데이터 시리즈와 범주 관리, 시리즈 데이터 채우기 및 서식 지정의 세 가지 주요 기능으로 나누어 보겠습니다.

### 기능 1: 프레젠테이션에 차트 만들기 및 추가

#### 개요

이 기능은 Python용 Aspose.Slides를 사용하여 프레젠테이션에 클러스터형 막대형 차트를 추가하는 데 중점을 둡니다.

#### 단계별 구현

```python
import aspose.slides as slides

def create_and_add_chart():
    with slides.Presentation() as pres:
        # 위치(100, 100)에 너비 400, 높이 300의 클러스터형 막대형 차트를 추가합니다.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        # 프레젠테이션을 출력 디렉토리에 파일로 저장합니다.
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_creation_out.pptx", slides.export.SaveFormat.PPTX)

create_and_add_chart()
```

**설명:**
- **차트 위치 및 크기:** 그만큼 `add_chart` 이 방법은 차트 유형, 위치(x,y), 너비, 높이를 지정하는 매개변수와 함께 사용됩니다.
- **프레젠테이션 저장:** 프레젠테이션은 지정된 디렉토리에 저장됩니다.

### 기능 2: 차트 데이터 시리즈 및 범주 관리

#### 개요

이 섹션에서는 차트 내에서 데이터 시리즈와 범주를 효과적으로 관리하는 방법을 보여줍니다.

#### 단계별 구현

```python
import aspose.slides as slides

def manage_chart_data_series_and_categories():
    with slides.Presentation() as pres:
        # 위치(100, 100)에 너비 400, 높이 300의 클러스터형 막대형 차트를 추가합니다.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # 새로운 시리즈와 카테고리를 추가하기 전에 기존 시리즈와 카테고리를 지우세요.
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # 차트에 "시리즈 1"이라는 새로운 시리즈를 추가합니다.
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # 차트 데이터에 세 가지 카테고리를 추가합니다.
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # 프레젠테이션을 출력 디렉토리에 파일로 저장합니다.
        pres.save("YOUR_OUTPUT_DIRECTORY/chart_series_categories_out.pptx", slides.export.SaveFormat.PPTX)

manage_chart_data_series_and_categories()
```

**설명:**
- **기존 데이터 지우기:** 새로운 시리즈와 카테고리를 추가하기 전에 기존 시리즈와 카테고리를 지워서 데이터 중복을 방지합니다.
- **시리즈 및 카테고리 추가:** 새로운 시리즈와 카테고리는 다음을 사용하여 추가됩니다. `chart_data_workbook` 물체.

### 기능 3: 시리즈 데이터 채우기 및 차트 서식 지정

#### 개요

이 기능을 사용하면 차트에 데이터 포인트를 채우고 서식을 적용하여 시각적인 매력을 높일 수 있습니다.

#### 단계별 구현

```python
import aspose.slides as slides
import aspose.pydrawing as drawing

def populate_and_format_series_data():
    with slides.Presentation() as pres:
        # 위치(100, 100)에 너비 400, 높이 300의 클러스터형 막대형 차트를 추가합니다.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # 새로운 시리즈와 카테고리를 추가하기 전에 기존 시리즈와 카테고리를 지우세요.
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # 차트에 "시리즈 1"이라는 새로운 시리즈를 추가합니다.
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # 차트 데이터에 세 가지 카테고리를 추가합니다.
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # 첫 번째 차트 시리즈를 가져와 데이터 포인트로 채웁니다.
        series = chart.chart_data.series[0]
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 1, 1, -20)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 2, 1, 50)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 3, 1, -30)
        )
        
        # 일련의 음수 값에 대한 색상을 설정합니다.
        invert_color = drawing.Color.red
        series.invert_if_negative = True
        series.format.fill.fill_type = slides.FillType.SOLID
        series.format.fill.solid_fill_color.color = series.get_automatic_series_color()
        series.inverted_solid_fill_color.color = invert_color
        
        # 프레젠테이션을 출력 디렉토리에 파일로 저장합니다.
        pres.save("YOUR_OUTPUT_DIRECTORY/populate_format_series_out.pptx", slides.export.SaveFormat.PPTX)

populate_and_format_series_data()
```

**설명:**
- **데이터 포인트 추가:** 데이터 포인트는 다음을 사용하여 추가됩니다. `add_data_point_for_bar_series`.
- **음수 값 서식 지정:** 음수 값에 대한 색상 반전과 같은 차트 서식 옵션은 데이터 가독성을 향상시킵니다.

## 실제 응용 프로그램

Aspose.Slides를 사용하면 프레젠테이션에 차트를 추가하고 서식을 지정할 수 있는 다양한 용도가 있습니다.

1. **사업 보고서:** 주요 지표를 명확하게 전달하는 역동적인 시각 자료로 분기별 보고서를 강화하세요.
2. **교육 자료:** 복잡한 정보를 시각적으로 표현하여 매력적인 교육 콘텐츠를 만드세요.
3. **프로젝트 프레젠테이션:** 차트를 사용하여 프로젝트 진행 상황과 결과를 효과적으로 보여줍니다.

이 가이드를 따르면 Python용 Aspose.Slides를 활용하여 눈길을 끄는 인상적인 프레젠테이션을 만들 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}