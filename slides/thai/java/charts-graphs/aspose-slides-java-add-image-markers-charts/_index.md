---
"date": "2025-04-17"
"description": "เรียนรู้วิธีปรับปรุงแผนภูมิของคุณใน Aspose.Slides สำหรับ Java โดยเพิ่มเครื่องหมายรูปภาพที่กำหนดเอง เพิ่มการมีส่วนร่วมด้วยการนำเสนอที่มีเอกลักษณ์เฉพาะตัว"
"title": "การควบคุม Aspose.Slides Java&#58; การเพิ่มเครื่องหมายภาพลงในแผนภูมิ"
"url": "/th/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การเรียนรู้ Aspose.Slides ใน Java: การเพิ่มเครื่องหมายภาพลงในแผนภูมิ

## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดสายตาเป็นกุญแจสำคัญในการสื่อสารอย่างมีประสิทธิผล และแผนภูมิเป็นเครื่องมือที่มีประสิทธิภาพในการถ่ายทอดข้อมูลที่ซับซ้อนได้อย่างชัดเจน เครื่องหมายแผนภูมิมาตรฐานบางครั้งอาจไม่สามารถช่วยให้ข้อมูลของคุณโดดเด่นได้ ด้วย Aspose.Slides สำหรับ Java คุณสามารถปรับปรุงแผนภูมิของคุณได้โดยการเพิ่มรูปภาพที่กำหนดเองเป็นเครื่องหมาย ทำให้แผนภูมิน่าสนใจและให้ข้อมูลมากขึ้น

ในบทช่วยสอนนี้ เราจะมาสำรวจวิธีการผสานรวมตัวระบุภาพเข้ากับแผนภูมิของคุณโดยใช้ไลบรารี Aspose.Slides ใน Java เมื่อคุณเชี่ยวชาญเทคนิคเหล่านี้แล้ว คุณจะสามารถสร้างงานนำเสนอที่ดึงดูดความสนใจด้วยองค์ประกอบภาพที่เป็นเอกลักษณ์ได้

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีการตั้งค่า Aspose.Slides สำหรับ Java
- การสร้างการนำเสนอและแผนภูมิพื้นฐาน
- การเพิ่มเครื่องหมายภาพลงในจุดข้อมูลแผนภูมิ
- การกำหนดค่าการตั้งค่าเครื่องหมายสำหรับการแสดงภาพที่เหมาะสมที่สุด

พร้อมที่จะยกระดับแผนภูมิของคุณหรือยัง มาเจาะลึกข้อกำหนดเบื้องต้นก่อนเริ่มต้นกันเลย!

### ข้อกำหนดเบื้องต้น
หากต้องการทำตามบทช่วยสอนนี้ คุณจะต้องมี:
1. **Aspose.Slides สำหรับไลบรารี Java**:รับได้ผ่านการอ้างอิง Maven หรือ Gradle หรือดาวน์โหลดโดยตรงจาก Aspose
2. **สภาพแวดล้อมการพัฒนา Java**:ตรวจสอบให้แน่ใจว่าได้ติดตั้ง JDK 16 ไว้ในเครื่องของคุณแล้ว
3. **ความรู้พื้นฐานด้านการเขียนโปรแกรม Java**: ความคุ้นเคยกับโครงสร้างและแนวคิดของ Java จะเป็นประโยชน์

## การตั้งค่า Aspose.Slides สำหรับ Java
ก่อนที่จะเจาะลึกโค้ด เรามาตั้งค่าสภาพแวดล้อมการพัฒนาด้วยไลบรารีที่จำเป็นกันก่อน

### การติดตั้ง Maven
เพิ่มการอ้างอิงต่อไปนี้ให้กับของคุณ `pom.xml` ไฟล์:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การติดตั้ง Gradle
รวมสิ่งนี้ไว้ในของคุณ `build.gradle` ไฟล์:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
หรือดาวน์โหลดเวอร์ชันล่าสุดได้จาก [Aspose.Slides สำหรับการเปิดตัว Java](https://releases-aspose.com/slides/java/).

#### ขั้นตอนการรับใบอนุญาต
- **ทดลองใช้งานฟรี**เริ่มต้นด้วยใบอนุญาตชั่วคราวเพื่อสำรวจฟีเจอร์ของ Aspose.Slides
- **ใบอนุญาตชั่วคราว**:เข้าถึงคุณสมบัติขั้นสูงโดยการรับใบอนุญาตชั่วคราว
- **ซื้อ**:หากต้องการใช้ในระยะยาว ควรพิจารณาซื้อใบอนุญาตแบบเต็มรูปแบบ

### การเริ่มต้นและการตั้งค่าเบื้องต้น
เริ่มต้นการใช้งาน `Presentation` วัตถุที่จะเริ่มสร้างสไลด์:

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // โค้ดของคุณสำหรับการเพิ่มสไลด์และแผนภูมิอยู่ที่นี่
    }
}
```

## คู่มือการใช้งาน
ตอนนี้เรามาดูขั้นตอนการเพิ่มเครื่องหมายรูปภาพลงในชุดแผนภูมิของคุณกัน

### สร้างงานนำเสนอใหม่ด้วยแผนภูมิ
ขั้นแรก เราต้องมีสไลด์ที่เราสามารถเพิ่มแผนภูมิของเราได้:

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // เริ่มต้นวัตถุการนำเสนอ
        Presentation presentation = new Presentation();

        // รับสไลด์แรกจากคอลเลกชัน
        ISlide slide = presentation.getSlides().get_Item(0);

        // เพิ่มแผนภูมิเส้นเริ่มต้นด้วยเครื่องหมายลงในสไลด์
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### การเข้าถึงและกำหนดค่าข้อมูลแผนภูมิ
ต่อไปเราจะเข้าถึงแผ่นงานข้อมูลของแผนภูมิของเราเพื่อจัดการชุดข้อมูล:

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // ล้างซีรีย์ที่มีอยู่และเพิ่มซีรีย์ใหม่
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### เพิ่มเครื่องหมายภาพลงในจุดข้อมูลแผนภูมิ
ตอนนี้มาถึงส่วนที่น่าตื่นเต้น—การเพิ่มรูปภาพเป็นเครื่องหมาย:

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // โหลดและเพิ่มรูปภาพเป็นเครื่องหมาย
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // เพิ่มจุดข้อมูลโดยใช้รูปภาพเป็นเครื่องหมาย
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### กำหนดค่าเครื่องหมายชุดแผนภูมิและบันทึกการนำเสนอ
สุดท้ายนี้ ให้ปรับขนาดเครื่องหมายเพื่อให้มองเห็นได้ชัดเจนขึ้นและบันทึกการนำเสนอของเรา:

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // โหลดและเพิ่มรูปภาพเป็นเครื่องหมาย (ตัวอย่างการใช้เส้นทางตัวแทน)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## บทสรุป
หากทำตามคำแนะนำนี้ คุณจะได้เรียนรู้วิธีปรับปรุงแผนภูมิของคุณใน Aspose.Slides สำหรับ Java โดยการเพิ่มเครื่องหมายรูปภาพแบบกำหนดเอง แนวทางนี้สามารถเพิ่มความมีส่วนร่วมและความชัดเจนในการนำเสนอของคุณได้อย่างมาก

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}