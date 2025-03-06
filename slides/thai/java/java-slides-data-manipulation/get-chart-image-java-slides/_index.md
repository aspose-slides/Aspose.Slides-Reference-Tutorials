---
title: รับภาพแผนภูมิใน Java Slides
linktitle: รับภาพแผนภูมิใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีรับภาพแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้ให้ซอร์สโค้ดและเคล็ดลับสำหรับการผสานรวมที่ราบรื่น
weight: 19
url: /th/java/data-manipulation/get-chart-image-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับภาพแผนภูมิใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการรับภาพแผนภูมิใน Java Slides

Aspose.Slides for Java เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม ด้วยไลบรารีนี้ คุณสามารถสร้าง จัดการ และแยกองค์ประกอบต่างๆ จากการนำเสนอ รวมถึงแผนภูมิด้วย ข้อกำหนดทั่วไปประการหนึ่งคือการได้รับภาพแผนภูมิจากสไลด์ และเราจะสาธิตวิธีการดังกล่าวในคู่มือนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและกำหนดค่าในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

เริ่มต้นด้วยการสร้างโปรเจ็กต์ Java ใน Integrated Development Environment (IDE) ที่คุณต้องการ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในการขึ้นต่อกันของโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ

ในการเริ่มต้น คุณจะต้องเริ่มต้นงานนำเสนอ PowerPoint ในตัวอย่างนี้ เราถือว่าคุณมีไฟล์ PowerPoint ชื่อ "test.pptx" ในไดเรกทอรีเอกสารของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ขั้นตอนที่ 3: เพิ่มแผนภูมิและรับรูปภาพ

จากนั้น คุณสามารถเพิ่มแผนภูมิลงในสไลด์และรับรูปภาพได้ ในตัวอย่างนี้ เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่ม

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

ในข้อมูลโค้ดนี้ เราสร้างแผนภูมิคอลัมน์แบบกลุ่มบนสไลด์แรกของงานนำเสนอ จากนั้นจึงได้ภาพขนาดย่อ รูปภาพจะถูกบันทึกเป็น "image.png" ในไดเร็กทอรีที่ระบุ

## กรอกซอร์สโค้ดเพื่อรับภาพแผนภูมิใน Java Slides

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

การได้รับภาพแผนภูมิจาก Java Slides โดยใช้ Aspose.Slides สำหรับ Java นั้นเป็นกระบวนการที่ไม่ซับซ้อน ด้วยโค้ดที่ให้มา คุณสามารถรวมฟังก์ชันนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างง่ายดาย ช่วยให้คุณสามารถทำงานกับงานนำเสนอ PowerPoint ได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร

 การติดตั้ง Aspose.Slides สำหรับ Java นั้นง่ายดาย คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบ

### ฉันสามารถปรับแต่งแผนภูมิก่อนรับรูปภาพได้หรือไม่

ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏ ข้อมูล และคุณสมบัติอื่นๆ ของแผนภูมิได้ก่อนที่จะได้รับรูปภาพ Aspose.Slides สำหรับ Java มีตัวเลือกมากมายสำหรับการปรับแต่งแผนภูมิ

### Aspose.Slides สำหรับ Java มีคุณสมบัติอื่นใดอีกบ้าง

Aspose.Slides for Java นำเสนอฟีเจอร์ที่หลากหลายสำหรับการทำงานกับงานนำเสนอ PowerPoint รวมถึงการสร้างสไลด์ การจัดการข้อความ การแก้ไขรูปร่าง และอื่นๆ อีกมากมาย คุณสามารถสำรวจเอกสารประกอบเพื่อดูข้อมูลโดยละเอียด

### Aspose.Slides สำหรับ Java เหมาะสำหรับใช้ในเชิงพาณิชย์หรือไม่

ใช่ Aspose.Slides สำหรับ Java สามารถใช้เพื่อวัตถุประสงค์ทางการค้าได้ มีตัวเลือกการออกใบอนุญาตที่เหมาะกับทั้งนักพัฒนารายบุคคลและองค์กร

### ฉันสามารถบันทึกรูปภาพแผนภูมิในรูปแบบอื่นได้หรือไม่

 แน่นอน! คุณสามารถบันทึกภาพแผนภูมิในรูปแบบต่างๆ เช่น JPEG หรือ GIF โดยระบุนามสกุลไฟล์ที่เหมาะสมในรูปแบบ`ImageIO.write` วิธี.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
