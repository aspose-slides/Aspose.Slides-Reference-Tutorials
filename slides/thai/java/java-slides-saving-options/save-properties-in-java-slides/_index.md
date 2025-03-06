---
title: บันทึกคุณสมบัติใน Java Slides
linktitle: บันทึกคุณสมบัติใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เพิ่มประสิทธิภาพการนำเสนอ PowerPoint ของคุณด้วย Aspose.Slides สำหรับ Java เรียนรู้การตั้งค่าคุณสมบัติ ปิดใช้งานการเข้ารหัส เพิ่มการป้องกันด้วยรหัสผ่าน และบันทึกได้อย่างง่ายดาย
weight: 12
url: /th/java/saving-options/save-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการบันทึกคุณสมบัติใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการบันทึกคุณสมบัติในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณจะได้เรียนรู้วิธีตั้งค่าคุณสมบัติเอกสาร ปิดใช้งานการเข้ารหัสสำหรับคุณสมบัติเอกสาร ตั้งรหัสผ่านเพื่อป้องกันงานนำเสนอของคุณ และบันทึกลงในไฟล์ เราจะให้คำแนะนำทีละขั้นตอนและตัวอย่างซอร์สโค้ดแก่คุณ

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จากเว็บไซต์ Aspose[ที่นี่](https://downloads.aspose.com/slides/java).

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ในการเริ่มต้น ให้นำเข้าคลาสและไลบรารีที่จำเป็น:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ขั้นตอนที่ 2: สร้างวัตถุการนำเสนอ

สร้างอินสแตนซ์วัตถุการนำเสนอเพื่อแสดงงานนำเสนอ PowerPoint ของคุณ คุณสามารถสร้างงานนำเสนอใหม่หรือโหลดงานนำเสนอที่มีอยู่ได้ ในตัวอย่างนี้ เราจะสร้างงานนำเสนอใหม่

```java
// เส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกงานนำเสนอ
String dataDir = "Your Document Directory";

// สร้างอินสแตนซ์วัตถุการนำเสนอ
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติเอกสาร

คุณสามารถตั้งค่าคุณสมบัติเอกสารต่างๆ เช่น ชื่อเรื่อง ผู้แต่ง คำสำคัญ และอื่นๆ ที่นี่ เราจะตั้งค่าคุณสมบัติทั่วไปบางประการ:

```java
// ตั้งชื่อหัวข้อการนำเสนอ
presentation.getDocumentProperties().setTitle("My Presentation");

//กำหนดผู้เขียนการนำเสนอ
presentation.getDocumentProperties().setAuthor("John Doe");

// กำหนดคำสำคัญสำหรับการนำเสนอ
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

## ขั้นตอนที่ 4: ปิดใช้งานการเข้ารหัสสำหรับคุณสมบัติเอกสาร

ตามค่าเริ่มต้น Aspose.Slides จะเข้ารหัสคุณสมบัติของเอกสาร หากคุณต้องการปิดใช้งานการเข้ารหัสสำหรับคุณสมบัติของเอกสาร ให้ใช้รหัสต่อไปนี้:

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

## ขั้นตอนที่ 5: ตั้งรหัสผ่านเพื่อป้องกันการนำเสนอ

 คุณสามารถป้องกันงานนำเสนอของคุณด้วยรหัสผ่านเพื่อจำกัดการเข้าถึง ใช้`encrypt` วิธีการตั้งรหัสผ่าน:

```java
// ตั้งรหัสผ่านเพื่อป้องกันการนำเสนอ
presentation.getProtectionManager().encrypt("your_password");
```

 แทนที่`"your_password"` ด้วยรหัสผ่านที่คุณต้องการ

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอลงในไฟล์ ในตัวอย่างนี้ เราจะบันทึกเป็นไฟล์ PPTX:

```java
// บันทึกงานนำเสนอลงในไฟล์
presentation.save(dataDir + "Password_Protected_Presentation_out.pptx", SaveFormat.Pptx);
```

 แทนที่`"Password_Protected_Presentation_out.pptx"` ด้วยชื่อไฟล์และเส้นทางที่คุณต้องการ

## กรอกซอร์สโค้ดสำหรับบันทึกคุณสมบัติใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์ PPT
Presentation presentation = new Presentation();
try
{
	//....มาทำงานที่นี่.....
	// การตั้งค่าการเข้าถึงคุณสมบัติเอกสารในโหมดป้องกันด้วยรหัสผ่าน
	presentation.getProtectionManager().setEncryptDocumentProperties(false);
	// การตั้งรหัสผ่าน
	presentation.getProtectionManager().encrypt("pass");
	// บันทึกงานนำเสนอของคุณลงในไฟล์
	presentation.save(dataDir + "Password Protected Presentation_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีบันทึกคุณสมบัติของเอกสารในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถตั้งค่าคุณสมบัติต่างๆ ปิดใช้งานการเข้ารหัสสำหรับคุณสมบัติเอกสาร ตั้งรหัสผ่านสำหรับการป้องกัน และบันทึกงานนำเสนอในรูปแบบที่คุณต้องการ

## คำถามที่พบบ่อย

### ฉันจะตั้งค่าคุณสมบัติเอกสารใน Aspose.Slides สำหรับ Java ได้อย่างไร

 หากต้องการตั้งค่าคุณสมบัติเอกสารใน Aspose.Slides สำหรับ Java คุณสามารถใช้ไฟล์`DocumentProperties` ระดับ. ต่อไปนี้คือตัวอย่างวิธีตั้งค่าคุณสมบัติ เช่น ชื่อเรื่อง ผู้แต่ง และคำสำคัญ:

```java
// ตั้งชื่อหัวข้อการนำเสนอ
presentation.getDocumentProperties().setTitle("My Presentation");

//กำหนดผู้เขียนการนำเสนอ
presentation.getDocumentProperties().setAuthor("John Doe");

// กำหนดคำสำคัญสำหรับการนำเสนอ
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

### จุดประสงค์ของการปิดใช้งานการเข้ารหัสสำหรับคุณสมบัติเอกสารคืออะไร?

การปิดใช้งานการเข้ารหัสสำหรับคุณสมบัติเอกสารทำให้คุณสามารถจัดเก็บข้อมูลเมตาของเอกสารได้โดยไม่ต้องเข้ารหัส สิ่งนี้มีประโยชน์เมื่อคุณต้องการให้คุณสมบัติของเอกสาร (เช่น ชื่อเรื่อง ผู้แต่ง ฯลฯ) มองเห็นและเข้าถึงได้โดยไม่ต้องป้อนรหัสผ่าน

คุณสามารถปิดการใช้งานการเข้ารหัสโดยใช้รหัสต่อไปนี้:

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

### ฉันจะป้องกันงานนำเสนอ PowerPoint ของฉันด้วยรหัสผ่านโดยใช้ Aspose.Slides สำหรับ Java ได้อย่างไร

เพื่อปกป้องงานนำเสนอ PowerPoint ของคุณด้วยรหัสผ่าน คุณสามารถใช้`encrypt` วิธีการที่กำหนดโดย`ProtectionManager` ระดับ. ต่อไปนี้เป็นวิธีตั้งรหัสผ่าน:

```java
// ตั้งรหัสผ่านเพื่อป้องกันการนำเสนอ
presentation.getProtectionManager().encrypt("your_password");
```

 แทนที่`"your_password"` ด้วยรหัสผ่านที่คุณต้องการ

### ฉันสามารถบันทึกงานนำเสนอในรูปแบบอื่นที่ไม่ใช่ PPTX ได้หรือไม่

 ใช่ คุณสามารถบันทึกงานนำเสนอในรูปแบบต่างๆ ที่ Aspose.Slides สำหรับ Java รองรับ เช่น PPT, PDF และอื่นๆ อีกมากมาย หากต้องการบันทึกในรูปแบบอื่น ให้เปลี่ยน`SaveFormat` พารามิเตอร์ใน`presentation.save` วิธี. ตัวอย่างเช่น หากต้องการบันทึกเป็น PDF:

```java
presentation.save(dataDir + "Presentation.pdf", SaveFormat.Pdf);
```

### จำเป็นต้องกำจัดวัตถุการนำเสนอหลังจากบันทึกหรือไม่?

 แนวทางปฏิบัติที่ดีในการกำจัดวัตถุการนำเสนอเพื่อนำออกใช้ทรัพยากรระบบ คุณสามารถใช้ก`finally` บล็อกเพื่อให้แน่ใจว่ามีการกำจัดอย่างเหมาะสม ดังที่แสดงในตัวอย่างโค้ด:

```java
finally {
    if (presentation != null) presentation.dispose();
}
```

ซึ่งจะช่วยป้องกันการรั่วไหลของหน่วยความจำในแอปพลิเคชันของคุณ

### ฉันจะเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java และฟีเจอร์ต่างๆ ได้อย่างไร

 คุณสามารถสำรวจเอกสาร Aspose.Slides สำหรับ Java ได้ที่[ที่นี่](https://docs.aspose.com/slides/java/) สำหรับข้อมูลโดยละเอียด บทช่วยสอน และตัวอย่างการใช้ห้องสมุด
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
