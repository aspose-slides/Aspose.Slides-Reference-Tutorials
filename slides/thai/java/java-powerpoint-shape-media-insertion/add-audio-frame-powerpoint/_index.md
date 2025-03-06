---
title: เพิ่มกรอบเสียงใน PowerPoint
linktitle: เพิ่มกรอบเสียงใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มเฟรมเสียงลงในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ยกระดับการนำเสนอของคุณด้วยองค์ประกอบเสียงที่น่าสนใจได้อย่างง่ายดาย
weight: 12
url: /th/java/java-powerpoint-shape-media-insertion/add-audio-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มกรอบเสียงใน PowerPoint

## การแนะนำ
การปรับปรุงการนำเสนอด้วยองค์ประกอบเสียงสามารถยกระดับผลกระทบและการมีส่วนร่วมได้อย่างมาก ด้วย Aspose.Slides สำหรับ Java การรวมเฟรมเสียงเข้ากับงานนำเสนอ PowerPoint กลายเป็นกระบวนการที่ราบรื่น บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอนในการเพิ่มเฟรมเสียงให้กับงานนำเสนอของคุณโดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว
2.  Aspose.Slides สำหรับไลบรารี Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/).
3. ไฟล์เสียง: เตรียมไฟล์เสียง (เช่น รูปแบบ WAV) ที่คุณต้องการเพิ่มลงในงานนำเสนอของคุณ
## แพ็คเกจนำเข้า
นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการของคุณ
ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าโครงสร้างไดเร็กทอรีสำหรับโปรเจ็กต์ของคุณ ถ้าไม่เช่นนั้น ให้สร้างขึ้นมาเพื่อจัดระเบียบไฟล์ของคุณอย่างมีประสิทธิภาพ
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของชั้นเรียนการนำเสนอ
 ยกตัวอย่าง`Presentation` คลาสเพื่อแสดงการนำเสนอ PowerPoint
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: รับสไลด์และโหลดไฟล์เสียง
ดึงสไลด์แรกและโหลดไฟล์เสียงจากไดเร็กทอรีของคุณ
```java
ISlide sld = pres.getSlides().get_Item(0);
FileInputStream fstr = new FileInputStream(dataDir + "sampleaudio.wav");
```
## ขั้นตอนที่ 4: เพิ่มกรอบเสียง
เพิ่มกรอบเสียงลงในสไลด์
```java
IAudioFrame audioFrame = sld.getShapes().addAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## ขั้นตอนที่ 5: ตั้งค่าคุณสมบัติเสียง
ตั้งค่าคุณสมบัติ เช่น การเล่นข้ามสไลด์ เสียงกรอกลับ โหมดการเล่น และระดับเสียง
```java
audioFrame.setPlayAcrossSlides(true);
audioFrame.setRewindAudio(true);
audioFrame.setPlayMode(AudioPlayModePreset.Auto);
audioFrame.setVolume(AudioVolumeMode.Loud);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขด้วยกรอบเสียงที่เพิ่ม
```java
pres.save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
การรวมองค์ประกอบเสียงเข้ากับงานนำเสนอ PowerPoint ของคุณสามารถเพิ่มประสิทธิภาพและดึงดูดผู้ชมของคุณได้ ด้วย Aspose.Slides สำหรับ Java กระบวนการเพิ่มเฟรมเสียงกลายเป็นเรื่องง่าย ช่วยให้คุณสร้างงานนำเสนอแบบไดนามิกและน่าดึงดูดได้อย่างง่ายดาย

## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มไฟล์เสียงในรูปแบบต่างๆ ลงในงานนำเสนอของฉันได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java รองรับรูปแบบเสียงที่หลากหลาย รวมถึง WAV, MP3 และอื่นๆ
### สามารถปรับระยะเวลาการเล่นเสียงในสไลด์ได้หรือไม่?
อย่างแน่นอน. คุณสามารถซิงโครไนซ์การเล่นเสียงกับการเปลี่ยนสไลด์เฉพาะได้โดยใช้ Aspose.Slides สำหรับ Java
### Aspose.Slides สำหรับ Java ให้การสนับสนุนความเข้ากันได้ข้ามแพลตฟอร์มหรือไม่
ได้ คุณสามารถสร้างงานนำเสนอ PowerPoint ด้วยเฟรมเสียงแบบฝังที่เข้ากันได้กับแพลตฟอร์มต่างๆ
### ฉันสามารถปรับแต่งรูปลักษณ์ของเครื่องเล่นเสียงในงานนำเสนอได้หรือไม่
Aspose.Slides for Java นำเสนอตัวเลือกการปรับแต่งที่หลากหลาย ซึ่งช่วยให้คุณปรับแต่งรูปลักษณ์ของเครื่องเล่นเสียงให้เหมาะกับความต้องการของคุณได้
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถเข้าถึง Aspose.Slides สำหรับ Java รุ่นทดลองใช้ฟรีได้จากที่นี่[เว็บไซต์](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
