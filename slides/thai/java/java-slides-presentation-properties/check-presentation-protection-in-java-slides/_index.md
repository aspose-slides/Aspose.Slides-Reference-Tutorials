---
title: ตรวจสอบการป้องกันการนำเสนอใน Java Slides
linktitle: ตรวจสอบการป้องกันการนำเสนอใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตรวจสอบการป้องกันการนำเสนอในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้ให้ตัวอย่างโค้ดสำหรับการตรวจสอบการป้องกันการเขียนและแบบเปิด
type: docs
weight: 15
url: /th/java/presentation-properties/check-presentation-protection-in-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการตรวจสอบการป้องกันการนำเสนอใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีตรวจสอบการป้องกันการนำเสนอโดยใช้ Aspose.Slides สำหรับ Java เราจะกล่าวถึงสองสถานการณ์: การตรวจสอบการป้องกันการเขียน และการตรวจสอบการป้องกันแบบเปิดสำหรับการนำเสนอ เราจะให้ตัวอย่างโค้ดทีละขั้นตอนสำหรับแต่ละสถานการณ์

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose และเพิ่มลงในการขึ้นต่อกันของโปรเจ็กต์ของคุณ

### การพึ่งพามาเวน

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

 แทนที่`your_version_here` ด้วยเวอร์ชันของ Aspose.Slides สำหรับ Java ที่คุณใช้

## ขั้นตอนที่ 1: ตรวจสอบการป้องกันการเขียน

 หากต้องการตรวจสอบว่างานนำเสนอมีการป้องกันการเขียนด้วยรหัสผ่านหรือไม่ คุณสามารถใช้`IPresentationInfo` อินเตอร์เฟซ. นี่คือรหัสที่ต้องทำ:

```java
// เส้นทางสำหรับการนำเสนอแหล่งที่มา
String pptxFile = "path_to_presentation.pptx";

// ตรวจสอบรหัสผ่านการป้องกันการเขียนผ่านอินเทอร์เฟซ IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

 แทนที่`"path_to_presentation.pptx"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณและ`"password_here"` ด้วยรหัสผ่านป้องกันการเขียน

## ขั้นตอนที่ 2: ตรวจสอบการป้องกันแบบเปิด

 หากต้องการตรวจสอบว่างานนำเสนอได้รับการป้องกันด้วยรหัสผ่านสำหรับการเปิดหรือไม่ คุณสามารถใช้`IPresentationInfo` อินเตอร์เฟซ. นี่คือรหัสที่ต้องทำ:

```java
// เส้นทางสำหรับการนำเสนอแหล่งที่มา
String pptFile = "path_to_presentation.ppt";

// ตรวจสอบการป้องกันการนำเสนอแบบเปิดผ่านอินเทอร์เฟซ IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

 แทนที่`"path_to_presentation.ppt"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

## ซอร์สโค้ดที่สมบูรณ์สำหรับการป้องกันการนำเสนอตรวจสอบใน Java Slides

```java
//เส้นทางสำหรับการนำเสนอแหล่งที่มา
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// ตรวจสอบรหัสผ่านการป้องกันการเขียนผ่านอินเทอร์เฟซ IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// ตรวจสอบรหัสผ่านการป้องกันการเขียนผ่านอินเทอร์เฟซ IProtectionManager
Presentation presentation = new Presentation();
try
{
	boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
	System.out.println("Is presentation write protected = " + isWriteProtected);
}
finally
{
	if (presentation != null) presentation.dispose();
}
// ตรวจสอบการป้องกันการนำเสนอแบบเปิดผ่านอินเทอร์เฟซ IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตรวจสอบการป้องกันการนำเสนอในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java เราครอบคลุมสองสถานการณ์: การตรวจสอบการป้องกันการเขียน และการตรวจสอบการป้องกันแบบเปิด ตอนนี้คุณสามารถรวมการตรวจสอบเหล่านี้เข้ากับแอปพลิเคชัน Java ของคุณเพื่อจัดการการนำเสนอที่ได้รับการป้องกันได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันจะรับ Aspose.Slides สำหรับ Java ได้อย่างไร

คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์ Aspose หรือเพิ่มเป็นการพึ่งพา Maven ในโปรเจ็กต์ของคุณ ดังที่แสดงในส่วนข้อกำหนดเบื้องต้น

### ฉันสามารถตรวจสอบทั้งการป้องกันการเขียนและการป้องกันแบบเปิดสำหรับการนำเสนอได้หรือไม่

ได้ คุณสามารถตรวจสอบทั้งการป้องกันการเขียนและการป้องกันแบบเปิดสำหรับการนำเสนอโดยใช้ตัวอย่างโค้ดที่ให้มา

### ฉันควรทำอย่างไรหากลืมรหัสผ่านป้องกัน?

หากคุณลืมรหัสผ่านการป้องกันสำหรับงานนำเสนอ จะไม่มีวิธีการกู้คืนรหัสผ่านในตัว ตรวจสอบให้แน่ใจว่าได้เก็บบันทึกรหัสผ่านของคุณเพื่อหลีกเลี่ยงสถานการณ์ดังกล่าว

### Aspose.Slides สำหรับ Java เข้ากันได้กับรูปแบบไฟล์ PowerPoint ล่าสุดหรือไม่

ใช่ Aspose.Slides สำหรับ Java รองรับรูปแบบไฟล์ PowerPoint ล่าสุด รวมถึงไฟล์ .pptx