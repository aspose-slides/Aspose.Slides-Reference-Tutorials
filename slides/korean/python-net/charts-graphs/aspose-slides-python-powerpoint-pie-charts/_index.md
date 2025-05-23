---
"date": "2025-04-22"
"description": "Aspose.Slides for Python을 사용하여 PowerPoint에서 원형 차트를 만들고 사용자 지정하는 방법을 알아보세요. 데이터 기반 인사이트로 프레젠테이션을 더욱 풍성하게 만들어 보세요."
"title": "Aspose.Slides for Python을 사용하여 매력적인 PowerPoint 원형 차트 만들기 | 차트 및 그래프 튜토리얼"
"url": "/ko/python-net/charts-graphs/aspose-slides-python-powerpoint-pie-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint 파이 차트 만들기

**범주:** 차트 및 그래프

데이터 기반 인사이트를 효과적으로 전달하려면 매력적이고 유익한 프레젠테이션을 만드는 것이 중요합니다. 시각적으로 매력적인 원형 차트를 사용하여 파워포인트 슬라이드를 더욱 돋보이게 만들고 싶다면, **Python용 Aspose.Slides** 라이브러리는 이 과정을 간소화하는 훌륭한 도구입니다. 이 튜토리얼에서는 Aspose.Slides for Python을 사용하여 PowerPoint에서 원형 차트를 만드는 방법을 안내합니다.

## 배울 내용:
- Python용 Aspose.Slides 설치 및 설정
- PowerPoint 슬라이드에서 기본 원형 차트 만들기
- 데이터 포인트, 색상, 테두리, 레이블, 지시선 및 회전을 사용하여 원형 차트를 사용자 지정하세요.
- 차트 작업 시 성능 최적화

시작하는 데 필요한 단계를 자세히 살펴보겠습니다.

## 필수 조건

코드를 구현하기 전에 다음 사항이 있는지 확인하세요.
- 시스템에 Python이 설치되어 있어야 합니다(버전 3.6 이상 권장)
- `pip` 라이브러리 설치를 위한 패키지 관리자
- Python 프로그래밍 및 PowerPoint 프레젠테이션에 대한 기본 이해

## Python용 Aspose.Slides 설정

Python용 Aspose.Slides를 사용하려면 pip를 사용하여 라이브러리를 설치해야 합니다.

```bash
pip install aspose.slides
```

**라이센스 취득:**
무료 평가판 라이센스를 다운로드하여 시작할 수 있습니다. [Aspose 다운로드 페이지](https://releases.aspose.com/slides/python-net/)더욱 광범위하게 사용하려면 정식 라이선스를 구매하거나 평가 목적으로 임시 라이선스를 구매하는 것을 고려해 보세요.

### 기본 초기화 및 설정

Aspose.Slides를 설치한 후 Python 스크립트에 필요한 모듈을 가져옵니다.

```python
import aspose.slides as slides
import aspose.pydrawing as drawing
```

## 구현 가이드

이 섹션에서는 파이 차트를 만드는 과정을 자세한 단계로 나누어 살펴보겠습니다.

### 파이 차트 만들기 및 사용자 지정

#### 개요
원형 차트를 만들려면 프레젠테이션 개체를 초기화하고, 슬라이드를 추가한 다음, 사용자 지정 데이터 포인트와 시각적 요소가 포함된 차트를 삽입해야 합니다.

#### 파이 차트를 만드는 단계

1. **프레젠테이션 클래스 인스턴스화**
   프레젠테이션 인스턴스를 만들어 시작하세요. 이 인스턴스는 슬라이드와 차트를 담을 컨테이너 역할을 합니다.

   ```python
   with slides.Presentation() as presentation:
       # 첫 번째 슬라이드에 접근하세요
       slide = presentation.slides[0]
   ```

2. **슬라이드에 원형 차트 추가**
   사용하세요 `add_chart` 슬라이드의 지정된 좌표에 파이 차트를 삽입하는 방법입니다.

   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

3. **차트 제목 설정**
   적절한 제목으로 차트를 사용자 지정하고 텍스트를 가운데에 정렬하도록 서식을 지정합니다.

   ```python
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

4. **Access 차트 데이터 통합 문서**
   사용하세요 `chart_data_workbook` 데이터 범주와 시리즈를 관리하고 사용자 정의합니다.

   ```python
   fact = chart.chart_data.chart_data_workbook
   default_worksheet_index = 0

   # 기존 시리즈나 카테고리를 모두 지웁니다.
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()

   # 새로운 카테고리(분기) 추가
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   # 새로운 시리즈 추가
   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   ```

5. **데이터 포인트로 시리즈 채우기**
   파이의 다양한 부분을 나타내기 위해 시리즈에 데이터 포인트를 삽입합니다.

   ```python
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 3, 1, 30))
   ```

6. **차트에 다양한 색상 적용**
   각 파이 조각을 다른 색상으로 사용자 정의하세요.

   ```python
   chart.chart_data.series_groups[0].is_color_varied = True

   # 포인트 모양을 사용자 정의하기 위한 기능 정의
   def customize_point(point, fill_color, line_color):
       point.format.fill.fill_type = slides.FillType.SOLID
       point.format.fill.solid_fill_color.color = drawing.Color(fill_color)
       
       point.format.line.fill_format.fill_type = slides.FillType.SOLID
       point.format.line.fill_format.solid_fill_color.color = drawing.Color(line_color)
       point.format.line.width = 3.0
       point.format.line.style = slides.LineStyle.THIN_THICK
       point.format.line.dash_style = slides.LineDashStyle.DASH_DOT
   
   # 첫 번째 데이터 포인트의 모양 사용자 지정
   customize_point(series.data_points[0], "Cyan", "Gray")
   ```

7. **데이터 포인트에 대한 레이블 사용자 지정**
   레이블 설정을 조정하여 값, 백분율 또는 시리즈 이름을 표시합니다.

   ```python
   def customize_label(point, show_value=True, show_legend_key=False,
                       show_percentage=False, show_series_name=False):
       lbl = point.label
       lbl.data_label_format.show_value = show_value
       lbl.data_label_format.show_legend_key = show_legend_key
       lbl.data_label_format.show_percentage = show_percentage
       lbl.data_label_format.show_series_name = show_series_name
   
   # 첫 번째 데이터 포인트에 대한 레이블 속성 설정
   customize_label(series.data_points[0], True)
   ```

8. **리더선 활성화 및 파이 조각 회전**
   가독성을 높이려면 지시선을 활성화하고 필요에 따라 슬라이스를 회전하세요.

   ```python
   series.labels.default_data_label_format.show_leader_lines = True

   # 첫 번째 파이 조각을 180도 회전합니다.
   chart.chart_data.series_groups[0].first_slice_angle = 180
   ```

9. **프레젠테이션 저장**
   마지막으로, 모든 사용자 정의를 적용하여 프레젠테이션을 저장합니다.

   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### 문제 해결 팁
- Aspose.Slides가 올바르게 설치되고 가져왔는지 확인하세요.
- 메서드 이름이나 매개변수에 오타가 있는지 확인하세요. 오타는 오류로 이어질 수 있습니다.
- 출력 파일을 저장할 디렉토리 경로가 있는지 확인하세요.

## 실제 응용 프로그램

원형 차트는 다양한 도메인에서 다재다능하고 유용합니다.
1. **비즈니스 분석**다양한 제품이나 서비스 간 수익 분배를 시각화합니다.
2. **마케팅 보고서**: 특정 산업에서 경쟁자의 시장 점유율을 보여줍니다.
3. **교육 프레젠테이션**: 학생 성취도나 인구 통계와 관련된 통계적 데이터를 보여줍니다.

## 성능 고려 사항
- 차트 요소를 최적화하고 불필요한 복잡성을 줄여 리소스 사용량을 최소화합니다.
- 차트의 대용량 데이터 세트를 처리할 때는 효율적인 데이터 구조를 사용하세요.
- 사용 후 리소스를 즉시 해제하여 메모리를 효과적으로 관리합니다.

## 결론

이 가이드를 따라 하면 Python용 Aspose.Slides를 사용하여 PowerPoint에서 원형 차트를 만드는 방법을 배우게 됩니다. 이제 이러한 기법을 프레젠테이션에 적용하고 더욱 다양한 사용자 지정 옵션을 탐색해 보세요. 다른 차트 유형을 통합하거나 Aspose.Slides의 추가 기능을 활용하여 데이터 시각화 기술을 향상하는 것도 고려해 보세요.

### 다음 단계
- 다양한 차트 사용자 정의를 실험해 보세요
- 동적 보고서에 차트 통합 살펴보기
- 더욱 고급 기능에 대한 Aspose.Slides 문서를 자세히 살펴보세요.

## FAQ 섹션

1. **Aspose.Slides란 무엇인가요?**
   - PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고 조작할 수 있는 강력한 라이브러리입니다.
2. **Aspose.Slides를 무료로 사용할 수 있나요?**
   - 네, 구매하기 전에 체험판 라이선스로 시작하거나 기능을 평가해 볼 수 있습니다.
3. **만들 수 있는 다른 차트 유형은 무엇이 있나요?**
   - Aspose.Slides를 사용하면 원형 차트 외에도 막대 차트, 선 그래프, 산점도 등을 만들 수 있습니다.

## 키워드 추천
- "Python용 Aspose.Slides"
- "파워포인트 파이 차트"
- "파이썬 파워포인트 차트"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}