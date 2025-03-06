---
title: PowerPoint에 포함된 비디오 프레임 추가
linktitle: PowerPoint에 포함된 비디오 프레임 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 이 단계별 튜토리얼을 통해 Java용 Aspose.Slides를 사용하여 PowerPoint에 비디오 프레임을 삽입하는 방법을 알아보세요. 프레젠테이션을 쉽게 향상시키세요.
weight: 21
url: /ko/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에 포함된 비디오 프레임 추가

## 소개
PowerPoint 프레젠테이션에 비디오를 추가하면 프레젠테이션을 더욱 매력적이고 유익하게 만들 수 있습니다. Aspose.Slides for Java를 사용하면 비디오를 슬라이드에 직접 쉽게 삽입할 수 있습니다. 이 튜토리얼에서는 프로세스를 단계별로 안내하여 코드의 모든 부분과 작동 방식을 이해할 수 있도록 합니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 가이드는 포함된 비디오를 사용하여 프레젠테이션을 향상시키는 데 도움이 될 것입니다.
## 전제 조건
코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. JDK(Java Development Kit): 컴퓨터에 JDK가 설치되어 있는지 확인하세요.
2. Aspose.Slides for Java: Aspose.Slides for Java 라이브러리를 다운로드하고 설치하세요.
3. 통합 개발 환경(IDE): 더 나은 개발 환경을 위해 IntelliJ IDEA 또는 Eclipse와 같은 IDE를 사용하세요.
4. 비디오 파일: PowerPoint 프레젠테이션에 포함할 비디오 파일이 있습니다.
## 패키지 가져오기
먼저 Aspose.Slides를 사용하려면 필요한 패키지를 가져와야 합니다. 이러한 가져오기는 슬라이드, 비디오 및 프리젠테이션 파일을 관리하는 데 도움이 됩니다.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## 1단계: 환경 설정
코딩을 시작하기 전에 환경이 올바르게 설정되었는지 확인하세요. 여기에는 필요한 디렉토리를 생성하고 비디오 파일을 준비하는 작업이 포함됩니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// 디렉터리가 아직 없으면 만듭니다.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## 2단계: 프레젠테이션 클래스 인스턴스화
 인스턴스를 생성합니다.`Presentation` 수업. 이 클래스는 PowerPoint 파일을 나타냅니다.
```java
// PPTX를 나타내는 프레젠테이션 클래스 인스턴스화
Presentation pres = new Presentation();
```
## 3단계: 첫 번째 슬라이드 가져오기
비디오를 포함할 프레젠테이션의 첫 번째 슬라이드에 액세스합니다.
```java
// 첫 번째 슬라이드 가져오기
ISlide sld = pres.getSlides().get_Item(0);
```
## 4단계: 프레젠테이션에 비디오 추가
프레젠테이션에 비디오 파일을 삽입합니다. 비디오 경로가 올바르게 지정되었는지 확인하십시오.
```java
// 프레젠테이션 내에 비디오 삽입
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## 5단계: 슬라이드에 비디오 프레임 추가
슬라이드에 비디오 프레임을 만들고 크기와 위치를 설정합니다.
```java
// 비디오 프레임 추가
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## 6단계: 비디오 프레임 속성 구성
비디오를 비디오 프레임으로 설정하고 재생 모드 및 볼륨과 같은 재생 설정을 구성합니다.
```java
// 비디오를 비디오 프레임으로 설정
vf.setEmbeddedVideo(vid);
// 재생 모드 및 비디오 볼륨 설정
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## 7단계: 프레젠테이션 저장
비디오가 포함된 프레젠테이션을 지정된 디렉터리에 저장합니다.
```java
// PPTX 파일을 디스크에 쓰기
pres.save(resultPath, SaveFormat.Pptx);
```
## 8단계: 리소스 정리
마지막으로 프레젠테이션 개체를 삭제하여 리소스를 확보합니다.
```java
// 프레젠테이션 개체 삭제
if (pres != null) pres.dispose();
```
## 결론
Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 비디오를 삽입하는 것은 간단한 과정입니다. 이 가이드에 설명된 단계를 따르면 매력적인 비디오 콘텐츠로 프레젠테이션을 향상시킬 수 있습니다. 연습이 완벽함을 기억하세요. 다양한 비디오를 삽입하고 해당 속성을 조정하여 귀하의 필요에 가장 적합한 것이 무엇인지 확인하십시오.
## FAQ
### 단일 슬라이드에 여러 비디오를 포함할 수 있나요?
예, 여러 비디오 프레임을 추가하여 단일 슬라이드에 여러 비디오를 포함할 수 있습니다.
### 비디오 재생을 어떻게 제어할 수 있나요?
 다음을 사용하여 재생을 제어할 수 있습니다.`setPlayMode` 그리고`setVolume` 방법`IVideoFrame` 수업.
### Aspose.Slides는 어떤 비디오 형식을 지원합니까?
Aspose.Slides는 MP4, AVI, WMV를 포함한 다양한 비디오 형식을 지원합니다.
### Aspose.Slides를 사용하려면 라이선스가 필요합니까?
예, Aspose.Slides를 사용하려면 유효한 라이선스가 필요합니다. 평가용 임시 라이센스를 얻을 수 있습니다.
### 비디오 프레임의 크기와 위치를 사용자 정의할 수 있나요?
예, 비디오 프레임을 추가할 때 적절한 매개변수를 설정하여 크기와 위치를 맞춤 설정할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
