---
title: PowerPoint에서 웹 소스의 비디오 프레임 추가
linktitle: PowerPoint에서 웹 소스의 비디오 프레임 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 웹 소스에서 비디오 프레임을 추가하여 PowerPoint 프레젠테이션을 향상시키는 방법을 알아보세요.
type: docs
weight: 18
url: /ko/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---
## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 YouTube와 같은 웹 소스의 비디오 프레임을 PowerPoint 프레젠테이션에 추가하는 방법을 알아봅니다. 이러한 단계별 지침을 따르면 매력적인 멀티미디어 요소를 통합하여 프레젠테이션을 향상시킬 수 있습니다.
## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.Slides가 다운로드되어 Java 프로젝트에 추가되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
- 웹 소스(예: YouTube)에 액세스하려면 활성 인터넷 연결이 필요합니다.

## 패키지 가져오기
먼저 필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;
import com.aspose.slides.examples.RunExamples;
import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## 1단계: PowerPoint 프레젠테이션 개체 만들기
PowerPoint 프레젠테이션을 나타내는 Presentation 개체를 초기화합니다.
```java
Presentation pres = new Presentation();
```
## 2단계: 비디오 프레임 추가
이제 프레젠테이션에 비디오 프레임을 추가해 보겠습니다. 이 프레임에는 웹 소스의 비디오가 포함됩니다. addVideoFrame 메소드를 사용하겠습니다:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID');
```
"VIDEO_ID"를 삽입하려는 YouTube 동영상의 ID로 바꾸세요.
## 3단계: 비디오 재생 모드 설정
비디오 프레임의 재생 모드를 설정합니다. 이 예에서는 Auto로 설정하겠습니다.
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## 4단계: 썸네일 로드
시각적 매력을 높이기 위해 동영상의 미리보기 이미지를 로드하겠습니다. 이 단계에는 웹 소스에서 썸네일 이미지를 가져오는 작업이 포함됩니다.
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## 5단계: 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 저장합니다.
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
"YOUR_DIRECTORY"를 프레젠테이션을 저장하려는 디렉터리로 바꾸세요.

## 결론
축하해요! Aspose.Slides for Java를 사용하여 PowerPoint의 웹 소스에서 비디오 프레임을 추가하는 방법을 성공적으로 배웠습니다. 비디오와 같은 멀티미디어 요소를 통합하면 프레젠테이션의 영향력과 참여도를 크게 높일 수 있습니다.
## FAQ
### YouTube 이외의 소스에서 비디오를 추가할 수 있나요?
예. 삽입 가능한 링크를 제공하는 한 다양한 웹 소스에서 비디오를 추가할 수 있습니다.
### 삽입된 비디오를 재생하려면 인터넷 연결이 필요합니까?
예, 웹 소스에서 비디오를 스트리밍하려면 활성 인터넷 연결이 필요합니다.
### 비디오 프레임의 모양을 사용자 정의할 수 있나요?
전적으로! Aspose.Slides는 비디오 프레임의 모양과 동작을 사용자 정의하기 위한 광범위한 옵션을 제공합니다.
### Aspose.Slides는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 다양한 PowerPoint 버전을 지원하여 다양한 플랫폼 간의 호환성을 보장합니다.
### Aspose.Slides에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 당신은 방문 할 수 있습니다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 지원, 문서 및 커뮤니티 지원이 필요합니다.