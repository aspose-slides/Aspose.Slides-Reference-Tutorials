---
"date": "2025-04-22"
"description": "Python용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에서 원형 차트를 만들고 사용자 지정하는 방법을 배우고 데이터 시각화 기술을 향상시키세요."
"title": "Python용 Aspose.Slides를 사용하여 PowerPoint에서 원형 차트를 만드는 방법"
"url": "/ko/python-net/charts-graphs/aspose-slides-python-pie-of-pie-chart-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint에서 원형 차트를 만드는 방법

'원형 대 원형' 차트처럼 시각적으로 매력적인 차트를 만들면 복잡한 정보를 더 이해하기 쉽게 만들어 파워포인트 프레젠테이션을 크게 향상시킬 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Python을 사용하여 '원형 대 원형' 차트를 만드는 방법을 안내합니다.

## 당신이 배울 것

- Python용 Aspose.Slides 설정
- 원형 차트를 사용하여 PowerPoint 프레젠테이션을 만드는 단계
- 가독성 향상을 위한 데이터 레이블 및 시리즈 그룹 옵션 구성
- 프레젠테이션에서 파이 차트의 실제 적용

이제 환경 설정과 이러한 기능 구현에 대해 알아보겠습니다.

### 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- **파이썬 설치됨**: Python 3.6 이상을 권장합니다.
- **Python용 Aspose.Slides**: pip를 사용하여 설치:
  ```bash
  pip install aspose.slides
  ```
- **특허**: Aspose에서 무료 평가판 라이선스를 받아 제한 없이 모든 기능을 사용해 보세요.

#### 지식 전제 조건

Python 프로그래밍에 대한 기본적인 지식과 PowerPoint 프레젠테이션에 대한 이해가 있으면 도움이 될 것입니다. 이러한 분야를 처음 접한다면 먼저 입문 자료를 살펴보는 것을 고려해 보세요.

### Python용 Aspose.Slides 설정

Python용 Aspose.Slides를 시작하려면 다음 간단한 단계를 따르세요.

1. **설치**: pip를 사용하여 라이브러리를 설치합니다.
   ```bash
   pip install aspose.slides
   ```

2. **라이센스 취득**: 
   - 방문하다 [Aspose 구매 페이지](https://purchase.aspose.com/buy) 라이센스를 구매하거나 무료 임시 평가판을 받으세요.
   - 다음 코드 조각을 프로젝트에 사용하여 라이선스를 적용하세요.
     ```python
     import aspose.slides as slides

     # 라이센스 파일을 로드합니다
     license = slides.License()
     license.set_license("path_to_your_license.lic")
     ```

3. **기본 초기화**:
   Aspose.Slides를 가져와서 프레젠테이션 객체를 시작하는 것으로 시작합니다.

### 구현 가이드

#### 기능 1: 차트를 활용한 프레젠테이션 만들기

이 기능에서는 PowerPoint 프레젠테이션을 만들고 첫 번째 슬라이드에 원형 차트를 추가하는 방법을 보여줍니다.

##### 차트 추가

새 프레젠테이션을 만들고 첫 번째 슬라이드의 위치(50, 50)에 원형 차트를 추가하여 시작하세요.

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # 지정된 차원으로 '원형 차트' 추가
    chart = presentation.slides[0].shapes.add_chart(
        slides.charts.ChartType.PIE_OF_PIE, 50, 50, 500, 400)
```

##### 데이터 레이블 구성

가독성을 높이려면 데이터 레이블을 구성하여 값을 표시하세요.

```python
# 더 나은 명확성을 위해 데이터 레이블에 값 표시를 활성화하세요.
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```

##### 파이 오브 파이 옵션 설정

두 번째 원형 차트 크기 및 분할 위치 등 원형 차트의 특정 속성을 구성합니다.

```python
# 두 번째 파이 크기 및 분할 속성 설정
chart.chart_data.series[0].parent_series_group.second_pie_size = 149
chart.chart_data.series[0].parent_series_group.pie_split_by = slides.charts.PieSplitType.BY_PERCENTAGE
chart.chart_data.series[0].parent_series_group.pie_split_position = 53
```

##### 프레젠테이션 저장

마지막으로, 원하는 디렉토리에 프레젠테이션을 저장합니다.

```python
# 차트와 함께 프레젠테이션을 저장합니다.
presentation.save("YOUR_OUTPUT_DIRECTORY/charts_second_plot_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### 실제 응용 프로그램

원형 차트는 다재다능하여 다양한 시나리오에서 사용할 수 있습니다.

1. **사업 보고서**: 다양한 부서나 제품에 대한 데이터 분포를 시각화합니다.
2. **학술 프로젝트**: 주요 주제와 덜 중요한 결과를 함께 보여주는 설문 조사 결과를 제시합니다.
3. **재무 분석**예산 보고서에서 1차 비용과 2차 비용을 비교합니다.

### 성능 고려 사항

Aspose.Slides를 사용할 때 최적의 성능을 얻으려면:

- 가능하다면 슬라이드와 차트의 수를 최소화하여 메모리 사용량을 줄이세요.
- 코드에서 사용되지 않는 리소스나 참조를 정기적으로 정리하세요.
- Python의 내장 가비지 수집을 사용하세요(`gc` 메모리를 효과적으로 관리하기 위한 모듈입니다.

### 결론

Aspose.Slides for Python을 사용하여 원형 차트가 포함된 파워포인트 프레젠테이션을 만드는 방법을 알아보았습니다. 이 기술은 프레젠테이션의 시각적 매력과 효과를 크게 향상시킬 수 있습니다. 애니메이션 추가나 멀티미디어 요소 통합 등 Aspose.Slides의 다양한 기능을 살펴보는 것도 좋습니다.

### 다음 단계

- Aspose.Slides에서 제공하는 다양한 차트 유형을 실험해 보세요.
- 이 기능을 더 큰 규모의 프레젠테이션 자동화 워크플로에 통합하세요.

### FAQ 섹션

**질문: 원형 차트의 색상을 사용자 지정할 수 있나요?**
A: 예, 차트 색상을 사용자 정의할 수 있습니다. `fill_format` 각 세그먼트의 속성.

**질문: Aspose.Slides를 사용하여 대용량 데이터 세트를 처리하려면 어떻게 해야 하나요?**
답변: 성능 유지를 위해 데이터 입력을 최적화하고 이를 더 작은 단위로 나누는 것을 고려하세요.

**질문: 여러 차트를 한 번에 자동으로 추가하는 방법이 있나요?**
A: 예, 데이터 세트를 반복하고 다음을 사용합니다. `add_chart` 단일 프레젠테이션 컨텍스트 내의 메서드.

### 자원

- **선적 서류 비치**: 자세한 가이드를 살펴보세요 [Aspose.Slides 문서](https://reference.aspose.com/slides/python-net/).
- **다운로드**: 최신 버전을 받으세요 [출시](https://releases.aspose.com/slides/python-net/).
- **구매 및 무료 체험**: 액세스 라이센스 옵션 [Aspose 구매](https://purchase.aspose.com/buy) 또는 시도해보세요 [무료 체험](https://releases.aspose.com/slides/python-net/).
- **지원하다**: 토론에 참여하세요 [Aspose 포럼](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}