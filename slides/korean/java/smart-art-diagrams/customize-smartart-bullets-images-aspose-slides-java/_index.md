---
"date": "2025-04-18"
"description": "Aspose.Slides for Java를 사용하여 SmartArt 글머리 기호를 이미지로 맞춤 설정하여 프레젠테이션을 더욱 돋보이게 하는 방법을 알아보세요. 전문가 수준의 프레젠테이션을 위한 단계별 가이드를 따라해 보세요."
"title": "Aspose.Slides for Java를 사용하여 이미지로 SmartArt 글머리 기호를 사용자 지정하는 방법 | 단계별 가이드"
"url": "/ko/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용하여 이미지로 SmartArt 글머리 기호를 사용자 지정하는 방법

## 소개

시각적으로 매력적인 프레젠테이션을 만드는 것은 청중의 관심을 사로잡고 메시지를 효과적으로 전달하는 데 매우 중요합니다. 슬라이드 디자인에서 흔히 겪는 어려움 중 하나는 사용자 지정 이미지를 사용하여 SmartArt 그래픽의 글머리 기호를 강조하는 것입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 SmartArt 노드에서 글머리 기호 채우기 서식을 그림으로 설정하는 방법을 안내합니다. 이를 통해 프레젠테이션을 더욱 전문적으로 향상시킬 수 있습니다.

**배울 내용:**
- Java용 Aspose.Slides 설정 및 사용
- SmartArt 그래픽에서 이미지를 사용하여 글머리 기호 사용자 지정
- 이 맞춤형 서비스의 실제 적용
- 일반적인 문제 해결

구현에 들어가기 전에 모든 것이 준비되었는지 확인하세요.

## 필수 조건

이 튜토리얼을 따라하려면 다음 전제 조건을 충족하는지 확인하세요.

1. **라이브러리 및 종속성**Aspose.Slides for Java 라이브러리 버전 25.4 이상이 필요합니다.
2. **환경 설정**:
   - IntelliJ IDEA 또는 Eclipse와 같은 호환 IDE
   - 컴퓨터에 JDK 16이 설치되어 있습니다
3. **지식 전제 조건**: Java 프로그래밍과 기본적인 PowerPoint 프레젠테이션 구조에 익숙함.

## Java용 Aspose.Slides 설정

시작하려면 다음 방법 중 하나를 사용하여 프로젝트에 Aspose.Slides 라이브러리를 포함하세요.

### 메이븐

이 종속성을 다음에 추가하세요. `pom.xml` 파일:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 그래들

이것을 당신의 것에 포함시키세요 `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드

또는 라이브러리를 다음에서 직접 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

**라이센스 취득 단계**: Aspose는 기능 테스트에 적합한 무료 평가판 라이선스를 제공합니다. 임시 라이선스를 요청하거나 구매하여 평가판의 제약을 해제할 수 있습니다.

환경을 초기화하고 설정하려면 인스턴스를 생성하세요. `Presentation` 표시된 대로 클래스:

```java
Presentation presentation = new Presentation();
```

## 구현 가이드

이 섹션에서는 원하는 기능을 달성하는 방법을 설명하면서 프로세스를 관리 가능한 단계로 나누어 설명합니다.

### 사용자 지정 글머리 기호 채우기로 SmartArt 추가

#### 개요

먼저 슬라이드에 SmartArt 도형을 추가하고 이미지 채우기를 사용하여 글머리 기호를 사용자 지정하는 것부터 시작해 보겠습니다.

#### 단계별 지침

**1. 프레젠테이션 객체 초기화**

```java
Presentation presentation = new Presentation();
```

*목적*: SmartArt 그래픽을 추가할 새 프레젠테이션 인스턴스를 초기화합니다.

**2. SmartArt 모양 추가**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*설명*: 이 줄은 첫 번째 슬라이드에 위치(x=10, y=10)에 500x400픽셀 크기의 새로운 SmartArt 도형을 추가합니다. `VerticalPictureList` 레이아웃은 수직 정렬에 사용됩니다.

**3. 글머리 기호 채우기 액세스 및 사용자 지정**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*목적*: 노드에 다음이 있는지 확인합니다. `BulletFillFormat` 속성입니다. 그렇다면 이미지를 로드하여 글머리 기호 채우기로 설정합니다.
*매개변수*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`: 이미지 파일의 경로입니다.
  - `PictureFillMode.Stretch`: 이미지가 글머리 기호 영역을 완전히 채우도록 합니다.

**4. 프레젠테이션 저장**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}