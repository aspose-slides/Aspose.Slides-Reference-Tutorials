---
title: PowerPoint의 기본 제공 속성에 액세스
linktitle: PowerPoint의 기본 제공 속성에 액세스
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint의 기본 제공 속성에 액세스하는 방법을 알아보세요. 이 튜토리얼에서는 작성자, 생성 날짜 등을 검색하는 과정을 안내합니다.
weight: 10
url: /ko/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 기본 제공 속성에 액세스하는 방법을 살펴보겠습니다. Aspose.Slides는 Java 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 사용하여 속성 읽기 및 수정과 같은 작업을 원활하게 수행할 수 있도록 하는 강력한 라이브러리입니다.
## 전제 조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하십시오. 다음에서 다운로드할 수 있습니다.[여기](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Java용 Aspose.Slides: 다음에서 Java용 Aspose.Slides를 다운로드하고 설치하세요.[이 링크](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
먼저 필요한 패키지를 Java 프로젝트로 가져와야 합니다. Java 파일 시작 부분에 다음 가져오기 문을 추가합니다.
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## 1단계: 프레젠테이션 개체 설정
작업하려는 PowerPoint 프레젠테이션을 나타내기 위해 프레젠테이션 개체를 설정하는 것부터 시작하세요. 방법은 다음과 같습니다.
```java
// 프리젠테이션 파일이 포함된 디렉토리의 경로
String dataDir = "path_to_your_presentation_directory/";
// 프레젠테이션 클래스 인스턴스화
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## 2단계: 문서 속성에 액세스
Presentation 개체를 설정한 후 IDocumentProperties 인터페이스를 사용하여 프레젠테이션의 기본 제공 속성에 액세스할 수 있습니다. 다양한 속성을 검색하는 방법은 다음과 같습니다.
### 범주
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### 현재 상태
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### 생산 일
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### 작가
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### 설명
```java
System.out.println("Description : " + documentProperties.getComments());
```
### 키워드
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### 최종 수정자
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### 감독자
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### 수정된 날짜
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### 프레젠테이션 형식
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### 마지막 인쇄 날짜
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### 생산자 간 공유
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### 주제
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### 제목
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 기본 제공 속성에 액세스하는 방법을 배웠습니다. 위에 설명된 단계를 수행하면 작성자, 생성 날짜, 제목 등의 다양한 속성을 프로그래밍 방식으로 쉽게 검색할 수 있습니다.
## FAQ
### Aspose.Slides for Java를 사용하여 이러한 내장 속성을 수정할 수 있나요?
예, Aspose.Slides를 사용하여 이러한 속성을 수정할 수 있습니다. IDocumentProperties 인터페이스에서 제공하는 적절한 setter 메서드를 사용하면 됩니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 다양한 PowerPoint 버전을 지원하여 다양한 플랫폼 간의 호환성을 보장합니다.
### 사용자 정의 속성도 검색할 수 있나요?
예, 내장 속성 외에도 Aspose.Slides for Java를 사용하여 사용자 정의 속성을 검색하고 수정할 수도 있습니다.
### Aspose.Slides는 문서와 지원을 제공합니까?
 예, 다음에서 포괄적인 문서를 찾아보고 지원 포럼에 액세스할 수 있습니다.[Aspose 웹사이트](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
