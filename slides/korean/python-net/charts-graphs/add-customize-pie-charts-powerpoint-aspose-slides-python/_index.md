---
"date": "2025-04-22"
"description": "Aspose.Slides for Python을 사용하여 PowerPoint 프레젠테이션에 원형 차트를 추가하고 사용자 지정하는 방법을 알아보세요. 이 단계별 가이드를 통해 시간을 절약하고 일관성을 유지하세요."
"title": "Python용 Aspose.Slides를 사용하여 PowerPoint에 원형 차트를 추가하고 사용자 지정하는 방법"
"url": "/ko/python-net/charts-graphs/add-customize-pie-charts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint에 원형 차트를 추가하고 사용자 지정하는 방법

## 소개
시각적으로 매력적인 프레젠테이션을 만드는 것은 매우 중요합니다. 특히 복잡한 데이터를 간결하게 전달해야 할 때 더욱 그렇습니다. 재무 보고서든 성과 지표든, 원형 차트는 비율을 한눈에 보여주는 효과적인 도구입니다. 하지만 이러한 차트를 슬라이드에 직접 추가하는 것은 시간이 많이 걸리고 일관성이 떨어지기 쉽습니다.

Aspose.Slides Python 라이브러리를 사용하면 이 과정을 자동화하는 것이 훨씬 수월해집니다. 이 튜토리얼에서는 Aspose.Slides for Python을 사용하여 PowerPoint 프레젠테이션에 원형 차트를 손쉽게 추가하고 사용자 지정하는 방법을 안내합니다. 따라 하면 시간을 절약할 수 있을 뿐만 아니라 슬라이드 전체의 일관성도 유지할 수 있습니다.

**배울 내용:**
- 슬라이드에 원형 차트를 추가하는 방법
- 파이 차트에 제목 설정 및 텍스트 가운데 정렬
- 자세한 통찰력을 위한 데이터 시리즈 및 범주 구성
- 각 슬라이스에 대한 자동 색상 변형 활성화

이러한 기능을 효과적으로 구현하는 방법을 자세히 살펴보겠습니다. 시작하기 전에 환경이 제대로 설정되어 있는지 확인하세요.

## 필수 조건
이 튜토리얼을 따르려면 다음이 필요합니다.
- 컴퓨터에 설치된 Python(버전 3.x 권장)
- Python용 Aspose.Slides 라이브러리
- Python 프로그래밍 및 PowerPoint 프레젠테이션에 대한 기본 이해

Python 스크립트를 실행하는 데 필요한 설정이 있는지 확인하세요. 그렇지 않은 경우 다음에서 Python을 설치하는 것을 고려해 보세요. [파이썬.org](https://www.python.org/downloads/).

## Python용 Aspose.Slides 설정
프로젝트에서 Aspose.Slides를 사용하려면 pip를 통해 설치하세요.

```bash
pip install aspose.slides
```

### 라이센스 취득 단계
Aspose는 라이브러리 무료 체험판을 제공합니다. 임시 라이선스를 다운로드하여 제한 없이 모든 기능을 사용해 보세요. 시작하려면:
- 방문하다 [Aspose 구매 페이지](https://purchase.aspose.com/buy) 구매 옵션에 대해서.
- 임시 면허를 취득하세요 [임시 면허 페이지](https://purchase.aspose.com/temporary-license/).

### 기본 초기화
Python 스크립트에서 Aspose.Slides를 초기화하는 방법은 다음과 같습니다.

```python
import aspose.slides as slides

# 프레젠테이션 파일을 만들거나 열려면 Presentation 클래스를 초기화합니다.
with slides.Presentation() as presentation:
    # 여기에 코드를 입력하세요
    pass
```

이렇게 설정하면 프레젠테이션에 파이 차트를 추가할 준비가 됩니다.

## 구현 가이드

### 슬라이드에 원형 차트 추가
#### 개요
기본 원형 차트를 추가하려면 새로운 유형의 모양을 만들어야 합니다. `Chart` 슬라이드에 추가하세요. 이 섹션에서는 기본 원형 차트를 추가하는 단계를 안내합니다.

#### 단계
1. **첫 번째 슬라이드에 접근하세요**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **파이 차트 모양 추가**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

   - 매개변수: `ChartType.PIE` 차트 유형을 지정합니다.
   - 좌표와 차원은 파이 차트의 위치와 크기를 정의합니다.

3. **프레젠테이션 저장**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_add_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### 파이 차트 제목 및 가운데 텍스트 설정
#### 개요
원형 차트에 제목을 추가하면 가독성이 높아지고 보는 사람에게 맥락을 제공할 수 있습니다.

#### 단계
1. **첫 번째 슬라이드에 액세스**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **차트 추가 및 제목 설정**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   # 제목 설정
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

3. **프레젠테이션 저장**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_pie_chart_title_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### 파이 차트 데이터 시리즈 및 범주 구성
#### 개요
원형 차트를 유익하게 만들려면 실제 데이터를 입력해야 합니다.

#### 단계
1. **첫 번째 슬라이드에 액세스**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **데이터 구성**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   fact = chart.chart_data.chart_data_workbook
   
   # 기존 데이터 지우기
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()
   
   # 데이터 포인트로 카테고리 및 시리즈 추가
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   
   # 데이터 포인트 추가
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 3, 1, 30))
   ```

3. **프레젠테이션 저장**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_configure_pie_chart_data_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### 자동 원형 차트 슬라이스 색상 활성화
#### 개요
슬라이스 색상을 자동으로 변경하여 시각적 매력을 높이면 차트가 더욱 매력적으로 보일 수 있습니다.

#### 단계
1. **첫 번째 슬라이드에 액세스**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **색상 변형 활성화**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   series = chart.chart_data.series[0]
   series.parent_series_group.is_color_varied = True
   ```

3. **프레젠테이션 저장**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_enable_automatic_pie_slice_colors_out.pptx", slides.export.SaveFormat.PPTX)
   ```

## 실제 응용 프로그램
1. **사업 보고서**: 파이 차트를 사용하여 경쟁사 간 시장 점유율 분포를 보여줍니다.
2. **교육 자료**: 커리큘럼에서 다루는 다양한 주제의 백분율을 보여 줍니다.
3. **재무 분석**: 총 예산에 대한 비율로 비용 범주를 표시합니다.
4. **마케팅 인사이트**: 인구 통계나 선호도에 따라 고객을 세분화하여 시각화합니다.

Pandas와 같은 데이터 분석 도구와 통합하면 프로세스를 더욱 자동화하여 프레젠테이션 내에서 실시간 업데이트가 가능해집니다.

## 성능 고려 사항
Aspose.Slides와 Python을 사용할 때:
- 특히 대규모 데이터 세트를 다루는 경우 메모리를 효율적으로 관리하기 위해 코드를 최적화하세요.
- 프레젠테이션 객체에 대한 중복 작업을 피하세요.
- 사용 `with` 사용 후 리소스가 적절하게 해제되도록 컨텍스트 관리를 위한 명령문입니다.

## 결론
이제 Aspose.Slides for Python을 사용하여 PowerPoint에서 원형 차트를 만들고 사용자 지정하는 방법을 전반적으로 이해하게 되었습니다. 이러한 작업을 자동화하면 프레젠테이션 전체의 일관성을 유지하면서 생산성을 크게 향상시킬 수 있습니다. 

이를 더욱 발전시키려면 동적 데이터 소스를 통합하거나 전체 슬라이드 데크 생성을 자동화하는 것을 살펴보세요.

## 키워드 추천
- "Python용 Aspose.Slides"
- "파워포인트 원형 차트"
- "Python을 사용하여 PowerPoint 차트를 자동화합니다"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}