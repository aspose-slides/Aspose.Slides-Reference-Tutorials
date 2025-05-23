---
"date": "2025-04-22"
"description": "Python용 Aspose.Slides를 사용하여 상자형 차트와 수염형 차트를 만드는 방법을 알아보세요. 프레젠테이션의 데이터 시각화를 향상시켜 보세요."
"title": "Aspose.Slides를 사용하여 Python에서 상자형 차트와 수염형 차트 만들기"
"url": "/ko/python-net/charts-graphs/create-box-whisker-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용하여 Python에서 상자형 차트와 수염형 차트 만들기

## Python용 Aspose.Slides를 사용하여 상자와 수염 차트를 만드는 방법

강력한 Aspose.Slides 라이브러리를 사용하여 상자형 차트와 수염형 차트를 만드는 방법을 배우고 데이터 시각화 기술을 향상시켜 보세요. 이 차트는 통계적 분포를 표시하는 데 매우 유용하며, 복잡한 데이터도 한눈에 쉽게 해석할 수 있도록 도와줍니다.

**배울 내용:**
- Python용 Aspose.Slides를 사용하여 환경 설정하기
- 상자형 차트와 수염형 차트 만들기 및 사용자 지정
- 실용적인 응용 프로그램 및 통합 기회
- 더 나은 성능을 위한 최적화 팁

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.
- **Python용 Aspose.Slides:** PowerPoint 프레젠테이션을 만들고 조작하는 데 필수적인 라이브러리입니다.
- **파이썬 환경:** 작동하는 Python 설치가 필요합니다(가급적 Python 3.x 이상).
- **기본 파이썬 지식:** Python 프로그래밍에 익숙하면 더 쉽게 따라갈 수 있습니다.

## Python용 Aspose.Slides 설정

### 설치 정보

시작하려면 pip를 사용하여 Aspose.Slides 라이브러리를 설치하세요.

```bash
pip install aspose.slides
```

### 라이센스 취득 단계

Aspose는 다양한 라이선스 옵션을 제공합니다.
- **무료 체험:** 평가판 제한 없이 모든 기능을 사용해보려면 임시 라이센스를 다운로드하세요.
- **임시 면허:** 단기 프로젝트나 테스트 목적에 이상적입니다.
- **구입:** 지속적으로 액세스해야 하는 경우 영구 라이선스를 얻으세요.

이러한 라이센스는 다음을 통해 획득할 수 있습니다. [구매 페이지](https://purchase.aspose.com/buy) 또는 무료 체험판을 요청하세요 [임시 면허 페이지](https://purchase.aspose.com/temporary-license/).

### 기본 초기화 및 설정

설치 후 Python용 Aspose.Slides를 초기화하여 프레젠테이션 작업을 시작하세요. 환경 설정 방법은 다음과 같습니다.

```python
import aspose.slides as slides

# 프레젠테이션 인스턴스 초기화
def setup_presentation():
    with slides.Presentation() as pres:
        # 여기에 차트를 추가하는 등의 작업을 수행합니다.
        pass
```

## 구현 가이드

이 섹션에서는 상자 수염 차트를 만드는 방법을 안내해 드리겠습니다.

### 프레젠테이션에 상자와 수염 차트 추가하기

#### 개요

프레젠테이션에서 데이터를 효과적으로 시각화하려면 Aspose.Slides for Python을 사용하여 상자 수염 차트를 만들어 보세요. 이 차트는 분포를 표시하고 이상치를 식별하는 데 매우 유용합니다.

#### 단계별 구현

1. **새로운 프레젠테이션 만들기:**
   
   새로운 프레젠테이션 인스턴스를 초기화하여 시작합니다.
   
   ```python
   import aspose.slides as slides
   
   def create_box_and_whisker_chart():
       # 새로운 프레젠테이션 인스턴스를 만듭니다
       with slides.Presentation() as pres:
           # 다음 단계에서 차트를 추가합니다.
           pass
   ```

2. **슬라이드에 차트 추가:**
   
   원하는 위치에 상자와 수염 차트를 삽입하세요.
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           # 첫 번째 슬라이드에 위치(50, 50)와 크기(500, 400)의 상자 및 수염 차트를 추가합니다.
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
   ```

3. **기존 데이터 지우기:**
   
   새 데이터를 추가하기 전에 차트가 비어 있는지 확인하세요.
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           
           # 기존 카테고리 및 시리즈 데이터를 지웁니다.
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)  # 새로운 데이터 입력을 위해 통합 문서를 비웁니다.
   ```

4. **차트에 카테고리 추가:**
   
   차트에 카테고리를 채우세요:
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           # 차트 데이터에 대한 범주 정의
           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))
   ```

5. **시리즈 구성:**
   
   원하는 속성으로 시리즈를 설정하세요.
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))

           # 새 시리즈를 추가하고 속성을 구성합니다.
           series = chart.chart_data.series.add(slides.charts.ChartType.BOX_AND_WHISKER)
           series.quartile_method = slides.charts.QuartileMethodType.EXCLUSIVE
           series.show_mean_line = True
           series.show_mean_markers = True
           series.show_inner_points = True
           series.show_outlier_points = True

           # 시리즈에 대한 데이터 포인트 정의
           values = [15, 41, 16, 10, 23, 16]
           for i, value in enumerate(values, start=1):
               series.data_points.add_data_point_for_box_and_whisker_series(wb.get_cell(0, f"B{i}", value))
   ```

6. **프레젠테이션 저장:**
   
   새로 추가된 차트로 작업을 저장하세요.
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))

           series = chart.chart_data.series.add(slides.charts.ChartType.BOX_AND_WHISKER)
           series.quartile_method = slides.charts.QuartileMethodType.EXCLUSIVE
           series.show_mean_line = True
           series.show_mean_markers = True
           series.show_inner_points = True
           series.show_outlier_points = True

           values = [15, 41, 16, 10, 23, 16]
           for i, value in enumerate(values, start=1):
               series.data_points.add_data_point_for_box_and_whisker_series(wb.get_cell(0, f"B{i}", value))

           # 프레젠테이션을 저장하세요
           pres.save("YOUR_OUTPUT_DIRECTORY/charts_box_chart_out.pptx", slides.export.SaveFormat.PPTX)

   create_box_and_whisker_chart()
   ```

### 문제 해결 팁

- **라이브러리 설치 확인:** 보장하다 `aspose.slides` 올바르게 설치되었습니다.
- **라이센스 설정 확인:** 제한 사항이 발생하는 경우 라이선스 파일이 올바르게 설정되었는지 확인하세요.
- **구문 오류:** 코드 구문에 오타나 오류가 있는지 다시 한번 확인하세요.

## 실용적인 응용 프로그램 및 통합 기회

상자 수염 차트는 비즈니스 분석에서 통계 데이터를 간결하게 표현하는 데 널리 사용됩니다. 데이터세트 내 추세, 이상치, 변동을 파악하는 데 도움이 되므로 프레젠테이션, 보고서, 대시보드에 적합합니다.

Aspose.Slides를 Python과 통합하면 풍부하고 대화형 PowerPoint 프레젠테이션을 프로그래밍 방식으로 원활하게 만들 수 있어 데이터 기반의 통찰력을 전달하는 방식이 향상됩니다.

## 더 나은 성능을 위한 최적화 팁

- **데이터 입력 간소화:** 시각화 과정에서 오류를 방지하려면 차트를 생성하기 전에 데이터 세트가 깔끔하고 잘 구성되어 있는지 확인하세요.
- **차트 사용자 정의 최적화:** Aspose.Slides의 사용자 정의 옵션을 현명하게 활용하면 과도한 요소로 프레젠테이션을 가득 채우지 않고도 차트의 가독성을 높일 수 있습니다.
- **반복적인 작업 자동화:** Python 스크립트를 활용하여 데이터 서식 지정, 차트 생성 등의 반복적인 작업을 자동화하고, 시간을 절약하고 오류를 줄이세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}