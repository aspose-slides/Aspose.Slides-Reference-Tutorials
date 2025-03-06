---
title: เพิ่มเฟรมวิดีโอจากแหล่งที่มาของเว็บใน PowerPoint
linktitle: เพิ่มเฟรมวิดีโอจากแหล่งที่มาของเว็บใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับปรุงงานนำเสนอ PowerPoint ของคุณโดยการเพิ่มเฟรมวิดีโอจากแหล่งที่มาของเว็บโดยใช้ Aspose.Slides สำหรับ Java
weight: 18
url: /th/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะได้เรียนรู้วิธีเพิ่มเฟรมวิดีโอจากแหล่งที่มาของเว็บ เช่น YouTube ลงในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามคำแนะนำทีละขั้นตอนเหล่านี้ คุณจะสามารถปรับปรุงการนำเสนอของคุณโดยผสมผสานองค์ประกอบมัลติมีเดียที่น่าสนใจ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง JDK (Java Development Kit) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและเพิ่มลงในโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- การเชื่อมต่ออินเทอร์เน็ตที่ใช้งานได้เพื่อเข้าถึงแหล่งที่มาของเว็บ (เช่น YouTube)

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## ขั้นตอนที่ 1: สร้างวัตถุการนำเสนอ PowerPoint
เริ่มต้นวัตถุการนำเสนอซึ่งแสดงถึงการนำเสนอ PowerPoint:
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 2: เพิ่มเฟรมวิดีโอ
ตอนนี้ เรามาเพิ่มเฟรมวิดีโอในการนำเสนอกันดีกว่า เฟรมนี้จะมีวิดีโอจากแหล่งที่มาของเว็บ เราจะใช้วิธี addVideoFrame:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
แทนที่ "VIDEO_ID" ด้วยรหัสของวิดีโอ YouTube ที่คุณต้องการฝัง
## ขั้นตอนที่ 3: ตั้งค่าโหมดการเล่นวิดีโอ
ตั้งค่าโหมดการเล่นสำหรับเฟรมวิดีโอ ในตัวอย่างนี้ เราจะตั้งค่าเป็นอัตโนมัติ:
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## ขั้นตอนที่ 4: โหลดรูปขนาดย่อ
เพื่อเพิ่มความน่าดึงดูดทางสายตา เราจะโหลดภาพขนาดย่อของวิดีโอ ขั้นตอนนี้เกี่ยวข้องกับการดึงภาพขนาดย่อจากแหล่งที่มาของเว็บ:
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้ว:
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
แทนที่ "YOUR_DIRECTORY" ด้วยไดเร็กทอรีที่คุณต้องการบันทึกงานนำเสนอ

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มเฟรมวิดีโอจากแหล่งที่มาของเว็บใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เรียบร้อยแล้ว การรวมองค์ประกอบมัลติมีเดีย เช่น วิดีโอ สามารถเพิ่มผลกระทบและการมีส่วนร่วมของงานนำเสนอของคุณได้อย่างมาก
## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มวิดีโอจากแหล่งอื่นที่ไม่ใช่ YouTube ได้หรือไม่
ได้ คุณสามารถเพิ่มวิดีโอจากแหล่งที่มาของเว็บต่างๆ ได้ ตราบใดที่แหล่งที่มาเหล่านั้นมีลิงก์แบบฝังได้
### ฉันจำเป็นต้องเชื่อมต่ออินเทอร์เน็ตเพื่อเล่นวิดีโอแบบฝังหรือไม่?
ใช่ จำเป็นต้องมีการเชื่อมต่ออินเทอร์เน็ตเพื่อสตรีมวิดีโอจากแหล่งที่มาของเว็บ
### ฉันสามารถปรับแต่งรูปลักษณ์ของเฟรมวิดีโอได้หรือไม่?
อย่างแน่นอน! Aspose.Slides มีตัวเลือกมากมายสำหรับปรับแต่งรูปลักษณ์และลักษณะการทำงานของเฟรมวิดีโอ
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides รองรับ PowerPoint เวอร์ชันต่างๆ มากมาย ทำให้มั่นใจได้ถึงความเข้ากันได้บนแพลตฟอร์มต่างๆ
### ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
 ท่านสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับความช่วยเหลือ เอกสาร และการสนับสนุนจากชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
