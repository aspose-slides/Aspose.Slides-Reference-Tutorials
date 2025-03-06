---
title: PowerPoint에 비디오 프레임 추가
linktitle: PowerPoint에 비디오 프레임 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 비디오 콘텐츠를 PowerPoint 프레젠테이션에 원활하게 통합하는 방법을 알아보세요. 청중의 관심을 끌 수 있는 멀티미디어 요소가 포함된 슬라이드.
weight: 17
url: /ko/java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 비디오 프레임을 추가하는 과정을 안내합니다. 이러한 단계별 지침을 따르면 비디오 콘텐츠를 프레젠테이션에 원활하게 통합할 수 있습니다.
## 전제 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 시스템에 설치된 JDK(Java Development Kit)
- Java 프로젝트에 다운로드 및 설정된 Java 라이브러리용 Aspose.Slides
## 패키지 가져오기
먼저 Java 코드에서 Aspose.Slides 기능을 활용하려면 필요한 패키지를 가져와야 합니다. 
```java
import com.aspose.slides.*;

import java.io.File;
```
## 1단계: 문서 디렉토리 설정
PowerPoint 파일을 저장할 디렉터리가 설정되어 있는지 확인하세요.
```java
String dataDir = "Your Document Directory";
```
## 2단계: 프리젠테이션 개체 만들기
 인스턴스화`Presentation` PowerPoint 파일을 나타내는 클래스입니다.
```java
Presentation pres = new Presentation();
```
## 3단계: 슬라이드에 비디오 프레임 추가
첫 번째 슬라이드를 가져와서 여기에 비디오 프레임을 추가하세요.
```java
ISlide sld = pres.getSlides().get_Item(0);
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
## 4단계: 재생 모드 및 볼륨 설정
비디오 프레임의 재생 모드와 볼륨을 설정합니다.
```java
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## 5단계: 프레젠테이션 저장
수정된 PowerPoint 파일을 디스크에 저장합니다.
```java
pres.save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
## 결론
축하해요! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 비디오 프레임을 추가하는 방법을 성공적으로 배웠습니다. 청중을 효과적으로 참여시킬 수 있는 멀티미디어 요소를 통합하여 프레젠테이션을 향상시키십시오.
## FAQ
### PowerPoint 프레젠테이션에 어떤 형식의 비디오도 추가할 수 있나요?
Aspose.Slides는 AVI, WMV, MP4 등과 같은 다양한 비디오 형식을 지원합니다. 형식이 PowerPoint와 호환되는지 확인하세요.
### Aspose.Slides는 다른 버전의 Java와 호환됩니까?
예, Java용 Aspose.Slides는 JDK 버전 6 이상과 호환됩니다.
### 비디오 프레임의 크기와 위치를 어떻게 조정하나요?
 다음의 매개변수를 수정하여 비디오 프레임의 크기와 좌표를 사용자 정의할 수 있습니다.`addVideoFrame` 방법.
### 비디오의 재생 설정을 제어할 수 있나요?
예, 원하는 대로 비디오 프레임의 재생 모드와 볼륨을 설정할 수 있습니다.
### Aspose.Slides에 대한 추가 지원과 리소스는 어디서 찾을 수 있나요?
 방문하다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 지원, 문서 및 커뮤니티 지원이 필요합니다.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
