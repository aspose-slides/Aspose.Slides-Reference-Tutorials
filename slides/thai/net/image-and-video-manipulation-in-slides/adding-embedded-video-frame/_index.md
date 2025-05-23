---
"description": "ปรับปรุงการนำเสนอของคุณด้วยวิดีโอที่ฝังไว้โดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น"
"linktitle": "Aspose.Slides - การเพิ่มวิดีโอที่ฝังไว้ในงานนำเสนอ .NET"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "Aspose.Slides - การเพิ่มวิดีโอที่ฝังไว้ในงานนำเสนอ .NET"
"url": "/th/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - การเพิ่มวิดีโอที่ฝังไว้ในงานนำเสนอ .NET

## การแนะนำ
ในโลกแห่งการนำเสนอที่เปลี่ยนแปลงตลอดเวลา การผสานรวมองค์ประกอบมัลติมีเดียเข้าด้วยกันสามารถช่วยเพิ่มการมีส่วนร่วมได้อย่างมาก Aspose.Slides สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับการรวมเฟรมวิดีโอที่ฝังไว้ในสไลด์การนำเสนอของคุณ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการ โดยแบ่งขั้นตอนต่างๆ ออกเป็นส่วนๆ เพื่อให้แน่ใจว่าจะได้รับประสบการณ์ที่ราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มเรียนรู้บทช่วยสอนนี้ ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- Aspose.Slides สำหรับไลบรารี .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก [หน้าวางจำหน่าย](https://releases-aspose.com/slides/net/).
- เนื้อหาสื่อ: มีไฟล์วิดีโอ (เช่น "Wildlife.mp4") ที่คุณต้องการฝังลงในงานนำเสนอของคุณ
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโครงการ .NET ของคุณ:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรี
ตรวจสอบให้แน่ใจว่าโครงการของคุณมีไดเร็กทอรีที่จำเป็นสำหรับไฟล์เอกสารและสื่อ:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## ขั้นตอนที่ 2: สร้างตัวอย่างคลาสการนำเสนอ
สร้างอินสแตนซ์ของคลาสการนำเสนอเพื่อแสดงไฟล์ PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // รับสไลด์แรก
    ISlide sld = pres.Slides[0];
```
## ขั้นตอนที่ 3: ฝังวิดีโอภายในงานนำเสนอ
ใช้โค้ดต่อไปนี้เพื่อฝังวิดีโอไว้ในงานนำเสนอ:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## ขั้นตอนที่ 4: เพิ่มเฟรมวิดีโอ
ตอนนี้เพิ่มเฟรมวิดีโอลงในสไลด์:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## ขั้นตอนที่ 5: ตั้งค่าคุณสมบัติวิดีโอ
ตั้งค่าวิดีโอให้เป็นเฟรมวิดีโอและกำหนดค่าโหมดการเล่นและระดับเสียง:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้ายให้บันทึกไฟล์ PPTX ลงในดิสก์:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
ทำซ้ำขั้นตอนเหล่านี้สำหรับแต่ละวิดีโอที่คุณต้องการฝังลงในงานนำเสนอของคุณ
## บทสรุป
ขอแสดงความยินดี! คุณได้เพิ่มเฟรมวิดีโอที่ฝังไว้ในงานนำเสนอของคุณสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET ฟีเจอร์ไดนามิกนี้สามารถยกระดับงานนำเสนอของคุณไปสู่ระดับใหม่ โดยดึงดูดผู้ฟังด้วยองค์ประกอบมัลติมีเดียที่ผสานรวมเข้ากับสไลด์ของคุณอย่างราบรื่น
## คำถามที่พบบ่อย
### ฉันสามารถฝังวิดีโอลงในสไลด์ใดๆ ของการนำเสนอได้หรือไม่
ใช่ คุณสามารถเลือกสไลด์ใดๆ ได้โดยการแก้ไขดัชนีใน `pres-Slides[index]`.
### รองรับรูปแบบวิดีโออะไรบ้าง?
Aspose.Slides รองรับรูปแบบวิดีโอหลากหลาย รวมถึง MP4, AVI และ WMV
### ฉันสามารถปรับแต่งขนาดและตำแหน่งของเฟรมวิดีโอได้หรือไม่
แน่นอนครับ ปรับค่าพารามิเตอร์ใน `AddVideoFrame(x, y, width, height, video)` ตามความจำเป็น.
### จำนวนวิดีโอที่สามารถฝังได้มีจำกัดหรือไม่
โดยทั่วไปจำนวนวิดีโอที่ฝังจะถูกจำกัดตามความจุของซอฟต์แวร์การนำเสนอของคุณ
### ฉันจะขอความช่วยเหลือเพิ่มเติมหรือแบ่งปันประสบการณ์ของฉันได้อย่างไร
เยี่ยมชม [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการหารือของชุมชน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}