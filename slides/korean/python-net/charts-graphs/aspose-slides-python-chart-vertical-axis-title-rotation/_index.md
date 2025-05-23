---
"date": "2025-04-23"
"description": "Python용 Aspose.Slides를 사용하여 프레젠테이션의 차트 제목 회전 각도를 조정하는 방법을 알아보고 가독성과 미적 감각을 향상시켜 보세요."
"title": "Python용 Aspose.Slides에서 차트의 세로 축 제목 회전을 설정하는 방법"
"url": "/ko/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides에서 차트의 세로 축 제목 회전을 설정하는 방법

## 소개

데이터 프레젠테이션에서 차트 가독성을 개선하는 것은 매우 중요합니다. Aspose.Slides for Python을 사용하여 차트 세로축 제목의 회전 각도를 조정하면 제목이 슬라이드에 깔끔하게 맞도록 하거나 눈에 띄도록 할 수 있습니다. 이 튜토리얼에서는 기능과 시각적 매력을 모두 향상시키기 위해 회전 각도를 설정하는 방법을 안내합니다.

**배울 내용:**
- Python에 Aspose.Slides를 설치하고 구성하는 방법.
- 슬라이드에 차트를 추가하고 사용자 지정하는 단계입니다.
- 차트 제목의 회전 각도를 설정하는 기술.
- 데이터 시각화에서 이러한 기능에 대한 실제 응용 프로그램.

구현에 들어가기에 앞서 전제 조건부터 살펴보겠습니다.

## 필수 조건

시작하기 전에 다음 사항을 확인하세요.
- **파이썬 환경**: Python 3.x를 설치하세요 [파이썬.org](https://www.python.org/).
- **Aspose.Slides 라이브러리**: pip를 통해 설치하여 프레젠테이션을 효과적으로 조작할 수 있습니다.
- **파이썬 프로그래밍에 대한 기본 지식**: Python 구문과 파일 작업에 익숙하면 따라가는 데 도움이 됩니다.

## Python용 Aspose.Slides 설정

Aspose.Slides를 사용하려면 pip를 사용하여 설치하세요. 터미널이나 명령 프롬프트를 열고 다음을 실행하세요.

```bash
pip install aspose.slides
```

### 라이센스 취득 단계

Aspose는 다양한 라이선스 옵션을 제공합니다.
- **무료 체험**: 평가판을 다운로드하세요 [Aspose의 릴리스 페이지](https://releases.aspose.com/slides/python-net/).
- **임시 면허**: 확장 기능에 대한 임시 라이센스를 얻으십시오. [구매 포털](https://purchase.aspose.com/temporary-license/).
- **구입**: 도구가 필수적이라고 생각되면 구매를 고려하십시오. [Aspose 구매 페이지](https://purchase.aspose.com/buy).

#### 기본 초기화 및 설정

Python 스크립트에서 Aspose.Slides를 초기화하는 방법은 다음과 같습니다.

```python
import aspose.slides as slides

# 프레젠테이션 객체를 생성합니다
def main():
    with slides.Presentation() as pres:
        # 여기에 코드가 들어갑니다
        pass

if __name__ == "__main__":
    main()
```

## 구현 가이드

### 차트 추가 및 사용자 지정

#### 개요

이 섹션에서는 슬라이드에 클러스터형 막대형 차트를 추가하고 세로 축 제목의 회전 각도를 설정하여 차트를 사용자 지정하겠습니다.

#### 단계:

##### 1단계: 클러스터형 막대형 차트 추가

정의된 치수를 사용하여 특정 좌표에 차트를 추가하여 시작합니다.

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # 슬라이드 1에 클러스터형 막대형 차트 추가
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### 2단계: 세로 축 제목 구성

수직 축 제목에 대한 회전 각도를 활성화하고 설정합니다.

```python
def configure_chart(chart):
    # 세로축 제목 활성화
    chart.axes.vertical_axis.has_title = True
    
    # 회전 각도를 90도로 설정하세요
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### 3단계: 프레젠테이션 저장

마지막으로, 변경 사항을 적용하여 프레젠테이션을 저장합니다.

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # 프레젠테이션을 저장하세요
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}