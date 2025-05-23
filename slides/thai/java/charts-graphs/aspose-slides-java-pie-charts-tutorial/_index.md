---
"date": "2025-04-17"
"description": "เรียนรู้วิธีสร้างและปรับแต่งแผนภูมิวงกลมโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้ครอบคลุมทุกอย่างตั้งแต่การตั้งค่าจนถึงการปรับแต่งขั้นสูง"
"title": "การสร้างแผนภูมิวงกลมใน Java ด้วย Aspose.Slides คู่มือที่ครอบคลุม"
"url": "/th/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การสร้างแผนภูมิวงกลมด้วย Aspose.Slides สำหรับ Java: บทช่วยสอนแบบสมบูรณ์

## การแนะนำ
การสร้างงานนำเสนอที่น่าดึงดูดและมีชีวิตชีวาถือเป็นสิ่งสำคัญสำหรับการนำเสนอข้อมูลที่มีประสิทธิภาพ ด้วย Aspose.Slides สำหรับ Java คุณสามารถผสานแผนภูมิที่ซับซ้อน เช่น แผนภูมิวงกลม เข้ากับสไลด์ของคุณได้อย่างราบรื่น ช่วยเพิ่มการแสดงข้อมูลได้อย่างง่ายดาย คู่มือที่ครอบคลุมนี้จะแนะนำคุณตลอดกระบวนการสร้างและปรับแต่งแผนภูมิวงกลมโดยใช้ Aspose.Slides Java และแก้ไขปัญหาการนำเสนอทั่วไปได้อย่างง่ายดาย

**สิ่งที่คุณจะได้เรียนรู้:**
- การเริ่มต้นการนำเสนอและการเพิ่มสไลด์
- การสร้างและการกำหนดค่าแผนภูมิวงกลมบนสไลด์ของคุณ
- การตั้งค่าชื่อแผนภูมิ ป้ายข้อมูล และสี
- เพิ่มประสิทธิภาพการทำงานและบริหารจัดการทรัพยากรอย่างมีประสิทธิผล
- การรวม Aspose.Slides เข้ากับโปรเจ็กต์ Java โดยใช้ Maven หรือ Gradle

เริ่มต้นด้วยการตรวจสอบให้แน่ใจว่าคุณมีเครื่องมือและความรู้ทั้งหมดที่จำเป็นในการปฏิบัติตาม!

## ข้อกำหนดเบื้องต้น
ก่อนจะเข้าสู่บทช่วยสอนนี้ ให้แน่ใจว่าคุณมีการตั้งค่าต่อไปนี้พร้อมแล้ว:

### ไลบรารี เวอร์ชัน และการอ้างอิงที่จำเป็น
- **Aspose.Slides สำหรับ Java**: ให้แน่ใจว่าคุณมีเวอร์ชัน 25.4 ขึ้นไป
- **ชุดพัฒนา Java (JDK)**: ต้องมีเวอร์ชัน 16 ขึ้นไป

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- สภาพแวดล้อมการพัฒนาที่มีการติดตั้งและกำหนดค่า Java
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น IntelliJ IDEA, Eclipse หรือ NetBeans

### ข้อกำหนดเบื้องต้นของความรู้
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- ความคุ้นเคยกับ Maven หรือ Gradle สำหรับการจัดการการอ้างอิง

## การตั้งค่า Aspose.Slides สำหรับ Java
หากต้องการเริ่มใช้ Aspose.Slides ในโปรเจ็กต์ Java ของคุณ คุณต้องเพิ่มไลบรารีเป็นส่วนที่ต้องพึ่งพา คุณสามารถทำได้โดยใช้เครื่องมือสร้างต่างๆ ดังต่อไปนี้:

**เมเวน**
เพิ่มส่วนนี้ลงในของคุณ `pom.xml` ไฟล์:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**แกรเดิล**
รวมสิ่งต่อไปนี้ไว้ในของคุณ `build.gradle` ไฟล์:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**ดาวน์โหลดโดยตรง**
หากคุณไม่ต้องการใช้เครื่องมือสร้าง โปรดดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose.Slides สำหรับการเปิดตัว Java](https://releases-aspose.com/slides/java/).

### ขั้นตอนการรับใบอนุญาต
- **ทดลองใช้งานฟรี**:เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจฟีเจอร์ Aspose.Slides
- **ใบอนุญาตชั่วคราว**:ขอใบอนุญาตชั่วคราวเพื่อใช้งานต่อเนื่องโดยไม่มีข้อจำกัด
- **ซื้อ**:โปรดพิจารณาซื้อหากคุณต้องการการเข้าถึงในระยะยาว

**การเริ่มต้นและการตั้งค่าเบื้องต้น**
ในการเริ่มใช้ Aspose.Slides ให้เริ่มต้นโครงการของคุณด้วยการสร้างวัตถุการนำเสนอใหม่:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## คู่มือการใช้งาน
ตอนนี้มาแบ่งกระบวนการการเพิ่มและปรับแต่งแผนภูมิวงกลมออกเป็นขั้นตอนต่างๆ ที่จัดการได้

### เริ่มต้นการนำเสนอและสไลด์
เริ่มต้นด้วยการตั้งค่าการนำเสนอใหม่และเข้าถึงสไลด์แรก นี่คือพื้นที่สำหรับสร้างแผนภูมิ:
```java
import com.aspose.slides.*;

// สร้างอินสแตนซ์การนำเสนอใหม่
Presentation presentation = new Presentation();
// เข้าถึงสไลด์แรกในการนำเสนอ
islide slides = presentation.getSlides().get_Item(0);
```

### เพิ่มแผนภูมิวงกลมลงในสไลด์
แทรกแผนภูมิวงกลมลงในตำแหน่งที่ระบุโดยใช้ชุดข้อมูลเริ่มต้น:
```java
import com.aspose.slides.*;

// เพิ่มแผนภูมิวงกลมที่ตำแหน่ง (100, 100) และมีขนาด (400, 400)
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### ตั้งค่าชื่อแผนภูมิ
ปรับแต่งแผนภูมิของคุณโดยการตั้งค่าและจัดตำแหน่งชื่อเรื่องให้ตรงกลาง:
```java
import com.aspose.slides.*;

// เพิ่มชื่อให้กับแผนภูมิวงกลม
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### กำหนดค่าป้ายข้อมูลสำหรับชุดข้อมูล
ตรวจสอบให้แน่ใจว่าป้ายข้อมูลแสดงค่าเพื่อความชัดเจน:
```java
import com.aspose.slides.*;

// แสดงค่าข้อมูลในซีรีส์แรก
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### เตรียมแผ่นงานข้อมูลแผนภูมิ
ตั้งค่าแผ่นงานข้อมูลแผนภูมิของคุณโดยการล้างชุดข้อมูลและหมวดหมู่ที่มีอยู่:
```java
import com.aspose.slides.*;

// เตรียมสมุดงานข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### เพิ่มหมวดหมู่ลงในแผนภูมิ
กำหนดหมวดหมู่สำหรับแผนภูมิวงกลมของคุณ:
```java
import com.aspose.slides.*;

// เพิ่มหมวดหมู่ใหม่
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### เพิ่มซีรีส์และเติมจุดข้อมูล
สร้างซีรีส์และเติมจุดข้อมูล:
```java
import com.aspose.slides.*;

// เพิ่มซีรีย์ใหม่และตั้งชื่อ
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### ปรับแต่งสีและขอบของซีรีย์
เพิ่มความน่าสนใจทางสายตาด้วยการตั้งค่าสีและปรับแต่งขอบ:
```java
import com.aspose.slides.*;

// ตั้งค่าสีต่างๆ ให้กับแต่ละภาคส่วน
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// ทำซ้ำสำหรับจุดข้อมูลอื่นด้วยสีและรูปแบบที่แตกต่างกัน
```

### กำหนดค่าป้ายข้อมูลที่กำหนดเอง
ปรับแต่งป้ายกำกับสำหรับจุดข้อมูลแต่ละจุด:
```java
import com.aspose.slides.*;

// กำหนดค่าฉลากที่กำหนดเอง
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// เปิดใช้งานเส้นผู้นำสำหรับป้ายกำกับ
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### ตั้งค่ามุมการหมุนและบันทึกการนำเสนอ
ทำให้แผนภูมิวงกลมของคุณเสร็จสิ้นโดยการตั้งค่ามุมการหมุนและบันทึกการนำเสนอ:
```java
import com.aspose.slides.*;

// ตั้งค่ามุมการหมุน
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// บันทึกการนำเสนอลงในไฟล์
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีสร้างและปรับแต่งแผนภูมิวงกลมโดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้แล้ว คุณจะสามารถปรับปรุงการนำเสนอของคุณด้วยการแสดงข้อมูลที่น่าสนใจ หากคุณมีคำถามหรือต้องการความช่วยเหลือเพิ่มเติม โปรดติดต่อเรา

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}