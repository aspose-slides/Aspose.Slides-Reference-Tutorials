---
title: ระบุภาษาข้อความเริ่มต้นใน Java PowerPoint
linktitle: ระบุภาษาข้อความเริ่มต้นใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีระบุภาษาข้อความเริ่มต้นใน Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เหมาะสำหรับนักพัฒนาที่ต้องการแปลข้อความโดยทางโปรแกรม
weight: 21
url: /th/java/java-powerpoint-text-font-customization/specify-default-text-language-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในขอบเขตของการพัฒนาแอปพลิเคชัน Java การจัดการและการจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรมถือเป็นข้อกำหนดทั่วไป Aspose.Slides สำหรับ Java นำเสนอชุดฟังก์ชันที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และปรับปรุงงานนำเสนอ PowerPoint ได้อย่างราบรื่นผ่านโค้ด Java บทช่วยสอนนี้มีจุดมุ่งหมายเพื่อแนะนำคุณตลอดขั้นตอนสำคัญของการระบุภาษาข้อความเริ่มต้นในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่นการตั้งค่า IntelliJ IDEA หรือ Eclipse
-  ติดตั้ง Aspose.Slides สำหรับไลบรารี Java แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
-  เข้าถึง Aspose.Slides สำหรับเอกสาร Java ซึ่งสามารถพบได้[ที่นี่](https://reference.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ก่อนที่คุณจะเริ่มเขียนโค้ด ตรวจสอบให้แน่ใจว่าได้นำเข้าคลาส Aspose.Slides ที่จำเป็นลงในไฟล์ Java ของคุณ:
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: ตั้งค่าตัวเลือกการโหลด
ขั้นแรก กำหนดค่าตัวเลือกการโหลดสำหรับการนำเสนอ โดยระบุภาษาข้อความเริ่มต้น (`en-US` ในกรณีนี้).
```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setDefaultTextLanguage("en-US");
```
## ขั้นตอนที่ 2: โหลดงานนำเสนอ
 ยกตัวอย่าง`Presentation` วัตถุโดยใช้ตัวเลือกการโหลดที่กำหนดค่าไว้เพื่อโหลดงานนำเสนอ PowerPoint ที่มีอยู่หรือสร้างงานนำเสนอใหม่
```java
Presentation pres = new Presentation(loadOptions);
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างด้วยข้อความ
เพิ่มรูปร่างสี่เหลี่ยมผืนผ้าลงในสไลด์แรกของงานนำเสนอและตั้งค่าเนื้อหาข้อความ
```java
IAutoShape shp = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 150, 50);
shp.getTextFrame().setText("New Text");
```
## ขั้นตอนที่ 4: ตรวจสอบภาษาของส่วนข้อความ
ดึงข้อมูลและตรวจสอบการตั้งค่าภาษาของส่วนข้อความภายในรูปร่างที่เพิ่ม
```java
PortionFormat portionFormat = shp.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat();
System.out.println(portionFormat.getLanguageId());
```
## ขั้นตอนที่ 5: กำจัดวัตถุการนำเสนอ
 ตรวจสอบให้แน่ใจว่ามีการกำจัดอย่างเหมาะสม`Presentation` คัดค้านการปล่อยทรัพยากรหลังการใช้งาน
```java
finally {
    if (pres != null) pres.dispose();
}
```

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีใช้ประโยชน์จาก Aspose.Slides สำหรับ Java เพื่อระบุภาษาข้อความเริ่มต้นในงานนำเสนอ PowerPoint โดยทางโปรแกรม ความสามารถนี้มีความสำคัญอย่างยิ่งในการรับประกันการตั้งค่าภาษาที่สอดคล้องกันในองค์ประกอบข้อความในงานนำเสนอของคุณ ช่วยเพิ่มความสามารถในการอ่านและการแปลเป็นภาษาท้องถิ่น
## คำถามที่พบบ่อย
### ฉันสามารถเปลี่ยนภาษาข้อความเริ่มต้นเป็นภาษาอื่น เช่น ฝรั่งเศส หรือสเปน ได้หรือไม่
ได้ คุณสามารถระบุรหัสภาษาที่รองรับได้เมื่อตั้งค่าภาษาข้อความเริ่มต้นโดยใช้ Aspose.Slides สำหรับ Java
### Aspose.Slides สำหรับ Java เหมาะสำหรับแอปพลิเคชันระดับองค์กรหรือไม่
อย่างแน่นอน. Aspose.Slides สำหรับ Java ได้รับการออกแบบมาเพื่อความสามารถในการปรับขนาดและประสิทธิภาพ ทำให้เหมาะสำหรับสภาพแวดล้อมองค์กร
### ฉันจะหาตัวอย่างและแหล่งข้อมูลเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถสำรวจเอกสารประกอบที่ครอบคลุมและตัวอย่างเพิ่มเติมได้ใน[Aspose.Slides สำหรับหน้าเอกสารประกอบ Java](https://reference.aspose.com/slides/java/).
### Aspose.Slides สำหรับ Java รองรับการผสานรวมกับบริการคลาวด์หรือไม่
ใช่ Aspose.Slides สำหรับ Java มี API ที่รองรับการผสานรวมกับแพลตฟอร์มคลาวด์ยอดนิยม
### ฉันสามารถประเมิน Aspose.Slides สำหรับ Java ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถขอรับ Aspose.Slides สำหรับ Java รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
