---
"description": "เพิ่มประสิทธิภาพการนำเสนอ PowerPoint ของคุณด้วย Aspose.Slides สำหรับ Java เรียนรู้วิธีตั้งค่าคุณสมบัติ ปิดการใช้งานการเข้ารหัส เพิ่มการป้องกันด้วยรหัสผ่าน และบันทึกข้อมูลได้อย่างง่ายดาย"
"linktitle": "บันทึกคุณสมบัติใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "บันทึกคุณสมบัติใน Java Slides"
"url": "/th/java/saving-options/save-properties-in-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# บันทึกคุณสมบัติใน Java Slides


## บทนำเกี่ยวกับการบันทึกคุณสมบัติใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการบันทึกคุณสมบัติในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณจะได้เรียนรู้วิธีตั้งค่าคุณสมบัติเอกสาร ปิดใช้งานการเข้ารหัสสำหรับคุณสมบัติเอกสาร ตั้งรหัสผ่านเพื่อปกป้องงานนำเสนอของคุณ และบันทึกลงในไฟล์ เราจะให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ดต้นฉบับแก่คุณ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าคุณมีไลบรารี Aspose.Slides สำหรับ Java ที่ผสานรวมเข้ากับโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จากเว็บไซต์ Aspose [ที่นี่](https://downloads-aspose.com/slides/java).

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ในการเริ่มต้น ให้นำเข้าคลาสและไลบรารีที่จำเป็น:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ขั้นตอนที่ 2: สร้างวัตถุการนำเสนอ

สร้างอ็อบเจ็กต์การนำเสนอเพื่อแสดงการนำเสนอ PowerPoint ของคุณ คุณสามารถสร้างการนำเสนอใหม่หรือโหลดการนำเสนอที่มีอยู่แล้วก็ได้ ในตัวอย่างนี้ เราจะสร้างการนำเสนอใหม่

```java
// เส้นทางไปยังไดเรกทอรีที่คุณต้องการบันทึกการนำเสนอ
String dataDir = "Your Document Directory";

// สร้างอินสแตนซ์ของวัตถุการนำเสนอ
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 3: ตั้งค่าคุณสมบัติเอกสาร

คุณสามารถตั้งค่าคุณสมบัติเอกสารต่างๆ เช่น ชื่อเรื่อง ผู้เขียน คำสำคัญ และอื่นๆ ได้ที่นี่ เราจะตั้งค่าคุณสมบัติทั่วไปบางประการ:

```java
// การกำหนดหัวข้อการนำเสนอ
presentation.getDocumentProperties().setTitle("My Presentation");

// ตั้งค่าผู้เขียนงานนำเสนอ
presentation.getDocumentProperties().setAuthor("John Doe");

// กำหนดคำสำคัญสำหรับการนำเสนอ
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

## ขั้นตอนที่ 4: ปิดใช้งานการเข้ารหัสสำหรับคุณสมบัติเอกสาร

ตามค่าเริ่มต้น Aspose.Slides จะเข้ารหัสคุณสมบัติของเอกสาร หากคุณต้องการปิดการใช้งานการเข้ารหัสสำหรับคุณสมบัติของเอกสาร ให้ใช้โค้ดต่อไปนี้:

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

## ขั้นตอนที่ 5: ตั้งรหัสผ่านเพื่อป้องกันการนำเสนอ

คุณสามารถป้องกันการนำเสนอของคุณด้วยรหัสผ่านเพื่อจำกัดการเข้าถึง ใช้ `encrypt` วิธีการตั้งรหัสผ่าน:

```java
// ตั้งรหัสผ่านเพื่อป้องกันการนำเสนอ
presentation.getProtectionManager().encrypt("your_password");
```

แทนที่ `"your_password"` ด้วยรหัสผ่านที่คุณต้องการ

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอลงในไฟล์ ในตัวอย่างนี้ เราจะบันทึกเป็นไฟล์ PPTX:

```java
// บันทึกการนำเสนอลงในไฟล์
presentation.save(dataDir + "Password_Protected_Presentation_out.pptx", SaveFormat.Pptx);
```

แทนที่ `"Password_Protected_Presentation_out.pptx"` ด้วยชื่อไฟล์และเส้นทางที่คุณต้องการ

## โค้ดต้นฉบับที่สมบูรณ์สำหรับการบันทึกคุณสมบัติใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของวัตถุการนำเสนอที่แสดงไฟล์ PPT
Presentation presentation = new Presentation();
try
{
	//....ก็ทำบางอย่างที่นี่.....
	// การตั้งค่าการเข้าถึงคุณสมบัติเอกสารในโหมดป้องกันด้วยรหัสผ่าน
	presentation.getProtectionManager().setEncryptDocumentProperties(false);
	// การตั้งรหัสผ่าน
	presentation.getProtectionManager().encrypt("pass");
	// บันทึกการนำเสนอของคุณลงในไฟล์
	presentation.save(dataDir + "Password Protected Presentation_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการบันทึกคุณสมบัติของเอกสารในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถตั้งค่าคุณสมบัติต่างๆ ปิดการใช้งานการเข้ารหัสสำหรับคุณสมบัติของเอกสาร ตั้งรหัสผ่านเพื่อการป้องกัน และบันทึกงานนำเสนอในรูปแบบที่คุณต้องการ

## คำถามที่พบบ่อย

### ฉันจะตั้งค่าคุณสมบัติเอกสารใน Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการตั้งค่าคุณสมบัติเอกสารใน Aspose.Slides สำหรับ Java คุณสามารถใช้ `DocumentProperties` คลาส นี่คือตัวอย่างวิธีการตั้งค่าคุณสมบัติ เช่น ชื่อเรื่อง ผู้แต่ง และคำสำคัญ:

```java
// การกำหนดหัวข้อการนำเสนอ
presentation.getDocumentProperties().setTitle("My Presentation");

// ตั้งค่าผู้เขียนงานนำเสนอ
presentation.getDocumentProperties().setAuthor("John Doe");

// กำหนดคำสำคัญสำหรับการนำเสนอ
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

### จุดประสงค์ของการปิดการใช้งานการเข้ารหัสสำหรับคุณสมบัติของเอกสารคืออะไร

การปิดใช้งานการเข้ารหัสสำหรับคุณสมบัติของเอกสารทำให้คุณสามารถจัดเก็บข้อมูลเมตาของเอกสารได้โดยไม่ต้องเข้ารหัส ซึ่งอาจมีประโยชน์เมื่อคุณต้องการให้คุณสมบัติของเอกสาร (เช่น ชื่อเรื่อง ผู้เขียน เป็นต้น) สามารถมองเห็นและเข้าถึงได้โดยไม่ต้องป้อนรหัสผ่าน

คุณสามารถปิดการใช้งานการเข้ารหัสโดยใช้รหัสดังต่อไปนี้:

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

### ฉันจะปกป้องการนำเสนอ PowerPoint ของฉันด้วยรหัสผ่านโดยใช้ Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการปกป้องการนำเสนอ PowerPoint ของคุณด้วยรหัสผ่าน คุณสามารถใช้ `encrypt` วิธีการที่ให้ไว้โดย `ProtectionManager` ชั้นเรียน วิธีการตั้งรหัสผ่านมีดังนี้:

```java
// ตั้งรหัสผ่านเพื่อป้องกันการนำเสนอ
presentation.getProtectionManager().encrypt("your_password");
```

แทนที่ `"your_password"` ด้วยรหัสผ่านที่คุณต้องการ

### ฉันสามารถบันทึกงานนำเสนอในรูปแบบอื่นนอกเหนือจาก PPTX ได้หรือไม่

ใช่ คุณสามารถบันทึกงานนำเสนอในรูปแบบต่างๆ ที่รองรับโดย Aspose.Slides สำหรับ Java เช่น PPT, PDF และอื่นๆ หากต้องการบันทึกในรูปแบบอื่น ให้เปลี่ยน `SaveFormat` พารามิเตอร์ใน `presentation.save` วิธีการ เช่น การบันทึกเป็น PDF:

```java
presentation.save(dataDir + "Presentation.pdf", SaveFormat.Pdf);
```

### จำเป็นต้องกำจัดวัตถุการนำเสนอหลังจากบันทึกหรือไม่

ถือเป็นแนวทางปฏิบัติที่ดีที่จะกำจัดวัตถุการนำเสนอเพื่อปลดปล่อยทรัพยากรระบบ คุณสามารถใช้ `finally` บล็อกเพื่อให้แน่ใจว่ากำจัดอย่างถูกต้องตามที่แสดงในตัวอย่างโค้ด:

```java
finally {
    if (presentation != null) presentation.dispose();
}
```

สิ่งนี้ช่วยป้องกันการรั่วไหลของหน่วยความจำในแอปพลิเคชันของคุณ

### ฉันจะเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java และคุณลักษณะต่างๆ ของมันได้อย่างไร

คุณสามารถสำรวจเอกสาร Aspose.Slides สำหรับ Java ได้ที่ [ที่นี่](https://docs.aspose.com/slides/java/) สำหรับข้อมูลโดยละเอียด บทช่วยสอน และตัวอย่างการใช้งานไลบรารี

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}