---
title: 비밀번호로 PowerPoint 저장
linktitle: 비밀번호로 PowerPoint 저장
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 비밀번호 보호를 추가하는 방법을 알아보세요. 슬라이드를 쉽게 보호하세요.
weight: 12
url: /ko/java/java-powerpoint-save-operations/save-powerpoint-with-password/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 비밀번호로 PowerPoint 프레젠테이션을 저장하는 과정을 안내합니다. 프레젠테이션에 암호를 추가하면 보안이 강화되어 승인된 개인만 콘텐츠에 액세스할 수 있습니다.
## 전제 조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Slides: 다음 사이트에서 Java용 Aspose.Slides를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
먼저 Java 파일에 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

import java.io.File;
```
## 1단계: 환경 설정
프레젠테이션 파일을 저장할 디렉터리가 있는지 확인하세요. 존재하지 않는 경우 새로 만듭니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "path/to/your/directory/";
// 디렉터리가 아직 없으면 만듭니다.
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## 2단계: 프리젠테이션 개체 만들기
PowerPoint 파일을 나타내는 프레젠테이션 개체를 인스턴스화합니다.
```java
// 프레젠테이션 개체 인스턴스화
Presentation pres = new Presentation();
```
## 3단계: 비밀번호 보호 설정
 다음을 사용하여 프레젠테이션의 비밀번호를 설정하세요.`encrypt` 의 방법`ProtectionManager`.
```java
// 비밀번호 설정
pres.getProtectionManager().encrypt("your_password");
```
 바꾸다`"your_password"` 프레젠테이션에 원하는 비밀번호를 입력하세요.
## 4단계: 프레젠테이션 저장
지정된 비밀번호를 사용하여 프레젠테이션을 파일에 저장합니다.
```java
// 프레젠테이션을 파일에 저장
pres.save(dataDir + "SaveWithPassword_out.pptx", SaveFormat.Pptx);
```
이 코드는 지정된 디렉토리에 비밀번호와 함께 프레젠테이션을 저장합니다.

## 결론
중요한 정보를 보호하려면 PowerPoint 프레젠테이션을 암호로 보호하는 것이 중요합니다. Aspose.Slides for Java를 사용하면 프레젠테이션에 비밀번호 보호를 쉽게 추가하여 승인된 사용자만 액세스할 수 있도록 할 수 있습니다.

## FAQ
### PowerPoint 프레젠테이션에서 비밀번호 보호를 제거할 수 있나요?
예, Aspose.Slides를 사용하여 비밀번호 보호를 제거할 수 있습니다. 자세한 지침은 설명서를 확인하세요.
### Aspose.Slides는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 PPTX, PPT 등을 포함한 다양한 PowerPoint 형식을 지원합니다. 호환성 세부정보는 설명서를 참조하세요.
### 프레젠테이션을 편집하고 볼 때 다른 비밀번호를 설정할 수 있나요?
예, Aspose.Slides를 사용하면 권한 편집 및 보기에 대해 별도의 비밀번호를 설정할 수 있습니다.
### Aspose.Slides for Java에 사용할 수 있는 평가판이 있습니까?
 예, Aspose에서 무료 평가판을 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/).
### Aspose.Slides에 대한 기술 지원은 어떻게 받을 수 있나요?
커뮤니티 및 Aspose 지원 직원의 기술 지원을 받으려면 Aspose.Slides 포럼을 방문하세요.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
