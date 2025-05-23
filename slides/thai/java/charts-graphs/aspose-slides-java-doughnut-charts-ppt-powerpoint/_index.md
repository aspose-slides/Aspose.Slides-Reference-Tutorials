---
"date": "2025-04-17"
"description": "เรียนรู้วิธีใช้ Aspose.Slides สำหรับ Java เพื่อสร้างแผนภูมิโดนัทแบบไดนามิกใน PowerPoint ปรับปรุงการนำเสนอของคุณด้วยขั้นตอนที่ทำตามได้ง่ายและตัวอย่างโค้ด"
"title": "สร้างแผนภูมิโดนัทแบบไดนามิกใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java"
"url": "/th/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิโดนัทแบบไดนามิกใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java

## การแนะนำ
การสร้างงานนำเสนอที่น่าสนใจมักต้องการมากกว่าแค่ข้อความและรูปภาพ แผนภูมิสามารถเพิ่มประสิทธิภาพการเล่าเรื่องได้อย่างมากโดยการแสดงข้อมูลในรูปแบบภาพอย่างมีประสิทธิภาพ อย่างไรก็ตาม นักพัฒนามากมายประสบปัญหาในการผสานรวมคุณลักษณะแผนภูมิแบบไดนามิกเข้ากับไฟล์ PowerPoint ด้วยโปรแกรม บทช่วยสอนนี้สาธิตวิธีใช้ Aspose.Slides สำหรับ Java เพื่อสร้างแผนภูมิโดนัทใน PowerPoint ซึ่งเป็นเครื่องมือที่มีประสิทธิภาพที่ผสมผสานความยืดหยุ่นและความสะดวกในการใช้งาน

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีการเริ่มต้นการนำเสนอโดยใช้ Aspose.Slides สำหรับ Java
- คู่มือทีละขั้นตอนในการเพิ่มแผนภูมิโดนัทลงในสไลด์ของคุณ
- การกำหนดค่าจุดข้อมูลและปรับแต่งคุณสมบัติของฉลาก
- บันทึกการนำเสนอที่ปรับเปลี่ยนแล้วด้วยความเที่ยงตรงสูง

มาสำรวจกันว่าคุณสามารถใช้คุณลักษณะเหล่านี้เพื่อปรับปรุงการนำเสนอของคุณได้อย่างไร ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณคุ้นเคยกับแนวคิดการเขียนโปรแกรม Java ขั้นพื้นฐาน

## ข้อกำหนดเบื้องต้น
หากต้องการปฏิบัติตามบทช่วยสอนนี้อย่างมีประสิทธิผล ต้องแน่ใจว่าคุณมี:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น IntelliJ IDEA หรือ Eclipse
- ติดตั้ง Maven หรือ Gradle เพื่อการจัดการการอ้างอิง
- ใบอนุญาต Aspose.Slides สำหรับ Java ที่ถูกต้อง คุณสามารถรับรุ่นทดลองใช้งานฟรีเพื่อทดสอบคุณสมบัติของมันได้

## การตั้งค่า Aspose.Slides สำหรับ Java
เริ่มต้นด้วยการรวม Aspose.Slides เข้ากับโปรเจ็กต์ของคุณ เลือกระหว่าง Maven และ Gradle ขึ้นอยู่กับว่าคุณชอบแบบไหน:

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

หากคุณต้องการดาวน์โหลดโดยตรง โปรดไปที่ [Aspose.Slides สำหรับการเปิดตัว Java](https://releases.aspose.com/slides/java/) หน้าหนังสือ.

### การขอใบอนุญาต
คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจฟีเจอร์ของ Aspose.Slides หากต้องการใช้งานแบบขยายเวลา ให้ซื้อใบอนุญาตหรือขอใบอนุญาตชั่วคราวจาก [เว็บไซต์ของ Aspose](https://purchase.aspose.com/temporary-license/)ปฏิบัติตามคำแนะนำที่ให้ไว้สำหรับการตั้งค่าสภาพแวดล้อมของคุณและการเริ่มต้น Aspose.Slides ในแอปพลิเคชันของคุณ

## คู่มือการใช้งาน
มาดูขั้นตอนที่จำเป็นในการสร้างแผนภูมิโดนัทใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java กัน แต่ละส่วนจะมุ่งเน้นไปที่ฟีเจอร์เฉพาะ เพื่อให้มีความชัดเจนและตรงประเด็น

### การเริ่มต้นการนำเสนอ
เริ่มต้นด้วยการโหลดหรือสร้างไฟล์ PowerPoint ใหม่ ขั้นตอนนี้จะตั้งค่าสภาพแวดล้อมการนำเสนอของคุณ

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// ตรวจสอบการโหลดสำเร็จโดยการบันทึกการนำเสนอเริ่มต้น
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### เพิ่มแผนภูมิโดนัท
เพิ่มแผนภูมิโดนัทลงในสไลด์ของคุณโดยปรับแต่งขนาดและรูปลักษณ์ของแผนภูมิ

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// กำหนดค่าคุณสมบัติของซีรีส์
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### กำหนดค่าจุดข้อมูลและป้ายกำกับ
ปรับแต่งลักษณะที่ปรากฏของจุดข้อมูลแต่ละจุดและกำหนดค่าฉลากเพื่อให้สามารถอ่านได้ง่ายขึ้น

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // จัดรูปแบบจุดข้อมูล
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // ปรับแต่งคุณสมบัติฉลากสำหรับซีรีย์สุดท้ายในแต่ละหมวดหมู่
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### บันทึกการนำเสนอ
หลังจากกำหนดค่าแผนภูมิของคุณแล้ว ให้บันทึกการนำเสนอเพื่อคงการเปลี่ยนแปลงของคุณไว้

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## การประยุกต์ใช้งานจริง
แผนภูมิโดนัทสามารถใช้ได้ในสถานการณ์ต่างๆ ดังนี้:
- **รายงานทางการเงิน:** แสดงภาพการจัดสรรงบประมาณหรือมาตรวัดทางการเงิน
- **การวิเคราะห์ตลาด:** แสดงการกระจายส่วนแบ่งการตลาดในหมู่คู่แข่ง
- **ผลการสำรวจ:** นำเสนอข้อมูลแบบหมวดหมู่จากการตอบแบบสำรวจอย่างมีประสิทธิผล

การบูรณาการกับระบบอื่นๆ เช่น ฐานข้อมูลและแอปพลิเคชันเว็บ ช่วยให้สร้างแผนภูมิแบบไดนามิกได้ตามข้อมูลเรียลไทม์

## การพิจารณาประสิทธิภาพ
เพื่อประสิทธิภาพที่เหมาะสมที่สุด:
- จัดการการใช้หน่วยความจำโดยการกำจัดทรัพยากรอย่างทันท่วงที
- จำกัดจำนวนแผนภูมิหรือสไลด์หากไม่จำเป็นเพื่อประหยัดพลังงานการประมวลผล
- ใช้โครงสร้างข้อมูลที่มีประสิทธิภาพเพื่อจัดการชุดข้อมูลขนาดใหญ่

การยึดมั่นตามแนวทางปฏิบัติที่ดีที่สุดจะช่วยให้แอปพลิเคชันของคุณทำงานได้อย่างราบรื่น โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับการนำเสนอที่ซับซ้อน

## บทสรุป
การสร้างแผนภูมิโดนัทแบบไดนามิกใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เป็นกระบวนการที่ตรงไปตรงมาเมื่อคุณเข้าใจขั้นตอนสำคัญต่างๆ แล้ว ด้วยคู่มือนี้ คุณจะพร้อมแล้วที่จะปรับปรุงการนำเสนอของคุณโดยการผสานแผนภูมิที่ดึงดูดสายตาซึ่งสามารถสื่อสารข้อมูลเชิงลึกได้อย่างมีประสิทธิภาพ

หากต้องการสำรวจฟังก์ชันการทำงานของ Aspose.Slides เพิ่มเติมและเจาะลึกความสามารถต่างๆ โปรดลองทดลองใช้แผนภูมิประเภทต่างๆ หรือฟีเจอร์ขั้นสูง เช่น แอนิเมชันและการเปลี่ยนผ่าน

## ส่วนคำถามที่พบบ่อย
**ถาม: ฉันสามารถใช้ Aspose.Slides สำหรับ Java ในแอปพลิเคชันเชิงพาณิชย์ได้หรือไม่**
A: ใช่ แต่คุณจะต้องซื้อใบอนุญาต คุณสามารถเริ่มด้วยการทดลองใช้งานฟรีเพื่อประเมินคุณสมบัติของมัน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}