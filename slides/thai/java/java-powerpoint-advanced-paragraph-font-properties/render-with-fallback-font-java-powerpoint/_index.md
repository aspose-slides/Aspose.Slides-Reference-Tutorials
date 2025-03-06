---
title: แสดงผลด้วยแบบอักษรทางเลือกใน Java PowerPoint
linktitle: แสดงผลด้วยแบบอักษรทางเลือกใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแสดงข้อความด้วยแบบอักษรสำรองในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อการใช้งานที่ราบรื่น
weight: 13
url: /th/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
การสร้างและจัดการงานนำเสนอ PowerPoint ใน Java อาจเป็นเรื่องที่ท้าทาย แต่ด้วย Aspose.Slides คุณสามารถทำได้อย่างมีประสิทธิภาพ คุณลักษณะที่สำคัญประการหนึ่งคือความสามารถในการแสดงข้อความด้วยแบบอักษรสำรอง บทความนี้ให้คำแนะนำโดยละเอียดทีละขั้นตอนเกี่ยวกับวิธีการใช้แบบอักษรทางเลือกในสไลด์ PowerPoint ของคุณโดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้งาน โปรดตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการ:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ
2.  Aspose.Slides สำหรับ Java: คุณสามารถดาวน์โหลดได้จากไฟล์[Aspose.Slides สำหรับหน้าดาวน์โหลด Java](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): IDE เช่น IntelliJ IDEA หรือ Eclipse จะทำให้กระบวนการพัฒนาของคุณราบรื่นยิ่งขึ้น
4. การขึ้นต่อกัน: รวม Aspose.Slides ในการขึ้นต่อกันของโปรเจ็กต์ของคุณ
## แพ็คเกจนำเข้า
ขั้นแรก เราต้องนำเข้าแพ็คเกจที่จำเป็นในโปรแกรม Java ของเรา
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
เรามาแบ่งกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
 ก่อนที่จะเขียนโค้ดใดๆ ตรวจสอบให้แน่ใจว่าโครงการของคุณได้รับการตั้งค่าอย่างถูกต้อง ซึ่งรวมถึงการเพิ่มไลบรารี Aspose.Slides ในโครงการของคุณ คุณสามารถทำได้โดยดาวน์โหลดไลบรารี่จาก[Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/) และเพิ่มลงในเส้นทางการสร้างของคุณ
## ขั้นตอนที่ 2: เริ่มต้นกฎทางเลือกแบบอักษร
 คุณต้องสร้างอินสแตนซ์ของ`IFontFallBackRulesCollection` ชั้นเรียนและเพิ่มกฎเกณฑ์ลงไป กฎเหล่านี้กำหนดทางเลือกแบบอักษรสำหรับช่วง Unicode ที่ระบุ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ใหม่ของคอลเลกชันกฎ
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// สร้างกฎจำนวนหนึ่ง
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## ขั้นตอนที่ 3: แก้ไขกฎทางเลือก
ในขั้นตอนนี้ เราจะแก้ไขกฎทางเลือกโดยการลบแบบอักษรทางเลือกที่มีอยู่ออก และอัปเดตกฎสำหรับช่วง Unicode ที่ระบุ
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // กำลังพยายามลบแบบอักษร FallBack "Tahoma" ออกจากกฎที่โหลด
    fallBackRule.remove("Tahoma");
    // อัปเดตกฎสำหรับช่วงที่ระบุ
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//ลบกฎที่มีอยู่ออกจากรายการ
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## ขั้นตอนที่ 4: โหลดการนำเสนอ
โหลดงานนำเสนอ PowerPoint ที่คุณต้องการแก้ไข
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## ขั้นตอนที่ 5: กำหนดกฎทางเลือกให้กับการนำเสนอ
กำหนดกฎทางเลือกที่เตรียมไว้ให้กับตัวจัดการแบบอักษรของงานนำเสนอ
```java
try {
    // การกำหนดรายการกฎเกณฑ์ที่เตรียมไว้สำหรับการใช้งาน
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // การแสดงภาพขนาดย่อโดยใช้การรวบรวมกฎเริ่มต้นและบันทึกเป็น PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## ขั้นตอนที่ 6: บันทึกและทดสอบ
สุดท้าย ให้บันทึกงานของคุณและทดสอบการใช้งานเพื่อให้แน่ใจว่าทุกอย่างทำงานได้ตามที่คาดหวัง หากคุณพบปัญหาใดๆ ให้ตรวจสอบการตั้งค่าของคุณอีกครั้งและให้แน่ใจว่ามีการเพิ่มการอ้างอิงทั้งหมดอย่างถูกต้อง
## บทสรุป
ด้วยการทำตามคำแนะนำนี้ คุณสามารถแสดงข้อความด้วยฟอนต์สำรองในงานนำเสนอ PowerPoint ของคุณได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Slides สำหรับ Java กระบวนการนี้ช่วยให้มั่นใจได้ว่างานนำเสนอของคุณจะมีการจัดรูปแบบที่สอดคล้องกัน แม้ว่าแบบอักษรหลักจะไม่พร้อมใช้งานก็ตาม ขอให้มีความสุขในการเขียนโค้ด!
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides for Java เป็นไลบรารีที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และเรนเดอร์งานนำเสนอ PowerPoint ในแอปพลิเคชัน Java
### ฉันจะเพิ่ม Aspose.Slides ในโครงการของฉันได้อย่างไร
 คุณสามารถดาวน์โหลดห้องสมุดได้จาก[หน้าดาวน์โหลด Aspose.Slides](https://releases.aspose.com/slides/java/) และเพิ่มลงในเส้นทางการสร้างโครงการของคุณ
### แบบอักษรสำรองคืออะไร
ฟอนต์สำรองเป็นฟอนต์ทางเลือกที่ใช้เมื่อฟอนต์ที่ระบุไม่พร้อมใช้งานหรือไม่รองรับอักขระบางตัว
### ฉันสามารถใช้กฎสำรองหลายกฎได้หรือไม่
ได้ คุณสามารถเพิ่มกฎทางเลือกหลายกฎเพื่อจัดการช่วง Unicode และแบบอักษรที่แตกต่างกันได้
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
 คุณสามารถรับการสนับสนุนจาก[ฟอรั่มการสนับสนุน Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
