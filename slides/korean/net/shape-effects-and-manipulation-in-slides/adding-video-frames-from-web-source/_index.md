---
title: .NET용 Aspose.Slides를 사용하여 비디오 프레임 삽입 튜토리얼
linktitle: Aspose.Slides를 사용하여 프레젠테이션 슬라이드에 웹 소스의 비디오 프레임 추가
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: Aspose.Slides for .NET을 사용하여 PowerPoint 슬라이드에 비디오 프레임을 원활하게 삽입하는 방법을 알아보세요. 손쉽게 멀티미디어를 사용하여 프레젠테이션을 향상하세요.
weight: 20
url: /ko/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
역동적인 프레젠테이션 세계에서 멀티미디어 요소를 통합하면 참여도를 크게 높이고 영향력 있는 메시지를 전달할 수 있습니다. 이를 달성하는 한 가지 강력한 방법은 프레젠테이션 슬라이드에 비디오 프레임을 삽입하는 것입니다. 이 튜토리얼에서는 .NET용 Aspose.Slides를 사용하여 이를 원활하게 수행하는 방법을 살펴보겠습니다. Aspose.Slides는 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 조작할 수 있도록 하는 강력한 라이브러리로, 슬라이드 생성, 편집 및 향상을 위한 광범위한 기능을 제공합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 사항이 준비되어 있는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Slides: 다음에서 라이브러리를 다운로드하고 설치하세요.[.NET 문서용 Aspose.Slides](https://reference.aspose.com/slides/net/).
2. 샘플 비디오 파일: 프레젠테이션에 포함할 비디오 파일을 준비합니다. 제공된 예를 "Wildlife.mp4"라는 비디오와 함께 사용할 수 있습니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.Slides 기능을 활용하는 데 필요한 네임스페이스를 포함합니다.
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드에 비디오 프레임을 삽입하는 과정을 관리 가능한 단계로 나누어 보겠습니다.
## 1단계: 디렉터리 설정
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// 디렉터리가 아직 없으면 만듭니다.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
"Your Document Directory" 및 "Your Media Directory"를 프로젝트의 적절한 경로로 바꾸십시오.
## 2단계: 프리젠테이션 개체 만들기
```csharp
using (Presentation pres = new Presentation())
{
    // 첫 번째 슬라이드 가져오기
    ISlide sld = pres.Slides[0];
```
새 프레젠테이션을 초기화하고 비디오 프레임을 삽입하기 위한 첫 번째 슬라이드에 액세스합니다.
## 3단계: 프레젠테이션에 비디오 포함
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
 활용`AddVideo` 파일 경로와 로드 동작을 지정하여 프레젠테이션에 비디오를 포함하는 메서드입니다.
## 4단계: 비디오 프레임 추가
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
슬라이드에 비디오 프레임을 만들고 위치와 크기를 정의합니다.
## 5단계: 비디오 설정 구성
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
비디오 프레임을 삽입된 비디오와 연결하고, 재생 모드를 설정하고, 원하는 대로 볼륨을 조정하세요.
## 6단계: 프레젠테이션 저장
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
포함된 비디오 프레임과 함께 수정된 프레젠테이션을 저장합니다.
## 결론
축하해요! Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드에 비디오 프레임을 삽입하는 방법을 성공적으로 배웠습니다. 이 기능은 청중을 사로잡는 역동적이고 매력적인 프레젠테이션을 만들 수 있는 흥미로운 가능성을 열어줍니다.
## 자주 묻는 질문
### Aspose.Slides를 사용하여 다양한 형식의 비디오를 삽입할 수 있나요?
예, Aspose.Slides는 다양한 비디오 형식을 지원하여 프레젠테이션의 유연성을 보장합니다.
### 삽입된 비디오의 재생 설정을 어떻게 제어할 수 있나요?
 조정하다`PlayMode` 그리고`Volume` 재생 동작을 사용자 정의하려면 비디오 프레임의 속성을 사용하세요.
### Aspose.Slides는 최신 버전의 .NET과 호환됩니까?
Aspose.Slides는 최신 .NET 프레임워크와의 호환성을 유지하기 위해 정기적으로 업데이트됩니다.
### Aspose.Slides를 사용하여 단일 슬라이드에 여러 비디오를 포함할 수 있나요?
예, 슬라이드에 추가 비디오 프레임을 추가하여 여러 비디오를 포함할 수 있습니다.
### Aspose.Slides 관련 쿼리에 대한 지원은 어디서 찾을 수 있나요?
 방문하다[Aspose.슬라이드 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티 지원 및 토론을 위해.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
