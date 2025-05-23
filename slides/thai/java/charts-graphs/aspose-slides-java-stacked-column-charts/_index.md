---
"date": "2025-04-17"
"description": "เรียนรู้การสร้างงานนำเสนอระดับมืออาชีพโดยใช้ Aspose.Slides สำหรับ Java คู่มือนี้ครอบคลุมถึงการตั้งค่าสภาพแวดล้อม การเพิ่มแผนภูมิคอลัมน์แบบซ้อนกัน และการปรับแต่งเพื่อความชัดเจน"
"title": "เรียนรู้การสร้างแผนภูมิคอลัมน์แบบเรียงซ้อนใน Java ด้วย Aspose.Slides และคู่มือฉบับสมบูรณ์"
"url": "/th/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เรียนรู้การสร้างแผนภูมิคอลัมน์แบบเรียงซ้อนใน Java ด้วย Aspose.Slides: คู่มือฉบับสมบูรณ์

## การแนะนำ

ยกระดับการนำเสนอของคุณด้วยการรวมการแสดงข้อมูลเชิงลึกด้วยพลังของ Aspose.Slides สำหรับ Java การสร้างสไลด์ที่ดูเป็นมืออาชีพด้วยแผนภูมิคอลัมน์แบบซ้อนกันนั้นเป็นเรื่องง่าย ไม่ว่าคุณจะกำลังเตรียมรายงานธุรกิจหรือแสดงสถิติโครงการ

ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีใช้ Aspose.Slides สำหรับ Java เพื่อสร้างการนำเสนอแบบไดนามิกและเพิ่มแผนภูมิคอลัมน์แบบเรียงซ้อนที่ดึงดูดสายตา เมื่ออ่านคู่มือนี้จบ คุณจะมีทักษะที่จำเป็นในการ:
- ตั้งค่าสภาพแวดล้อมของคุณเพื่อใช้ Aspose.Slides
- สร้างการนำเสนอตั้งแต่เริ่มต้น
- เพิ่มและปรับแต่งแผนภูมิคอลัมน์แบบเรียงซ้อนเปอร์เซ็นต์
- จัดรูปแบบแกนแผนภูมิและป้ายข้อมูลเพื่อความชัดเจน

มาเริ่มสร้างงานนำเสนอที่สามารถดึงดูดผู้ฟังของคุณกันดีกว่า

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- **ชุดพัฒนา Java (JDK):** เวอร์ชัน 8 ขึ้นไป.
- **ไอดี:** สภาพแวดล้อมการพัฒนาแบบบูรณาการ เช่น IntelliJ IDEA หรือ Eclipse
- **เมเวน/เกรเดิล:** สำหรับการจัดการการอ้างอิง (ทางเลือกแต่แนะนำ)
- **ความรู้พื้นฐานเกี่ยวกับ Java:** มีความคุ้นเคยกับแนวคิดการเขียนโปรแกรมภาษา Java

## การตั้งค่า Aspose.Slides สำหรับ Java
ในการเริ่มต้น คุณต้องรวมไลบรารี Aspose.Slides ไว้ในโปรเจ็กต์ของคุณ ดังต่อไปนี้:

**เมเวน:**
เพิ่มการอ้างอิงนี้ให้กับคุณ `pom.xml` ไฟล์:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**เกรเดิ้ล:**
รวมสิ่งนี้ไว้ในของคุณ `build.gradle` ไฟล์:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**ดาวน์โหลดโดยตรง:**
หรือดาวน์โหลด JAR เวอร์ชันล่าสุดจาก [Aspose.Slides สำหรับการเปิดตัว Java](https://releases-aspose.com/slides/java/).

### การขอใบอนุญาต
คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจฟีเจอร์ของ Aspose.Slides หากต้องการลบข้อจำกัดในการประเมิน โปรดพิจารณาซื้อใบอนุญาตชั่วคราวหรือใบอนุญาตที่ซื้อมา
- **ทดลองใช้งานฟรี:** เข้าถึงคุณสมบัติที่จำกัดโดยไม่ต้องเสียค่าใช้จ่ายทันที
- **ใบอนุญาตชั่วคราว:** ขอความผ่านทาง [เว็บไซต์ของ Aspose](https://purchase-aspose.com/temporary-license/).
- **ซื้อ:** เยี่ยมชมหน้าการซื้อเพื่อการเข้าถึงแบบเต็มรูปแบบ

### การเริ่มต้นขั้นพื้นฐาน
นี่คือวิธีการเริ่มต้น Aspose.Slides ในแอปพลิเคชัน Java ของคุณ:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // สร้างอินสแตนซ์ของคลาสการนำเสนอ
        Presentation presentation = new Presentation();
        
        // ดำเนินการกับวัตถุการนำเสนอ
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## คู่มือการใช้งาน

### การสร้างงานนำเสนอและการเพิ่มสไลด์
**ภาพรวม:**
เริ่มต้นด้วยการสร้างการนำเสนอแบบง่ายๆ ด้วยสไลด์เริ่มต้น ซึ่งถือเป็นพื้นฐานสำหรับการปรับปรุงเพิ่มเติม

#### ขั้นตอนที่ 1: เริ่มต้นวัตถุการนำเสนอ
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // สร้างอินสแตนซ์การนำเสนอใหม่
        Presentation presentation = new Presentation();
        
        // อ้างอิงสไลด์แรก (สร้างอัตโนมัติ)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### ขั้นตอนที่ 2: บันทึกการนำเสนอ
```java
// บันทึกการนำเสนอลงในไฟล์
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### การเพิ่มแผนภูมิคอลัมน์แบบเรียงซ้อนเปอร์เซ็นต์ลงในสไลด์
**ภาพรวม:**
เพิ่มประสิทธิภาพสไลด์ของคุณด้วยการเพิ่มแผนภูมิคอลัมน์แบบเรียงซ้อนเปอร์เซ็นต์ ช่วยให้เปรียบเทียบข้อมูลได้อย่างง่ายดาย

#### ขั้นตอนที่ 1: เริ่มต้นและเข้าถึงสไลด์
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // ดำเนินการเพิ่มแผนภูมิในขั้นตอนถัดไป
    }
}
```

#### ขั้นตอนที่ 2: เพิ่มแผนภูมิลงในสไลด์
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### การปรับแต่งรูปแบบตัวเลขแกนของแผนภูมิ
**ภาพรวม:**
ปรับแต่งรูปแบบตัวเลขของแกนแนวตั้งของแผนภูมิของคุณเพื่อให้สามารถอ่านได้ง่ายขึ้น

#### ขั้นตอนที่ 1: เพิ่มและเข้าถึงแผนภูมิ
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### ขั้นตอนที่ 2: ตั้งค่ารูปแบบตัวเลขแบบกำหนดเอง
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### การเพิ่มชุดข้อมูลและจุดข้อมูลลงในแผนภูมิ
**ภาพรวม:**
เติมแผนภูมิของคุณด้วยชุดข้อมูลเพื่อให้มีข้อมูลและน่าดูมากขึ้น

#### ขั้นตอนที่ 1: เริ่มต้นการนำเสนอและแผนภูมิ
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### ขั้นตอนที่ 2: เพิ่มชุดข้อมูล
```java
// ล้างซีรีย์ที่มีอยู่และเพิ่มซีรีย์ใหม่
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// เพิ่มจุดข้อมูลเพิ่มเติมตามต้องการ
```

### การจัดรูปแบบการเติมสีซีรีย์
**ภาพรวม:**
เพิ่มความสวยงามให้กับแผนภูมิของคุณด้วยการจัดรูปแบบสีเติมของแต่ละชุด

#### ขั้นตอนที่ 1: เริ่มต้นและเข้าถึงแผนภูมิ
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### ขั้นตอนที่ 2: ตั้งค่าสีเติม
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// ทำซ้ำสำหรับซีรีย์อื่นๆ ที่มีสีต่างกัน
```

### การจัดรูปแบบฉลากข้อมูล
**ภาพรวม:**
ทำให้ป้ายข้อมูลของคุณอ่านง่ายขึ้นโดยการกำหนดรูปแบบเอง

#### ขั้นตอนที่ 1: เข้าถึงชุดแผนภูมิและจุดข้อมูล
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### ขั้นตอนที่ 2: ปรับแต่งป้ายข้อมูล
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## บทสรุป
หากทำตามคำแนะนำนี้ คุณจะได้เรียนรู้วิธีการตั้งค่า Aspose.Slides สำหรับ Java และสร้างการนำเสนอแบบไดนามิกด้วยแผนภูมิคอลัมน์แบบเรียงซ้อนเปอร์เซ็นต์ ปรับแต่งแผนภูมิของคุณเพิ่มเติมโดยปรับสีและป้ายกำกับให้เหมาะกับความต้องการของคุณ

สนุกกับการเขียนโค้ด!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}