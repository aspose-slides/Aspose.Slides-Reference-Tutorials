---
title: คุณสมบัติที่แนะนำแบบอ่านอย่างเดียวใน Java Slides
linktitle: คุณสมบัติที่แนะนำแบบอ่านอย่างเดียวใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเปิดใช้งานคุณสมบัติที่แนะนำแบบอ่านอย่างเดียวในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนพร้อมตัวอย่างซอร์สโค้ดเพื่อเพิ่มความปลอดภัยในการนำเสนอ
weight: 17
url: /th/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## ข้อมูลเบื้องต้นเกี่ยวกับการเปิดใช้งานคุณสมบัติที่แนะนำแบบอ่านอย่างเดียวใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการเปิดใช้งานคุณสมบัติที่แนะนำแบบอ่านอย่างเดียวสำหรับงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสมบัติที่แนะนำแบบอ่านอย่างเดียวจะมีประโยชน์เมื่อคุณต้องการกระตุ้นให้ผู้ใช้ดูงานนำเสนอโดยไม่ต้องทำการเปลี่ยนแปลงใดๆ คุณสมบัติเหล่านี้แนะนำว่าควรเปิดงานนำเสนอในโหมดอ่านอย่างเดียว เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ด Java เพื่อให้บรรลุเป้าหมายนี้

## ข้อกำหนดเบื้องต้น

 ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Slides สำหรับเว็บไซต์ Java](https://products.aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างงานนำเสนอ PowerPoint ใหม่

เราจะเริ่มต้นด้วยการสร้างงานนำเสนอ PowerPoint ใหม่โดยใช้ Aspose.Slides สำหรับ Java หากคุณมีการนำเสนออยู่แล้ว คุณสามารถข้ามขั้นตอนนี้ได้

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

ในโค้ดด้านบน เราได้กำหนดเส้นทางสำหรับไฟล์ PowerPoint ผลลัพธ์และสร้างวัตถุการนำเสนอใหม่

## ขั้นตอนที่ 2: เปิดใช้งานคุณสมบัติที่แนะนำแบบอ่านอย่างเดียว

ตอนนี้ เรามาเปิดใช้งานคุณสมบัติ "แนะนำแบบอ่านอย่างเดียว" สำหรับงานนำเสนอกันดีกว่า

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

 ในข้อมูลโค้ดนี้ เราใช้`getProtectionManager().setReadOnlyRecommended(true)` วิธีการตั้งค่าคุณสมบัติแนะนำให้อ่านอย่างเดียวเป็น`true`- เพื่อให้แน่ใจว่าเมื่อมีคนเปิดงานนำเสนอ พวกเขาจะได้รับแจ้งให้เปิดในโหมดอ่านอย่างเดียว

## ขั้นตอนที่ 3: บันทึกการนำเสนอ

สุดท้ายนี้ เราจะบันทึกงานนำเสนอโดยเปิดใช้งานคุณสมบัติ "แนะนำแบบอ่านอย่างเดียว"

## กรอกซอร์สโค้ดสำหรับคุณสมบัติที่แนะนำแบบอ่านอย่างเดียวใน Java Slides

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

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีเปิดใช้งานคุณสมบัติ "แนะนำแบบอ่านอย่างเดียว" สำหรับงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสมบัตินี้จะมีประโยชน์เมื่อคุณต้องการจำกัดการแก้ไขและกระตุ้นให้ผู้ดูใช้งานนำเสนอในโหมดอ่านอย่างเดียว คุณสามารถเพิ่มความปลอดภัยเพิ่มเติมได้ด้วยการตั้งรหัสผ่านสำหรับการนำเสนอ

## คำถามที่พบบ่อย

### ฉันจะปิดการใช้งานคุณสมบัติที่แนะนำแบบอ่านอย่างเดียวได้อย่างไร

เมื่อต้องการปิดใช้งานคุณสมบัติแนะนำแบบอ่านอย่างเดียว เพียงใช้รหัสต่อไปนี้:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### ฉันสามารถตั้งรหัสผ่านสำหรับงานนำเสนอที่แนะนำแบบอ่านอย่างเดียวได้หรือไม่

ได้ คุณสามารถตั้งรหัสผ่านสำหรับงานนำเสนอที่แนะนำแบบอ่านอย่างเดียวได้โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถใช้`setPassword` วิธีการตั้งรหัสผ่านสำหรับการนำเสนอ หากมีการตั้งรหัสผ่าน ผู้ใช้จะต้องป้อนรหัสผ่านเพื่อเปิดงานนำเสนอ แม้ว่าจะอยู่ในโหมดอ่านอย่างเดียวก็ตาม

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 อย่าลืมเปลี่ยน`"YourPassword"` ด้วยรหัสผ่านที่คุณต้องการ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
