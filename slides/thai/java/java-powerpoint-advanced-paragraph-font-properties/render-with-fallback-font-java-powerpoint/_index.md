---
"description": "เรียนรู้วิธีแสดงข้อความด้วยแบบอักษรสำรองในงานนำเสนอ PowerPoint ในรูปแบบ Java โดยใช้ Aspose.Slides ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อการใช้งานที่ราบรื่น"
"linktitle": "การเรนเดอร์ด้วยฟอนต์ Fallback ใน Java PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การเรนเดอร์ด้วยฟอนต์ Fallback ใน Java PowerPoint"
"url": "/th/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การเรนเดอร์ด้วยฟอนต์ Fallback ใน Java PowerPoint

## การแนะนำ
การสร้างและจัดการงานนำเสนอ PowerPoint ใน Java อาจเป็นเรื่องท้าทาย แต่ด้วย Aspose.Slides คุณจะทำสิ่งนี้ได้อย่างมีประสิทธิภาพ คุณลักษณะที่สำคัญอย่างหนึ่งคือความสามารถในการแสดงข้อความด้วยแบบอักษรสำรอง บทความนี้ให้คำแนะนำโดยละเอียดทีละขั้นตอนเกี่ยวกับวิธีการนำแบบอักษรสำรองไปใช้ในสไลด์ PowerPoint ของคุณโดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มใช้งานจริง เรามาตรวจสอบก่อนว่าคุณมีทุกสิ่งที่คุณต้องการ:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK ไว้ในระบบของคุณแล้ว
2. Aspose.Slides สำหรับ Java: คุณสามารถดาวน์โหลดได้จาก [หน้าดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases-aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): IDE เช่น IntelliJ IDEA หรือ Eclipse จะทำให้กระบวนการพัฒนาของคุณราบรื่นยิ่งขึ้น
4. การอ้างอิง: รวม Aspose.Slides ไว้ในการอ้างอิงของโครงการของคุณ
## แพ็คเกจนำเข้า
ก่อนอื่น เราต้องนำเข้าแพ็คเกจที่จำเป็นลงในโปรแกรม Java ของเรา
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
มาแบ่งกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ก่อนที่จะเขียนโค้ดใดๆ โปรดตรวจสอบให้แน่ใจว่าโครงการของคุณได้รับการตั้งค่าอย่างถูกต้อง ซึ่งรวมถึงการเพิ่มไลบรารี Aspose.Slides ลงในโครงการของคุณ คุณสามารถทำได้โดยดาวน์โหลดไลบรารีจาก [Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/) และเพิ่มลงในเส้นทางการสร้างของคุณ
## ขั้นตอนที่ 2: เริ่มต้นกฎการสำรองแบบอักษร
คุณต้องสร้างอินสแตนซ์ของ `IFontFallBackRulesCollection` และเพิ่มกฎเกณฑ์ให้กับคลาส กฎเกณฑ์เหล่านี้จะกำหนดฟอนต์สำรองสำหรับช่วง Unicode เฉพาะ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ใหม่ของคอลเลกชันกฎ
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// สร้างกฎจำนวนหนึ่ง
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## ขั้นตอนที่ 3: แก้ไขกฎสำรอง
ในขั้นตอนนี้เราจะปรับเปลี่ยนกฎสำรองโดยการลบแบบอักษรสำรองที่มีอยู่และอัปเดตกฎสำหรับช่วง Unicode เฉพาะ
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // กำลังพยายามลบแบบอักษร FallBack "Tahoma" จากกฎที่โหลด
    fallBackRule.remove("Tahoma");
    // อัปเดตกฎสำหรับช่วงที่ระบุ
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
// ลบกฎที่มีอยู่ทั้งหมดออกจากรายการ
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## ขั้นตอนที่ 4: โหลดงานนำเสนอ
โหลดงานนำเสนอ PowerPoint ที่คุณต้องการแก้ไข
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## ขั้นตอนที่ 5: กำหนดกฎสำรองให้กับการนำเสนอ
กำหนดกฎการสำรองข้อมูลที่เตรียมไว้ให้กับตัวจัดการแบบอักษรของการนำเสนอ
```java
try {
    // การกำหนดรายการกฎเกณฑ์ที่เตรียมไว้สำหรับการใช้งาน
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // การเรนเดอร์ภาพขนาดย่อโดยใช้คอลเลกชันกฎที่เริ่มต้นและบันทึกลงใน PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## ขั้นตอนที่ 6: บันทึกและทดสอบ
สุดท้าย ให้บันทึกงานของคุณและทดสอบการใช้งานเพื่อให้แน่ใจว่าทุกอย่างทำงานได้ตามที่คาดหวัง หากคุณพบปัญหาใดๆ ให้ตรวจสอบการตั้งค่าของคุณอีกครั้งและให้แน่ใจว่าได้เพิ่มการอ้างอิงทั้งหมดอย่างถูกต้อง
## บทสรุป
หากทำตามคำแนะนำนี้ คุณจะสามารถแสดงข้อความด้วยแบบอักษรสำรองในงานนำเสนอ PowerPoint ของคุณได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Slides สำหรับ Java กระบวนการนี้จะช่วยให้มั่นใจว่างานนำเสนอของคุณมีการจัดรูปแบบที่สม่ำเสมอ แม้ว่าแบบอักษรหลักจะไม่พร้อมใช้งานก็ตาม ขอให้สนุกกับการเขียนโค้ด!
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็นไลบรารีที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และเรนเดอร์งานนำเสนอ PowerPoint ในแอปพลิเคชัน Java ได้
### ฉันจะเพิ่ม Aspose.Slides ลงในโปรเจ็กต์ของฉันได้อย่างไร
คุณสามารถดาวน์โหลดห้องสมุดได้จาก [หน้าดาวน์โหลด Aspose.Slides](https://releases.aspose.com/slides/java/) และเพิ่มลงในเส้นทางการสร้างโครงการของคุณ
### ฟอนต์ Fallback คืออะไร?
แบบอักษรสำรองคือแบบอักษรทางเลือกที่ใช้เมื่อแบบอักษรที่ระบุไม่สามารถใช้งานได้ หรือไม่รองรับอักขระบางตัว
### ฉันสามารถใช้กฎสำรองหลายรายการได้หรือไม่
ใช่ คุณสามารถเพิ่มกฎการสำรองข้อมูลหลายรายการเพื่อจัดการช่วง Unicode และแบบอักษรที่แตกต่างกันได้
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides ได้จากที่ไหน
คุณสามารถรับการสนับสนุนได้จาก [ฟอรั่มสนับสนุน Aspose.Slides](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}