---
"description": "이 단계별 튜토리얼을 통해 Aspose.Slides for Java를 사용하여 PowerPoint에 비디오 프레임을 삽입하는 방법을 알아보세요. 프레젠테이션을 더욱 쉽게 개선해 보세요."
"linktitle": "PowerPoint에 내장 비디오 프레임 추가"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에 내장 비디오 프레임 추가"
"url": "/ko/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에 내장 비디오 프레임 추가

## 소개
PowerPoint 프레젠테이션에 비디오를 추가하면 더욱 매력적이고 유익한 프레젠테이션을 만들 수 있습니다. Aspose.Slides for Java를 사용하면 슬라이드에 비디오를 쉽게 삽입할 수 있습니다. 이 튜토리얼에서는 코드의 모든 부분과 그 기능을 이해할 수 있도록 단계별로 과정을 안내해 드립니다. 숙련된 개발자든 초보자든, 이 가이드를 통해 내장된 비디오를 활용하여 프레젠테이션을 더욱 풍성하게 만들 수 있습니다.
## 필수 조건
코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. Java Development Kit(JDK): 컴퓨터에 JDK가 설치되어 있는지 확인하세요.
2. Java용 Aspose.Slides: Java용 Aspose.Slides 라이브러리를 다운로드하여 설치하세요.
3. 통합 개발 환경(IDE): 더 나은 개발 경험을 위해 IntelliJ IDEA나 Eclipse와 같은 IDE를 사용하세요.
4. 비디오 파일: PowerPoint 프레젠테이션에 포함하고 싶은 비디오 파일이 있습니다.
## 패키지 가져오기
먼저 Aspose.Slides를 사용하는 데 필요한 패키지를 가져와야 합니다. 이러한 패키지를 가져오면 슬라이드, 비디오 및 프레젠테이션 파일을 관리하는 데 도움이 됩니다.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## 1단계: 환경 설정
코딩을 시작하기 전에 환경이 올바르게 설정되어 있는지 확인하세요. 여기에는 필요한 디렉터리를 생성하고 비디오 파일을 준비하는 작업이 포함됩니다.
```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// 디렉토리가 없으면 새로 만듭니다.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## 2단계: 프레젠테이션 클래스 인스턴스화
인스턴스를 생성합니다 `Presentation` 클래스입니다. 이 클래스는 PowerPoint 파일을 나타냅니다.
```java
// PPTX를 나타내는 Presentation 클래스를 인스턴스화합니다.
Presentation pres = new Presentation();
```
## 3단계: 첫 번째 슬라이드 가져오기
비디오를 삽입할 프레젠테이션의 첫 번째 슬라이드에 액세스하세요.
```java
// 첫 번째 슬라이드를 받으세요
ISlide sld = pres.getSlides().get_Item(0);
```
## 4단계: 프레젠테이션에 비디오 추가
비디오 파일을 프레젠테이션에 삽입하세요. 비디오 경로가 올바르게 지정되었는지 확인하세요.
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
비디오를 비디오 프레임으로 설정하고 재생 모드, 볼륨 등의 재생 설정을 구성합니다.
```java
// 비디오를 비디오 프레임으로 설정
vf.setEmbeddedVideo(vid);
// 비디오의 재생 모드 및 볼륨 설정
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## 7단계: 프레젠테이션 저장
비디오가 포함된 프레젠테이션을 지정된 디렉토리에 저장합니다.
```java
// PPTX 파일을 디스크에 쓰기
pres.save(resultPath, SaveFormat.Pptx);
```
## 8단계: 리소스 정리
마지막으로, 프레젠테이션 객체를 삭제하여 리소스를 확보합니다.
```java
// 프레젠테이션 객체를 폐기합니다
if (pres != null) pres.dispose();
```
## 결론
Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 비디오를 삽입하는 것은 매우 간단합니다. 이 가이드에 설명된 단계를 따르면 매력적인 비디오 콘텐츠로 프레젠테이션을 더욱 돋보이게 만들 수 있습니다. 연습이 완벽을 만든다는 것을 기억하세요. 다양한 비디오를 삽입하고 속성을 조정하여 필요에 가장 적합한 것을 찾아보세요.
## 자주 묻는 질문
### 하나의 슬라이드에 여러 개의 비디오를 삽입할 수 있나요?
네, 여러 개의 비디오 프레임을 추가하여 하나의 슬라이드에 여러 개의 비디오를 삽입할 수 있습니다.
### 비디오 재생을 어떻게 제어할 수 있나요?
재생을 제어할 수 있습니다. `setPlayMode` 그리고 `setVolume` 의 방법 `IVideoFrame` 수업.
### Aspose.Slides는 어떤 비디오 형식을 지원하나요?
Aspose.Slides는 MP4, AVI, WMV를 포함한 다양한 비디오 형식을 지원합니다.
### Aspose.Slides를 사용하려면 라이선스가 필요합니까?
네, Aspose.Slides를 사용하려면 유효한 라이선스가 필요합니다. 평가판으로 임시 라이선스를 받으실 수 있습니다.
### 비디오 프레임의 크기와 위치를 사용자 지정할 수 있나요?
네, 비디오 프레임을 추가할 때 적절한 매개변수를 설정하여 크기와 위치를 사용자 지정할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}