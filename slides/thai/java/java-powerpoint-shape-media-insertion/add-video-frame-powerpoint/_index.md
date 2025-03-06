---
title: เพิ่มเฟรมวิดีโอใน PowerPoint
linktitle: เพิ่มเฟรมวิดีโอใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีผสานรวมเนื้อหาวิดีโอเข้ากับงานนำเสนอ PowerPoint ได้อย่างราบรื่นโดยใช้ Aspose.Slides สำหรับ Java สไลด์ของคุณพร้อมองค์ประกอบมัลติมีเดียเพื่อดึงดูดผู้ชมของคุณ
weight: 17
url: /th/java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มเฟรมวิดีโอลงในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามคำแนะนำทีละขั้นตอนเหล่านี้ คุณจะสามารถรวมเนื้อหาวิดีโอเข้ากับงานนำเสนอของคุณได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและตั้งค่าในโปรเจ็กต์ Java ของคุณ
## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Slides ในโค้ด Java ของคุณ 
```java
import com.aspose.slides.*;

import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเร็กทอรีเพื่อจัดเก็บไฟล์ PowerPoint ของคุณ
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: สร้างวัตถุการนำเสนอ
 ยกตัวอย่าง`Presentation` คลาสเพื่อแสดงไฟล์ PowerPoint
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เพิ่มเฟรมวิดีโอลงในสไลด์
รับสไลด์แรกและเพิ่มเฟรมวิดีโอลงไป
```java
ISlide sld = pres.getSlides().get_Item(0);
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
## ขั้นตอนที่ 4: ตั้งค่าโหมดการเล่นและระดับเสียง
ตั้งค่าโหมดการเล่นและระดับเสียงของเฟรมวิดีโอ
```java
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกไฟล์ PowerPoint ที่แก้ไขลงในดิสก์
```java
pres.save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มเฟรมวิดีโอลงในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เรียบร้อยแล้ว ปรับปรุงการนำเสนอของคุณโดยผสมผสานองค์ประกอบมัลติมีเดียเพื่อดึงดูดผู้ชมของคุณอย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มวิดีโอทุกรูปแบบลงในงานนำเสนอ PowerPoint ได้หรือไม่
Aspose.Slides รองรับรูปแบบวิดีโอต่าง ๆ เช่น AVI, WMV, MP4 และอื่น ๆ ตรวจสอบให้แน่ใจว่ารูปแบบเข้ากันได้กับ PowerPoint
### Aspose.Slides เข้ากันได้กับ Java เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Slides สำหรับ Java เข้ากันได้กับ JDK เวอร์ชัน 6 ขึ้นไป
### ฉันจะปรับขนาดและตำแหน่งของเฟรมวิดีโอได้อย่างไร?
 คุณสามารถปรับแต่งขนาดและพิกัดของเฟรมวิดีโอได้โดยการแก้ไขพารามิเตอร์ใน`addVideoFrame` วิธี.
### ฉันสามารถควบคุมการตั้งค่าการเล่นของวิดีโอได้หรือไม่?
ได้ คุณสามารถตั้งค่าโหมดการเล่นและระดับเสียงของเฟรมวิดีโอได้ตามความต้องการของคุณ
### ฉันจะหาการสนับสนุนและทรัพยากรเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับความช่วยเหลือ เอกสาร และการสนับสนุนจากชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
