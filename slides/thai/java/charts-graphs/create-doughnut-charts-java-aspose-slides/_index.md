---
"date": "2025-04-17"
"description": "เรียนรู้วิธีสร้างแผนภูมิโดนัทที่สวยงามใน Java ด้วย Aspose.Slides คู่มือที่ครอบคลุมนี้ครอบคลุมถึงการเริ่มต้น การกำหนดค่าข้อมูล และการบันทึกการนำเสนอ"
"title": "สร้างแผนภูมิโดนัทใน Java โดยใช้ Aspose.Slides คู่มือฉบับสมบูรณ์"
"url": "/th/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิโดนัทใน Java โดยใช้ Aspose.Slides: คำแนะนำทีละขั้นตอน

## การแนะนำ

ในสภาพแวดล้อมที่ขับเคลื่อนด้วยข้อมูลในปัจจุบัน การสร้างภาพข้อมูลอย่างมีประสิทธิผลถือเป็นกุญแจสำคัญในการเสริมสร้างความเข้าใจและการมีส่วนร่วม แม้ว่าการสร้างแผนภูมิแบบมืออาชีพด้วยโปรแกรมอาจดูท้าทาย โดยเฉพาะกับ Java แต่คู่มือนี้จะแนะนำคุณเกี่ยวกับการใช้ Aspose.Slides สำหรับ Java เพื่อสร้างแผนภูมิโดนัทได้อย่างง่ายดาย

โดยทำตามขั้นตอนเหล่านี้ นักพัฒนาจะได้รับประสบการณ์ปฏิบัติจริงในการจัดการสไลด์การนำเสนอและบูรณาการการแสดงภาพข้อมูลได้อย่างราบรื่น

**ประเด็นสำคัญ:**
- เริ่มต้นวัตถุการนำเสนอโดยใช้ Aspose.Slides Java
- กำหนดค่าข้อมูลแผนภูมิและจัดการชุดข้อมูลหรือหมวดหมู่ที่มีอยู่
- เพิ่มและปรับแต่งชุดและหมวดหมู่สำหรับแผนภูมิของคุณ
- จัดรูปแบบและแสดงจุดข้อมูลอย่างมีประสิทธิภาพ
- บันทึกการนำเสนอของคุณในรูปแบบต่างๆ ได้อย่างง่ายดาย

ก่อนจะเริ่มใช้งาน ให้แน่ใจว่าคุณมีทุกสิ่งที่จำเป็นในการเริ่มต้น

## ข้อกำหนดเบื้องต้น

หากต้องการทำตามบทช่วยสอนนี้ โปรดแน่ใจว่าคุณมี:

- **ห้องสมุดที่จำเป็น:**
  - Aspose.Slides สำหรับ Java เวอร์ชัน 25.4 ขึ้นไป
  
- **การตั้งค่าสภาพแวดล้อม:**
  - ติดตั้ง JDK 16 หรือสูงกว่าบนระบบของคุณ
  - IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans

- **ข้อกำหนดความรู้เบื้องต้น:**
  - ความเข้าใจพื้นฐานเกี่ยวกับแนวคิดการเขียนโปรแกรมภาษา Java
  - ความคุ้นเคยกับการจัดการการอ้างอิงในโครงการ Maven หรือ Gradle

## การตั้งค่า Aspose.Slides สำหรับ Java

หากต้องการรวม Aspose.Slides เข้ากับโปรเจ็กต์ของคุณ ให้ทำตามขั้นตอนเหล่านี้ตามเครื่องมือสร้างของคุณ:

**การตั้งค่า Maven:**
เพิ่มการอ้างอิงต่อไปนี้ให้กับของคุณ `pom.xml` ไฟล์:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**การตั้งค่า Gradle:**
รวมสิ่งต่อไปนี้ไว้ในของคุณ `build.gradle` ไฟล์:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**ดาวน์โหลดโดยตรง:**
หรือดาวน์โหลดเวอร์ชันล่าสุดโดยตรงจาก [Aspose.Slides สำหรับการเปิดตัว Java](https://releases-aspose.com/slides/java/).

### การขอใบอนุญาต

การใช้ Aspose.Slides โดยไม่มีข้อจำกัดในการประเมิน:
- **ทดลองใช้งานฟรี:** เริ่มต้นด้วยใบอนุญาตชั่วคราวเพื่อสำรวจคุณสมบัติทั้งหมด
- **ใบอนุญาตชั่วคราว:** รับหนึ่งผ่านทาง [เว็บไซต์อาโพส](https://purchase-aspose.com/temporary-license/).
- **ซื้อ:** ควรพิจารณาซื้อเพื่อใช้งานอย่างต่อเนื่อง

ใช้ใบอนุญาตของคุณในแอปพลิเคชัน Java โดยใช้:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## คู่มือการใช้งาน

### การเริ่มต้นการนำเสนอและแผนภูมิ

#### ภาพรวม
เริ่มต้นด้วยการสร้างวัตถุการนำเสนอและเพิ่มแผนภูมิโดนัทลงในสไลด์แรก

**ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ**
โหลดไฟล์ PPTX ที่มีอยู่หรือสร้างไฟล์ใหม่:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**ขั้นตอนที่ 2: เพิ่มแผนภูมิโดนัท**
สร้างแผนภูมิบนสไลด์แรกตามพิกัดที่ระบุ:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### การกำหนดค่าสมุดงานข้อมูลแผนภูมิและการล้างชุดข้อมูล/หมวดหมู่ที่มีอยู่

#### ภาพรวม
กำหนดค่าสมุดงานข้อมูลแผนภูมิและลบชุดข้อมูลหรือหมวดหมู่ที่มีอยู่ก่อนหน้านี้

**ขั้นตอนที่ 1: เข้าถึงสมุดงานข้อมูลแผนภูมิ**
ดึงข้อมูลสมุดงานที่เชื่อมโยงกับแผนภูมิของคุณ:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**ขั้นตอนที่ 2: ล้างซีรีย์และหมวดหมู่ที่มีอยู่**
ตรวจสอบให้แน่ใจว่าไม่มีจุดข้อมูลที่เหลืออยู่:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### การเพิ่มซีรีส์ลงในแผนภูมิ

#### ภาพรวม
เติมแผนภูมิของคุณด้วยชุดข้อมูลต่างๆ มากมาย โดยแต่ละรายการมีการปรับแต่งตามลักษณะที่ปรากฏและพฤติกรรม

**ขั้นตอนที่ 1: เพิ่มซีรีส์แบบวนซ้ำ**
วนซ้ำผ่านดัชนีเพื่อเพิ่มซีรีส์:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // ปรับแต่งซีรีย์
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### การเพิ่มหมวดหมู่และจุดข้อมูลลงในแผนภูมิ

#### ภาพรวม
กำหนดค่าหมวดหมู่และเพิ่มจุดข้อมูลที่มีการจัดรูปแบบเฉพาะสำหรับป้ายกำกับ

**ขั้นตอนที่ 1: เพิ่มหมวดหมู่**
วนซ้ำดัชนีสำหรับแต่ละหมวดหมู่:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**ขั้นตอนที่ 2: เพิ่มจุดข้อมูลให้กับแต่ละชุด**
ทำซ้ำผ่านแต่ละชุดสำหรับหมวดหมู่ปัจจุบัน:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // การตั้งค่ารูปแบบจุดข้อมูล
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // การจัดรูปแบบฉลากสำหรับซีรีย์สุดท้าย
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // ปรับแต่งตัวเลือกการแสดงผล
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // ปรับตำแหน่งฉลาก
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### การบันทึกการนำเสนอ

#### ภาพรวม
เมื่อคุณกำหนดค่าแผนภูมิของคุณแล้ว ให้บันทึกการนำเสนอไปยังไดเร็กทอรีที่ระบุ

**ขั้นตอนที่ 1: บันทึกการนำเสนอ**
ใช้ `save` วิธีการเขียนการเปลี่ยนแปลง:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## บทสรุป

ตอนนี้คุณได้เรียนรู้วิธีการสร้างและปรับแต่งแผนภูมิโดนัทใน Java โดยใช้ Aspose.Slides แล้ว ขั้นตอนเหล่านี้จะเป็นพื้นฐานสำหรับการผสานการแสดงภาพข้อมูลที่ซับซ้อนเข้ากับการนำเสนอของคุณ

**ขั้นตอนต่อไป:**
- ทดลองใช้ประเภทแผนภูมิต่างๆ ที่มีอยู่ใน Aspose.Slides
- สำรวจตัวเลือกการปรับแต่งเพิ่มเติม เช่น สี แบบอักษร และสไตล์ เพื่อให้ตรงกับความต้องการด้านแบรนด์ของคุณ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}