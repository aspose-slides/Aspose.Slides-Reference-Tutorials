---
"description": "เรียนรู้วิธีการแยกวิดีโอจากสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนนี้จะทำให้กระบวนการนี้ง่ายขึ้นสำหรับคุณ"
"linktitle": "ดึงวิดีโอจากสไลด์"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "วิธีการแยกวิดีโอจากสไลด์โดยใช้ Aspose.Slides สำหรับ .NET"
"url": "/th/net/audio-and-video-extraction/extract-video/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# วิธีการแยกวิดีโอจากสไลด์โดยใช้ Aspose.Slides สำหรับ .NET


Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้คุณสามารถทำงานกับงานนำเสนอ PowerPoint ในสภาพแวดล้อม .NET ได้ คุณลักษณะที่มีประโยชน์อย่างหนึ่งที่ไลบรารีนี้มอบให้คือความสามารถในการแยกวิดีโอจากสไลด์ ในคู่มือทีละขั้นตอนนี้ เราจะแสดงวิธีการแยกวิดีโอจากสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Aspose.Slides สำหรับ .NET: คุณต้องติดตั้ง Aspose.Slides สำหรับ .NET คุณสามารถรับได้จาก [เว็บไซต์](https://purchase-aspose.com/buy).

- การนำเสนอ PowerPoint: เตรียมการนำเสนอ PowerPoint (เช่น Video.pptx) ที่มีวิดีโอที่คุณต้องการแยก

## นำเข้าเนมสเปซ

คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Slides สำหรับ .NET คุณสามารถทำได้ดังนี้:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

ตอนนี้มาแบ่งกระบวนการในการแยกวิดีโอออกจากสไลด์ออกเป็นขั้นตอนต่างๆ กัน

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร

```csharp
string dataDir = "Your Document Directory";
```

แทนที่ `"Your Document Directory"` โดยมีเส้นทางไปยังไดเร็กทอรีที่มีการนำเสนอ PowerPoint ของคุณอยู่

## ขั้นตอนที่ 2: โหลดงานนำเสนอ

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

โค้ดนี้จะเริ่มต้นวัตถุการนำเสนอที่แสดงไฟล์การนำเสนอ PowerPoint ของคุณ

## ขั้นตอนที่ 3: ทำซ้ำผ่านสไลด์และรูปร่าง

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

ที่นี่ เราจะวนซ้ำผ่านแต่ละสไลด์ในงานนำเสนอ จากนั้นจึงวนซ้ำผ่านรูปร่างในสไลด์แรก (ปรับเปลี่ยนตามต้องการ)

## ขั้นตอนที่ 4: ตรวจสอบว่ารูปร่างเป็นเฟรมวิดีโอหรือไม่

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

ขั้นตอนนี้จะตรวจสอบว่ารูปร่างบนสไลด์เป็นเฟรมวิดีโอหรือไม่

## ขั้นตอนที่ 5: แยกข้อมูลวิดีโอ

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

โค้ดนี้จะดึงข้อมูลเกี่ยวกับวิดีโอ รวมทั้งประเภทเนื้อหาและข้อมูลไบนารี

## ขั้นตอนที่ 6: บันทึกวิดีโอ

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

สุดท้ายขั้นตอนนี้จะบันทึกวิดีโอไปยังไฟล์ใหม่ในไดเร็กทอรีที่ระบุ

เมื่อคุณทำตามขั้นตอนเหล่านี้เสร็จเรียบร้อยแล้ว คุณก็จะแยกวิดีโอจากสไลด์ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET

## บทสรุป

Aspose.Slides สำหรับ .NET ช่วยให้กระบวนการทำงานกับงานนำเสนอ PowerPoint ง่ายขึ้น ช่วยให้คุณสามารถทำงานต่างๆ เช่น การแยกวิดีโอออกจากสไลด์ได้อย่างง่ายดาย เพียงทำตามคำแนะนำทีละขั้นตอนนี้และใช้ไลบรารี Aspose.Slides คุณก็ปรับปรุงแอปพลิเคชัน .NET ของคุณด้วยฟีเจอร์ PowerPoint ที่ทรงพลังได้

## คำถามที่พบบ่อย (FAQs)

### Aspose.Slides สำหรับ .NET คืออะไร?
Aspose.Slides สำหรับ .NET เป็นไลบรารีที่ช่วยให้แอปพลิเคชัน .NET ทำงานกับงานนำเสนอ PowerPoint ได้ รวมถึงการสร้าง แก้ไข และแยกเนื้อหา

### ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
คุณสามารถค้นหาเอกสารประกอบได้ [ที่นี่](https://reference-aspose.com/slides/net/).

### Aspose.Slides สำหรับ .NET มีให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถรับเวอร์ชันทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-aspose.com/).

### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
คุณสามารถขอใบอนุญาตชั่วคราวได้จาก [ลิงค์นี้](https://purchase-aspose.com/temporary-license/).

### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน
คุณสามารถหาการสนับสนุนได้ที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}