---
title: ตัวเลือกการแสดงผลใน PowerPoint
linktitle: ตัวเลือกการแสดงผลใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีจัดการตัวเลือกการเรนเดอร์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับแต่งสไลด์ของคุณเพื่อให้ภาพดูโดดเด่นที่สุด
type: docs
weight: 13
url: /th/java/java-powerpoint-rendering-techniques/render-options-powerpoint/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการใช้ประโยชน์จาก Aspose.Slides สำหรับ Java เพื่อจัดการตัวเลือกการเรนเดอร์ในงานนำเสนอ PowerPoint ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คู่มือนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ Java คุณสามารถรับได้จาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มต้นใช้งาน Aspose.Slides ในโปรเจ็กต์ Java ของคุณ
```java
import com.aspose.slides.IRenderingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.RenderingOptions;

import javax.imageio.ImageIO;
import java.io.File;
import java.io.IOException;
```
## ขั้นตอนที่ 1: โหลดงานนำเสนอ
เริ่มต้นด้วยการโหลดงานนำเสนอ PowerPoint ที่คุณต้องการใช้งาน
```java
String presPath = "path/to/your/presentation.pptx";
Presentation pres = new Presentation(presPath);
```
## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการแสดงผล
ตอนนี้ มากำหนดค่าตัวเลือกการเรนเดอร์ตามความต้องการของคุณกัน
```java
IRenderingOptions renderingOpts = new RenderingOptions();
renderingOpts.getNotesCommentsLayouting().setNotesPosition(NotesPositions.BottomTruncated);
```
## ขั้นตอนที่ 3: เรนเดอร์สไลด์
จากนั้น เรนเดอร์สไลด์โดยใช้ตัวเลือกการเรนเดอร์ที่ระบุ
```java
ImageIO.write(pres.getSlides().get_Item(0).getThumbnail(renderingOpts, 4 / 3f, 4 / 3f),
    "PNG", new File("path/to/save/RenderingOptions-Slide1-Original.png"));
```
## ขั้นตอนที่ 4: แก้ไขตัวเลือกการแสดงผล
คุณสามารถแก้ไขตัวเลือกการแสดงภาพได้ตามต้องการสำหรับสไลด์ต่างๆ
```java
renderingOpts.getNotesCommentsLayouting().setNotesPosition(NotesPositions.None);
renderingOpts.setDefaultRegularFont("Arial Black");
```
## ขั้นตอนที่ 5: แสดงผลอีกครั้ง
เรนเดอร์สไลด์อีกครั้งด้วยตัวเลือกการเรนเดอร์ที่อัปเดต
```java
ImageIO.write(pres.getSlides().get_Item(0).getThumbnail(renderingOpts, 4 / 3f, 4 / 3f),
    "PNG", new File("path/to/save/RenderingOptions-Slide1-ArialBlackDefault.png"));
```
## ขั้นตอนที่ 6: กำจัดการนำเสนอ
สุดท้ายนี้ อย่าลืมกำจัดออบเจ็กต์การนำเสนอเพื่อเผยแพร่ทรัพยากร
```java
if (pres != null) pres.dispose();
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงวิธีจัดการตัวเลือกการเรนเดอร์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถปรับแต่งกระบวนการเรนเดอร์ได้ตามความต้องการเฉพาะของคุณ ซึ่งจะช่วยปรับปรุงลักษณะที่ปรากฏของสไลด์ของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถแสดงสไลด์เป็นรูปแบบรูปภาพอื่นนอกเหนือจาก PNG ได้หรือไม่
ใช่ Aspose.Slides รองรับการเรนเดอร์สไลด์เป็นรูปแบบรูปภาพต่างๆ เช่น JPEG, BMP, GIF และ TIFF
### เป็นไปได้ไหมที่จะแสดงสไลด์เฉพาะแทนการนำเสนอทั้งหมด
อย่างแน่นอน! คุณสามารถระบุดัชนีสไลด์หรือช่วงเพื่อแสดงเฉพาะสไลด์ที่ต้องการได้
### Aspose.Slides มีตัวเลือกในการจัดการภาพเคลื่อนไหวระหว่างการเรนเดอร์หรือไม่
ได้ คุณสามารถควบคุมวิธีจัดการภาพเคลื่อนไหวในระหว่างกระบวนการเรนเดอร์ได้ รวมถึงว่าจะรวมหรือยกเว้นภาพเคลื่อนไหวเหล่านั้นด้วย
### ฉันสามารถแสดงสไลด์ด้วยสีพื้นหลังหรือการไล่ระดับสีแบบกำหนดเองได้หรือไม่
แน่นอน! Aspose.Slides ช่วยให้คุณสามารถตั้งค่าพื้นหลังที่กำหนดเองสำหรับสไลด์ก่อนที่จะเรนเดอร์
### มีวิธีแสดงสไลด์โดยตรงไปยังเอกสาร PDF หรือไม่
ใช่ Aspose.Slides มีฟังก์ชันในการแปลงงานนำเสนอ PowerPoint เป็นไฟล์ PDF ที่มีความเที่ยงตรงสูงได้โดยตรง