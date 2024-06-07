---
title: เพิ่ม OLE Object Frame ใน PowerPoint
linktitle: เพิ่ม OLE Object Frame ใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีผสานรวม OLE Object Frames เข้ากับงานนำเสนอ PowerPoint ได้อย่างราบรื่นโดยใช้ Aspose.Slides สำหรับ Java
type: docs
weight: 13
url: /th/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/
---
## การแนะนำ
การเพิ่มกรอบวัตถุ OLE (การเชื่อมโยงและการฝังวัตถุ) ในงานนำเสนอ PowerPoint สามารถปรับปรุงรูปลักษณ์และฟังก์ชันการทำงานของสไลด์ของคุณได้อย่างมาก ด้วย Aspose.Slides สำหรับ Java กระบวนการนี้จะมีความคล่องตัวและมีประสิทธิภาพ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนที่จำเป็นในการรวม OLE Object Frames เข้ากับงานนำเสนอ PowerPoint ของคุณได้อย่างราบรื่น
### ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2. Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จากเว็บไซต์[ที่นี่](https://releases.aspose.com/slides/java/).
3. ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java: ทำความคุ้นเคยกับแนวคิดและไวยากรณ์การเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.Slides สำหรับ Java ต่อไปนี้คือวิธีที่คุณสามารถทำได้:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อมของคุณ
ตรวจสอบให้แน่ใจว่าโปรเจ็กต์ของคุณได้รับการกำหนดค่าอย่างถูกต้องและไลบรารี Aspose.Slides รวมอยู่ใน classpath ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
สร้างวัตถุการนำเสนอเพื่อแสดงไฟล์ PowerPoint ที่คุณใช้งานอยู่:
```java
String dataDir = "Your Document Directory";
String outPath = RunExamples.getOutPath();
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึง PPTX
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
## ขั้นตอนที่ 4: สร้างออบเจ็กต์ข้อมูลที่ฝังตัว
สร้างวัตถุข้อมูลสำหรับการฝังไฟล์:
```java
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.toByteArray(), "xlsx");
```
## ขั้นตอนที่ 5: เพิ่ม OLE Object Frame
เพิ่มรูปร่าง OLE Object Frame ลงในสไลด์:
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วลงในดิสก์:
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่ม OLE Object Frame ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เรียบร้อยแล้ว ฟีเจอร์อันทรงพลังนี้ช่วยให้คุณสามารถฝังวัตถุประเภทต่างๆ ได้ ปรับปรุงการโต้ตอบและรูปลักษณ์ที่สวยงามของสไลด์ของคุณ

## คำถามที่พบบ่อย
### ฉันสามารถฝังวัตถุอื่นที่ไม่ใช่ไฟล์ Excel โดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ได้ คุณสามารถฝังออบเจ็กต์ได้หลายประเภท รวมถึงเอกสาร Word, ไฟล์ PDF และอื่นๆ อีกมากมาย
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ หรือไม่
Aspose.Slides ให้ความเข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ มากมาย รับประกันการผสานรวมที่ราบรื่น
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของ OLE Object Frame ได้หรือไม่
อย่างแน่นอน! Aspose.Slides มีตัวเลือกมากมายสำหรับการปรับแต่งรูปลักษณ์และการทำงานของ OLE Object Frames
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถขอการสนับสนุนและความช่วยเหลือได้จากฟอรัม Aspose.Slides[ที่นี่](https://forum.aspose.com/c/slides/11).