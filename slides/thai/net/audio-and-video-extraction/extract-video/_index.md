---
title: วิธีแยกวิดีโอจากสไลด์โดยใช้ Aspose.Slides สำหรับ .NET
linktitle: แยกวิดีโอออกจากสไลด์
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีแยกวิดีโอจากสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนนี้ทำให้กระบวนการของคุณง่ายขึ้น
weight: 14
url: /th/net/audio-and-video-extraction/extract-video/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้คุณสามารถทำงานกับงานนำเสนอ PowerPoint ในสภาพแวดล้อม .NET ได้ หนึ่งในคุณสมบัติที่มีประโยชน์ที่มีให้คือความสามารถในการแยกวิดีโอจากสไลด์ ในคำแนะนำทีละขั้นตอนนี้ เราจะแสดงวิธีแยกวิดีโอจากสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Slides สำหรับ .NET: คุณต้องติดตั้ง Aspose.Slides สำหรับ .NET คุณสามารถรับได้จาก[เว็บไซต์](https://purchase.aspose.com/buy).

- งานนำเสนอ PowerPoint: เตรียมงานนำเสนอ PowerPoint (เช่น Video.pptx) ที่มีวิดีโอที่คุณต้องการแยก

## นำเข้าเนมสเปซ

คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Slides สำหรับ .NET ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

ตอนนี้ เรามาแบ่งกระบวนการแยกวิดีโอจากสไลด์ออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร

```csharp
string dataDir = "Your Document Directory";
```

 แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่มีงานนำเสนอ PowerPoint ของคุณ

## ขั้นตอนที่ 2: โหลดงานนำเสนอ

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

รหัสนี้เริ่มต้นวัตถุการนำเสนอซึ่งเป็นตัวแทนของไฟล์งานนำเสนอ PowerPoint ของคุณ

## ขั้นตอนที่ 3: วนซ้ำผ่านสไลด์และรูปร่าง

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

ที่นี่ เราวนซ้ำแต่ละสไลด์ในงานนำเสนอ จากนั้นวนซ้ำรูปร่างในสไลด์แรก (แก้ไขตามต้องการ)

## ขั้นตอนที่ 4: ตรวจสอบว่ารูปร่างเป็นกรอบวิดีโอหรือไม่

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

ขั้นตอนนี้จะตรวจสอบว่ารูปร่างบนสไลด์เป็นกรอบวิดีโอหรือไม่

## ขั้นตอนที่ 5: แยกข้อมูลวิดีโอ

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

รหัสนี้จะแยกข้อมูลเกี่ยวกับวิดีโอ รวมถึงประเภทเนื้อหาและข้อมูลไบนารี

## ขั้นตอนที่ 6: บันทึกวิดีโอ

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

สุดท้าย ขั้นตอนนี้จะบันทึกวิดีโอเป็นไฟล์ใหม่ในไดเร็กทอรีที่ระบุ

เมื่อคุณทำตามขั้นตอนเหล่านี้เสร็จแล้ว คุณจะดึงวิดีโอจากสไลด์ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET

## บทสรุป

Aspose.Slides สำหรับ .NET ทำให้กระบวนการทำงานกับงานนำเสนอ PowerPoint ง่ายขึ้น ช่วยให้คุณสามารถทำงานต่างๆ เช่น แยกวิดีโอออกจากสไลด์ได้อย่างง่ายดาย ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และใช้งานไลบรารี Aspose.Slides คุณจะปรับปรุงแอปพลิเคชัน .NET ของคุณด้วยฟีเจอร์ PowerPoint อันทรงพลังได้

## คำถามที่พบบ่อย (FAQ)

### Aspose.Slides สำหรับ .NET คืออะไร
Aspose.Slides สำหรับ .NET เป็นไลบรารีที่ช่วยให้แอปพลิเคชัน .NET สามารถทำงานร่วมกับงานนำเสนอ PowerPoint ได้ รวมถึงการสร้าง แก้ไข และแยกเนื้อหา

### ฉันจะหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณสามารถค้นหาเอกสาร[ที่นี่](https://reference.aspose.com/slides/net/).

### Aspose.Slides สำหรับ .NET มีให้ทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถรับเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
 คุณสามารถขอใบอนุญาตชั่วคราวได้จาก[ลิงค์นี้](https://purchase.aspose.com/temporary-license/).

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณสามารถค้นหาการสนับสนุนได้ที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
