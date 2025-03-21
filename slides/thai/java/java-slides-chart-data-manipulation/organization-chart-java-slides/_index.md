---
title: แผนผังองค์กรใน Java Slides
linktitle: แผนผังองค์กรใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างแผนภูมิองค์กรที่น่าทึ่งใน Java Slides ด้วยบทช่วยสอน Aspose.Slides ทีละขั้นตอน ปรับแต่งและแสดงภาพโครงสร้างองค์กรของคุณได้อย่างง่ายดาย
weight: 22
url: /th/java/chart-data-manipulation/organization-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แผนผังองค์กรใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการสร้างแผนผังองค์กรใน Java Slides โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีสร้างแผนผังองค์กรใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API แผนผังองค์กรคือการแสดงภาพโครงสร้างลำดับชั้นขององค์กร โดยทั่วไปจะใช้เพื่อแสดงความสัมพันธ์และลำดับชั้นระหว่างพนักงานหรือแผนกต่างๆ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- [Aspose.Slides สำหรับ Java](https://products.aspose.com/slides/java) ไลบรารี่ที่ติดตั้งในโปรเจ็กต์ Java ของคุณ
- Java Integrated Development Environment (IDE) เช่น IntelliJ IDEA หรือ Eclipse

## ขั้นตอนที่ 1: ตั้งค่าโครงการ Java ของคุณ

1. สร้างโปรเจ็กต์ Java ใหม่ใน IDE ที่คุณต้องการ
2.  เพิ่มไลบรารี Aspose.Slides สำหรับ Java ให้กับโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดห้องสมุดได้จาก[เว็บไซต์กำหนด](https://products.aspose.com/slides/java) และรวมไว้เป็นที่พึ่งด้วย

## ขั้นตอนที่ 2: นำเข้าไลบรารีที่จำเป็น
ในคลาส Java ของคุณ ให้นำเข้าไลบรารีที่จำเป็นเพื่อทำงานกับ Aspose.Slides:

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 3: สร้างแผนผังองค์กร

ตอนนี้ เรามาสร้างแผนผังองค์กรโดยใช้ Aspose.Slides กันดีกว่า เราจะทำตามขั้นตอนเหล่านี้:

1. ระบุเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
2. โหลดงานนำเสนอ PowerPoint ที่มีอยู่หรือสร้างงานนำเสนอใหม่
3. เพิ่มรูปร่างแผนผังองค์กรลงในสไลด์
4. บันทึกงานนำเสนอด้วยแผนผังองค์กร

นี่คือรหัสเพื่อทำสิ่งนี้ให้สำเร็จ:

```java
// ระบุเส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// โหลดงานนำเสนอที่มีอยู่หรือสร้างงานนำเสนอใหม่
Presentation pres = new Presentation(dataDir + "test.pptx");
try {
    // เพิ่มรูปร่างแผนผังองค์กรลงในสไลด์แรก
    ISmartArt smartArt = pres.getSlides().get_Item(0).getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.PictureOrganizationChart);

    // บันทึกงานนำเสนอด้วยแผนผังองค์กร
    pres.save(dataDir + "OrganizationChart.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 แทนที่`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณและ`"test.pptx"` ด้วยชื่อของงานนำเสนอ PowerPoint ที่คุณป้อนข้อมูล

## ขั้นตอนที่ 4: เรียกใช้โค้ด

ตอนนี้คุณได้เพิ่มโค้ดเพื่อสร้างแผนผังองค์กรแล้ว ให้รันแอปพลิเคชัน Java ของคุณ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Slides ได้รับการเพิ่มลงในโปรเจ็กต์ของคุณอย่างถูกต้อง และการอ้างอิงที่จำเป็นได้รับการแก้ไขแล้ว

## กรอกซอร์สโค้ดสำหรับแผนผังองค์กรใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	ISmartArt smartArt = pres.getSlides().get_Item(0).getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.PictureOrganizationChart);
	pres.save(dataDir + "OrganizationChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีสร้างแผนผังองค์กรใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API คุณสามารถปรับแต่งลักษณะที่ปรากฏและเนื้อหาของแผนผังองค์กรได้ตามความต้องการเฉพาะของคุณ Aspose.Slides มีคุณสมบัติที่หลากหลายสำหรับการทำงานกับงานนำเสนอ PowerPoint ทำให้เป็นเครื่องมือที่ทรงพลังสำหรับการจัดการและสร้างเนื้อหาภาพ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏของแผนผังองค์กรได้อย่างไร

คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนผังองค์กรได้โดยการปรับเปลี่ยนคุณสมบัติ เช่น สี สไตล์ และแบบอักษร โปรดดูเอกสารประกอบของ Aspose.Slides สำหรับรายละเอียดเกี่ยวกับวิธีปรับแต่งรูปร่าง SmartArt

### ฉันสามารถเพิ่มรูปร่างหรือข้อความเพิ่มเติมลงในแผนผังองค์กรได้หรือไม่

ได้ คุณสามารถเพิ่มรูปร่าง ข้อความ และตัวเชื่อมต่อเพิ่มเติมลงในแผนผังองค์กรเพื่อแสดงโครงสร้างองค์กรของคุณได้อย่างถูกต้อง ใช้ Aspose.Slides API เพื่อเพิ่มและจัดรูปแบบรูปร่างภายในไดอะแกรม SmartArt

### ฉันจะส่งออกแผนผังองค์กรเป็นรูปแบบอื่น เช่น PDF หรือรูปภาพได้อย่างไร

 คุณสามารถส่งออกงานนำเสนอที่มีแผนผังองค์กรเป็นรูปแบบต่างๆ ได้โดยใช้ Aspose.Slides ตัวอย่างเช่น หากต้องการส่งออกเป็น PDF ให้ใช้ไฟล์`SaveFormat.Pdf` ตัวเลือกเมื่อบันทึกการนำเสนอ ในทำนองเดียวกัน คุณสามารถส่งออกเป็นรูปแบบภาพ เช่น PNG หรือ JPEG ได้

### เป็นไปได้ไหมที่จะสร้างโครงสร้างองค์กรที่ซับซ้อนที่มีหลายระดับ?

ใช่ Aspose.Slides ช่วยให้คุณสร้างโครงสร้างองค์กรที่ซับซ้อนได้หลายระดับโดยการเพิ่มและจัดเรียงรูปร่างภายในแผนผังองค์กร คุณสามารถกำหนดความสัมพันธ์แบบลำดับชั้นระหว่างรูปร่างเพื่อแสดงโครงสร้างที่ต้องการได้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
