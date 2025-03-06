---
title: บทช่วยสอนการฝังเฟรมวิดีโอด้วย Aspose.Slides สำหรับ .NET
linktitle: การเพิ่มเฟรมวิดีโอจากแหล่งที่มาของเว็บในสไลด์การนำเสนอด้วย Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีฝังเฟรมวิดีโอลงในสไลด์ PowerPoint ได้อย่างราบรื่นโดยใช้ Aspose.Slides สำหรับ .NET ปรับปรุงการนำเสนอด้วยมัลติมีเดียได้อย่างง่ายดาย
weight: 20
url: /th/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในโลกการนำเสนอแบบไดนามิก การผสมผสานองค์ประกอบมัลติมีเดียสามารถปรับปรุงการมีส่วนร่วมและส่งข้อความที่มีผลกระทบได้อย่างมาก วิธีหนึ่งที่มีประสิทธิภาพในการบรรลุเป้าหมายนี้คือการฝังเฟรมวิดีโอลงในสไลด์การนำเสนอ ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำให้สิ่งนี้สำเร็จได้อย่างราบรื่นโดยใช้ Aspose.Slides สำหรับ .NET Aspose.Slides เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม โดยให้ความสามารถที่ครอบคลุมในการสร้าง แก้ไข และปรับปรุงสไลด์
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Aspose.Slides สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/).
2. ไฟล์วิดีโอตัวอย่าง: เตรียมไฟล์วิดีโอที่คุณต้องการฝังในงานนำเสนอของคุณ คุณสามารถใช้ตัวอย่างที่ให้มากับวิดีโอชื่อ "Wildlife.mp4"
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้รวมเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชัน Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
เรามาแจกแจงขั้นตอนการฝังเฟรมวิดีโอลงในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET ให้เป็นขั้นตอนที่สามารถจัดการได้:
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรี
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// สร้างไดเร็กทอรีหากไม่มีอยู่
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
ตรวจสอบให้แน่ใจว่าได้แทนที่ "ไดเรกทอรีเอกสารของคุณ" และ "ไดเรกทอรีสื่อของคุณ" ด้วยเส้นทางที่เหมาะสมในโครงการของคุณ
## ขั้นตอนที่ 2: สร้างวัตถุการนำเสนอ
```csharp
using (Presentation pres = new Presentation())
{
    // รับสไลด์แรก
    ISlide sld = pres.Slides[0];
```
เริ่มต้นการนำเสนอใหม่และเข้าถึงสไลด์แรกเพื่อฝังเฟรมวิดีโอ
## ขั้นตอนที่ 3: ฝังวิดีโอในการนำเสนอ
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
 ใช้`AddVideo` วิธีการฝังวิดีโอลงในการนำเสนอ โดยระบุพาธของไฟล์และลักษณะการโหลด
## ขั้นตอนที่ 4: เพิ่มเฟรมวิดีโอ
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
สร้างเฟรมวิดีโอบนสไลด์ โดยกำหนดตำแหน่งและขนาดของสไลด์
## ขั้นตอนที่ 5: กำหนดการตั้งค่าวิดีโอ
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
เชื่อมโยงเฟรมวิดีโอกับวิดีโอที่ฝังไว้ ตั้งค่าโหมดการเล่น และปรับระดับเสียงตามความต้องการของคุณ
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
บันทึกงานนำเสนอที่แก้ไขด้วยเฟรมวิดีโอแบบฝัง
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีฝังเฟรมวิดีโอลงในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว ฟีเจอร์นี้เปิดโอกาสที่น่าตื่นเต้นสำหรับการสร้างงานนำเสนอแบบไดนามิกและน่าดึงดูดซึ่งดึงดูดผู้ชมของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถฝังวิดีโอในรูปแบบต่าง ๆ โดยใช้ Aspose.Slides ได้หรือไม่
ใช่ Aspose.Slides รองรับรูปแบบวิดีโอที่หลากหลาย ทำให้มั่นใจได้ถึงความยืดหยุ่นในการนำเสนอของคุณ
### ฉันจะควบคุมการตั้งค่าการเล่นวิดีโอที่ฝังไว้ได้อย่างไร?
 ปรับ`PlayMode` และ`Volume` คุณสมบัติของเฟรมวิดีโอเพื่อปรับแต่งพฤติกรรมการเล่น
### Aspose.Slides เข้ากันได้กับ .NET เวอร์ชันล่าสุดหรือไม่
Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อรักษาความเข้ากันได้กับเฟรมเวิร์ก .NET ล่าสุด
### ฉันสามารถฝังวิดีโอหลายรายการในสไลด์เดียวโดยใช้ Aspose.Slides ได้หรือไม่
ใช่ คุณสามารถฝังวิดีโอได้หลายรายการโดยเพิ่มเฟรมวิดีโอเพิ่มเติมลงในสไลด์
### ฉันจะรับการสนับสนุนสำหรับคำค้นหาที่เกี่ยวข้องกับ Aspose.Slides ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการอภิปรายของชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
