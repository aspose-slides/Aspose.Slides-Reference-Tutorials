---
title: PowerPoint에 오디오 프레임 추가
linktitle: PowerPoint에 오디오 프레임 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 오디오 프레임을 추가하는 방법을 알아보세요. 매력적인 오디오 요소를 사용하여 손쉽게 프레젠테이션의 수준을 높이세요.
type: docs
weight: 12
url: /ko/java/java-powerpoint-shape-media-insertion/add-audio-frame-powerpoint/
---
## 소개
오디오 요소를 사용하여 프레젠테이션을 향상하면 영향력과 참여도를 크게 높일 수 있습니다. Aspose.Slides for Java를 사용하면 오디오 프레임을 PowerPoint 프레젠테이션에 통합하는 과정이 원활해집니다. 이 튜토리얼은 Aspose.Slides for Java를 사용하여 프레젠테이션에 오디오 프레임을 추가하는 단계별 프로세스를 안내합니다.
## 전제조건
시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
1. JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요.
2.  Aspose.Slides for Java 라이브러리: Aspose.Slides for Java 라이브러리를 다운로드하고 설치하세요. 다음에서 다운로드할 수 있습니다.[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/).
3. 오디오 파일: 프레젠테이션에 추가할 오디오 파일(예: WAV 형식)을 준비합니다.
## 패키지 가져오기
필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## 1단계: 프로젝트 디렉터리 설정
프로젝트에 디렉터리 구조가 설정되어 있는지 확인하세요. 그렇지 않은 경우 파일을 효과적으로 정리할 수 있는 파일을 만드십시오.
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## 2단계: 프레젠테이션 클래스 인스턴스화
 인스턴스화`Presentation` PowerPoint 프레젠테이션을 나타내는 클래스입니다.
```java
Presentation pres = new Presentation();
```
## 3단계: 슬라이드 가져오기 및 오디오 파일 로드
첫 번째 슬라이드를 검색하고 디렉터리에서 오디오 파일을 로드합니다.
```java
ISlide sld = pres.getSlides().get_Item(0);
FileInputStream fstr = new FileInputStream(dataDir + "sampleaudio.wav");
```
## 4단계: 오디오 프레임 추가
슬라이드에 오디오 프레임을 추가합니다.
```java
IAudioFrame audioFrame = sld.getShapes().addAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## 5단계: 오디오 속성 설정
슬라이드 전체 재생, 오디오 되감기, 재생 모드, 볼륨 등의 속성을 설정합니다.
```java
audioFrame.setPlayAcrossSlides(true);
audioFrame.setRewindAudio(true);
audioFrame.setPlayMode(AudioPlayModePreset.Auto);
audioFrame.setVolume(AudioVolumeMode.Loud);
```
## 6단계: 프레젠테이션 저장
추가된 오디오 프레임과 함께 수정된 프레젠테이션을 저장합니다.
```java
pres.save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```

## 결론
PowerPoint 프레젠테이션에 오디오 요소를 통합하면 효과가 향상되고 청중의 관심을 끌 수 있습니다. Aspose.Slides for Java를 사용하면 오디오 프레임을 추가하는 과정이 쉬워져 역동적이고 매력적인 프레젠테이션을 쉽게 만들 수 있습니다.

## FAQ
### 내 프레젠테이션에 다양한 형식의 오디오 파일을 추가할 수 있나요?
예, Aspose.Slides for Java는 WAV, MP3 등을 포함한 다양한 오디오 형식을 지원합니다.
### 슬라이드에서 오디오 재생 타이밍을 조정할 수 있습니까?
전적으로. Aspose.Slides for Java를 사용하여 오디오 재생을 특정 슬라이드 전환과 동기화할 수 있습니다.
### Aspose.Slides for Java는 플랫폼 간 호환성을 지원합니까?
예. 다양한 플랫폼에서 호환되는 오디오 프레임이 포함된 PowerPoint 프레젠테이션을 만들 수 있습니다.
### 프레젠테이션에서 오디오 플레이어의 모양을 사용자 지정할 수 있나요?
Aspose.Slides for Java는 광범위한 사용자 정의 옵션을 제공하므로 오디오 플레이어의 모양을 원하는 대로 조정할 수 있습니다.
### Aspose.Slides for Java에 사용할 수 있는 평가판이 있습니까?
 예, 다음 사이트에서 Aspose.Slides for Java의 무료 평가판에 액세스할 수 있습니다.[웹사이트](https://releases.aspose.com/).