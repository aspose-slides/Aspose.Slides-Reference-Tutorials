---
"description": "เรียนรู้วิธีปรับปรุงการนำเสนอ PowerPoint ของคุณด้วยการเพิ่มเฟรมวิดีโอจากแหล่งบนเว็บโดยใช้ Aspose.Slides สำหรับ Java"
"linktitle": "เพิ่มเฟรมวิดีโอจากแหล่งเว็บใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มเฟรมวิดีโอจากแหล่งเว็บใน PowerPoint"
"url": "/th/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มเฟรมวิดีโอจากแหล่งเว็บใน PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีเพิ่มเฟรมวิดีโอจากแหล่งข้อมูลบนเว็บ เช่น YouTube ลงในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java หากปฏิบัติตามคำแนะนำทีละขั้นตอนเหล่านี้ คุณจะสามารถปรับปรุงงานนำเสนอของคุณได้โดยการรวมองค์ประกอบมัลติมีเดียที่น่าสนใจ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- JDK (Java Development Kit) ติดตั้งอยู่บนระบบของคุณ
- ดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java และเพิ่มลงในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
- การเชื่อมต่ออินเตอร์เน็ตที่ใช้งานได้เพื่อเข้าถึงแหล่งข้อมูลบนเว็บ (เช่น YouTube)

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ:
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
ตอนนี้เรามาเพิ่มเฟรมวิดีโอลงในงานนำเสนอกัน เฟรมนี้จะบรรจุวิดีโอจากแหล่งที่มาบนเว็บ เราจะใช้เมธอด addVideoFrame:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
แทนที่ "VIDEO_ID" ด้วย ID ของวิดีโอ YouTube ที่คุณต้องการฝัง
## ขั้นตอนที่ 3: ตั้งค่าโหมดการเล่นวิดีโอ
ตั้งค่าโหมดการเล่นสำหรับเฟรมวิดีโอ ในตัวอย่างนี้ เราจะตั้งค่าเป็นอัตโนมัติ:
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## ขั้นตอนที่ 4: โหลดภาพขนาดย่อ
เพื่อเพิ่มความสวยงาม เราจะโหลดภาพขนาดย่อของวิดีโอ ขั้นตอนนี้เกี่ยวข้องกับการดึงภาพขนาดย่อจากแหล่งที่มาบนเว็บ:
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
สุดท้ายให้บันทึกการนำเสนอที่แก้ไขแล้ว:
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
แทนที่ "YOUR_DIRECTORY" ด้วยไดเร็กทอรีที่คุณต้องการบันทึกการนำเสนอ

## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการเพิ่มเฟรมวิดีโอจากแหล่งข้อมูลบนเว็บใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว การรวมองค์ประกอบมัลติมีเดีย เช่น วิดีโอ สามารถเพิ่มผลกระทบและความน่าสนใจให้กับงานนำเสนอของคุณได้อย่างมาก
## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มวิดีโอจากแหล่งอื่นนอกเหนือจาก YouTube ได้หรือไม่?
ใช่ คุณสามารถเพิ่มวิดีโอจากแหล่งเว็บต่าง ๆ ได้ตราบใดที่มีลิงก์ที่ฝังได้
### ฉันจำเป็นต้องมีการเชื่อมต่ออินเทอร์เน็ตเพื่อเล่นวิดีโอที่ฝังหรือไม่
ใช่ ต้องมีการเชื่อมต่ออินเทอร์เน็ตที่ใช้งานได้เพื่อสตรีมวิดีโอจากแหล่งเว็บ
### ฉันสามารถปรับแต่งลักษณะของเฟรมวิดีโอได้หรือไม่
แน่นอน! Aspose.Slides มีตัวเลือกมากมายในการปรับแต่งลักษณะที่ปรากฏและพฤติกรรมของเฟรมวิดีโอ
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกเวอร์ชันหรือไม่
Aspose.Slides รองรับ PowerPoint เวอร์ชันต่างๆ มากมาย เพื่อให้แน่ใจว่าสามารถใช้งานร่วมกับแพลตฟอร์มต่างๆ ได้
### ฉันสามารถหาทรัพยากรและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Slides ได้จากที่ใด
คุณสามารถเยี่ยมชม [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับความช่วยเหลือ เอกสาร และการสนับสนุนจากชุมชน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}