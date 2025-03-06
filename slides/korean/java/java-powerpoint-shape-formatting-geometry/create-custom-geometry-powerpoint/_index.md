---
title: PowerPoint에서 사용자 정의 형상 만들기
linktitle: PowerPoint에서 사용자 정의 형상 만들기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint에서 사용자 정의 기하학 모양을 만드는 방법을 알아보세요. 이 가이드는 독특한 모양으로 프레젠테이션을 향상시키는 데 도움이 될 것입니다.
weight: 21
url: /ko/java/java-powerpoint-shape-formatting-geometry/create-custom-geometry-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
PowerPoint에서 사용자 정의 모양과 기하학을 만들면 프레젠테이션의 시각적 매력을 크게 향상시킬 수 있습니다. Aspose.Slides for Java는 개발자가 PowerPoint 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드에서 사용자 정의 기하학, 특히 별 모양을 만드는 방법을 살펴보겠습니다. 뛰어들어보자!
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2. Java용 Aspose.Slides: Aspose.Slides 라이브러리를 다운로드하고 설치합니다.
   - [Java용 Aspose.Slides 다운로드](https://releases.aspose.com/slides/java/)
3. IDE(통합 개발 환경): IntelliJ IDEA 또는 Eclipse와 같은 IDE입니다.
4. Java에 대한 기본 이해: Java 프로그래밍에 대한 지식이 필요합니다.
## 패키지 가져오기
코딩 부분을 살펴보기 전에 필요한 패키지를 가져와 보겠습니다.
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.util.ArrayList;
import java.util.List;
```
## 1단계: 프로젝트 설정
 시작하려면 Java 프로젝트를 설정하고 프로젝트 종속성에 Aspose.Slides for Java 라이브러리를 포함하세요. Maven을 사용하는 경우 다음 종속성을 추가하십시오.`pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>YOUR_VERSION_HERE</version>
</dependency>
```
## 2단계: 프레젠테이션 초기화
이 단계에서는 새 PowerPoint 프레젠테이션을 초기화합니다.
```java
public static void main(String[] args) throws Exception {
    // 프레젠테이션 객체 초기화
    Presentation pres = new Presentation();
    try {
        // 귀하의 코드는 여기에 저장됩니다
    } finally {
        if (pres != null) pres.dispose();
    }
}
```
## 3단계: 별 형상 경로 생성
별 모양에 대한 기하 경로를 생성하는 메서드를 만들어야 합니다. 이 방법은 외부 및 내부 반경을 기준으로 별의 점을 계산합니다.
```java
private static GeometryPath createStarGeometry(float outerRadius, float innerRadius) {
    GeometryPath starPath = new GeometryPath();
    List<Point2D.Float> points = new ArrayList<>();
    int step = 72; // 별점 사이의 각도
    for (int angle = -90; angle < 270; angle += step) {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.cos(radians);
        double y = outerRadius * Math.sin(radians);
        points.add(new Point2D.Float((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.cos(radians);
        y = innerRadius * Math.sin(radians);
        points.add(new Point2D.Float((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.moveTo(points.get(0));
    for (int i = 1; i < points.size(); i++) {
        starPath.lineTo(points.get(i));
    }
    starPath.closeFigure();
    return starPath;
}
```
## 4단계: 슬라이드에 사용자 정의 모양 추가
다음으로, 이전 단계에서 만든 별 모양 경로를 사용하여 프레젠테이션의 첫 번째 슬라이드에 사용자 정의 모양을 추가하겠습니다.
```java
// 슬라이드에 사용자 정의 모양 추가
float R = 100, r = 50; // 외부 및 내부 별 반경
GeometryPath starPath = createStarGeometry(R, r);
// 새 모양 만들기
GeometryShape shape = (GeometryShape)pres.getSlides().get_Item(0).
        getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
// 모양에 새 형상 경로 설정
shape.setGeometryPath(starPath);
```
## 5단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 파일로 저장합니다.
```java
// 출력 파일 이름
String resultPath = "GeometryShapeCreatesCustomGeometry.pptx";
// 프레젠테이션 저장
pres.save(resultPath, SaveFormat.Pptx);
```

## 결론
Aspose.Slides for Java를 사용하여 PowerPoint에서 사용자 정의 형상을 만드는 것은 간단하며 프레젠테이션에 많은 시각적 흥미를 더해줍니다. 단 몇 줄의 코드만으로 별과 같은 복잡한 모양을 생성하고 이를 슬라이드에 포함할 수 있습니다. 이 가이드에서는 프로젝트 설정부터 최종 프레젠테이션 저장까지 프로세스를 단계별로 다루었습니다.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 Java 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 수정 및 관리할 수 있는 강력한 라이브러리입니다.
### 별 외에 다른 모양을 만들 수 있나요?
예, 형상 경로를 정의하여 다양한 사용자 정의 모양을 만들 수 있습니다.
### Aspose.Slides for Java는 무료인가요?
Aspose.Slides for Java는 무료 평가판을 제공합니다. 장기간 사용하려면 라이센스를 구입해야 합니다.
### Aspose.Slides for Java를 실행하려면 특별한 설정이 필요합니까?
JDK를 설치하고 프로젝트에 Aspose.Slides 라이브러리를 포함하는 것 외에는 특별한 설정이 필요하지 않습니다.
### Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 에서 지원을 받으실 수 있습니다.[Aspose.Slides 지원 포럼](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
