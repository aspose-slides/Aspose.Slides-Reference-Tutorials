---
"date": "2025-04-23"
"description": "Aspose.Slides for Python을 사용하여 PowerPoint에서 차트를 만들고 맞춤 설정하는 방법을 알아보세요. 전문적인 시각 자료로 프레젠테이션을 손쉽게 개선해 보세요."
"title": "Aspose.Slides for Python으로 PowerPoint 차트를 마스터하세요. 쉽게 만들고 사용자 지정하세요."
"url": "/ko/python-net/charts-graphs/create-customize-powerpoint-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 PowerPoint에서 차트 만들기 및 사용자 지정 마스터하기

## 소개
시각적으로 매력적인 프레젠테이션을 만드는 것은 효과적인 소통을 위해 필수적입니다. 회의실에서 프레젠테이션을 하든 고객과 데이터 통찰력을 공유하든 마찬가지입니다. 가장 큰 어려움은 데이터를 정확하게 표현하는 매력적인 차트를 파워포인트 슬라이드에 통합하는 것입니다. **Python용 Aspose.Slides**, 이 작업은 원활하고 효율적으로 진행됩니다.

이 포괄적인 튜토리얼에서는 Aspose.Slides Python을 사용하여 PowerPoint 차트를 손쉽게 만들고 사용자 지정하는 방법을 살펴봅니다. 이 강력한 라이브러리는 전문가 수준의 시각 자료로 프레젠테이션을 더욱 돋보이게 하는 강력한 기능을 제공합니다.

**배울 내용:**
- Python용 Aspose.Slides 설정 방법
- 슬라이드 내에서 선형 차트 만들기
- 기존 차트 데이터 수정
- 이미지를 사용하여 사용자 정의 마커 설정
- 이러한 기술의 실제 적용

파워포인트 차트를 더욱 멋지게 만들 준비가 되셨나요? 자, 이제 필수 조건을 살펴보고 시작해 볼까요!

## 필수 조건
시작하기에 앞서, 따라하기 위해 필요한 도구와 지식이 있는지 확인하세요.

1. **파이썬 설치**: 시스템에 Python이 설치되어 있는지 확인하세요(버전 3.6 이상 권장).
2. **Python용 Aspose.Slides**: pip를 통해 설치:
   ```bash
   pip install aspose.slides
   ```
3. **개발 환경**: VSCode나 PyCharm과 같은 IDE를 사용하면 코드 관리가 더 쉬워집니다.
4. **기본 파이썬 지식**Python 구문과 프로그래밍 개념에 익숙해야 합니다.

## Python용 Aspose.Slides 설정
시작하려면 개발 환경에서 Python용 Aspose.Slides를 설정해야 합니다.

### 설치
pip를 사용하여 라이브러리를 설치하세요:
```bash
pip install aspose.slides
```

### 라이센스 취득
Aspose.Slides는 다양한 라이선스 옵션을 제공합니다.
- **무료 체험**: 기능이 제한된 테스트 기능입니다.
- **임시 면허**: 테스트 기간 동안 모든 기능에 액세스할 수 있는 무료 임시 라이선스를 받으세요.
- **구입**: 지속적으로 사용하려면 구독을 구매하는 것을 고려해 보세요.

**기본 초기화 및 설정:**
```python
import aspose.slides as slides

# 프레젠테이션 객체 초기화
with slides.Presentation() as presentation:
    # 여기에 코드를 추가하여 프레젠테이션을 조작하세요.
    pass
```

## 구현 가이드
구현을 세 가지 주요 기능으로 나누어 보겠습니다.

### 차트 만들기 및 추가
#### 개요
이 기능은 PowerPoint 슬라이드에 마커가 있는 선형 차트를 추가하는 방법을 보여줍니다.

**단계:**
1. **오픈 프레젠테이션**새 프레젠테이션이나 기존 프레젠테이션을 열어보세요.
2. **슬라이드 선택**: 차트를 추가할 슬라이드를 선택하세요.
3. **선형 차트 추가**: 사용 `add_chart` 차트를 삽입하는 방법.
4. **프레젠테이션 저장**: 업데이트된 슬라이드에 변경 사항을 저장합니다.

**코드 구현:**
```python
import aspose.slides as slides

def add_chart_to_slide():
    # 새로운 프레젠테이션을 엽니다
    with slides.Presentation() as presentation:
        # 첫 번째 슬라이드를 선택하세요
        slide = presentation.slides[0]
        
        # 선택한 슬라이드에 위치(0, 0) 및 크기(400, 400)에 마커가 있는 선형 차트를 추가합니다.
        chart = slide.shapes.add_chart(
            slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400
        )
        
        # 추가된 차트가 포함된 프레젠테이션을 디스크에 저장합니다.
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_marker_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### 차트 데이터 수정
#### 개요
기존 데이터를 지우고 차트에 새로운 일련의 점을 추가하는 방법을 알아보세요.

**단계:**
1. **액세스 차트**: 슬라이드에서 차트를 검색합니다.
2. **기존 시리즈 지우기**: 기존 데이터 시리즈를 제거합니다.
3. **새로운 데이터 포인트 추가**: 시리즈에 새로운 데이터를 삽입합니다.
4. **변경 사항 저장**: 프레젠테이션 파일의 변경 사항을 유지합니다.

**코드 구현:**
```python
import aspose.slides as slides

def modify_chart_data():
    with slides.Presentation() as presentation:
        slide = presentation.slides[0]
        chart = slide.shapes.add_chart(slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400)
        
        # 차트 데이터의 기본 워크시트 인덱스에 액세스
        default_worksheet_index = 0
        fact = chart.chart_data.chart_data_workbook
        
        # 차트에서 기존 시리즈를 모두 지웁니다.
        chart.chart_data.series.clear()
        
        # 지정된 이름과 유형으로 차트에 새 시리즈를 추가합니다.
        chart.chart_data.series.add(fact.get_cell(default_worksheet_index, 1, 1, "Series 1"), chart.type)
        
        # 차트 데이터의 첫 번째(그리고 유일한) 시리즈에 액세스합니다.
        series = chart.chart_data.series[0]
        
        # 시리즈에 데이터 포인트를 추가하고 값을 설정합니다.
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 1, 1, 4.5))
        point.value = 4.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 2, 1, 2.5))
        point.value = 2.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 3, 1, 3.5))
        point.value = 3.5
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 4, 1, 4.5))
        point.value = 4.5
        
        # 업데이트된 프레젠테이션을 디스크에 저장
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_marker_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### 이미지로 차트 마커 설정
#### 개요
데이터 포인트에 사용자 정의 이미지 마커를 설정하여 차트를 더욱 풍부하게 만들어 보세요.

**단계:**
1. **선형 차트 추가**: 슬라이드에 선형 차트를 삽입합니다.
2. **이미지 로드**: 문서 디렉토리에서 마커로 사용할 이미지를 추가합니다.
3. **이미지 마커 설정**: 이러한 이미지를 시리즈의 특정 데이터 포인트에 적용합니다.
4. **마커 크기 조정**: 더 나은 가시성을 위해 이미지 마커의 크기를 사용자 정의합니다.

**코드 구현:**
```python
import aspose.slides as slides

def set_chart_markers_with_images():
    # 새로운 프레젠테이션을 엽니다
    with slides.Presentation() as presentation:
        slide = presentation.slides[0]
        
        # 선택한 슬라이드에 위치(0, 0) 및 크기(400, 400)에 마커가 있는 선형 차트를 추가합니다.
        chart = slide.shapes.add_chart(
            slides.charts.ChartType.LINE_WITH_MARKERS, 0, 0, 400, 400
        )
        
        # 차트 데이터의 기본 워크시트 인덱스에 액세스
        default_worksheet_index = 0
        fact = chart.chart_data.chart_data_workbook
        
        # 차트에서 기존 시리즈를 지우고 새 시리즈를 추가합니다.
        chart.chart_data.series.clear()
        chart.chart_data.series.add(fact.get_cell(default_worksheet_index, 1, 1, "Series 1"), chart.type)
        
        # 차트 데이터의 첫 번째(그리고 유일한) 시리즈에 액세스합니다.
        series = chart.chart_data.series[0]
        
        # 이미지를 로드하여 프레젠테이션의 이미지 컬렉션에 추가합니다.
        image1 = slides.Images.from_file("YOUR_DOCUMENT_DIRECTORY/image1.jpg")
        imgx1 = presentation.images.add_image(image1)
        
        image2 = slides.Images.from_file("YOUR_DOCUMENT_DIRECTORY/image2.jpg")
        imgx2 = presentation.images.add_image(image2)
        
        # 데이터 포인트를 추가하고 마커 이미지를 설정합니다.
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 1, 1, 4.5))
        point.marker.format.fill.fill_type = slides.FillType.PICTURE
        point.marker.format.fill.picture_fill_format.picture.image = imgx1
        
        point = series.data_points.add_data_point_for_line_series(fact.get_cell(default_worksheet_index, 2, 1, 2.5))
        point.marker.format.fill.fill_type = slides.FillType.PICTURE
        point.marker.format.fill.picture_fill_format.picture.image = imgx2
        
        # 사용자 정의된 마커가 포함된 프레젠테이션을 디스크에 저장합니다.
        presentation.save("YOUR_OUTPUT_DIRECTORY/charts_with_image_markers_out.pptx", slides.export.SaveFormat.PPTX)
```

## 결론
이 튜토리얼을 따라 하면 이제 Python용 Aspose.Slides를 사용하여 PowerPoint에서 차트를 만들고 사용자 정의하는 데 필요한 탄탄한 기반을 갖추게 됩니다. 새로운 데이터 시리즈를 추가하거나 이미지 마커를 사용하여 시각화를 강화하는 등, 이러한 기술을 활용하면 더욱 효과적인 프레젠테이션을 만들 수 있습니다.

## 키워드 추천
- "Python용 Aspose.Slides"
- "PowerPoint 차트 사용자 지정"
- "Python을 사용하여 PowerPoint에서 차트 만들기"
- "파이썬 프레젠테이션 향상"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}