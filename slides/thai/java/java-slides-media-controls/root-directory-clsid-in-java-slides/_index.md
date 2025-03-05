---
title: ไดเรกทอรีราก ClsId ใน Java Slides
linktitle: ไดเรกทอรีราก ClsId ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่า Root Directory ClsId ใน Aspose.Slides สำหรับการนำเสนอ Java ปรับแต่งพฤติกรรมไฮเปอร์ลิงก์ด้วย CLSID
type: docs
weight: 10
url: /th/java/media-controls/root-directory-clsid-in-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการตั้งค่า Root Directory ClsId ใน Aspose.Slides สำหรับ Java

ใน Aspose.Slides สำหรับ Java คุณสามารถตั้งค่า Root Directory ClsId ซึ่งเป็น CLSID (Class Identifier) ที่ใช้เพื่อระบุแอปพลิเคชันที่จะใช้เป็นไดเร็กทอรีรากเมื่อเปิดใช้งานไฮเปอร์ลิงก์ในงานนำเสนอของคุณ ในคู่มือนี้ เราจะอธิบายวิธีดำเนินการทีละขั้นตอนให้คุณทราบ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  เพิ่ม Aspose.Slides สำหรับไลบรารี Java ในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/).
- โปรแกรมแก้ไขโค้ดหรือ Integrated Development Environment (IDE) ที่ตั้งค่าสำหรับการพัฒนา Java

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

ขั้นแรก เรามาสร้างงานนำเสนอใหม่โดยใช้ Aspose.Slides สำหรับ Java ในตัวอย่างนี้ เราจะสร้างงานนำเสนอเปล่า

```java
// ชื่อไฟล์เอาท์พุต
String resultPath = "your_output_path/pres.ppt"; // แทนที่ "your_output_path" ด้วยไดเร็กทอรีเอาต์พุตที่คุณต้องการ
Presentation pres = new Presentation();
```

ในโค้ดด้านบน เรากำหนดเส้นทางสำหรับไฟล์การนำเสนอเอาท์พุตและสร้างไฟล์ใหม่`Presentation` วัตถุ.

## ขั้นตอนที่ 2: ตั้งค่า ClsId ไดเรกทอรีราก

 หากต้องการตั้งค่า Root Directory ClsId คุณต้องสร้างอินสแตนซ์ของ`PptOptions` และตั้งค่า CLSID ที่ต้องการ CLSID แสดงถึงแอปพลิเคชันที่จะใช้เป็นไดเร็กทอรีรากเมื่อเปิดใช้งานไฮเปอร์ลิงก์

```java
PptOptions pptOptions = new PptOptions();
// ตั้งค่า CLSID เป็น 'Microsoft Powerpoint.Show.8'
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

 ในโค้ดข้างต้น เราสร้างไฟล์`PptOptions` object และตั้งค่า CLSID เป็น 'Microsoft Powerpoint.Show.8' คุณสามารถแทนที่ด้วย CLSID ของแอปพลิเคชันที่คุณต้องการใช้เป็นไดเร็กทอรีรากได้

## ขั้นตอนที่ 3: บันทึกการนำเสนอ

ตอนนี้ มาบันทึกงานนำเสนอด้วยชุด Root Directory ClsId กัน

```java
// บันทึกการนำเสนอ
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

 ในขั้นตอนนี้ เราจะบันทึกการนำเสนอตามที่ระบุ`resultPath` กับ`PptOptions` เราสร้างไว้ก่อนหน้านี้

## ขั้นตอนที่ 4: การล้างข้อมูล

 อย่าลืมทิ้งของ`Presentation` คัดค้านการปล่อยทรัพยากรที่ได้รับการจัดสรร

```java
if (pres != null) {
    pres.dispose();
}
```

## กรอกซอร์สโค้ดสำหรับ Root Directory ClsId ใน Java Slides

```java
// ชื่อไฟล์เอาท์พุต
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	//ตั้งค่า CLSID เป็น 'Microsoft Powerpoint.Show.8'
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// บันทึกการนำเสนอ
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## บทสรุป

คุณได้ตั้งค่า Root Directory ClsId ใน Aspose.Slides สำหรับ Java เรียบร้อยแล้ว ซึ่งช่วยให้คุณสามารถระบุแอปพลิเคชันที่จะใช้เป็นไดเร็กทอรีรากเมื่อไฮเปอร์ลิงก์ถูกเปิดใช้งานในงานนำเสนอของคุณ คุณสามารถปรับแต่ง CLSID ได้ตามความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะค้นหา CLSID สำหรับแอปพลิเคชันเฉพาะได้อย่างไร

หากต้องการค้นหา CLSID สำหรับแอปพลิเคชันเฉพาะ คุณสามารถดูเอกสารประกอบหรือแหล่งข้อมูลที่นักพัฒนาแอปพลิเคชันมอบให้ CLSID คือตัวระบุเฉพาะที่กำหนดให้กับออบเจ็กต์ COM และโดยทั่วไปจะระบุเฉพาะสำหรับแต่ละแอปพลิเคชัน

### ฉันสามารถตั้งค่า CLSID แบบกำหนดเองสำหรับไดเร็กทอรีรากได้หรือไม่

 ได้ คุณสามารถตั้งค่า CLSID แบบกำหนดเองสำหรับไดเร็กทอรีรากได้โดยการระบุค่า CLSID ที่ต้องการโดยใช้`setRootDirectoryClsid` วิธีการดังแสดงในตัวอย่างโค้ด ซึ่งจะทำให้คุณสามารถใช้แอปพลิเคชันเฉพาะเป็นไดเร็กทอรีรากได้เมื่อมีการเปิดใช้งานไฮเปอร์ลิงก์ในงานนำเสนอของคุณ

### จะเกิดอะไรขึ้นหากฉันไม่ได้ตั้งค่า Root Directory ClsId

หากคุณไม่ได้ตั้งค่า Root Directory ClsId ลักษณะการทำงานเริ่มต้นจะขึ้นอยู่กับผู้ดูหรือแอปพลิเคชันที่ใช้ในการเปิดงานนำเสนอ อาจใช้แอปพลิเคชันเริ่มต้นของตัวเองเป็นไดเร็กทอรีรากเมื่อเปิดใช้งานไฮเปอร์ลิงก์

### ฉันสามารถเปลี่ยน Root Directory ClsId สำหรับไฮเปอร์ลิงก์แต่ละรายการได้หรือไม่

ไม่ โดยปกติแล้ว Root Directory ClsId จะถูกตั้งค่าไว้ที่ระดับการนำเสนอ และใช้กับไฮเปอร์ลิงก์ทั้งหมดภายในงานนำเสนอ หากคุณต้องการระบุแอปพลิเคชันที่แตกต่างกันสำหรับไฮเปอร์ลิงก์แต่ละรายการ คุณอาจต้องจัดการไฮเปอร์ลิงก์เหล่านั้นแยกกันในโค้ดของคุณ

### มีข้อจำกัดใดๆ เกี่ยวกับ CLSID ที่ฉันสามารถใช้ได้หรือไม่

โดยทั่วไป CLSID ที่คุณสามารถใช้ได้จะถูกกำหนดโดยแอปพลิเคชันที่ติดตั้งบนระบบ คุณควรใช้ CLSID ที่สอดคล้องกับแอปพลิเคชันที่ถูกต้องที่สามารถจัดการไฮเปอร์ลิงก์ได้ โปรดทราบว่าการใช้ CLSID ที่ไม่ถูกต้องอาจส่งผลให้เกิดการทำงานที่ไม่คาดคิด