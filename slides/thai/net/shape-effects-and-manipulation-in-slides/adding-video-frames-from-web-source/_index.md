---
"description": "เรียนรู้วิธีฝังเฟรมวิดีโอลงในสไลด์ PowerPoint ได้อย่างราบรื่นโดยใช้ Aspose.Slides สำหรับ .NET ปรับปรุงการนำเสนอด้วยมัลติมีเดียได้อย่างง่ายดาย"
"linktitle": "การเพิ่มเฟรมวิดีโอจากแหล่งเว็บลงในสไลด์การนำเสนอด้วย Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "บทช่วยสอนการฝังเฟรมวิดีโอด้วย Aspose.Slides สำหรับ .NET"
"url": "/th/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# บทช่วยสอนการฝังเฟรมวิดีโอด้วย Aspose.Slides สำหรับ .NET

## การแนะนำ
ในโลกแห่งการนำเสนอที่เปลี่ยนแปลงตลอดเวลา การรวมเอาองค์ประกอบมัลติมีเดียเข้าด้วยกันสามารถช่วยเพิ่มการมีส่วนร่วมและนำเสนอข้อความที่ทรงพลังได้อย่างมาก วิธีที่มีประสิทธิภาพวิธีหนึ่งในการบรรลุผลดังกล่าวคือการฝังเฟรมวิดีโอลงในสไลด์การนำเสนอ ในบทช่วยสอนนี้ เราจะมาสำรวจวิธีการบรรลุผลดังกล่าวอย่างราบรื่นโดยใช้ Aspose.Slides สำหรับ .NET Aspose.Slides เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้ผู้พัฒนาสามารถจัดการการนำเสนอ PowerPoint ได้ด้วยโปรแกรม ซึ่งให้ความสามารถมากมายสำหรับการสร้าง แก้ไข และปรับแต่งสไลด์
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Aspose.Slides สำหรับไลบรารี .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก [เอกสาร Aspose.Slides สำหรับ .NET](https://reference-aspose.com/slides/net/).
2. ไฟล์วิดีโอตัวอย่าง: เตรียมไฟล์วิดีโอที่คุณต้องการฝังในงานนำเสนอของคุณ คุณสามารถใช้ตัวอย่างที่ให้มากับวิดีโอชื่อ "Wildlife.mp4"
## นำเข้าเนมสเปซ
ในโครงการ .NET ของคุณ ให้รวมเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานของ Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
มาแบ่งกระบวนการฝังเฟรมวิดีโอลงในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET ออกเป็นขั้นตอนที่สามารถจัดการได้:
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรี
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
อย่าลืมแทนที่ "ไดเร็กทอรีเอกสารของคุณ" และ "ไดเร็กทอรีสื่อของคุณ" ด้วยเส้นทางที่เหมาะสมในโครงการของคุณ
## ขั้นตอนที่ 2: สร้างวัตถุการนำเสนอ
```csharp
using (Presentation pres = new Presentation())
{
    // รับสไลด์แรก
    ISlide sld = pres.Slides[0];
```
เริ่มการนำเสนอใหม่และเข้าถึงสไลด์แรกเพื่อฝังเฟรมวิดีโอ
## ขั้นตอนที่ 3: ฝังวิดีโอในงานนำเสนอ
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
การใช้ประโยชน์จาก `AddVideo` วิธีการฝังวิดีโอลงในงานนำเสนอ โดยระบุเส้นทางไฟล์และลักษณะการโหลด
## ขั้นตอนที่ 4: เพิ่มเฟรมวิดีโอ
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
สร้างเฟรมวิดีโอบนสไลด์โดยกำหนดตำแหน่งและขนาด
## ขั้นตอนที่ 5: กำหนดค่าการตั้งค่าวิดีโอ
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
บันทึกงานนำเสนอที่แก้ไขแล้วพร้อมเฟรมวิดีโอที่ฝังไว้
## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการฝังเฟรมวิดีโอลงในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว ฟีเจอร์นี้เปิดโอกาสให้สร้างสรรค์งานนำเสนอที่น่าดึงดูดและมีชีวิตชีวาเพื่อดึงดูดผู้ชม
## คำถามที่พบบ่อย
### ฉันสามารถฝังวิดีโอรูปแบบต่างๆ โดยใช้ Aspose.Slides ได้หรือไม่
ใช่ Aspose.Slides รองรับรูปแบบวิดีโอที่หลากหลาย ช่วยเพิ่มความยืดหยุ่นให้กับการนำเสนอของคุณ
### ฉันจะควบคุมการตั้งค่าการเล่นวิดีโอที่ฝังไว้ได้อย่างไร
ปรับแต่ง `PlayMode` และ `Volume` คุณสมบัติของเฟรมวิดีโอเพื่อปรับแต่งพฤติกรรมการเล่น
### Aspose.Slides เข้ากันได้กับ .NET เวอร์ชันล่าสุดหรือไม่
Aspose.Slides ได้รับการอัปเดตเป็นประจำเพื่อรักษาความเข้ากันได้กับกรอบงาน .NET ล่าสุด
### ฉันสามารถฝังวิดีโอหลายรายการในสไลด์เดียวโดยใช้ Aspose.Slides ได้หรือไม่
ใช่ คุณสามารถฝังวิดีโอหลายรายการได้โดยการเพิ่มเฟรมวิดีโอเพิ่มเติมลงในสไลด์
### ฉันสามารถค้นหาการสนับสนุนสำหรับแบบสอบถามที่เกี่ยวข้องกับ Aspose.Slides ได้ที่ไหน
เยี่ยมชม [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการหารือของชุมชน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}