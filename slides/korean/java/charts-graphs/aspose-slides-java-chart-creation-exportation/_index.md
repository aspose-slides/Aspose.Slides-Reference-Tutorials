---
"date": "2025-04-17"
"description": "Java에서 Aspose.Slides를 사용하여 차트를 만들고 내보내는 방법을 배우세요. 단계별 가이드와 코드 예제를 통해 데이터 시각화 기법을 마스터하세요."
"title": "Aspose.Slides Java&#58; 데이터 시각화를 위한 차트 만들기 및 내보내기"
"url": "/ko/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java를 사용하여 차트 만들기 및 내보내기

**Aspose.Slides for Java를 활용한 마스터 데이터 시각화 기술**

오늘날의 데이터 중심 환경에서 효과적인 데이터 시각화는 정보에 기반한 의사 결정을 내리는 데 필수적입니다. Java 애플리케이션에 차트 기능을 통합하면 원시 데이터를 매력적인 시각적 스토리로 변환할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 차트를 만들고 내보내는 방법을 안내하여 유익하면서도 시각적으로 매력적인 프레젠테이션을 만들 수 있도록 합니다.

**배울 내용:**
- 프레젠테이션 파일을 손쉽게 로드하고 조작하세요
- 슬라이드에 다양한 유형의 차트를 추가하세요
- 차트 데이터를 외부 통합 문서로 원활하게 내보내기
- 효율적인 데이터 관리를 위해 외부 통합 문서 경로 설정

시작해 볼까요!

## 필수 조건
시작하기에 앞서 다음 설정이 준비되어 있는지 확인하세요.

### 필수 라이브러리 및 버전
- **Java용 Aspose.Slides** 버전 25.4 이상

### 환경 설정 요구 사항
- Java Development Kit(JDK) 16 이상
- IntelliJ IDEA 또는 Eclipse와 같은 코드 편집기 또는 IDE

### 지식 전제 조건
- Java 프로그래밍에 대한 기본 이해
- Maven 또는 Gradle 빌드 시스템에 대한 지식

## Java용 Aspose.Slides 설정
Aspose.Slides를 사용하려면 프로젝트에 Aspose.Slides를 포함해야 합니다. 방법은 다음과 같습니다.

**메이븐**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**그래들**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 다음을 수행할 수 있습니다. [최신 버전을 직접 다운로드하세요](https://releases.aspose.com/slides/java/).

### 라이센스 취득 단계
Aspose.Slides는 모든 기능을 체험해 볼 수 있는 무료 체험판 라이선스를 제공합니다. 임시 라이선스를 신청하거나 장기 사용을 위해 라이선스를 구매할 수도 있습니다. 다음 단계를 따르세요.
1. 방문하세요 [Aspose 구매 페이지](https://purchase.aspose.com/buy) 면허를 취득하려면.
2. 무료 체험판을 원하시면 다음에서 다운로드하세요. [출시](https://releases.aspose.com/slides/java/).
3. 임시 면허 신청 [여기](https://purchase.aspose.com/temporary-license/).

라이선스 파일을 받으면 Java 애플리케이션에서 초기화하세요.
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## 구현 가이드
### 기능 1: 부하 표현
프레젠테이션을 로딩하는 것은 모든 조작 작업의 첫 번째 단계입니다.

#### 개요
이 기능은 Aspose.Slides for Java를 사용하여 기존 PowerPoint 파일을 로드하는 방법을 보여줍니다.

#### 단계별 구현
**슬라이드에 차트 추가**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // 문서 디렉토리 경로를 설정하세요
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // 기존 프레젠테이션 로드
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // 자원 정리
        if (pres != null) pres.dispose();
    }
}
```
**설명:**
- `Presentation` 귀하의 경로로 초기화됩니다 `.pptx` 파일.
- 항상 폐기하세요 `Presentation` 무료 리소스에 반대합니다.

### 기능 2: 슬라이드에 차트 추가
차트를 추가하면 데이터 표현이 크게 향상될 수 있습니다.

#### 개요
이 기능은 프레젠테이션의 첫 번째 슬라이드에 원형 차트를 추가하는 방법을 보여줍니다.

#### 단계별 구현
**슬라이드에 차트 추가**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // 문서 디렉토리 경로를 설정하세요
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // 위치(50, 50)에 너비 400, 높이 600의 원형 차트를 추가합니다.
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**설명:**
- `addChart` 파이 차트를 삽입하려면 이 방법을 사용합니다.
- 매개변수에는 차트 유형과 슬라이드에서의 위치/크기가 포함됩니다.

### 기능 3: 차트 데이터를 외부 통합 문서로 내보내기
데이터를 내보내면 PowerPoint 외부에서 추가 분석이 가능합니다.

#### 개요
이 기능은 프레젠테이션의 차트 데이터를 외부 Excel 통합 문서로 내보내는 방법을 보여줍니다.

#### 단계별 구현
**데이터 내보내기**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // 문서 디렉토리와 출력 디렉토리 경로를 설정하세요
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // 첫 번째 슬라이드 차트에 접근하세요
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // 외부 통합 문서의 경로 정의
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // 차트 데이터를 Excel 스트림으로 내보내기
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**설명:**
- `readWorkbookStream` 차트 데이터를 추출합니다.
- 데이터는 다음을 사용하여 Excel 파일에 기록됩니다. `FileOutputStream`.

### 기능 4: 차트 데이터에 대한 외부 통합 문서 설정
차트를 외부 통합 문서에 연결하면 데이터 관리가 간소화됩니다.

#### 개요
이 기능은 차트 데이터를 저장하기 위한 외부 통합 문서 경로를 설정하는 방법을 보여줍니다.

#### 단계별 구현
**외부 통합 문서 경로 설정**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // 문서 디렉토리 경로를 설정하세요
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // 첫 번째 슬라이드 차트에 접근하세요
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // 외부 통합 문서의 경로를 정의하고 설정합니다.
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**설명:**
- `setExternalWorkbook` 차트를 Excel 파일에 연결하여 동적 데이터 업데이트를 가능하게 합니다.

## 실제 응용 프로그램
Aspose.Slides는 다양한 시나리오에 맞는 다목적 솔루션을 제공합니다.

1. **사업 보고서:** Java 애플리케이션에서 직접 차트를 포함한 자세한 보고서를 작성합니다.
2. **학술 발표:** 대화형 차트로 교육 콘텐츠를 강화하세요.
3. **재무 분석:** 심층 분석을 위해 재무 데이터를 Excel로 내보내세요.
4. **마케팅 분석:** 동적 차트를 사용하여 캠페인 성과를 시각화하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}