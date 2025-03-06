---
title: Aspose.Slides - .NET 프레젠테이션에 포함된 비디오 추가하기
linktitle: Aspose.Slides - .NET 프레젠테이션에 포함된 비디오 추가하기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 포함된 비디오로 프레젠테이션을 향상하세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
weight: 19
url: /ko/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
역동적인 프레젠테이션 세계에서 멀티미디어 요소를 통합하면 참여도가 크게 향상될 수 있습니다. .NET용 Aspose.Slides는 내장된 비디오 프레임을 프레젠테이션 슬라이드에 통합하기 위한 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 원활한 경험을 보장하기 위해 각 단계를 세분화하여 프로세스를 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.
-  .NET 라이브러리용 Aspose.Slides: 다음에서 라이브러리를 다운로드하고 설치하세요.[릴리스 페이지](https://releases.aspose.com/slides/net/).
- 미디어 콘텐츠: 프레젠테이션에 포함하려는 비디오 파일(예: "Wildlife.mp4")이 있습니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 필요한 네임스페이스를 가져오는 것부터 시작하세요.
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## 1단계: 디렉터리 설정
프로젝트에 문서 및 미디어 파일에 필요한 디렉터리가 있는지 확인하세요.
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// 디렉터리가 아직 없으면 만듭니다.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## 2단계: 프레젠테이션 클래스 인스턴스화
PPTX 파일을 나타내는 Presentation 클래스의 인스턴스를 만듭니다.
```csharp
using (Presentation pres = new Presentation())
{
    // 첫 번째 슬라이드 가져오기
    ISlide sld = pres.Slides[0];
```
## 3단계: 프레젠테이션 내부에 비디오 삽입
프레젠테이션 내에 비디오를 삽입하려면 다음 코드를 사용하십시오.
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## 4단계: 비디오 프레임 추가
이제 슬라이드에 비디오 프레임을 추가합니다.
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## 5단계: 비디오 속성 설정
비디오를 비디오 프레임으로 설정하고 재생 모드와 볼륨을 구성합니다.
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## 6단계: 프레젠테이션 저장
마지막으로 PPTX 파일을 디스크에 저장합니다.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
프레젠테이션에 포함하려는 각 비디오에 대해 이 단계를 반복합니다.
## 결론
축하해요! .NET용 Aspose.Slides를 사용하여 프레젠테이션에 포함된 비디오 프레임을 성공적으로 추가했습니다. 이 동적 기능은 프레젠테이션을 새로운 차원으로 끌어올려 슬라이드에 원활하게 통합된 멀티미디어 요소로 청중의 시선을 사로잡을 수 있습니다.
## 자주 묻는 질문
### 프레젠테이션의 모든 슬라이드에 비디오를 포함할 수 있나요?
 예, 다음에서 색인을 수정하여 모든 슬라이드를 선택할 수 있습니다.`pres.Slides[index]`.
### 어떤 비디오 형식이 지원되나요?
Aspose.Slides는 MP4, AVI 및 WMV를 포함한 다양한 비디오 형식을 지원합니다.
### 비디오 프레임의 크기와 위치를 사용자 정의할 수 있나요?
 전적으로! 매개변수를 조정하세요.`AddVideoFrame(x, y, width, height, video)` 필요에 따라.
### 삽입할 수 있는 동영상 수에 제한이 있나요?
포함된 비디오 수는 일반적으로 프레젠테이션 소프트웨어의 용량에 따라 제한됩니다.
### 추가 지원을 요청하거나 내 경험을 공유하려면 어떻게 해야 합니까?
 방문하다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티 지원 및 토론을 위해.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
