---
title: Aspose.Slides - การเพิ่มวิดีโอแบบฝังในการนำเสนอ .NET
linktitle: Aspose.Slides - การเพิ่มวิดีโอแบบฝังในการนำเสนอ .NET
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: ปรับปรุงการนำเสนอของคุณด้วยวิดีโอแบบฝังโดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 19
url: /th/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - การเพิ่มวิดีโอแบบฝังในการนำเสนอ .NET

## การแนะนำ
ในโลกการนำเสนอแบบไดนามิก การบูรณาการองค์ประกอบมัลติมีเดียสามารถช่วยเพิ่มการมีส่วนร่วมได้อย่างมาก Aspose.Slides สำหรับ .NET มอบโซลูชั่นอันทรงพลังสำหรับการรวมเฟรมวิดีโอที่ฝังไว้ในสไลด์การนำเสนอของคุณ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการ โดยแจกแจงแต่ละขั้นตอนเพื่อให้แน่ใจว่าได้รับประสบการณ์ที่ราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
-  Aspose.Slides สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[หน้าปล่อย](https://releases.aspose.com/slides/net/).
- เนื้อหาสื่อ: มีไฟล์วิดีโอ (เช่น "Wildlife.mp4") ที่คุณต้องการฝังในงานนำเสนอของคุณ
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นในโครงการ .NET ของคุณ:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรี
ตรวจสอบให้แน่ใจว่าโปรเจ็กต์ของคุณมีไดเร็กทอรีที่จำเป็นสำหรับไฟล์เอกสารและสื่อ:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// สร้างไดเร็กทอรีหากไม่มีอยู่
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของชั้นเรียนการนำเสนอ
สร้างอินสแตนซ์ของคลาสการนำเสนอเพื่อแสดงไฟล์ PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // รับสไลด์แรก
    ISlide sld = pres.Slides[0];
```
## ขั้นตอนที่ 3: ฝังวิดีโอภายในการนำเสนอ
ใช้รหัสต่อไปนี้เพื่อฝังวิดีโอภายในงานนำเสนอ:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## ขั้นตอนที่ 4: เพิ่มเฟรมวิดีโอ
ตอนนี้ เพิ่มเฟรมวิดีโอลงในสไลด์:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## ขั้นตอนที่ 5: ตั้งค่าคุณสมบัติวิดีโอ
ตั้งค่าวิดีโอเป็นเฟรมวิดีโอและกำหนดค่าโหมดการเล่นและระดับเสียง:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกไฟล์ PPTX ลงในดิสก์:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
ทำซ้ำขั้นตอนเหล่านี้สำหรับวิดีโอแต่ละรายการที่คุณต้องการฝังในงานนำเสนอของคุณ
## บทสรุป
ยินดีด้วย! คุณได้เพิ่มเฟรมวิดีโอแบบฝังลงในงานนำเสนอของคุณสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET คุณลักษณะแบบไดนามิกนี้สามารถยกระดับการนำเสนอของคุณไปสู่อีกระดับหนึ่ง ดึงดูดผู้ชมด้วยองค์ประกอบมัลติมีเดียที่ผสานรวมเข้ากับสไลด์ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ฉันสามารถฝังวิดีโอลงในสไลด์ใดก็ได้ของงานนำเสนอได้หรือไม่
 ใช่ คุณสามารถเลือกสไลด์ใดก็ได้โดยแก้ไขดัชนี`pres.Slides[index]`.
### รองรับรูปแบบวิดีโอใดบ้าง?
Aspose.Slides รองรับรูปแบบวิดีโอที่หลากหลาย รวมถึง MP4, AVI และ WMV
### ฉันสามารถกำหนดขนาดและตำแหน่งของเฟรมวิดีโอได้หรือไม่?
 อย่างแน่นอน! ปรับพารามิเตอร์ใน`AddVideoFrame(x, y, width, height, video)` ตามความจำเป็น.
### มีการจำกัดจำนวนวิดีโอที่ฉันสามารถฝังได้หรือไม่?
โดยทั่วไปจำนวนวิดีโอที่ฝังไว้จะถูกจำกัดตามความสามารถของซอฟต์แวร์การนำเสนอของคุณ
### ฉันจะขอความช่วยเหลือเพิ่มเติมหรือแบ่งปันประสบการณ์ของฉันได้อย่างไร?
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการอภิปรายของชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
