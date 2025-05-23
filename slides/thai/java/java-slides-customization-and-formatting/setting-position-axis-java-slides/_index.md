---
"description": "ปรับปรุงแผนภูมิของคุณด้วย Aspose.Slides สำหรับ Java เรียนรู้วิธีการตั้งค่าแกนตำแหน่งในสไลด์ Java สร้างการนำเสนอที่สวยงาม และปรับแต่งเค้าโครงแผนภูมิได้อย่างง่ายดาย"
"linktitle": "การตั้งค่าตำแหน่งแกนใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การตั้งค่าตำแหน่งแกนใน Java Slides"
"url": "/th/java/customization-and-formatting/setting-position-axis-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าตำแหน่งแกนใน Java Slides


## บทนำเกี่ยวกับการตั้งค่าตำแหน่งแกนใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีกำหนดตำแหน่งแกนในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java การกำหนดตำแหน่งแกนอาจมีประโยชน์เมื่อคุณต้องการปรับแต่งลักษณะและเค้าโครงของแผนภูมิ เราจะสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์และปรับตำแหน่งของแกนแนวนอนระหว่างหมวดหมู่

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: การสร้างงานนำเสนอ

ก่อนอื่นให้สร้างการนำเสนอใหม่เพื่อใช้งาน:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

อย่าลืมเปลี่ยน `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: การเพิ่มแผนภูมิ

ต่อไปเราจะเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ลงในสไลด์ โดยระบุประเภทแผนภูมิ ตำแหน่ง (พิกัด x, y) และขนาด (ความกว้างและความสูง) ของแผนภูมิ:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

ที่นี่ เราได้เพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ที่ตำแหน่ง (50, 50) โดยมีความกว้าง 450 และความสูง 300 คุณสามารถปรับค่าเหล่านี้ได้ตามต้องการ

## ขั้นตอนที่ 3: ตั้งค่าตำแหน่งแกน

ในการกำหนดตำแหน่งแกนระหว่างหมวดหมู่ คุณสามารถใช้โค้ดดังต่อไปนี้:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

โค้ดนี้จะกำหนดแกนแนวนอนที่จะแสดงระหว่างหมวดหมู่ ซึ่งอาจเป็นประโยชน์สำหรับเค้าโครงแผนภูมิบางประเภท

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้ายเรามาบันทึกการนำเสนอด้วยแผนภูมิกัน:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

แทนที่ `"AsposeClusteredColumnChart.pptx"` ด้วยชื่อไฟล์ที่คุณต้องการ

เสร็จเรียบร้อย! คุณได้สร้างแผนภูมิคอลัมน์แบบคลัสเตอร์และกำหนดตำแหน่งแกนระหว่างหมวดหมู่โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว

## ซอร์สโค้ดที่สมบูรณ์
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้ศึกษาวิธีการตั้งค่าแกนตำแหน่งในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณจะเรียนรู้วิธีสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์และปรับแต่งลักษณะที่ปรากฏโดยการวางตำแหน่งแกนแนวนอนระหว่างหมวดหมู่ Aspose.Slides สำหรับ Java มีคุณสมบัติอันทรงพลังสำหรับการทำงานกับแผนภูมิและการนำเสนอ ทำให้เป็นเครื่องมือที่มีประโยชน์สำหรับนักพัฒนา Java

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งแผนภูมิเพิ่มเติมได้อย่างไร?

คุณสามารถปรับแต่งลักษณะต่างๆ ของแผนภูมิได้ เช่น ชุดข้อมูล ชื่อแผนภูมิ คำอธิบายแผนภูมิ และอื่นๆ โปรดดูที่ [เอกสาร Aspose.Slides สำหรับ Java](https://reference.aspose.com/slides/java/) สำหรับคำแนะนำและตัวอย่างโดยละเอียด

### ฉันสามารถเปลี่ยนประเภทแผนภูมิได้หรือไม่

ใช่ คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการแก้ไข `ChartType` พารามิเตอร์เมื่อเพิ่มแผนภูมิ Aspose.Slides สำหรับ Java รองรับแผนภูมิประเภทต่างๆ เช่น แผนภูมิแท่ง แผนภูมิเส้น และอื่นๆ

### ฉันสามารถหาตัวอย่างและเอกสารเพิ่มเติมได้ที่ไหน

คุณสามารถค้นหาเอกสารประกอบที่ครอบคลุมและตัวอย่างเพิ่มเติมได้ที่ [เอกสาร Aspose.Slides สำหรับ Java](https://reference.aspose.com/slides/java/) หน้าหนังสือ.

อย่าลืมกำจัดวัตถุการนำเสนอเมื่อคุณใช้งานเสร็จเพื่อปลดปล่อยทรัพยากรระบบ:

```java
if (pres != null) pres.dispose();
```

เท่านี้ก็เสร็จสิ้นสำหรับบทช่วยสอนนี้ คุณได้เรียนรู้วิธีกำหนดตำแหน่งแกนในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java แล้ว

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}