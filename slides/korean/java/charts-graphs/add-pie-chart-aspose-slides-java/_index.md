---
date: '2026-01-09'
description: aspose slides maven을 사용하여 슬라이드에 차트를 추가하고 Java 프레젠테이션에서 파이 차트를 맞춤 설정하는
  방법을 알아보세요. 단계별 설정, 코드 및 실제 예제.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven - 프레젠테이션에 파이 차트 추가'
url: /ko/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java를 사용하여 프레젠테이션에 파이 차트 추가하기

## 소개
대표적으로 매력적인 프레젠테이션을 만드는 것은 정보를 흡수 전달하는 데 활동이며, 특히 데이터를 다루는 중요한 역할을 할 때 더욱 중요합니다. **슬라이드 maven**을 사용하여 이 작업을 작동하고 있으며, 여기가 바로 번역입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 **슬라이드에 차트 추가**— 일부 파이 차트—를 추가하는 방법을 실제 시나리오에 놀라운 커스터마이징하는 방법을 살펴봅니다.

### 무엇을 배울 것인가
- Java 프레젠테이션에서 끌어오는 방법.
- 슬라이드 첫 슬라이드에 **원형 차트 java를 추가**하는 단계.
- 차트 데이터 워크북에 접근하고 워크시트를 흐름하는 방법.

Aspose.Slides Java를 유동적으로 유동 차트로 프레젠테이션을 강화하는 방법을 지금 바로 살펴보세요!

## 빠른 답변
- **Maven을 통해 차트를 추가하는 라이브러리는 무엇입니까?**슬라이드 Maven을 제안합니다.
- **어떤 차트 유형이 보여지나요?**원형 차트(슬라이드에 차트 추가)
- **최소 Java 버전이 필요합니까?**JDK16 이상
- **테스트하려면 라이센스가 필요합니까?**무료 평가판이 작동합니다. 생산에는 라이센스가 필요합니다
- **Maven 종속성은 어디에서 찾을 수 있나요?**아래 설정 섹션에서

## Aspose Slides Maven이란 무엇입니까?
Aspose.Slides for Java는 개발자의 프로그래밍 방식으로 PowerPoint 파일을 생성하고 수정 및 확장할 수 있게 해 주는 강력한 API입니다. Maven 패키지(`aspose-slides`)는 의존성을 관리하고 관리함으로써, 파이 차트 추가와 같은 슬라이드 구축 및 커스터마이징에 집중할 수 있게 공유할 수 있습니다.

## Aspose.Slides Maven을 사용하여 슬라이드에 차트를 추가하는 이유는 무엇입니까?
- **자동화:** 견적과 대시보드를 자동으로 생성합니다.
- **정밀도:** 차트 유형, 데이터 및 스타일을 확실히 제어합니다.
- **크로스 플랫폼:** Java 호환 환경에 반응합니다.

## 전제조건
- **Aspose.Slides for Java** 버전25.4 이상(Maven/Gradle).
- JDK16+ 설치.
- IDE(IntelliJ IDEA, Eclipse 등).
- 기본적으로 Java 지식 및 Maven 또는 Gradle 사용 환경.

## Java용 Aspose.Slides 설정
먼저 Maven 또는 Gradle을 통해 프로젝트에 Aspose.Slides를 포함합니다.

**메이븐:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 Aspose 공식 웹사이트에서 직접 [download the latest release](https://releases.aspose.com/slides/java/)를 받을 수 있습니다.

### 라이선스 취득
Aspose.Slides for Java는 테스트용 임시 기계를 제공하는 무료 체험판을 제공합니다. 오로지 사용을 위해 [구매 페이지](https://purchase.aspose.com/buy)에서 인스턴스를 구매하세요.

## 구현 가이드
아래에서는 두 가지 기능으로 솔루션을 나눕니다: 파이 차트 추가와 차트 데이터 워크북 접근.

### 기능 1: 프레젠테이션 만들기 및 차트 추가
#### 개요
새로운 프레젠테이션을 처음으로 편집하는 슬라이드에 **원형 차트를 추가**하는 방법을 보여줍니다.

#### 단계별

**1단계: 새 프리젠테이션 개체 초기화**
```java
Presentation pres = new Presentation();
```
*프레젠테이션에 삽입된 모든 슬라이드를 보관할 '프레젠테이션'을 생성합니다.*

**2단계: 원형 차트 추가**
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*좌표 (50, 50) 위치에 너비 400, 높이 500인 파이 차트를 배치합니다. `ChartType.Pie` 열거형이 Aspose에 파이 차트를 렌더링하도록 지시합니다.*

**3단계: 자원 폐기**  
```java
if (pres != null) pres.dispose();
```
*네이티브 리소스를 해제합니다; 작업이 끝났을 때 항상 `dispose()`를 호출하세요.*

### 기능 2: 차트 데이터 통합 ​​문서 및 워크시트에 액세스
#### 개요
차트 데이터를 생성하는 기본워크북에 접근하고 워크시트를 순회하는 방법을 배웁니다.

#### 단계별

**1단계: (재사용) 새 프리젠테이션 개체 초기화**
*기능1, 단계1과 동일합니다.*

**2단계: (재사용) 원형 차트 추가**
*기능1, 단계2는 동일합니다.*

**3단계: 차트 데이터 통합문서 가져오기**
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*차트와 연결된 `IChartDataWorkbook`을 가져옵니다.*

**4단계: 워크시트를 반복합니다** 
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*각 워크시트의 이름을 출력하여 데이터 구조를 확인합니다.*

**5단계: 리소스 폐기**
*기능1, 단계3과 동일합니다.*

## 실제 적용
- **데이터 보고:** 인텔리전스의 최신 인덱스를 자동으로 슬라이드 형식으로 생성할 수 있습니다.
- **학술적 발표:** 연구 결과를 수동으로 생성할 수 있습니다.
- **마케팅 자료:** 제품 성과에 대한 만족도를 즉시 보여줄 수 있습니다.

## 성능 고려 사항
- 슬라이드와 레이아웃을 유지하세요. 메모리가 없어졌습니다.
- 항상 `dispose()`를 호출해 달라고 요청합니다.
-워크북 데이터 처리를 최적화하고, 하나의 차트에 디스플레이 데이터를 로드하는 것을 피하세요.

## 결론
**슬라이드 maven을 활용**을 다루는 프로그래밍 방식으로 **슬라이드에 차트 추가**를 수행하고 차트 데이터워크북을 활용하는 방법을 살펴봅니다. 이 기본 블록을 활용하면 복잡한 PowerPoint 출력이 필요한 모든 보고 워크플로를 활동할 수 있습니다.

### 다음 단계
- 차트 스타일 옵션(색상, 범례, 변수 레이블) 탐색하기.
- 외부 데이터 소스(CSV, 데이터베이스)와 연결해 차트를 동적으로 기록합니다.
- 풍부한 스토리텔링을 위해 하나의 프레젠테이션에 다양한 차트를 결합하기.

## 자주 묻는 질문

**Q: Java용 Aspose.Slides를 어떻게 설치하나요?**
A: 위에 표시된 Maven 또는 Gradle 종속성을 사용하거나 릴리스 페이지에서 라이브러리를 다운로드하세요.

**Q: Aspose.Slides의 시스템 요구 사항은 무엇입니까?**
답변: JDK16 이상; 라이브러리는 플랫폼 독립적입니다.

**Q: 원형 차트 외에 다른 차트 유형을 추가할 수 있나요?**
A: 예, Aspose.Slides는 막대, 선, 분산형 및 더 많은 차트 유형을 지원합니다.

**Q: 대규모 프레젠테이션을 효율적으로 처리하려면 어떻게 해야 합니까?**
A: 개체를 즉시 폐기하고, 고해상도 이미지 수를 제한하고, 가능하면 차트 템플릿을 재사용하십시오.

**질문: Aspose.Slides 기능에 대한 자세한 내용은 어디에서 확인할 수 있나요?**
답변: 전체 API 참조는 [Aspose 문서](https://reference.aspose.com/slides/java/)를 참조하세요.

**질문: 상업적 용도로 사용하려면 라이선스가 필요한가요?**
답변: 프로덕션 환경에서 사용하려면 유효한 라이선스가 필요하며, 평가를 위해 무료 평가판을 이용할 수 있습니다.

**질문: Maven 패키지에 모든 차트 기능이 포함되어 있나요?**
답변: 네, `aspose-slides` Maven 아티팩트에는 전체 차트 엔진이 포함되어 있습니다.

## 리소스
- 문서: [Aspose.Slides Java API 참조](https://reference.aspose.com/slides/java/)
- 다운로드: [최신 릴리스](https://releases.aspose.com/slides/java/)
- 구매 및 체험판: [구매 페이지](https://purchase.aspose.com/buy)
- 무료 체험판: [체험판 다운로드](https://releases.aspose.com/slides/java/)
- 임시 라이선스: [임시 라이선스 요청](https://purchase.aspose.com/temporary-license/)
- 지원 포럼: [Aspose 커뮤니티 포럼](https://forum.aspose.com/c/slides/11)

---  

**Last Updated:** 2026-01-09  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
