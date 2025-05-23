---
"date": "2025-04-17"
"description": "Aspose.Slides를 사용하여 Java 프레젠테이션에서 도넛형 차트를 만들고 사용자 지정하는 방법을 알아보세요. 여기에는 환경 설정 및 차트 미학 조정도 포함됩니다."
"title": "Aspose.Slides를 사용하여 Java에서 프레젠테이션용 도넛 차트를 만드는 방법"
"url": "/ko/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용하여 Java에서 프레젠테이션용 도넛 차트를 만드는 방법

## 소개
시각적으로 매력적인 프레젠테이션을 만드는 것은 정보를 효과적으로 전달하는 데 필수적입니다. 차트는 데이터 분포에 대한 이해를 높이는 데 중요한 요소입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 사용자 정의 가능한 도넛형 차트를 만드는 방법을 안내합니다. 구멍 크기 및 위치와 같은 다양한 사용자 정의 옵션을 통해 차트를 손쉽게 생성할 수 있습니다.

**배울 내용:**
- Java용 Aspose.Slides 설정
- 프레젠테이션에서 도넛형 차트 만들기 및 구성
- 구멍 크기와 같은 차트 미학 조정
- 새 차트로 프레젠테이션 저장

먼저 환경 설정부터 시작해 보겠습니다!

## 필수 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

### 필수 라이브러리 및 버전
Java용 Aspose.Slides를 사용하려면 Maven이나 Gradle을 통해 프로젝트에 포함하거나 직접 다운로드하세요.

#### 환경 설정 요구 사항
- 작동하는 Java 개발 키트(JDK)는 버전 8 이상이 바람직합니다.
- IntelliJ IDEA나 Eclipse와 같은 통합 개발 환경(IDE).

### 지식 전제 조건
Java와 기본 프로그래밍 개념에 대한 지식이 있으면 좋습니다. Maven이나 Gradle에 대한 기본 지식이 있으면 설정 과정을 간소화하는 데 도움이 됩니다.

## Java용 Aspose.Slides 설정
Aspose.Slides를 프로젝트에 통합하는 방법은 여러 가지가 있습니다.

**메이븐:**
이 종속성을 다음에 추가하세요. `pom.xml` 파일:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**그래들:**
이것을 당신의 것에 포함시키세요 `build.gradle` 파일:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**직접 다운로드:**
또는 다음에서 최신 버전을 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

### 라이센스 취득
- **무료 체험**: Aspose.Slides의 기능을 살펴보려면 평가판 버전을 다운로드하세요.
- **임시 면허**: 제한 없이 확장된 기능을 사용할 수 있는 임시 라이선스를 얻습니다.
- **구입**: 지속적으로 사용하려면 라이센스를 구매해야 합니다.

라이브러리를 설정하고 환경을 준비했으면 도넛 차트를 구현해 보겠습니다.

## 구현 가이드

### 도넛 차트 만들기
Aspose.Slides를 사용하여 맞춤형 도넛형 차트가 포함된 프레젠테이션을 만드는 과정은 여러 단계로 구성됩니다. 이해를 돕기 위해 각 단계를 자세히 살펴보겠습니다.

#### 프레젠테이션 객체 초기화
인스턴스를 생성하여 시작하세요. `Presentation` PowerPoint 문서를 나타내는 클래스입니다.
```java
// PPTX 문서를 나타내기 위해 Presentation 클래스 인스턴스를 생성합니다.
Presentation presentation = new Presentation();
```
이 단계에서는 슬라이드와 차트를 추가할 수 있는 프레젠테이션을 초기화합니다.

#### 슬라이드에 도넛형 차트 추가
첫 번째 슬라이드에 접근하거나 필요한 경우 슬라이드를 만들어 도넛형 차트를 추가합니다.
```java
// 프레젠테이션의 첫 번째 슬라이드에 접근하세요
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // (50, 50)에 위치, 크기는 400x400입니다.
```
이 코드 조각은 첫 번째 슬라이드에 도넛형 차트를 추가합니다. 매개변수는 슬라이드에서 도넛형 차트의 위치와 크기를 정의합니다.

#### 도넛 구멍 크기 구성
도넛형 차트에 독특한 모양을 주려면 구멍 크기를 조정하세요.
```java
// 도넛 차트의 구멍 크기를 90%로 설정하세요.
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```
여기서는 구멍 크기를 90%로 설정하여 거의 완전한 원을 만듭니다. 디자인 요구 사항에 따라 이 값을 조정하세요.

#### 프레젠테이션 저장
차트를 구성한 후 프레젠테이션을 저장합니다.
```java
// PPTX 형식으로 지정된 디렉토리에 프레젠테이션을 디스크에 저장합니다.
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```
이 줄은 변경 사항을 다음 이름의 파일에 기록합니다. `DoughnutHoleSize_out.pptx` 귀하가 지정한 디렉토리에 보관하세요.

#### 청소 자원
마지막으로, 프레젠테이션 객체를 폐기하세요.
```java
// 프레젠테이션 객체를 폐기하여 리소스를 해제합니다.
if (presentation != null) presentation.dispose();
```
이 단계는 리소스 관리와 메모리 누수 방지에 중요합니다.

### 실제 응용 프로그램
도넛 차트는 다재다능합니다. 도넛 차트가 빛을 발하는 몇 가지 상황을 소개합니다.
1. **예산 할당**: 예산이 부서별로 어떻게 분배되는지 표시합니다.
2. **설문조사 결과**: 객관식 답변이 있는 질문에 대한 답변을 시각화합니다.
3. **웹사이트 트래픽 소스**: 다양한 소스에서 유입되는 트래픽의 비율을 보여줍니다.

### 성능 고려 사항
Aspose.Slides를 사용할 때 최적의 성능을 위해 다음 팁을 고려하세요.
- 더 이상 필요하지 않은 객체를 삭제하여 메모리를 관리합니다.
- 대용량 데이터 세트의 경우 스트림을 사용하여 메모리 사용량을 최소화합니다.
- 가능한 경우 인스턴스를 재사용하여 코드를 최적화하세요.

## 결론
축하합니다! Aspose.Slides for Java를 사용하여 도넛형 차트를 만들고 사용자 지정하는 방법을 배웠습니다. 이 튜토리얼에서는 라이브러리 설정, 프레젠테이션에 차트 추가, 그리고 디자인 조정 방법을 다루었습니다.

Aspose.Slides의 기능을 계속 탐색하려면 다른 차트 유형을 실험하거나 프레젠테이션 자동화 기능을 더 자세히 살펴보세요.

**다음 단계:**
- 다양한 차트 구성을 실험해 보세요.
- 더욱 고급 기능에 대한 자세한 내용은 Aspose.Slides의 추가 문서를 참조하세요.

나만의 도넛형 차트를 만들 준비가 되셨나요? 다음 프로젝트에 이 솔루션을 적용해 보세요!

## FAQ 섹션
1. **도넛형 차트 세그먼트의 색상을 조정할 수 있나요?**
   예, 다음을 사용하여 세그먼트 색상을 사용자 정의할 수 있습니다. `chart.getChartData().getSeries(i).getDataPointsForBarChart().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid);` 단색 채우기 유형을 설정하고 원하는 색상을 지정합니다.

2. **차트에 데이터 레이블을 추가하려면 어떻게 해야 하나요?**
   사용 `chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category"));` 데이터 포인트와 레이블을 프로그래밍 방식으로 추가하는 유사한 방법.

3. **PPTX 이외의 형식으로 차트를 저장할 수 있나요?**
   물론입니다! Aspose.Slides는 PDF, XPS, PNG, JPEG 등의 이미지 형식 등 다양한 출력 형식을 지원합니다.

4. **프레젠테이션을 저장하는 동안 오류가 발생하면 어떻게 해야 하나요?**
   디렉터리 경로가 올바른지, 그리고 지정된 위치에 대한 쓰기 권한이 있는지 확인하세요. 사용 중인 Aspose.Slides 버전이 저장하려는 파일 형식을 지원하는지 확인하세요.

5. **라이브 데이터 소스를 사용해 차트 업데이트를 자동화할 수 있나요?**
   네, API나 데이터베이스를 Java 애플리케이션에 통합하면 필요에 따라 차트 데이터를 동적으로 업데이트하고 프레젠테이션을 새로 고칠 수 있습니다.

## 자원
- **선적 서류 비치**: 자세한 API 참조를 살펴보세요. [Java용 Aspose.Slides](https://reference.aspose.com/slides/java/).
- **다운로드**: 최신 라이브러리 버전을 받으세요 [Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).
- **구입**: 전체 액세스를 위해서는 라이선스를 구매하세요. [Aspose 구매](https://purchase.aspose.com/buy).
- **무료 체험**: 다운로드 페이지에서 무료 평가판을 이용해 Aspose.Slides를 테스트해 보세요.
- **임시 면허**제한 없이 장기간 테스트를 위한 임시 라이센스를 얻으세요.
- **지원하다**: 질문이 있으신가요? 방문하세요 [Aspose 포럼](https://forum.aspose.com/c/slides/11) 도움이 필요하면.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}