---
"date": "2025-04-22"
"description": "Python과 Aspose.Slides를 사용하여 도넛형 차트를 만드는 방법을 알아보세요. 이 단계별 가이드에서는 프레젠테이션을 개선하기 위한 설정, 사용자 지정 및 모범 사례를 다룹니다."
"title": "Aspose.Slides를 사용하여 Python에서 도넛 차트를 만드는 방법 - 단계별 가이드"
"url": "/ko/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용하여 Python에서 도넛 차트를 만드는 방법: 단계별 가이드

데이터 시각화 분야에서 정보를 효과적으로 표현하는 것은 정보의 이해와 의사 결정에 큰 영향을 미칠 수 있습니다. 비즈니스 프레젠테이션을 제작하든 복잡한 데이터 세트를 분석하든 차트는 필수적인 도구입니다. 다양한 차트 유형 중에서도 도넛 차트는 직관적인 중앙 구멍을 통해 비례 데이터를 표현하는 매력적인 방법을 제공합니다. 이 단계별 가이드는 프레젠테이션을 조작하는 강력한 라이브러리인 Aspose.Slides를 사용하여 Python에서 도넛 차트를 만드는 방법을 안내합니다.

## 당신이 배울 것
- Python용 Aspose.Slides 설정 및 사용 방법
- 프레젠테이션 슬라이드에 도넛형 차트를 추가하는 과정
- 차트 내 시리즈 및 범주 사용자 지정
- 라벨, 색상, 폭발 효과 등의 시각적 요소 조정
- Aspose.Slides를 사용하여 성능을 최적화하기 위한 모범 사례

## 필수 조건
시작하기 전에 다음 사항을 확인하세요.
- **파이썬 환경**: Python 3.x가 컴퓨터에 설치되어 있습니다.
- **Python용 Aspose.Slides**: pip를 사용하여 이 라이브러리를 설치합니다.
- **파이썬 프로그래밍에 대한 기본 이해**: 루프와 객체 지향 프로그래밍에 대한 지식이 있으면 도움이 됩니다.

## Python용 Aspose.Slides 설정
시작하려면 pip를 통해 Aspose.Slides 라이브러리를 설치하세요.

```bash
pip install aspose.slides
```

### 라이센스 취득
Aspose는 제한된 기간 동안 제한 없이 기능을 테스트할 수 있는 무료 체험판을 제공합니다. 무료 체험판을 이용하려면 다음을 수행하세요.
1. 방문하세요 [무료 체험](https://releases.aspose.com/slides/python-net/) 페이지.
2. 임시 라이센스를 다운로드하고 적용하려면 지침을 따르세요.

계속 사용하려면 다음에서 구독을 구매하는 것을 고려하세요. [구매 페이지](https://purchase.aspose.com/buy).

### 기본 초기화
Aspose.Slides를 설정한 후 다음과 같이 초기화합니다.

```python
import aspose.slides as slides

# Presentation 클래스의 인스턴스를 생성합니다.
with slides.Presentation() as pres:
    # 프레젠테이션을 조작하는 코드는 여기에 입력하세요.

# 변경 사항을 적용한 후 프레젠테이션을 저장합니다.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## 구현 가이드
Aspose.Slides를 설정한 후 다음 단계에 따라 슬라이드별로 도넛형 차트를 프레젠테이션에 추가하세요.

### 새 프레젠테이션 만들기 및 슬라이드 추가
인스턴스를 생성하여 시작하세요. `Presentation` 수업:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # 이 컨텍스트 내에서 슬라이드에 접근하거나 슬라이드를 만듭니다.
```

### 첫 번째 슬라이드에 도넛 차트 추가
첫 번째 슬라이드에 접근하여 사용하세요 `add_chart` 방법. 차트 유형을 다음과 같이 지정하세요. `DOUGHNUT`, 위치 및 크기와 함께:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### 차트 데이터 구성
기존 데이터를 지우고 범례 숨기기 등의 설정을 구성합니다.

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### 시리즈 및 카테고리 추가
도넛형 차트에 여러 시리즈와 범주를 추가합니다. 특정 속성을 가진 15개의 시리즈를 만드는 방법은 다음과 같습니다.

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

비슷한 방식으로 카테고리를 추가합니다.

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # 각 시리즈에 대한 데이터 포인트를 추가합니다.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # 각 데이터 포인트의 모양을 사용자 지정합니다.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # 마지막 시리즈에 대한 라벨 설정을 구성합니다.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### 프레젠테이션 저장
마지막으로, 프레젠테이션을 지정된 디렉토리에 저장합니다.

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## 실제 응용 프로그램
도넛형 차트는 다용도로 활용 가능하며, 다음과 같은 다양한 시나리오에 활용할 수 있습니다.
1. **예산 할당**: 각 부서가 할당된 자금을 어떻게 사용하는지 보여줍니다.
2. **시장 점유율 분석**: 경쟁 제품이나 회사의 시장 점유율을 비교합니다.
3. **설문조사 결과**: 선호도나 만족도에 대한 설문조사 질문에 대한 응답을 시각화합니다.

## 성능 고려 사항
Aspose.Slides를 사용할 때 최적의 성능을 보장하려면:
- 사용 후 객체를 적절히 폐기하여 메모리 사용량을 최소화하세요.
- 필요할 때만 프레젠테이션을 메모리에 로드하고 가능한 한 빨리 닫으세요.
- 많은 수의 차트를 다루는 경우 슬라이드를 일괄 처리하는 것을 고려하세요.

## 결론
이 가이드를 따라 Aspose.Slides for Python을 사용하여 동적 도넛형 차트를 만드는 방법을 알아보았습니다. 이러한 시각화는 데이터를 더욱 이해하기 쉽고 매력적으로 만들어 프레젠테이션을 더욱 풍부하게 만들어 줍니다. 라이브러리의 기능을 계속 탐색하여 차트를 더욱 맞춤 설정하고 최적화하세요.

## FAQ 섹션
1. **라이선스를 구매하지 않고도 Aspose.Slides를 사용할 수 있나요?**
   - 네, 평가 목적으로 무료 체험판 라이선스로 시작할 수 있습니다.
2. **Aspose.Slides에서 차트 색상을 어떻게 변경합니까?**
   - 사용하세요 `fill_format` 차트 요소에 원하는 색상을 설정하는 속성입니다.
3. **차트를 이미지로 내보낼 수 있나요?**
   - 네, 라이브러리의 렌더링 기능을 사용하여 차트가 포함된 슬라이드를 이미지 형식으로 렌더링할 수 있습니다.
4. **차트를 추가할 때 흔히 발생하는 문제는 무엇입니까?**
   - 차트를 저장하거나 표시하기 전에 모든 데이터 포인트와 범주가 제대로 추가되었는지 확인하세요.
5. **Aspose.Slides를 다른 Python 라이브러리와 통합할 수 있나요?**
   - 물론입니다! Pandas 같은 라이브러리와 함께 사용하면 더욱 향상된 데이터 조작 기능을 활용할 수 있습니다.

## 자원
- [Aspose.Slides 문서](https://reference.aspose.com/slides/python-net/)
- [Aspose.Slides 다운로드](https://releases.aspose.com/slides/python-net/)
- [라이센스 구매](https://purchase.aspose.com/buy)
- [무료 체험판 및 임시 라이센스](https://releases.aspose.com/slides/python-net/)
- [Aspose 커뮤니티 포럼](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}