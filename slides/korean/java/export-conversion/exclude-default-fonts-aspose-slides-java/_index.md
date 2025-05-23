---
"date": "2025-04-17"
"description": "Aspose.Slides for Java를 사용하여 HTML 변환 중에 기본 글꼴을 제외하고 플랫폼 전체에서 일관된 인쇄 체계를 보장하는 방법을 알아보세요."
"title": "Java용 Aspose.Slides를 사용하여 HTML 변환에서 기본 글꼴을 제외하는 방법"
"url": "/ko/java/export-conversion/exclude-default-fonts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java용 Aspose.Slides를 사용하여 HTML 변환에서 기본 글꼴을 제외하는 방법
## 소개
프레젠테이션을 HTML로 변환할 때 기본 글꼴 설정으로 인해 사용자 지정 글꼴을 유지하는 것이 매우 중요합니다. 이 가이드에서는 Aspose.Slides for Java를 사용하여 이러한 기본 글꼴을 제거하고 다양한 플랫폼에서 일관된 타이포그래피를 유지하는 방법을 보여줍니다.
**배울 내용:**
- Aspose.Slides for Java를 사용하여 환경 설정하기
- HTML 변환 중 기본 글꼴을 제외하는 기술
- 주요 구성 옵션 및 출력에 미치는 영향
- 실제 시나리오에서의 실용적인 응용 프로그램
구현 가이드를 살펴보기에 앞서 전제 조건부터 논의해 보겠습니다.
## 필수 조건
이 튜토리얼을 효과적으로 따르려면 다음 사항이 있는지 확인하세요.
- **Java용 Aspose.Slides 라이브러리**: 25.4 버전 이상을 설치하세요.
- **자바 개발 키트(JDK)**: 이 코드 예제는 JDK 16을 대상으로 합니다. 컴퓨터에 설치되어 있는지 확인하세요.
- **기본 자바 프로그래밍 지식**: Java 구문과 기본 프로그래밍 개념에 익숙하다고 가정합니다.
## Java용 Aspose.Slides 설정
### 종속성 설치
**메이븐:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
**그래들:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
또는 라이브러리를 다음에서 직접 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).
### 라이센스 취득
무료 체험판을 이용하거나 임시 라이선스를 요청하여 모든 기능을 제한 없이 사용해 보세요. 장기 사용 시 라이선스 구매를 권장합니다.
**기본 설정:**
프로젝트에서 Aspose.Slides를 초기화하려면:
```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation pres = new Presentation("your-pptx-file-path");
        // 프레젠테이션을 조작하는 코드
    }
}
```
## 구현 가이드
### 기능 개요: HTML 변환에서 기본 글꼴 제외
이 기능은 PowerPoint 파일을 HTML로 변환하는 동안 글꼴 처리를 사용자 지정하여 브랜딩과 일관성을 강화하는 데 도움이 됩니다.
#### 1단계: 환경 준비
위의 지침에 따라 Aspose.Slides가 올바르게 설정되었는지 확인하세요. 여기에는 종속성을 추가하거나 JAR 파일을 프로젝트에 직접 다운로드하는 작업이 포함됩니다.
#### 2단계: 프레젠테이션 로드
다음을 사용하여 프레젠테이션을 로드하세요. `Presentation` 수업:
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/presentation.pptx";
try {
    Presentation pres = new Presentation(dataDir);
```
#### 3단계: 글꼴 제외 정의
제외할 글꼴을 지정하는 배열을 만듭니다. 이 예제에서는 빈 목록을 자리 표시자로 사용합니다.
```java
String[] fontNameExcludeList = {};
```
#### 4단계: 사용자 지정 HTML 컨트롤러 초기화
그만큼 `LinkAllFontsHtmlController` 클래스는 변환 과정에서 사용자 정의 글꼴을 처리하는 데 사용됩니다.
```java
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, "YOUR_DOCUMENT_DIRECTORY");
```
#### 5단계: HTML 옵션 구성
설정하세요 `HtmlOptions` 사용자 정의 포맷터를 사용하려면:
```java
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(linkcont));
```
#### 6단계: HTML로 저장
마지막으로, 변환된 프레젠테이션을 HTML 형식으로 저장합니다.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/pres.html", SaveFormat.Html, htmlOptionsEmbed);
} catch (Exception e) {
    e.printStackTrace();
}
```
**설명:** 이 코드 조각은 HTML 변환 중에 사용자 정의 포매터를 구성하여 기본 글꼴을 제외하는 방법을 보여줍니다.
## 실제 응용 프로그램
1. **웹 기반 프레젠테이션**: 브랜드 일관성을 유지하면서 기업 웹사이트에 프레젠테이션을 삽입합니다.
2. **문서 이식성**: 다양한 기기와 플랫폼에서 문서가 동일하게 보이는지 확인합니다.
3. **CMS와의 통합**: 사용자 정의 글꼴이 필수적인 콘텐츠 관리 시스템에 원활하게 통합됩니다.
## 성능 고려 사항
- **메모리 사용 최적화**: Aspose.Slides의 메모리 관리 기능을 사용하면 대용량 프레젠테이션을 효율적으로 처리할 수 있습니다.
- **자원 관리**: 작업 후 스트림을 제대로 닫아 리소스를 확보합니다.
- **모범 사례**: 성능 향상 및 버그 수정을 위해 라이브러리 버전을 정기적으로 업데이트하세요.
## 결론
Aspose.Slides for Java를 사용하여 HTML 변환 시 기본 글꼴을 제외하는 방법을 알아보았습니다. 이 기능은 다양한 플랫폼에서 프레젠테이션의 일관성을 향상시켜 브랜딩 및 전문적인 문서 작성에 매우 중요합니다.
기술을 더욱 향상시키려면 Aspose.Slides의 다른 기능을 살펴보거나 이 기능을 대규모 프로젝트에 통합하세요.
**다음 단계:**
다양한 글꼴 제외 기능을 실험해 보고 최종 HTML 출력 결과에 어떤 영향을 미치는지 확인해 보세요. 이러한 기술을 자동화된 워크플로에 통합하여 문서 변환 프로세스를 간소화하는 것을 고려해 보세요.
## FAQ 섹션
1. **Java용 Aspose.Slides란 무엇인가요?**
   - Java 애플리케이션에서 프레젠테이션을 조작하는 강력한 라이브러리입니다.
2. **장기 사용 라이센스는 어떻게 얻을 수 있나요?**
   - 방문하세요 [구매 페이지](https://purchase.aspose.com/buy) 라이선스 옵션을 구매하거나 문의하세요.
3. **여러 글꼴을 동시에 제외할 수 있나요?**
   - 예, 제외하려는 모든 글꼴 이름을 추가합니다. `fontNameExcludeList` 정렬.
4. **HTML 출력에 글꼴이 누락된 경우 어떻게 해야 합니까?**
   - 사용자 지정 HTML 컨트롤러가 올바르게 구성되었고 경로가 정확하게 설정되었는지 확인하세요.
5. **글꼴을 제외하면 성능에 영향이 있나요?**
   - 대용량 글꼴 라이브러리는 성능에 영향을 줄 수 있습니다. Aspose의 메모리 관리 기능을 사용하여 필요에 따라 최적화하세요.
## 자원
- [선적 서류 비치](https://reference.aspose.com/slides/java/)
- [라이브러리 다운로드](https://releases.aspose.com/slides/java/)
- [라이센스 구매](https://purchase.aspose.com/buy)
- [무료 체험](https://releases.aspose.com/slides/java/)
- [임시 면허](https://purchase.aspose.com/temporary-license/)
- [지원 포럼](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}