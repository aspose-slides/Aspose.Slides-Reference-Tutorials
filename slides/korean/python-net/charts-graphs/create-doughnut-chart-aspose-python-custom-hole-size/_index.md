---
"date": "2025-04-22"
"description": "Aspose.Slides for Python을 사용하여 PowerPoint에서 도넛형 차트를 만들고 사용자 지정하는 방법을 알아보세요. 이 튜토리얼에서는 도넛형 차트의 구멍 크기 설정, 프레젠테이션 저장 및 모범 사례를 다룹니다."
"title": "Python용 Aspose.Slides를 사용하여 PowerPoint에서 사용자 지정 구멍 크기가 있는 도넛형 차트를 만드는 방법"
"url": "/ko/python-net/charts-graphs/create-doughnut-chart-aspose-python-custom-hole-size/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint에서 사용자 지정 구멍 크기가 있는 도넛형 차트를 만드는 방법

## 소개
PowerPoint에서 시각적으로 매력적인 차트를 만들면 데이터를 더욱 매력적이고 이해하기 쉽게 만들 수 있습니다. 프로그래밍 방식으로 차트를 생성할 때 흔히 발생하는 문제는 사용자 지정 옵션이 부족하다는 것입니다. 이 튜토리얼에서는 Aspose.Slides for Python을 사용하여 사용자 지정 구멍 크기가 있는 도넛형 차트를 만드는 방법을 보여줌으로써 이 문제를 해결합니다.

**키워드:** Aspose.Slides Python, 도넛형 차트, 사용자 정의 구멍 크기

### 배울 내용:
- Python용 Aspose.Slides 설정 및 사용
- PowerPoint에서 도넛형 차트 만들기
- 도넛 차트의 구멍 크기 사용자 지정
- 프레젠테이션 저장 및 내보내기 모범 사례

## 필수 조건
시작하기 전에 다음 사항을 확인하세요.
- **파이썬 3.x** 귀하의 시스템에 설치되었습니다.
- Python 프로그래밍 개념에 대한 기본 지식.
- 그만큼 `aspose.slides` 라이브러리(설치 지침은 아래에 제공됨).

## Python용 Aspose.Slides 설정
시작하려면 pip를 사용하여 Python용 Aspose.Slides를 설치하세요.

```bash
pip install aspose.slides
```

### 라이센스 취득
Aspose는 문서 수나 사용 시간에 제한 없이 기능을 탐색할 수 있는 무료 평가판을 제공합니다.
- **무료 체험:** 모든 기능을 테스트하려면 임시 라이센스로 시작하세요.
- **임시 면허:** 평가 목적으로 사용 가능합니다.
- **구입:** 장기적으로 사용하려면 라이선스 구매를 고려하세요.

설치 및 설정 후 프로그래밍 방식으로 프레젠테이션을 제작할 수 있습니다. Aspose.Slides를 초기화하는 방법은 다음과 같습니다.

```python
import aspose.slides as slides

# 프레젠테이션 객체를 초기화합니다
class PresentationCreator:
    def create_presentation(self):
        with slides.Presentation() as presentation:
            # 여기에 코드를 입력하세요
```

## 구현 가이드
이 섹션에서는 Aspose.Slides를 사용하여 PowerPoint에서 도넛형 차트를 만들고 사용자 지정하는 데 필요한 단계를 설명합니다.

### 1단계: 슬라이드 액세스 및 수정
시작하려면 프레젠테이션의 첫 번째 슬라이드에 액세스하세요. 여기에 사용자 지정 도넛형 차트를 추가할 것입니다.

```python
# 첫 번째 슬라이드에 접근하세요
class SlideModifier:
    def modify_slide(self, presentation):
        first_slide = presentation.slides[0]
```

### 2단계: 도넛 차트 추가
도넛형 차트는 위치와 크기를 지정하여 모든 슬라이드에 추가할 수 있습니다. 여기서는 좌표 (50, 50)에 400x400 크기로 배치하겠습니다.

```python
class ChartAdder:
    def add_doughnut_chart(self, first_slide):
        # 도넛 차트 추가
        chart = first_slide.shapes.add_chart(
            slides.charts.ChartType.DOUGHNUT,
            50, 50, 400, 400
        )
```

### 3단계: 구멍 크기 사용자 지정
도넛형 차트의 구멍 크기를 조정하는 것은 간단합니다. 뚜렷한 효과를 원하면 90%로 설정하세요.

```python
class ChartCustomizer:
    def customize_hole_size(self, chart):
        # 사용자 정의 구멍 크기 설정
        chart.chart_data.series_groups[0].doughnut_hole_size = 90
```

### 4단계: 프레젠테이션 저장
마지막으로, 선택한 파일 이름으로 원하는 위치에 프레젠테이션을 저장합니다.

```python
class PresentationSaver:
    def save_presentation(self, presentation):
        # 프레젠테이션을 저장하세요
        presentation.save(
            "charts_doughnut_chart_hole_out.pptx",
            slides.export.SaveFormat.PPTX
        )
```

## 실제 응용 프로그램
사용자 정의 도넛형 차트를 만드는 것은 다음을 포함한 다양한 시나리오에서 유용할 수 있습니다.
- **사업 보고서:** 시각적으로 구별되는 세그먼트를 통해 주요 성과 지표를 강조합니다.
- **교육적 내용:** 학생이나 동료에게 통계자료를 보여줍니다.
- **마케팅 자료:** 제품 세부 정보나 고객 인구 통계를 보여줍니다.

Aspose의 포괄적인 API를 사용하여 차트를 이미지로 내보내거나 웹 애플리케이션에 내장하면 다른 시스템과 통합할 수 있습니다.

## 성능 고려 사항
Aspose.Slides를 사용할 때 최적의 성능을 위해 다음 팁을 고려하세요.
- 필요한 슬라이드만 로딩하여 리소스 사용량을 최소화합니다.
- 사용 후 프레젠테이션을 즉시 닫아 메모리를 효과적으로 관리하세요.
- 일괄 처리를 활용하여 여러 차트를 한 번에 생성합니다.

모범 사례를 따르면 애플리케이션이 원활하고 효율적으로 실행됩니다.

## 결론
이 가이드를 따라 하면 Aspose.Slides for Python을 사용하여 PowerPoint에서 사용자 지정 구멍 크기가 있는 도넛형 차트를 만드는 방법을 배우게 됩니다. 이 방법은 프레젠테이션의 시각적 매력을 향상시킬 뿐만 아니라 데이터 표현의 유연성도 높여줍니다.

Aspose.Slides의 기능을 더 자세히 알아보려면 다른 차트 유형과 프레젠테이션 기능을 실험해 보세요. 즐거운 코딩 되세요!

## FAQ 섹션
1. **도넛형 차트에 설정할 수 있는 최대 구멍 크기는 얼마입니까?**
   - 전체 원형 차트의 경우 최대 100%까지 설정할 수 있습니다.
2. **Aspose.Slides를 사용하여 PowerPoint 파일의 기존 차트를 수정할 수 있나요?**
   - 네, 기존 프레젠테이션을 로드하여 편집할 수 있습니다.
3. **프레젠테이션을 저장할 때 오류를 어떻게 처리하나요?**
   - 출력 경로가 쓰기 가능한지 확인하고 권한 문제가 있는지 확인하세요.
4. **도넛형 차트 외에 다른 차트 유형도 지원되나요?**
   - 물론입니다. Aspose.Slides는 다양한 차트 유형을 지원합니다.
5. **Aspose.Slides를 웹 애플리케이션과 함께 사용할 수 있나요?**
   - 네, API는 백엔드 시스템에 통합되어 웹 서비스를 통해 공개될 수 있습니다.

## 자원
- [선적 서류 비치](https://reference.aspose.com/slides/python-net/)
- [다운로드](https://releases.aspose.com/slides/python-net/)
- [구입](https://purchase.aspose.com/buy)
- [무료 체험](https://releases.aspose.com/slides/python-net/)
- [임시 면허](https://purchase.aspose.com/temporary-license/)
- [지원 포럼](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}