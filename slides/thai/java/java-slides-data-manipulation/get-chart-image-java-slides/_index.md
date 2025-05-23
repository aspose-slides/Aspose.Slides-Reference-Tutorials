---
"description": "เรียนรู้วิธีการรับภาพแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้ประกอบด้วยโค้ดต้นฉบับและเคล็ดลับสำหรับการผสานรวมที่ราบรื่น"
"linktitle": "รับภาพแผนภูมิใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "รับภาพแผนภูมิใน Java Slides"
"url": "/th/java/data-manipulation/get-chart-image-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# รับภาพแผนภูมิใน Java Slides


## การแนะนำการรับภาพแผนภูมิใน Java Slides

Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณทำงานกับการนำเสนอ PowerPoint ได้ด้วยโปรแกรม ด้วยไลบรารีนี้ คุณสามารถสร้าง จัดการ และแยกองค์ประกอบต่างๆ จากการนำเสนอ รวมถึงแผนภูมิ ข้อกำหนดทั่วไปอย่างหนึ่งคือการรับภาพแผนภูมิจากสไลด์ และเราจะสาธิตวิธีการดำเนินการดังกล่าวในคู่มือนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกโค้ด โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- ดาวน์โหลดและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

เริ่มต้นด้วยการสร้างโปรเจ็กต์ Java ใน Integrated Development Environment (IDE) ที่คุณต้องการ ตรวจสอบว่าคุณได้เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในส่วนที่ต้องมีของโปรเจ็กต์แล้ว

## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ

ในการเริ่มต้น คุณต้องเริ่มต้นการนำเสนอ PowerPoint ในตัวอย่างนี้ เราจะถือว่าคุณมีไฟล์ PowerPoint ชื่อ "test.pptx" ในไดเร็กทอรีเอกสารของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ขั้นตอนที่ 3: เพิ่มแผนภูมิและรับภาพ

จากนั้นคุณสามารถเพิ่มแผนภูมิลงในสไลด์และรับรูปภาพได้ ในตัวอย่างนี้ เราจะเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

ในโค้ดสั้นๆ นี้ เราสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์บนสไลด์แรกของการนำเสนอ จากนั้นจึงรับรูปภาพขนาดย่อของแผนภูมินั้น รูปภาพจะถูกบันทึกเป็น "image.png" ในไดเร็กทอรีที่ระบุ

## โค้ดต้นฉบับที่สมบูรณ์สำหรับรับภาพแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

การรับภาพแผนภูมิจาก Java Slides โดยใช้ Aspose.Slides สำหรับ Java เป็นกระบวนการที่ตรงไปตรงมา ด้วยโค้ดที่ให้มา คุณสามารถผสานฟังก์ชันนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างง่ายดาย ช่วยให้คุณทำงานกับการนำเสนอ PowerPoint ได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร?

การติดตั้ง Aspose.Slides สำหรับ Java นั้นง่ายมาก คุณสามารถดาวน์โหลดไลบรารีได้จาก [ที่นี่](https://releases.aspose.com/slides/java/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ระบุไว้ในเอกสาร

### ฉันสามารถปรับแต่งแผนภูมิได้ก่อนที่จะได้รับรูปภาพหรือไม่?

ใช่ คุณสามารถปรับแต่งรูปลักษณ์ ข้อมูล และคุณสมบัติอื่นๆ ของแผนภูมิได้ก่อนที่จะได้รับรูปภาพ Aspose.Slides สำหรับ Java มีตัวเลือกมากมายสำหรับการปรับแต่งแผนภูมิ

### Aspose.Slides สำหรับ Java มีฟีเจอร์อื่นๆ อะไรอีกบ้าง?

Aspose.Slides สำหรับ Java นำเสนอฟีเจอร์มากมายสำหรับการทำงานกับการนำเสนอ PowerPoint รวมถึงการสร้างสไลด์ การจัดการข้อความ การแก้ไขรูปร่าง และอื่นๆ อีกมากมาย คุณสามารถศึกษาข้อมูลโดยละเอียดได้จากเอกสารประกอบ

### Aspose.Slides สำหรับ Java เหมาะกับการใช้งานในเชิงพาณิชย์หรือไม่

ใช่ Aspose.Slides สำหรับ Java สามารถใช้เพื่อวัตถุประสงค์เชิงพาณิชย์ได้ โดยมีตัวเลือกการออกใบอนุญาตที่เหมาะสำหรับทั้งนักพัฒนารายบุคคลและองค์กร

### ฉันสามารถบันทึกภาพแผนภูมิในรูปแบบอื่นได้หรือไม่

แน่นอน! คุณสามารถบันทึกภาพแผนภูมิในรูปแบบต่างๆ เช่น JPEG หรือ GIF โดยระบุนามสกุลไฟล์ที่เหมาะสมใน `ImageIO.write` วิธี.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}