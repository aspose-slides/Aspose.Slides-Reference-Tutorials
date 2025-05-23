---
"description": "เรียนรู้วิธีตั้งค่า ClsId ของรูทไดเร็กทอรีใน Aspose.Slides สำหรับการนำเสนอ Java ปรับแต่งพฤติกรรมไฮเปอร์ลิงก์ด้วย CLSID"
"linktitle": "ClsId ไดเร็กทอรีรูทใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ClsId ไดเร็กทอรีรูทใน Java Slides"
"url": "/th/java/media-controls/root-directory-clsid-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ClsId ไดเร็กทอรีรูทใน Java Slides


## บทนำเกี่ยวกับการตั้งค่า ClsId ของไดเรกทอรีรูทใน Aspose.Slides สำหรับ Java

ใน Aspose.Slides สำหรับ Java คุณสามารถตั้งค่า ClsId ของไดเรกทอรีรูท ซึ่งเป็น CLSID (ตัวระบุคลาส) ที่ใช้ระบุแอปพลิเคชันที่จะใช้เป็นไดเรกทอรีรูทเมื่อเปิดใช้งานไฮเปอร์ลิงก์ในงานนำเสนอของคุณ ในคู่มือนี้ เราจะแนะนำคุณทีละขั้นตอนว่าต้องทำอย่างไร

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [เอกสาร Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).
- ตัวแก้ไขโค้ดหรือสภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่ตั้งค่าไว้สำหรับการพัฒนา Java

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

ขั้นแรก เราจะสร้างงานนำเสนอใหม่โดยใช้ Aspose.Slides สำหรับ Java ในตัวอย่างนี้ เราจะสร้างงานนำเสนอเปล่า

```java
// ชื่อไฟล์เอาท์พุต
String resultPath = "your_output_path/pres.ppt"; // แทนที่ "your_output_path" ด้วยไดเร็กทอรีเอาต์พุตที่คุณต้องการ
Presentation pres = new Presentation();
```

ในโค้ดด้านบน เราได้กำหนดเส้นทางสำหรับไฟล์นำเสนอเอาท์พุตและสร้างไฟล์ใหม่ `Presentation` วัตถุ.

## ขั้นตอนที่ 2: ตั้งค่าไดเรกทอรีรูท ClsId

หากต้องการตั้งค่า ClsId ของไดเรกทอรีรูท คุณต้องสร้างอินสแตนซ์ของ `PptOptions` และตั้งค่า CLSID ที่ต้องการ CLSID แสดงถึงแอปพลิเคชันที่จะใช้เป็นไดเร็กทอรีรูทเมื่อเปิดใช้งานไฮเปอร์ลิงก์

```java
PptOptions pptOptions = new PptOptions();
// ตั้งค่า CLSID เป็น 'Microsoft Powerpoint.Show.8'
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

ในโค้ดด้านบน เราสร้าง `PptOptions` วัตถุและตั้งค่า CLSID เป็น 'Microsoft Powerpoint.Show.8' คุณสามารถแทนที่ด้วย CLSID ของแอปพลิเคชันที่คุณต้องการใช้เป็นไดเร็กทอรีรูทได้

## ขั้นตอนที่ 3: บันทึกการนำเสนอ

ตอนนี้มาบันทึกการนำเสนอโดยกำหนด ClsId ของไดเรกทอรีรูทกัน

```java
// บันทึกการนำเสนอ
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

ในขั้นตอนนี้เราจะบันทึกการนำเสนอไปยังตำแหน่งที่ระบุ `resultPath` ด้วย `PptOptions` เราสร้างไว้ก่อนหน้านี้แล้ว

## ขั้นตอนที่ 4: การทำความสะอาด

อย่าลืมทิ้ง `Presentation` คัดค้านการปล่อยทรัพยากรใด ๆ ที่ได้รับการจัดสรร

```java
if (pres != null) {
    pres.dispose();
}
```

## โค้ดต้นฉบับสมบูรณ์สำหรับ ClsId ไดเร็กทอรีรูทในสไลด์ Java

```java
// ชื่อไฟล์เอาท์พุต
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	// ตั้งค่า CLSID เป็น 'Microsoft Powerpoint.Show.8'
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// บันทึกการนำเสนอ
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## บทสรุป

คุณได้ตั้งค่า ClsId ของไดเรกทอรีรูทใน Aspose.Slides สำหรับ Java สำเร็จแล้ว การดำเนินการนี้ช่วยให้คุณระบุแอปพลิเคชันที่จะใช้เป็นไดเรกทอรีรูทเมื่อเปิดใช้งานไฮเปอร์ลิงก์ในงานนำเสนอของคุณ คุณสามารถปรับแต่ง CLSID ตามความต้องการเฉพาะของคุณได้

## คำถามที่พบบ่อย

### ฉันจะค้นหา CLSID สำหรับแอปพลิเคชันเฉพาะได้อย่างไร

หากต้องการค้นหา CLSID สำหรับแอปพลิเคชันเฉพาะ คุณสามารถดูเอกสารหรือทรัพยากรที่จัดเตรียมโดยนักพัฒนาแอปพลิเคชัน CLSID คือตัวระบุเฉพาะที่กำหนดให้กับอ็อบเจ็กต์ COM และโดยทั่วไปจะเฉพาะเจาะจงสำหรับแต่ละแอปพลิเคชัน

### ฉันสามารถตั้งค่า CLSID แบบกำหนดเองสำหรับไดเร็กทอรีรูทได้หรือไม่

ใช่ คุณสามารถตั้งค่า CLSID แบบกำหนดเองสำหรับไดเร็กทอรีรูทได้โดยระบุค่า CLSID ที่ต้องการโดยใช้ `setRootDirectoryClsid` วิธีการดังที่แสดงในตัวอย่างโค้ด วิธีนี้ช่วยให้คุณสามารถใช้แอปพลิเคชันเฉพาะเป็นไดเร็กทอรีรูทเมื่อเปิดใช้งานไฮเปอร์ลิงก์ในงานนำเสนอของคุณ

### จะเกิดอะไรขึ้นถ้าฉันไม่ตั้งค่า ClsId ไดเรกทอรีรูท?

หากคุณไม่ตั้งค่า ClsId ของไดเรกทอรีรูท พฤติกรรมเริ่มต้นจะขึ้นอยู่กับโปรแกรมดูหรือแอปพลิเคชันที่ใช้เปิดการนำเสนอ อาจใช้แอปพลิเคชันเริ่มต้นของตัวเองเป็นไดเรกทอรีรูทเมื่อเปิดใช้งานไฮเปอร์ลิงก์

### ฉันสามารถเปลี่ยน ClsId ไดเรกทอรีรูทสำหรับไฮเปอร์ลิงก์แต่ละรายการได้หรือไม่

ไม่ ClsId ของไดเรกทอรีรูทมักจะถูกตั้งค่าในระดับการนำเสนอและใช้กับไฮเปอร์ลิงก์ทั้งหมดภายในการนำเสนอ หากคุณจำเป็นต้องระบุแอปพลิเคชันที่แตกต่างกันสำหรับไฮเปอร์ลิงก์แต่ละรายการ คุณอาจต้องจัดการไฮเปอร์ลิงก์เหล่านั้นแยกกันในโค้ดของคุณ

### มีข้อจำกัดใด ๆ เกี่ยวกับ CLSID ที่ฉันสามารถใช้ได้หรือไม่

CLSID ที่คุณสามารถใช้ได้นั้นโดยทั่วไปจะกำหนดโดยแอปพลิเคชันที่ติดตั้งบนระบบ คุณควรใช้ CLSID ที่สอดคล้องกับแอปพลิเคชันที่ถูกต้องที่สามารถจัดการไฮเปอร์ลิงก์ได้ โปรดทราบว่าการใช้ CLSID ที่ไม่ถูกต้องอาจส่งผลให้เกิดพฤติกรรมที่ไม่คาดคิด

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}