---
"description": "ปรับปรุงคุณสมบัติฟอนต์ของแผนภูมิในสไลด์ Java ด้วย Aspose.Slides สำหรับ Java ปรับแต่งขนาด สไตล์ และสีของฟอนต์เพื่อการนำเสนอที่มีประสิทธิภาพ"
"linktitle": "คุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "คุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides"
"url": "/th/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# คุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides


## บทนำเกี่ยวกับคุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides

คู่มือนี้จะแนะนำคุณเกี่ยวกับการตั้งค่าคุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides คุณสามารถปรับแต่งขนาดแบบอักษรและรูปลักษณ์ของข้อความในแผนภูมิเพื่อเพิ่มความสวยงามให้กับงานนำเสนอของคุณได้

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดแน่ใจว่าคุณได้รวม Aspose.Slides สำหรับ Java API ไว้ในโปรเจ็กต์ของคุณแล้ว หากคุณยังไม่ได้ทำ คุณสามารถดาวน์โหลดได้จาก [เอกสาร Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรก ให้สร้างงานนำเสนอใหม่โดยใช้โค้ดต่อไปนี้:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

ตอนนี้ มาเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในการนำเสนอของคุณกัน:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

ที่นี่ เรากำลังเพิ่มแผนภูมิคอลัมน์แบบกลุ่มในสไลด์แรกที่พิกัด (100, 100) โดยมีความกว้าง 500 หน่วยและความสูง 400 หน่วย

## ขั้นตอนที่ 3: ปรับแต่งคุณสมบัติแบบอักษร

ต่อไปเราจะปรับแต่งคุณสมบัติของแบบอักษรของแผนภูมิ ในตัวอย่างนี้ เราจะกำหนดขนาดแบบอักษรเป็น 20 สำหรับข้อความในแผนภูมิทั้งหมด:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

โค้ดนี้จะกำหนดขนาดตัวอักษรเป็น 20 พอยต์สำหรับข้อความทั้งหมดภายในแผนภูมิ

## ขั้นตอนที่ 4: แสดงป้ายข้อมูล

คุณยังสามารถแสดงป้ายข้อมูลบนแผนภูมิได้โดยใช้โค้ดต่อไปนี้:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

บรรทัดโค้ดนี้จะเปิดใช้งานป้ายข้อมูลสำหรับชุดข้อมูลแรกในแผนภูมิ โดยแสดงค่าในคอลัมน์แผนภูมิ

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกการนำเสนอด้วยคุณสมบัติแบบอักษรแผนภูมิที่คุณกำหนดเอง:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

โค้ดนี้จะบันทึกการนำเสนอไปยังไดเร็กทอรีที่ระบุโดยมีชื่อไฟล์ว่า "FontPropertiesForChart.pptx"

## โค้ดต้นฉบับที่สมบูรณ์สำหรับคุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีปรับแต่งคุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถใช้เทคนิคเหล่านี้เพื่อปรับปรุงรูปลักษณ์ของแผนภูมิและการนำเสนอของคุณ สำรวจตัวเลือกเพิ่มเติมใน [เอกสาร Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีตัวอักษรได้อย่างไร?

หากต้องการเปลี่ยนสีแบบอักษรสำหรับข้อความแผนภูมิ ให้ใช้ `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, แทนที่ `Color.RED` ด้วยสีที่ต้องการ

### ฉันสามารถเปลี่ยนรูปแบบอักษร (ตัวหนา ตัวเอียง ฯลฯ) ได้หรือไม่?

ใช่ คุณสามารถเปลี่ยนรูปแบบอักษรได้ ใช้ `chart.getTextFormat().getPortionFormat().setFontBold(true);` เพื่อทำให้แบบอักษรเป็นตัวหนา ในทำนองเดียวกัน คุณสามารถใช้ `setFontItalic(true)` การทำให้เป็นตัวเอียง

### ฉันจะกำหนดคุณสมบัติแบบอักษรสำหรับองค์ประกอบแผนภูมิเฉพาะได้อย่างไร

หากต้องการกำหนดคุณสมบัติฟอนต์ให้กับองค์ประกอบแผนภูมิเฉพาะ เช่น ป้ายแกนหรือข้อความคำอธิบาย คุณสามารถเข้าถึงองค์ประกอบเหล่านั้นและตั้งค่าคุณสมบัติฟอนต์ได้โดยใช้วิธีการที่คล้ายกันดังที่แสดงด้านบน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}