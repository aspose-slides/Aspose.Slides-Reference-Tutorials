---
"date": "2025-04-17"
"description": "เรียนรู้วิธีการสร้างและกำหนดค่าการนำเสนอแบบไดนามิกด้วยแผนภูมิใน Java โดยใช้ Aspose.Slides เรียนรู้การเพิ่ม ปรับแต่ง และบันทึกการนำเสนออย่างมีประสิทธิภาพ"
"title": "สร้างการนำเสนอ Java ด้วยแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java"
"url": "/th/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการสร้างและกำหนดค่าการนำเสนอด้วยแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java

## การแนะนำ

การสร้างงานนำเสนอแบบไดนามิกที่ถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญในสภาพแวดล้อมทางธุรกิจที่เปลี่ยนแปลงอย่างรวดเร็วในปัจจุบัน ไม่ว่าคุณจะกำลังเตรียมรายงานทางการเงินหรือนำเสนอข้อมูลโครงการ การเพิ่มแผนภูมิจะช่วยเพิ่มผลกระทบของงานนำเสนอของคุณได้อย่างมาก บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการสร้างและกำหนดค่างานนำเสนอด้วยแผนภูมิคอลัมน์แบบเรียงซ้อน 3 มิติโดยใช้ Aspose.Slides สำหรับ Java ซึ่งเป็นไลบรารีอันทรงพลังที่ออกแบบมาเพื่อจัดการงานนำเสนอด้วยโปรแกรม

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีการสร้างงานนำเสนอใหม่
- เพิ่มและกำหนดค่าแผนภูมิในสไลด์
- ปรับแต่งข้อมูลและลักษณะแผนภูมิ
- บันทึกการนำเสนอของคุณอย่างมีประสิทธิภาพ

พร้อมที่จะเรียนรู้การสร้างงานนำเสนอที่ดึงดูดสายตาด้วย Java แล้วหรือยัง มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนจะเริ่มเรียนรู้บทช่วยสอนนี้ ให้แน่ใจว่าคุณได้ครอบคลุมข้อกำหนดเบื้องต้นเหล่านี้แล้ว:

- **ห้องสมุดและสิ่งที่ต้องพึ่งพา**:จะต้องติดตั้ง Aspose.Slides สำหรับ Java
- **การตั้งค่าสภาพแวดล้อม**:ทำงานในสภาพแวดล้อม Java (แนะนำ JDK 16 หรือใหม่กว่า)
- **ฐานความรู้**:ความคุ้นเคยกับแนวคิดการเขียนโปรแกรม Java ขั้นพื้นฐานจะเป็นประโยชน์

## การตั้งค่า Aspose.Slides สำหรับ Java

### การติดตั้ง

หากต้องการรวม Aspose.Slides เข้ากับโปรเจ็กต์ของคุณ ให้ทำตามขั้นตอนเหล่านี้:

**เมเวน**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**แกรเดิล**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**ดาวน์โหลดโดยตรง**: หรือดาวน์โหลดเวอร์ชันล่าสุดได้จาก [Aspose.Slides สำหรับการเปิดตัว Java](https://releases-aspose.com/slides/java/).

### การขอใบอนุญาต
- **ทดลองใช้งานฟรี**:เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติต่างๆ
- **ใบอนุญาตชั่วคราว**: การขอใบอนุญาตชั่วคราวเพื่อการทดสอบขยายเวลา
- **ซื้อ**:รับใบอนุญาตเต็มรูปแบบเพื่อการใช้งานเชิงพาณิชย์

เมื่อติดตั้งแล้ว ให้เริ่มต้นไลบรารีในสภาพแวดล้อม Java ของคุณโดยสร้างอินสแตนซ์ของ `Presentation` ชั้นเรียนนี้จะเป็นการวางรากฐานสำหรับการเพิ่มแผนภูมิและองค์ประกอบอื่นๆ ลงในงานนำเสนอของคุณ

## คู่มือการใช้งาน

### สร้างและกำหนดค่าการนำเสนอด้วยแผนภูมิ

#### ภาพรวม
การสร้างงานนำเสนอตั้งแต่ต้นนั้นเป็นเรื่องง่ายด้วย Aspose.Slides ในส่วนนี้ เราจะเพิ่มแผนภูมิคอลัมน์แบบเรียงซ้อน 3 มิติลงในสไลด์แรกของงานนำเสนอ

**ขั้นตอน:**

1. **เริ่มต้นวัตถุการนำเสนอ**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // เริ่มต้นวัตถุการนำเสนอใหม่
           Presentation presentation = new Presentation();
           
           // เข้าถึงสไลด์แรกในการนำเสนอ
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // เพิ่มแผนภูมิคอลัมน์แบบเรียงซ้อน 3 มิติลงในสไลด์ที่ตำแหน่ง (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **อธิบายพารามิเตอร์**-
   - `ChartType.StackedColumn3D`: ระบุประเภทแผนภูมิ
   - ตำแหน่งและขนาด `(0, 0, 500, 500)`: กำหนดว่าแผนภูมิจะปรากฏที่ตำแหน่งใดบนสไลด์

### กำหนดค่าข้อมูลแผนภูมิ

#### ภาพรวม
หากต้องการให้แผนภูมิของคุณมีความหมาย ให้กำหนดค่าชุดข้อมูลและหมวดหมู่ของแผนภูมิ หัวข้อนี้จะแสดงวิธีการเพิ่มจุดข้อมูลเฉพาะลงในแผนภูมิของคุณ

**ขั้นตอน:**

1. **สมุดงานข้อมูลของแผนภูมิการเข้าถึง**

   ```java
   public static void configureChartData(IChart chart) {
       // ตั้งค่าดัชนีของเวิร์กชีตที่ประกอบด้วยข้อมูลแผนภูมิ
       int defaultWorksheetIndex = 0;
       
       // เข้าถึงสมุดงานข้อมูลของแผนภูมิ
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // เพิ่มซีรีย์ 2 เรื่อง พร้อมชื่อ
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // เพิ่มสามหมวดหมู่
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### ตั้งค่าคุณสมบัติ Rotation3D สำหรับแผนภูมิ

#### ภาพรวม
เพิ่มความน่าสนใจให้กับแผนภูมิของคุณด้วยคุณสมบัติการหมุน 3 มิติ การปรับแต่งนี้ช่วยให้คุณปรับมุมมองและความลึกได้

**ขั้นตอน:**

1. **กำหนดค่าการหมุน 3 มิติ**

   ```java
   public static void setRotation3D(IChart chart) {
       // เปิดใช้งานแกนมุมฉากและกำหนดค่าการหมุนในทิศทาง X, Y และเปอร์เซ็นต์ความลึก
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **อธิบายพารามิเตอร์**-
   - `setRightAngleAxes(true)`:ให้แน่ใจว่าแกนตั้งฉาก
   - ค่าการหมุน: ปรับมุมและความลึกของมุมมอง 3 มิติ

### เติมข้อมูลชุดข้อมูลลงในแผนภูมิ

#### ภาพรวม
การเติมจุดข้อมูลลงในแผนภูมิของคุณถือเป็นสิ่งสำคัญสำหรับการวิเคราะห์ ที่นี่ เราจะเพิ่มค่าเฉพาะลงในชุดข้อมูลภายในแผนภูมิของเรา

**ขั้นตอน:**

1. **เพิ่มจุดข้อมูล**

   ```java
   public static void populateSeriesData(IChart chart) {
       // เข้าถึงชุดแผนภูมิที่สอง
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // เพิ่มจุดข้อมูลสำหรับชุดแท่งด้วยค่าที่ระบุ
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### ปรับการทับซ้อนของซีรีส์ในแผนภูมิ

#### ภาพรวม
การปรับแต่งรูปลักษณ์ของแผนภูมิของคุณให้ดีขึ้นสามารถช่วยให้อ่านได้ง่ายขึ้น หัวข้อนี้จะกล่าวถึงวิธีปรับแต่งคุณสมบัติการทับซ้อนเพื่อให้แสดงข้อมูลได้ดีขึ้น

**ขั้นตอน:**

1. **ตั้งค่าซีรีย์ทับซ้อน**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // รับซีรีส์ที่สองจากแผนภูมิและตั้งค่าการทับซ้อนเป็น 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### บันทึกการนำเสนอ

#### ภาพรวม
เมื่อกำหนดค่าการนำเสนอของคุณแล้ว ให้บันทึกลงในดิสก์ในรูปแบบที่ต้องการ ขั้นตอนนี้จะช่วยให้มั่นใจว่าการเปลี่ยนแปลงทั้งหมดได้รับการเก็บรักษาไว้

**ขั้นตอน:**

1. **บันทึกการนำเสนอ**

   ```java
   public static void savePresentation(Presentation presentation) {
       // บันทึกการนำเสนอที่แก้ไขแล้วลงในไฟล์
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## บทสรุป

ตอนนี้คุณได้เรียนรู้วิธีการสร้างและกำหนดค่าการนำเสนอด้วยแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java แล้ว คู่มือนี้ครอบคลุมถึงการเริ่มต้นการนำเสนอ การเพิ่มแผนภูมิคอลัมน์แบบเรียงซ้อน 3 มิติ การกำหนดค่าชุดข้อมูลและหมวดหมู่ การตั้งค่าคุณสมบัติการหมุน การเติมข้อมูลชุดข้อมูล การปรับการทับซ้อนของชุดข้อมูล และการบันทึกการนำเสนอขั้นสุดท้าย

สำหรับคุณลักษณะขั้นสูงและตัวเลือกการปรับแต่งเพิ่มเติม โปรดดูที่ [เอกสาร Aspose.Slides สำหรับ Java](https://docs-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}