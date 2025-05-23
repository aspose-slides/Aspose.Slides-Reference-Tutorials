---
"description": "เรียนรู้วิธีการตั้งค่าคุณสมบัติแบบอักษรในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้ประกอบด้วยตัวอย่างโค้ดและคำถามที่พบบ่อย"
"linktitle": "การตั้งค่าคุณสมบัติฟอนต์ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การตั้งค่าคุณสมบัติฟอนต์ใน Java Slides"
"url": "/th/java/customization-and-formatting/setting-font-properties-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าคุณสมบัติฟอนต์ใน Java Slides


## บทนำเกี่ยวกับการตั้งค่าคุณสมบัติฟอนต์ใน Java Slides

ในบทช่วยสอนนี้ เราจะมาดูวิธีการตั้งค่าคุณสมบัติแบบอักษรสำหรับข้อความในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คุณสมบัติแบบอักษร เช่น ตัวหนาและขนาดแบบอักษรสามารถปรับแต่งได้เพื่อปรับปรุงรูปลักษณ์ของสไลด์ของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ

ขั้นแรก คุณต้องเริ่มต้นวัตถุการนำเสนอโดยโหลดไฟล์ PowerPoint ที่มีอยู่ แทนที่ `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

ในตัวอย่างนี้ เราจะใช้แผนภูมิในสไลด์แรก คุณสามารถเปลี่ยนดัชนีสไลด์ได้ตามความต้องการ เราจะเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์และเปิดใช้งานตารางข้อมูล

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.setDataTable(true);
```

## ขั้นตอนที่ 3: ปรับแต่งคุณสมบัติแบบอักษร

ต่อไปเรามาปรับแต่งคุณสมบัติของฟอนต์ในตารางข้อมูลแผนภูมิกัน โดยเราจะตั้งค่าฟอนต์ให้เป็นตัวหนา และปรับความสูงของฟอนต์ (ขนาด)

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
```

- `setFontBold(NullableBool.True)`:บรรทัดนี้จะตั้งค่าแบบอักษรให้เป็นตัวหนา
- `setFontHeight(20)`:บรรทัดนี้กำหนดความสูงของแบบอักษรเป็น 20 จุด คุณสามารถปรับค่านี้ได้ตามต้องการ

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์ใหม่ คุณสามารถระบุรูปแบบผลลัพธ์ได้ ในกรณีนี้ เราจะบันทึกเป็นไฟล์ PPTX

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับการตั้งค่าคุณสมบัติฟอนต์ใน Java Slides

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

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการตั้งค่าคุณสมบัติแบบอักษรสำหรับข้อความในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถใช้เทคนิคเหล่านี้เพื่อปรับปรุงรูปลักษณ์ของข้อความในงานนำเสนอ PowerPoint ของคุณได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีตัวอักษรได้อย่างไร?

หากต้องการเปลี่ยนสีตัวอักษร ให้ใช้ `setFontColor` วิธีการและระบุสีที่ต้องการ เช่น:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontColor(Color.RED);
```

### ฉันสามารถเปลี่ยนแบบอักษรสำหรับข้อความอื่นในสไลด์ได้หรือไม่

ใช่ คุณสามารถเปลี่ยนแบบอักษรสำหรับองค์ประกอบข้อความอื่นๆ ในสไลด์ได้ เช่น ชื่อเรื่องและป้ายกำกับ ใช้วัตถุและวิธีการที่เหมาะสมเพื่อเข้าถึงและปรับแต่งคุณสมบัติแบบอักษรสำหรับองค์ประกอบข้อความเฉพาะ

### ฉันจะตั้งค่าแบบอักษรตัวเอียงได้อย่างไร?

หากต้องการตั้งค่าแบบอักษรเป็นตัวเอียง ให้ใช้ `setFontItalic` วิธี:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontItalic(NullableBool.True);
```

ปรับแต่ง `NullableBool.True` พารามิเตอร์ตามต้องการเพื่อเปิดใช้งานหรือปิดใช้งานรูปแบบตัวเอียง

### ฉันจะเปลี่ยนแบบอักษรสำหรับป้ายข้อมูลในแผนภูมิได้อย่างไร

หากต้องการเปลี่ยนแบบอักษรสำหรับป้ายข้อมูลในแผนภูมิ คุณจำเป็นต้องเข้าถึงรูปแบบข้อความป้ายข้อมูลโดยใช้วิธีการที่เหมาะสม ตัวอย่างเช่น:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0); // เปลี่ยนดัชนีตามต้องการ
series.getLabels().getDefaultDataLabelFormat().getPortionFormat().setFontBold(NullableBool.True);
```

โค้ดนี้จะกำหนดแบบอักษรของป้ายข้อมูลในชุดแรกให้เป็นตัวหนา

### ฉันจะเปลี่ยนแบบอักษรสำหรับข้อความเฉพาะบางส่วนได้อย่างไร

หากคุณต้องการเปลี่ยนแบบอักษรสำหรับส่วนข้อความเฉพาะภายในองค์ประกอบข้อความ คุณสามารถใช้ `PortionFormat` คลาส เข้าถึงส่วนที่คุณต้องการแก้ไขแล้วตั้งค่าคุณสมบัติฟอนต์ที่ต้องการ

```java
IAutoShape textShape = (IAutoShape)slide.getShapes().get_Item(0); // เปลี่ยนดัชนีตามต้องการ
ITextFrame textFrame = textShape.getTextFrame();
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // เปลี่ยนดัชนีตามต้องการ
IPortion portion = paragraph.getPortions().get_Item(0); // เปลี่ยนดัชนีตามต้องการ

portion.getPortionFormat().setFontBold(NullableBool.True);
portion.getPortionFormat().setFontHeight(24);
```

โค้ดนี้จะกำหนดแบบอักษรของส่วนแรกของข้อความภายในรูปร่างให้เป็นตัวหนาและปรับความสูงของแบบอักษร

### ฉันจะนำการเปลี่ยนแปลงแบบอักษรไปใช้กับสไลด์ทั้งหมดในงานนำเสนอได้อย่างไร

หากต้องการใช้การเปลี่ยนแปลงแบบอักษรกับสไลด์ทั้งหมดในงานนำเสนอ คุณสามารถทำซ้ำในสไลด์และปรับคุณสมบัติแบบอักษรตามต้องการ ใช้ลูปเพื่อเข้าถึงสไลด์แต่ละสไลด์และองค์ประกอบข้อความภายในสไลด์ จากนั้นปรับแต่งคุณสมบัติแบบอักษร

```java
for (ISlide slide : pres.getSlides()) {
    // เข้าถึงและปรับแต่งคุณสมบัติแบบอักษรขององค์ประกอบข้อความได้ที่นี่
}
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}