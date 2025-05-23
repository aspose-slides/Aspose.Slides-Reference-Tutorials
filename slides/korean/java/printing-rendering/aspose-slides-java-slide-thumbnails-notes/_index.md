---
"date": "2025-04-17"
"description": "Aspose.Slides for Java를 사용하여 노트가 포함된 슬라이드 썸네일을 생성하는 방법을 알아보세요. 이 가이드에서는 설정, 구성 및 실제 활용 사례를 다룹니다."
"title": "Aspose.Slides Java를 사용하여 노트가 포함된 슬라이드 썸네일 만들기 단계별 가이드"
"url": "/ko/java/printing-rendering/aspose-slides-java-slide-thumbnails-notes/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java를 사용하여 노트가 포함된 슬라이드 썸네일 만들기
## 인쇄 및 렌더링
### 단계별 가이드
오늘날처럼 빠르게 변화하는 디지털 세상에서 프레젠테이션 콘텐츠를 효율적으로 관리하고 공유하는 것은 매우 중요합니다. PowerPoint 프레젠테이션을 통합하는 개발자이든, 노트가 포함된 슬라이드 썸네일을 추출하는 프로세스를 자동화하는 개발자이든, **Java용 Aspose.Slides** 이러한 작업을 간소화하는 강력한 기능을 제공합니다. 이 포괄적인 튜토리얼에서는 Aspose.Slides를 사용하여 슬라이드 썸네일을 생성하고 하단에 노트를 표시하는 방법과 슬라이드의 기본 글꼴 설정을 변경하는 방법을 안내합니다.

## 당신이 배울 것
- 노트가 표시된 슬라이드 썸네일을 검색하는 방법
- 슬라이드 렌더링에서 기본 일반 글꼴 변경
- Java용 Aspose.Slides 설정 및 구성
- 이러한 기능의 실제 응용 프로그램

시작하기 전에 전제 조건을 살펴보겠습니다.

### 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- **Java용 Aspose.Slides** 라이브러리: 25.4 버전 이상이 필요합니다.
- 시스템에 설치된 Java 개발 키트(JDK)
- Java 프로그래밍에 대한 기본 지식과 Maven 또는 Gradle 빌드 도구에 대한 익숙함

## Java용 Aspose.Slides 설정
Aspose.Slides를 사용하려면 먼저 프로젝트에 라이브러리를 포함해야 합니다.

### Maven 종속성
이것을 당신의 것에 추가하세요 `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle 종속성
이것을 당신의 것에 포함시키세요 `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### 직접 다운로드
또는 다음에서 최신 라이브러리를 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

#### 라이센스 취득
무료 체험판을 시작하거나 임시 라이선스를 요청하여 모든 기능을 사용해 보세요. 계속 사용하려면 라이선스 구매를 고려해 보세요.

#### 기본 초기화 및 설정
```java
import com.aspose.slides.Presentation;
// 프레젠테이션 파일을 로드하세요
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/RenderingOptions.pptx");
```
## 구현 가이드
### 노트 레이아웃으로 슬라이드 축소판 가져오기
이 기능을 사용하면 슬라이드 축소판 그림을 생성하는 동시에 하단에 메모를 표시하여 맥락과 추가 정보를 제공할 수 있습니다.
#### 1단계: 프레젠테이션 로드
먼저 Aspose.Slides를 사용하여 프레젠테이션 파일을 로드합니다.
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
String presPath = "YOUR_DOCUMENT_DIRECTORY/RenderingOptions.pptx";
Presentation pres = new Presentation(presPath);
```
#### 2단계: 렌더링 옵션 구성
다음으로, 하단에 메모를 포함하도록 렌더링 옵션을 설정합니다.
```java
import com.aspose.slides.IRenderingOptions;
import com.aspose.slides.RenderingOptions;
IRenderingOptions renderingOpts = new RenderingOptions();
INotesCommentsLayoutingOptions notesOptions = new NotesCommentsLayoutingOptions();
// 잘라낼 노트의 위치를 아래쪽으로 설정하세요
notesOptions.setNotesPosition(NotesPositions.BottomTruncated);
renderingOpts.setSlidesLayoutOptions(notesOptions);
```
#### 3단계: 썸네일 검색 및 저장
마지막으로, 원하는 크기로 슬라이드 이미지를 검색하여 저장합니다.
```java
import com.aspose.slides.IImage;
import java.io.IOException;
// 출력 경로 및 형식 지정
String outputPath = "YOUR_OUTPUT_DIRECTORY/RenderingOptions-Slide1-Original.png";
try {
    IImage image = pres.getSlides().get_Item(0).getImage(renderingOpts, 4 / 3f, 4 / 3f);
    image.save(outputPath, com.aspose.slides.export.ImageFormat.getPng());
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
### 기본 일반 글꼴 변경
이 기능은 슬라이드 축소판 렌더링에 사용되는 기본 일반 글꼴을 변경하는 방법을 보여줍니다.
#### 1단계: 프레젠테이션 로드
이전 섹션과 비슷하게 프레젠테이션 파일을 로드하여 시작하세요.
```java
String presPath = "YOUR_DOCUMENT_DIRECTORY/RenderingOptions.pptx";
Presentation pres = new Presentation(presPath);
```
#### 2단계: 기본 일반 글꼴 설정
Arial Black이나 Arial Narrow와 같은 특정 글꼴을 사용하도록 렌더링 옵션을 구성합니다.
```java
IRenderingOptions renderingOpts = new RenderingOptions();
renderingOpts.setDefaultRegularFont("Arial Black");
```
#### 3단계: 새 글꼴 설정으로 썸네일 검색 및 저장
업데이트된 글꼴 설정을 사용하여 슬라이드 이미지를 저장합니다.
```java
String outputPath = "YOUR_OUTPUT_DIRECTORY/RenderingOptions-Slide1-ArialBlackDefault.png";
try {
    IImage image = pres.getSlides().get_Item(0).getImage(renderingOpts, 4 / 3f, 4 / 3f);
    image.save(outputPath, com.aspose.slides.export.ImageFormat.getPng());
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## 실제 응용 프로그램
이러한 기능은 다음과 같은 다양한 애플리케이션에 통합될 수 있습니다.
- **콘텐츠 관리 시스템**: CMS에 저장된 프레젠테이션의 썸네일을 자동으로 생성합니다.
- **문서 보관 솔루션**: 쉽게 검색할 수 있도록 메모와 함께 인덱스된 썸네일을 만듭니다.
- **협업 도구**: 상황에 맞는 메모를 포함하여 프레젠테이션 공유를 향상시킵니다.
Aspose.Slides를 클라우드 스토리지 솔루션, 자동 보고서 생성기, 맞춤형 문서 관리 시스템과 결합하면 생산성을 더욱 높일 수 있습니다.
## 성능 고려 사항
Aspose.Slides를 사용할 때 성능을 최적화하려면:
- 프레젠테이션을 신속하게 폐기하여 효율적인 메모리 관리를 보장하세요.
- 애플리케이션의 요구 사항에 따라 적절한 이미지 형식과 해상도를 사용하세요.
- 가능한 경우 멀티스레딩을 활용하여 여러 슬라이드를 동시에 처리합니다.
## 결론
이제 Aspose.Slides for Java를 사용하여 노트가 포함된 슬라이드 썸네일을 만들고 기본 글꼴을 변경하는 방법을 확실히 이해하셨을 것입니다. 이러한 기능은 다양한 애플리케이션에서 프레젠테이션 관리 프로세스를 크게 향상시킬 수 있습니다. 더 자세히 알아보려면 Aspose.Slides에서 제공하는 다른 렌더링 옵션을 실험해 보세요.
## FAQ 섹션
1. **기본 일반 글꼴을 설정할 때 글꼴 크기를 변경할 수 있나요?**
   - 네, 슬라이드 내의 특정 텍스트 요소에 접근하여 글꼴 크기와 스타일을 사용자 정의할 수 있습니다.
2. **프레젠테이션의 모든 슬라이드에 대한 썸네일을 렌더링하는 것이 가능합니까?**
   - 물론입니다! 각 슬라이드를 반복합니다. `pres.getSlides().size()` 그리고 그에 따라 렌더링 로직을 적용합니다.
3. **이미지를 저장할 때 예외가 발생하면 어떻게 처리하나요?**
   - 이미지 저장 코드 주변에 try-catch 블록을 사용하여 잠재적인 IOException을 우아하게 관리합니다.
4. **Aspose.Slides를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**
   - 네, .NET, C++ 등 여러 언어를 지원합니다.
5. **평가판 기간 이후에도 Aspose.Slides를 사용할 수 있는 라이선스 옵션은 무엇입니까?**
   - 라이선스를 구매하거나 구독 기반 모델을 선택하여 모든 기능을 사용할 수 있습니다.
## 자원
- [Aspose.Slides 문서](https://reference.aspose.com/slides/java/)
- [최신 버전 다운로드](https://releases.aspose.com/slides/java/)
- [라이센스 구매](https://purchase.aspose.com/buy)
- [무료 체험](https://releases.aspose.com/slides/java/)
- [임시 면허 요청](https://purchase.aspose.com/temporary-license/)
- [Aspose 지원 포럼](https://forum.aspose.com/c/slides/11)

Java 프로젝트에 Aspose.Slides를 구현하기 시작하면서 더 자세한 정보와 지원을 얻으려면 다음 리소스를 자유롭게 살펴보세요. 즐거운 코딩 되세요!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}