---
title: เชี่ยวชาญการแยกเสียงและวิดีโอด้วย Aspose.Slides สำหรับ .NET
linktitle: การแยกเสียงและวิดีโอจากสไลด์โดยใช้ Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีแยกเสียงและวิดีโอจากสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET การสกัดมัลติมีเดียอย่างง่ายดาย
type: docs
weight: 10
url: /th/net/audio-and-video-extraction/audio-and-video-extraction/
---

## การแนะนำ

ในยุคดิจิทัล การนำเสนอมัลติมีเดียกลายเป็นส่วนสำคัญของการสื่อสาร การศึกษา และความบันเทิง สไลด์ PowerPoint มักใช้ในการถ่ายทอดข้อมูล และมักจะมีองค์ประกอบที่จำเป็น เช่น เสียงและวิดีโอ การแยกองค์ประกอบเหล่านี้อาจมีความสำคัญด้วยเหตุผลหลายประการ ตั้งแต่การเก็บถาวรงานนำเสนอไปจนถึงการนำเนื้อหาไปใช้ใหม่

ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีการแยกเสียงและวิดีโอจากสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนา .NET สามารถทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม ทำให้งานต่างๆ เช่น การแยกมัลติมีเดีย เข้าถึงได้ง่ายกว่าที่เคย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกรายละเอียดของการแยกเสียงและวิดีโอจากสไลด์ PowerPoint มีข้อกำหนดเบื้องต้นบางประการที่คุณต้องมี:

1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนเครื่องของคุณสำหรับการพัฒนา .NET

2.  Aspose.Slides สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ .NET คุณสามารถค้นหาห้องสมุดและเอกสารประกอบได้ที่[Aspose.Slides สำหรับเว็บไซต์ .NET](https://releases.aspose.com/slides/net/).

3. งานนำเสนอ PowerPoint: เตรียมงานนำเสนอ PowerPoint ที่มีองค์ประกอบเสียงและวิดีโอสำหรับฝึกการแยกส่วน

ตอนนี้ เรามาแจกแจงขั้นตอนการแยกเสียงและวิดีโอจากสไลด์ PowerPoint ออกเป็นขั้นตอนที่ง่ายต่อการปฏิบัติหลายขั้นตอน

## การแยกเสียงจากสไลด์

### ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

เริ่มต้นด้วยการสร้างโครงการใหม่ใน Visual Studio และนำเข้าเนมสเปซ Aspose.Slides ที่จำเป็น:

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideShow;
```

### ขั้นตอนที่ 2: โหลดงานนำเสนอ

โหลดงานนำเสนอ PowerPoint ที่มีเสียงที่คุณต้องการแยก:

```csharp
string dataDir = "Your Document Directory";
string presName = dataDir + "AudioSlide.ppt";
Presentation pres = new Presentation(presName);
```

### ขั้นตอนที่ 3: เข้าถึงสไลด์ที่ต้องการ

 หากต้องการเข้าถึงสไลด์ใดโดยเฉพาะ คุณสามารถใช้`ISlide` อินเตอร์เฟซ:

```csharp
ISlide slide = pres.Slides[0];
```

### ขั้นตอนที่ 4: แยกเสียง

ดึงข้อมูลเสียงจากเอฟเฟกต์การเปลี่ยนแปลงของสไลด์:

```csharp
ISlideShowTransition transition = slide.SlideShowTransition;
byte[] audio = transition.Sound.BinaryData;
System.Console.WriteLine("Length: " + audio.Length);
```

## การแยกวิดีโอออกจากสไลด์

### ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

เช่นเดียวกับในตัวอย่างการแยกเสียง ให้เริ่มต้นด้วยการสร้างโปรเจ็กต์ใหม่และนำเข้าเนมสเปซ Aspose.Slides ที่จำเป็น

### ขั้นตอนที่ 2: โหลดงานนำเสนอ

โหลดงานนำเสนอ PowerPoint ที่มีวิดีโอที่คุณต้องการแยก:

```csharp
string dataDir = "Your Document Directory";
string presName = dataDir + "Video.pptx";
Presentation pres = new Presentation(presName);
```

### ขั้นตอนที่ 3: วนซ้ำผ่านสไลด์และรูปร่าง

วนซ้ำสไลด์และรูปร่างเพื่อระบุเฟรมวิดีโอ:

```csharp
foreach (ISlide slide in pres.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
        if (shape is VideoFrame)
        {
            // แยกข้อมูลเฟรมวิดีโอ
            IVideoFrame vf = shape as IVideoFrame;
            String type = vf.EmbeddedVideo.ContentType;
            int ss = type.LastIndexOf('/');
            type = type.Remove(0, type.LastIndexOf('/') + 1);
            
            // รับข้อมูลวิดีโอเป็นอาร์เรย์ไบต์
            Byte[] buffer = vf.EmbeddedVideo.BinaryData;
            
            // บันทึกวิดีโอลงในไฟล์
            using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
            {
                stream.Write(buffer, 0, buffer.Length);
            }
        }
    }
}
```

## บทสรุป

Aspose.Slides สำหรับ .NET ช่วยให้กระบวนการแยกเสียงและวิดีโอจากงานนำเสนอ PowerPoint ง่ายขึ้น ไม่ว่าคุณกำลังเก็บถาวร ปรับใช้ใหม่ หรือวิเคราะห์เนื้อหามัลติมีเดีย ไลบรารีนี้จะเพิ่มความคล่องตัวให้กับงาน

ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณสามารถแยกเสียงและวิดีโอจากงานนำเสนอ PowerPoint ของคุณได้อย่างง่ายดาย และใช้ประโยชน์จากองค์ประกอบเหล่านี้ในรูปแบบต่างๆ

โปรดจำไว้ว่า การแยกมัลติมีเดียที่มีประสิทธิภาพด้วย Aspose.Slides สำหรับ .NET ขึ้นอยู่กับการมีเครื่องมือที่เหมาะสม ไลบรารี และการนำเสนอ PowerPoint ที่มีองค์ประกอบมัลติมีเดีย

## คำถามที่พบบ่อย

### Aspose.Slides สำหรับ .NET เข้ากันได้กับรูปแบบ PowerPoint ล่าสุดหรือไม่
ใช่ Aspose.Slides สำหรับ .NET รองรับรูปแบบ PowerPoint ล่าสุด รวมถึง PPTX

### ฉันสามารถแยกเสียงและวิดีโอจากหลายสไลด์พร้อมกันได้หรือไม่
ได้ คุณสามารถแก้ไขโค้ดเพื่อวนซ้ำผ่านสไลด์ต่างๆ และแยกมัลติมีเดียจากแต่ละสไลด์ได้

### มีตัวเลือกสิทธิ์การใช้งานสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 Aspose เสนอตัวเลือกใบอนุญาตที่หลากหลาย รวมถึงการทดลองใช้ฟรีและใบอนุญาตชั่วคราว คุณสามารถสำรวจตัวเลือกเหล่านี้ได้[เว็บไซต์](https://purchase.aspose.com/buy).

### ฉันจะรับการสนับสนุน Aspose.Slides สำหรับ .NET ได้อย่างไร
 สำหรับการสนับสนุนด้านเทคนิคและการอภิปรายในชุมชน คุณสามารถไปที่ Aspose.Slides[ฟอรั่ม](https://forum.aspose.com/).

### ฉันสามารถทำงานได้อะไรอีกบ้างด้วย Aspose.Slides สำหรับ .NET
Aspose.Slides สำหรับ .NET มีคุณสมบัติที่หลากหลาย รวมถึงการสร้าง การแก้ไข และการแปลงงานนำเสนอ PowerPoint คุณสามารถสำรวจเอกสารประกอบเพื่อดูรายละเอียดเพิ่มเติม:[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/).
