---
"description": "เรียนรู้วิธีเปิดใช้งานคุณสมบัติแนะนำแบบอ่านอย่างเดียวในงานนำเสนอ PowerPoint ในรูปแบบ Java โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราพร้อมตัวอย่างโค้ดต้นฉบับเพื่อความปลอดภัยในการนำเสนอที่ดีขึ้น"
"linktitle": "คุณสมบัติที่แนะนำให้อ่านอย่างเดียวใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "คุณสมบัติที่แนะนำให้อ่านอย่างเดียวใน Java Slides"
"url": "/th/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# คุณสมบัติที่แนะนำให้อ่านอย่างเดียวใน Java Slides


## การแนะนำการเปิดใช้งานคุณสมบัติที่แนะนำแบบอ่านอย่างเดียวใน Java Slides

ในบทช่วยสอนนี้ เราจะมาดูวิธีเปิดใช้งานคุณสมบัติแนะนำแบบอ่านอย่างเดียวสำหรับการนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสมบัติแนะนำแบบอ่านอย่างเดียวอาจมีประโยชน์เมื่อคุณต้องการสนับสนุนให้ผู้ใช้ดูการนำเสนอโดยไม่ต้องทำการเปลี่ยนแปลงใดๆ คุณสมบัติเหล่านี้แนะนำว่าควรเปิดการนำเสนอในโหมดอ่านอย่างเดียว เราจะให้คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับของ Java แก่คุณเพื่อให้บรรลุสิ่งนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [Aspose.Slides สำหรับเว็บไซต์ Java](https://products-aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างการนำเสนอ PowerPoint ใหม่

เราจะเริ่มต้นด้วยการสร้างงานนำเสนอ PowerPoint ใหม่โดยใช้ Aspose.Slides สำหรับ Java หากคุณมีงานนำเสนออยู่แล้ว คุณสามารถข้ามขั้นตอนนี้ได้

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

ในโค้ดด้านบน เราได้กำหนดเส้นทางสำหรับไฟล์ PowerPoint เอาต์พุต และสร้างอ็อบเจ็กต์การนำเสนอใหม่

## ขั้นตอนที่ 2: เปิดใช้งานคุณสมบัติที่แนะนำแบบอ่านอย่างเดียว

ตอนนี้ มาเปิดใช้งานคุณสมบัติแนะนำให้อ่านอย่างเดียวสำหรับการนำเสนอกัน

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

ในโค้ดตัวอย่างนี้ เราใช้ `getProtectionManager().setReadOnlyRecommended(true)` วิธีการตั้งค่าคุณสมบัติแนะนำให้อ่านอย่างเดียวเป็น `true`การดำเนินการนี้จะช่วยให้มั่นใจได้ว่าเมื่อมีใครก็ตามเปิดการนำเสนอ พวกเขาจะได้รับแจ้งให้เปิดในโหมดอ่านอย่างเดียว

## ขั้นตอนที่ 3: บันทึกการนำเสนอ

ในที่สุด เราบันทึกการนำเสนอโดยเปิดใช้งานคุณสมบัติแนะนำให้อ่านอย่างเดียว

## โค้ดต้นฉบับที่สมบูรณ์สำหรับคุณสมบัติที่แนะนำให้อ่านอย่างเดียวใน Java Slides

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีเปิดใช้งานคุณสมบัติ Read-Only Recommended สำหรับการนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสมบัตินี้อาจมีประโยชน์เมื่อคุณต้องการจำกัดการแก้ไขและสนับสนุนให้ผู้ชมใช้การนำเสนอในโหมดอ่านอย่างเดียว คุณสามารถปรับปรุงความปลอดภัยเพิ่มเติมได้โดยการตั้งรหัสผ่านสำหรับการนำเสนอ

## คำถามที่พบบ่อย

### ฉันจะปิดใช้งานคุณสมบัติแนะนำให้อ่านอย่างเดียวได้อย่างไร

หากต้องการปิดใช้งานคุณสมบัติแนะนำให้อ่านอย่างเดียว ให้ใช้โค้ดดังต่อไปนี้:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### ฉันสามารถตั้งรหัสผ่านสำหรับการนำเสนอที่แนะนำให้อ่านอย่างเดียวได้หรือไม่

ใช่ คุณสามารถตั้งรหัสผ่านสำหรับการนำเสนอแบบอ่านอย่างเดียวที่แนะนำได้โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถใช้ `setPassword` วิธีการตั้งรหัสผ่านสำหรับการนำเสนอ หากตั้งรหัสผ่านไว้ ผู้ใช้จะต้องป้อนรหัสผ่านเพื่อเปิดการนำเสนอ แม้ว่าจะอยู่ในโหมดอ่านอย่างเดียวก็ตาม

```java
pres.getProtectionManager().setPassword("YourPassword");
```

อย่าลืมเปลี่ยน `"YourPassword"` ด้วยรหัสผ่านที่คุณต้องการ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}