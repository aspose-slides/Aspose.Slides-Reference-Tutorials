---
"description": "เรียนรู้วิธีการผสานรวม OLE Object Frames เข้ากับงานนำเสนอ PowerPoint ได้อย่างราบรื่นโดยใช้ Aspose.Slides สำหรับ Java"
"linktitle": "เพิ่ม OLE Object Frame ใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่ม OLE Object Frame ใน PowerPoint"
"url": "/th/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่ม OLE Object Frame ใน PowerPoint

## การแนะนำ
การเพิ่ม OLE (Object Linking and Embedding) Object Frame ในงานนำเสนอ PowerPoint จะช่วยปรับปรุงความสวยงามและการใช้งานของสไลด์ของคุณได้อย่างมาก ด้วย Aspose.Slides สำหรับ Java กระบวนการนี้จะกระชับและมีประสิทธิภาพมากขึ้น ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนต่างๆ ที่จำเป็นในการผสาน OLE Object Frame เข้ากับงานนำเสนอ PowerPoint ของคุณอย่างราบรื่น
### ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) ในระบบของคุณแล้ว
2. Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จากเว็บไซต์ [ที่นี่](https://releases-aspose.com/slides/java/).
3. ความเข้าใจพื้นฐานในการเขียนโปรแกรม Java: ทำความคุ้นเคยกับแนวคิดและรูปแบบการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.Slides สำหรับ Java คุณสามารถทำได้ดังนี้:
```java
import com.aspose.slides.*;

import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อมของคุณ
ตรวจสอบให้แน่ใจว่าโครงการของคุณได้รับการกำหนดค่าอย่างถูกต้องและไลบรารี Aspose.Slides ถูกรวมอยู่ในคลาสพาธของคุณ
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
สร้างวัตถุการนำเสนอเพื่อแสดงไฟล์ PowerPoint ที่คุณกำลังทำงานด้วย:
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดง PPTX
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์และโหลดวัตถุ
เข้าถึงสไลด์ที่คุณต้องการเพิ่ม OLE Object Frame และโหลดไฟล์อ็อบเจ็กต์:
```java
ISlide sld = pres.getSlides().get_Item(0);
// โหลดไฟล์เพื่อสตรีม
FileInputStream fs = new FileInputStream(dataDir + "book1.xlsx");
ByteArrayOutputStream mstream = new ByteArrayOutputStream();
byte[] buf = new byte[4096];
while (true) {
    int bytesRead = fs.read(buf, 0, buf.length);
    if (bytesRead <= 0)
        break;
    mstream.write(buf, 0, bytesRead);
}
```
## ขั้นตอนที่ 4: สร้างวัตถุข้อมูลฝังตัว
สร้างวัตถุข้อมูลสำหรับการฝังไฟล์:
```java
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.toByteArray(), "xlsx");
```
## ขั้นตอนที่ 5: เพิ่มเฟรมวัตถุ OLE
เพิ่มรูปร่าง OLE Object Frame ลงในสไลด์:
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไขแล้วลงในดิสก์:
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการเพิ่ม OLE Object Frame ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว ฟีเจอร์อันทรงพลังนี้ช่วยให้คุณฝังวัตถุประเภทต่างๆ ได้ ช่วยเพิ่มการโต้ตอบและความสวยงามให้กับสไลด์ของคุณ

## คำถามที่พบบ่อย
### ฉันสามารถฝังวัตถุอื่นนอกเหนือจากไฟล์ Excel โดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ใช่ คุณสามารถฝังวัตถุประเภทต่างๆ ได้ รวมถึงเอกสาร Word ไฟล์ PDF และอื่นๆ อีกมากมาย
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ ได้หรือไม่
Aspose.Slides มีความเข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ มากมาย ช่วยให้บูรณาการได้อย่างราบรื่น
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของ OLE Object Frame ได้หรือไม่
แน่นอน! Aspose.Slides นำเสนอตัวเลือกมากมายในการปรับแต่งลักษณะที่ปรากฏและพฤติกรรมของ OLE Object Frames
### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides สำหรับ Java หรือไม่
ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-aspose.com/).
### ฉันสามารถค้นหาการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถขอความช่วยเหลือและการสนับสนุนจากฟอรัม Aspose.Slides ได้ [ที่นี่](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}