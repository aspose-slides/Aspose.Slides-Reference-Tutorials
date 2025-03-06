---
title: การตั้งค่าคุณสมบัติแบบอักษรใน Java Slides
linktitle: การตั้งค่าคุณสมบัติแบบอักษรใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการตั้งค่าคุณสมบัติแบบอักษรในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้ประกอบด้วยตัวอย่างโค้ดและคำถามที่พบบ่อย
weight: 15
url: /th/java/customization-and-formatting/setting-font-properties-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าคุณสมบัติแบบอักษรใน Java Slides


## รู้เบื้องต้นเกี่ยวกับการตั้งค่าคุณสมบัติแบบอักษรใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีตั้งค่าคุณสมบัติแบบอักษรสำหรับข้อความในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คุณสมบัติแบบอักษร เช่น ตัวหนาและขนาดแบบอักษรสามารถปรับแต่งได้เพื่อปรับปรุงลักษณะที่ปรากฏของสไลด์ของคุณ

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ

 ขั้นแรก คุณต้องเริ่มต้นวัตถุการนำเสนอโดยการโหลดไฟล์ PowerPoint ที่มีอยู่ แทนที่`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

ในตัวอย่างนี้ เราจะทำงานกับแผนภูมิในสไลด์แรก คุณสามารถเปลี่ยนดัชนีสไลด์ได้ตามความต้องการของคุณ เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มและเปิดใช้งานตารางข้อมูล

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.setDataTable(true);
```

## ขั้นตอนที่ 3: ปรับแต่งคุณสมบัติแบบอักษร

ตอนนี้ เรามาปรับแต่งคุณสมบัติแบบอักษรของตารางข้อมูลแผนภูมิกันดีกว่า เราจะตั้งค่าแบบอักษรให้เป็นตัวหนาและปรับความสูงของแบบอักษร (ขนาด)

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
```

- `setFontBold(NullableBool.True)`: บรรทัดนี้กำหนดแบบอักษรให้เป็นตัวหนา
- `setFontHeight(20)`: บรรทัดนี้กำหนดความสูงของแบบอักษรเป็น 20 พอยต์ คุณสามารถปรับค่านี้ได้ตามต้องการ

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วเป็นไฟล์ใหม่ คุณสามารถระบุรูปแบบเอาต์พุต ในกรณีนี้ เรากำลังบันทึกเป็นไฟล์ PPTX

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับการตั้งค่าคุณสมบัติแบบอักษรใน Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.setDataTable(true);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีตั้งค่าคุณสมบัติแบบอักษรสำหรับข้อความในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถใช้เทคนิคเหล่านี้เพื่อปรับปรุงลักษณะที่ปรากฏของข้อความในงานนำเสนอ PowerPoint ของคุณ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีตัวอักษรได้อย่างไร?

 หากต้องการเปลี่ยนสีตัวอักษร ให้ใช้`setFontColor` วิธีการและระบุสีที่ต้องการ ตัวอย่างเช่น:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontColor(Color.RED);
```

### ฉันสามารถเปลี่ยนแบบอักษรสำหรับข้อความอื่นในสไลด์ได้หรือไม่

ได้ คุณสามารถเปลี่ยนแบบอักษรสำหรับองค์ประกอบข้อความอื่นๆ ในสไลด์ เช่น ชื่อเรื่องและป้ายกำกับได้ ใช้วัตถุและวิธีการที่เหมาะสมเพื่อเข้าถึงและปรับแต่งคุณสมบัติแบบอักษรสำหรับองค์ประกอบข้อความเฉพาะ

### ฉันจะตั้งค่ารูปแบบตัวอักษรตัวเอียงได้อย่างไร

 หากต้องการตั้งค่ารูปแบบตัวอักษรให้เป็นตัวเอียง ให้ใช้`setFontItalic` วิธี:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontItalic(NullableBool.True);
```

 ปรับ`NullableBool.True` พารามิเตอร์ตามความจำเป็นเพื่อเปิดหรือปิดใช้รูปแบบตัวเอียง

### ฉันจะเปลี่ยนแบบอักษรสำหรับป้ายชื่อข้อมูลในแผนภูมิได้อย่างไร

หากต้องการเปลี่ยนแบบอักษรสำหรับป้ายข้อมูลในแผนภูมิ คุณต้องเข้าถึงรูปแบบข้อความป้ายข้อมูลโดยใช้วิธีการที่เหมาะสม ตัวอย่างเช่น:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0); // เปลี่ยนดัชนีตามความจำเป็น
series.getLabels().getDefaultDataLabelFormat().getPortionFormat().setFontBold(NullableBool.True);
```

รหัสนี้ตั้งค่าแบบอักษรของป้ายกำกับข้อมูลในชุดแรกให้เป็นตัวหนา

### ฉันจะเปลี่ยนแบบอักษรสำหรับข้อความเฉพาะบางส่วนได้อย่างไร

 หากคุณต้องการเปลี่ยนแบบอักษรสำหรับข้อความบางส่วนภายในองค์ประกอบข้อความ คุณสามารถใช้`PortionFormat` ระดับ. เข้าถึงส่วนที่คุณต้องการแก้ไข จากนั้นตั้งค่าคุณสมบัติแบบอักษรที่ต้องการ

```java
IAutoShape textShape = (IAutoShape)slide.getShapes().get_Item(0); // เปลี่ยนดัชนีตามความจำเป็น
ITextFrame textFrame = textShape.getTextFrame();
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // เปลี่ยนดัชนีตามความจำเป็น
IPortion portion = paragraph.getPortions().get_Item(0); // เปลี่ยนดัชนีตามความจำเป็น

portion.getPortionFormat().setFontBold(NullableBool.True);
portion.getPortionFormat().setFontHeight(24);
```

รหัสนี้จะตั้งค่าแบบอักษรของส่วนแรกของข้อความภายในรูปร่างให้เป็นตัวหนาและปรับความสูงของแบบอักษร

### ฉันจะนำการเปลี่ยนแปลงแบบอักษรไปใช้กับสไลด์ทั้งหมดในงานนำเสนอได้อย่างไร

หากต้องการนำการเปลี่ยนแปลงแบบอักษรไปใช้กับสไลด์ทั้งหมดในงานนำเสนอ คุณสามารถวนซ้ำสไลด์และปรับคุณสมบัติแบบอักษรได้ตามต้องการ ใช้การวนซ้ำเพื่อเข้าถึงแต่ละสไลด์และองค์ประกอบข้อความภายในสไลด์ จากนั้นปรับแต่งคุณสมบัติแบบอักษร

```java
for (ISlide slide : pres.getSlides()) {
    // เข้าถึงและปรับแต่งคุณสมบัติแบบอักษรขององค์ประกอบข้อความได้ที่นี่
}
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
