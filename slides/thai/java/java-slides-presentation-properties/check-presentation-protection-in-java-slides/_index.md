---
"description": "เรียนรู้วิธีตรวจสอบการป้องกันการนำเสนอในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้มีตัวอย่างโค้ดสำหรับการตรวจสอบการป้องกันการเขียนและการเปิด"
"linktitle": "ตรวจสอบการป้องกันการนำเสนอใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตรวจสอบการป้องกันการนำเสนอใน Java Slides"
"url": "/th/java/presentation-properties/check-presentation-protection-in-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตรวจสอบการป้องกันการนำเสนอใน Java Slides


## การแนะนำการตรวจสอบการป้องกันการนำเสนอใน Java Slides

ในบทช่วยสอนนี้ เราจะมาสำรวจวิธีการตรวจสอบการป้องกันการนำเสนอโดยใช้ Aspose.Slides สำหรับ Java เราจะครอบคลุมสองสถานการณ์ ได้แก่ การตรวจสอบการป้องกันการเขียนและการตรวจสอบการป้องกันการเปิดสำหรับการนำเสนอ เราจะให้ตัวอย่างโค้ดทีละขั้นตอนสำหรับแต่ละสถานการณ์

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีดังกล่าวได้จากเว็บไซต์ Aspose และเพิ่มไลบรารีดังกล่าวลงในส่วนที่ต้องมีของโปรเจ็กต์ของคุณ

### การพึ่งพา Maven

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

แทนที่ `your_version_here` ด้วยเวอร์ชัน Aspose.Slides สำหรับ Java ที่คุณใช้งานอยู่

## ขั้นตอนที่ 1: ตรวจสอบการป้องกันการเขียน

ในการตรวจสอบว่าการนำเสนอได้รับการป้องกันการเขียนด้วยรหัสผ่านหรือไม่ คุณสามารถใช้ `IPresentationInfo` อินเทอร์เฟซ นี่คือโค้ดสำหรับทำสิ่งนั้น:

```java
// เส้นทางการนำเสนอแหล่งที่มา
String pptxFile = "path_to_presentation.pptx";

// ตรวจสอบรหัสผ่านการป้องกันการเขียนผ่านอินเทอร์เฟซ IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

แทนที่ `"path_to_presentation.pptx"` ด้วยเส้นทางจริงไปยังไฟล์การนำเสนอของคุณและ `"password_here"` ด้วยรหัสผ่านการป้องกันการเขียน

## ขั้นตอนที่ 2: ตรวจสอบการป้องกันการเปิด

ในการตรวจสอบว่าการนำเสนอได้รับการป้องกันด้วยรหัสผ่านในการเปิดหรือไม่ คุณสามารถใช้ `IPresentationInfo` อินเทอร์เฟซ นี่คือโค้ดสำหรับทำสิ่งนั้น:

```java
// เส้นทางการนำเสนอแหล่งที่มา
String pptFile = "path_to_presentation.ppt";

// ตรวจสอบการปกป้องการเปิดการนำเสนอผ่านอินเทอร์เฟซ IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

แทนที่ `"path_to_presentation.ppt"` พร้อมเส้นทางจริงไปยังไฟล์การนำเสนอของคุณ

## โค้ดต้นฉบับที่สมบูรณ์สำหรับการตรวจสอบการป้องกันการนำเสนอใน Java Slides

```java
//เส้นทางการนำเสนอแหล่งข้อมูล
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
// ตรวจสอบการปกป้องการเปิดการนำเสนอผ่านอินเทอร์เฟซ IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการตรวจสอบการป้องกันการนำเสนอในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java เราได้ครอบคลุมสองสถานการณ์ ได้แก่ การตรวจสอบการป้องกันการเขียนและการตรวจสอบการป้องกันการเปิด ตอนนี้คุณสามารถรวมการตรวจสอบเหล่านี้เข้ากับแอปพลิเคชัน Java ของคุณเพื่อจัดการการนำเสนอที่ได้รับการป้องกันอย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันจะรับ Aspose.Slides สำหรับ Java ได้อย่างไร

คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์ Aspose หรือเพิ่มเป็นไฟล์ที่ต้องพึ่งพา Maven ในโปรเจ็กต์ของคุณ ดังที่แสดงในส่วนข้อกำหนดเบื้องต้น

### ฉันสามารถตรวจสอบการป้องกันการเขียนและการป้องกันการเปิดสำหรับการนำเสนอได้หรือไม่

ใช่ คุณสามารถตรวจสอบการป้องกันการเขียนและการป้องกันการเปิดสำหรับการนำเสนอได้โดยใช้ตัวอย่างโค้ดที่ให้มา

### ฉันควรทำอย่างไรหากลืมรหัสผ่านการป้องกัน?

หากคุณลืมรหัสผ่านการป้องกันสำหรับการนำเสนอ จะไม่มีวิธีการกู้คืนรหัสผ่านในตัว ดังนั้นอย่าลืมเก็บรหัสผ่านของคุณไว้เพื่อหลีกเลี่ยงสถานการณ์ดังกล่าว

### Aspose.Slides สำหรับ Java เข้ากันได้กับรูปแบบไฟล์ PowerPoint ล่าสุดหรือไม่

ใช่ Aspose.Slides สำหรับ Java รองรับรูปแบบไฟล์ PowerPoint ล่าสุด รวมถึงไฟล์ .pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}