---
date: '2026-02-17'
description: Aspose.Slides for Java를 사용하여 파이 차트가 포함된 PowerPoint 프레젠테이션을 추가하는 방법을 배워보세요.
  단계별 가이드를 따라 전문적인 파이 차트를 만들고 맞춤 설정하세요.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Aspose.Slides for Java를 사용하여 PowerPoint에 파이 차트 추가하는 방법
url: /ko/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint에서 Aspose.Slides for Java를 사용하여 파이 차트 만들기 및 사용자 지정

## 소개

PowerPoint 프레젠테이션에서 데이터를 효과적으로 시각화하는 데 어려움을 겪고 계신가요? **Adding a pie chart PowerPoint** 슬라이드를 추가하면 원시 데이터를 즉시 명확한 시각 스토리로 바꿀 수 있습니다. Aspose.Slides for Java를 사용하면 프로그래밍 방식으로 **add pie chart PowerPoint** 파일을 추가할 수 있어 PowerPoint를 직접 열지 않고도 디자인과 데이터를 완전히 제어할 수 있습니다. 이 튜토리얼에서는 라이브러리 설정부터 개별 데이터 포인트 사용자 지정까지 전체 과정을 단계별로 안내하므로 몇 분 안에 다듬어진 데이터 기반 슬라이드를 제공할 수 있습니다.

### 빠른 답변
- **필요한 라이브러리는 무엇인가요?** Aspose.Slides for Java (latest version).  
- **PowerPoint를 설치하지 않고 차트를 만들 수 있나요?** Yes, the API works completely offline.  
- **필요한 Java 버전은?** JDK 16 or later is recommended.  
- **슬라이스 색상을 어떻게 변경하나요?** Use the `setFillType` and `setSolidFillColor` methods on the data point.  
- **라이선스가 필수인가요?** A trial works for development; a permanent license removes evaluation limits.

### 배울 내용
- **add pie chart PowerPoint**를 Java로 프로그래밍 방식으로 추가하는 방법.  
- 슬라이스 폭발, 색상 및 기타 시각 속성을 사용자 지정하는 방법.  
- 대용량 프레젠테이션을 처리할 때 리소스 관리 및 성능에 대한 모범 사례.

## 왜 Aspose.Slides for Java를 사용하여 파이 차트를 PowerPoint에 추가하나요?
코드에서 직접 파이 차트를 삽입하면 최신 보고서를 생성하고, 월간 대시보드를 자동화하거나, 즉석에서 맞춤형 슬라이드 데크를 만들 수 있습니다. 수동 복사‑붙여넣기 오류를 없애고, 프레젠테이션 전반에 걸쳐 일관성을 보장하며, 기존 Java 백엔드와 원활하게 통합됩니다.

## 사전 요구 사항

시작하기 전에 다음을 확인하세요:

- **Aspose.Slides for Java library** – 이 튜토리얼은 버전 25.4(작성 시 최신 릴리스)를 참조합니다.  
- 호환되는 **Java Development Kit (JDK)** – JDK 16+ 권장.  
- 의존성 관리를 위해 **Maven** 또는 **Gradle**에 대한 기본 지식.  

## Aspose.Slides for Java 설정

시작하려면 프로젝트에 Aspose.Slides 라이브러리를 포함하세요.

### Maven
`pom.xml` 파일에 다음 의존성을 추가하세요:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` 파일에 다음을 포함하세요:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 최신 버전을 직접 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드하세요.

### 라이선스
제한 없이 Aspose.Slides를 사용하려면:

- API를 평가하려면 **free trial**부터 시작하세요.  
- [Temporary License](https://purchase.aspose.com/temporary-license/) 페이지에서 **temporary license**를 요청하여 테스트 기간을 연장하세요.  
- [Purchase page](https://purchase.aspose.com/buy)에서 전체 구독을 구매하세요.

## Aspose.Slides for Java를 사용하여 파이 차트를 PowerPoint에 추가하는 방법

아래는 파이 차트를 만들고 사용자 지정하는 정확한 단계별 가이드입니다.

### 단계 1: 프레젠테이션 초기화
먼저 새 `Presentation` 객체를 생성합니다. 이는 빈 PowerPoint 파일을 나타냅니다.
```java
Presentation pres = new Presentation();
```

### 단계 2: 파이 차트 추가
첫 번째 슬라이드에 파이 차트를 삽입합니다. 좌표 (50, 50)와 크기 (600 × 400)는 표준 16:9 슬라이드에 적합합니다.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### 단계 3: 프레젠테이션 저장
프레젠테이션을 디스크에 저장합니다. `YOUR_OUTPUT_DIRECTORY`를 파일을 저장하려는 폴더 경로로 교체하세요.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### 단계 4: 리소스 정리
`Presentation` 객체를 폐기하여 네이티브 리소스를 해제합니다.
```java
if (pres != null) pres.dispose();
```

## 데이터 포인트 폭발 및 색상 사용자 지정

개별 슬라이스를 사용자 지정하면 차트를 더 쉽게 읽을 수 있으며, 특히 특정 값을 강조하고 싶을 때 유용합니다.

### 단계 1: 기존 프레젠테이션 로드(또는 방금 만든 프레젠테이션 재사용)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### 단계 2: 차트 및 대상 데이터 포인트 접근
여기서는 첫 번째 시리즈에서 두 번째 데이터 포인트(인덱스 1)를 가져옵니다.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### 단계 3: 폭발 및 색상 적용
시각적으로 슬라이스를 분리하고 채우기 색상을 파란색으로 변경합니다.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### 단계 4: 저장 및 폐기
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## 실용적인 적용 사례
- **Sales Reports:** 폭발된 슬라이스로 최고 판매 제품을 강조합니다.  
- **Budget Analysis:** 부서별로 구별되는 색상을 지정하여 빠른 시각 비교를 가능하게 합니다.  
- **Educational Slides:** 복잡한 개념을 쉽게 소화할 수 있는 차트 세그먼트로 분해합니다.

## 성능 고려 사항
- **Dispose objects**를 즉시 수행하여 메모리 누수를 방지합니다. 특히 루프에서 많은 슬라이드를 생성할 때 중요합니다.  
- 대용량 프레젠테이션의 경우 **Monitor heap usage**를 확인하고, `OutputStream`을 받는 `Save` 오버로드를 사용해 스트리밍 출력을 고려하세요.  
- 최신 가비지 컬렉션 개선을 활용하려면 **JDK 16+**를 사용하세요.

## 결론
이제 Aspose.Slides for Java를 사용하여 **add pie chart PowerPoint** 파일을 만들기 위한 완전하고 프로덕션 준비된 워크플로우를 갖추었습니다. 다양한 폭발 거리, 색상 및 데이터 세트를 실험하여 브랜드에 맞추세요. 준비가 되면 다른 차트 유형(막대, 선, 산점도)을 탐색하여 PowerPoint 내부에 전체 분석 대시보드를 구축할 수 있습니다.

## FAQ 섹션
1. **Aspose.Slides for Java를 사용하는 주요 장점은 무엇인가요?**  
   - PowerPoint 파일을 프로그래밍 방식으로 생성 및 조작을 단순화하고 다양한 기능을 제공합니다.  
2. **다른 차트 유형도 Aspose.Slides로 사용자 지정할 수 있나요?**  
   - 물론입니다! Aspose.Slides는 막대, 선, 산점도 차트와 같은 다양한 차트 유형을 지원합니다.  
3. **차트를 만들 때 여러 슬라이드를 어떻게 처리하나요?**  
   - `get_Item()` 메서드를 사용하여 인덱스로 각 슬라이드에 접근하고, 다른 슬라이드에 변경 사항을 적용합니다.  
4. **사용자 지정 후 파이 차트가 올바르게 표시되지 않으면 어떻게 해야 하나요?**  
   - `addChart()`에 사용된 좌표와 크기가 슬라이드 레이아웃에 맞는지 확인하세요.  
5. **Aspose.Slides의 고급 기능은 어디서 찾을 수 있나요?**  
   - 추가 기능 및 옵션을 알아보려면 [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)을 탐색하세요.

## 리소스
- **Documentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}