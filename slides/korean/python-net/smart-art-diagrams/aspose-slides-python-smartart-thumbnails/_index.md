---
"date": "2025-04-23"
"description": "Python용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 그래픽을 자동으로 만드는 방법을 알아보세요. 여기에는 효율적으로 축소판을 추출하고 저장하는 방법도 포함됩니다."
"title": "Python용 Aspose.Slides를 사용하여 SmartArt 썸네일을 만들고 검색하는 방법"
"url": "/ko/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 SmartArt 썸네일을 만들고 검색하는 방법

## 소개

시각적으로 매력적인 프레젠테이션을 만드는 것은 청중의 관심을 사로잡는 데 필수적입니다. 슬라이드 자료를 더욱 돋보이게 하는 효과적인 방법 중 하나는 PowerPoint 프레젠테이션에 SmartArt와 같은 역동적인 그래픽을 통합하는 것입니다. 이러한 시각 자료를 자동으로 생성하고 썸네일을 추출하는 방법을 찾고 있다면 "Aspose.Slides Python" 가이드가 매우 유용할 것입니다.

Python용 Aspose.Slides를 사용하면 SmartArt 그래픽을 손쉽게 제작하고, 그래픽 내 특정 노드에 접근하고, 해당 노드의 이미지 썸네일을 가져오고, 프로젝트에 저장할 수 있습니다. 이 튜토리얼에서는 각 단계를 자세히 안내합니다.

**배울 내용:**
- Python에 Aspose.Slides를 설치하고 설정하는 방법.
- PowerPoint 프레젠테이션에서 SmartArt 그래픽을 만드는 방법.
- SmartArt 그래픽 내의 노드에 접근합니다.
- 특정 노드에서 이미지 썸네일을 추출하여 저장합니다.

시작하기 전에 전제 조건을 살펴보겠습니다.

## 필수 조건

시작하기 전에 다음 사항을 준비하세요.

- **필수 라이브러리:** Python용 Aspose.Slides가 필요합니다. 사용 환경이 Python 3.x를 지원하는지 확인하세요.
- **환경 설정 요구 사항:** Python이 제대로 설치되어 있어야 하며 VSCode나 PyCharm과 같은 적합한 IDE나 텍스트 편집기가 필요합니다.
- **지식 전제 조건:** 함수 정의와 파일 작업을 포함한 Python 프로그래밍에 대한 기본적인 이해가 필요합니다.

## Python용 Aspose.Slides 설정

먼저 Aspose.Slides 라이브러리를 설치해야 합니다. pip를 사용하면 쉽게 설치할 수 있습니다.

```bash
pip install aspose.slides
```

설치 후 모든 기능을 제한 없이 사용하려면 라이선스를 구매하세요. 무료 체험판으로 시작하거나, 임시 라이선스를 신청하거나, 장기 사용을 위해 라이선스를 구매할 수 있습니다.

Python 환경에서 Aspose.Slides를 초기화하려면 스크립트 시작 부분에서 라이브러리를 가져옵니다.

```python
import aspose.slides as slides
```

## 구현 가이드

SmartArt 썸네일을 만들고 검색하는 과정을 명확한 단계로 나누어 살펴보겠습니다.

### 1단계: 새 프레젠테이션 인스턴스 만들기

프레젠테이션 인스턴스를 만들어 시작하세요. 이 인스턴스에 SmartArt 그래픽을 추가할 수 있습니다.

```python
with slides.Presentation() as pres:
```

사용 중 `with` 리소스가 적절하게 관리되도록 하고, 종료 시 자동으로 파일을 저장하고 닫습니다.

### 2단계: 첫 번째 슬라이드에 SmartArt 추가

다음으로, 첫 번째 슬라이드에 SmartArt 그래픽을 추가해 보겠습니다. 방법은 다음과 같습니다.

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

이렇게 하면 위치(10, 10)에 400x300픽셀 크기의 SmartArt 그래픽에 대한 기본 순환 레이아웃이 추가됩니다.

### 3단계: 두 번째 노드에 액세스

SmartArt 내의 특정 노드에 접근합니다. 이 예시에서는 두 번째 노드에 접근합니다.

```python
node = smart.nodes[1]
```

노드는 0부터 시작하여 인덱싱됩니다. 따라서, `nodes[1]` 목록의 두 번째 노드를 나타냅니다.

### 4단계: 이미지 썸네일 검색

선택한 노드 내의 모양의 이미지 썸네일을 얻으려면:

```python
image = node.shapes[0].get_image()
```

이는 지정된 SmartArt 노드에서 첫 번째 모양의 이미지를 썸네일로 검색합니다.

### 5단계: 검색된 이미지 저장

마지막으로, 이 썸네일을 JPEG 형식으로 원하는 위치에 저장합니다.

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}