---
title: ส่งออกไฟล์มีเดียเป็น HTML จากการนำเสนอ
linktitle: ส่งออกไฟล์มีเดียเป็น HTML จากการนำเสนอ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เพิ่มประสิทธิภาพการแบ่งปันการนำเสนอของคุณด้วย Aspose.Slides สำหรับ .NET! เรียนรู้วิธีส่งออกไฟล์สื่อจากงานนำเสนอของคุณเป็น HTML ในคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 15
url: /th/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการส่งออกไฟล์สื่อเป็น HTML จากงานนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET Aspose.Slides เป็น API ที่ทรงพลังที่ช่วยให้คุณทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม เมื่อสิ้นสุดคู่มือนี้ คุณจะสามารถแปลงงานนำเสนอของคุณเป็นรูปแบบ HTML ได้อย่างง่ายดาย เอาล่ะ มาเริ่มกันเลย!

## 1. บทนำ

งานนำเสนอ PowerPoint มักจะมีองค์ประกอบมัลติมีเดีย เช่น วิดีโอ และคุณอาจต้องส่งออกงานนำเสนอเหล่านี้เป็นรูปแบบ HTML เพื่อให้เข้ากันได้กับเว็บ Aspose.Slides สำหรับ .NET มอบวิธีที่สะดวกในการทำงานนี้ให้สำเร็จโดยทางโปรแกรม

## 2. ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

-  Aspose.Slides สำหรับ .NET: คุณควรติดตั้งไลบรารี Aspose.Slides สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/net/).

## 3. กำลังโหลดการนำเสนอ

ในการเริ่มต้น คุณจะต้องโหลดงานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็น HTML คุณจะต้องระบุไดเร็กทอรีเอาต์พุตที่จะบันทึกไฟล์ HTML ด้วย นี่คือรหัสสำหรับการโหลดงานนำเสนอ:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// กำลังโหลดงานนำเสนอ
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // รหัสของคุณที่นี่
}
```

## 4. การตั้งค่าตัวเลือก HTML

ตอนนี้ มาตั้งค่าตัวเลือก HTML สำหรับการแปลงกัน เราจะกำหนดค่าตัวควบคุม HTML, ตัวจัดรูปแบบ HTML และรูปแบบภาพสไลด์ รหัสนี้จะช่วยให้แน่ใจว่าไฟล์ HTML ของคุณมีส่วนประกอบที่จำเป็นสำหรับการแสดงองค์ประกอบมัลติมีเดีย

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.example.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// การตั้งค่าตัวเลือก HTML
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. บันทึกไฟล์ HTML

 เมื่อกำหนดค่าตัวเลือก HTML แล้ว คุณสามารถบันทึกไฟล์ HTML ได้แล้ว ที่`Save` วิธีการของวัตถุการนำเสนอจะสร้างไฟล์ HTML พร้อมองค์ประกอบมัลติมีเดียที่ฝังอยู่

```csharp
// กำลังบันทึกไฟล์
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. บทสรุป

ยินดีด้วย! คุณได้ส่งออกไฟล์สื่อไปยัง HTML จากงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ .NET สิ่งนี้ทำให้คุณสามารถแบ่งปันการนำเสนอของคุณทางออนไลน์ได้อย่างง่ายดาย และรับประกันว่าองค์ประกอบมัลติมีเดียจะแสดงอย่างเหมาะสม

## 7. คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Slides สำหรับ .NET เป็นไลบรารี่ฟรีหรือไม่
 ตอบ 1: Aspose.Slides สำหรับ .NET เป็นไลบรารีเชิงพาณิชย์ แต่คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/) เพื่อลองดู

### คำถามที่ 2: ฉันสามารถปรับแต่งเอาต์พุต HTML เพิ่มเติมได้หรือไม่
A2: ใช่ คุณสามารถปรับแต่งเอาต์พุต HTML ได้โดยการปรับเปลี่ยนตัวเลือก HTML ในโค้ด

### คำถามที่ 3: Aspose.Slides สำหรับ .NET รองรับรูปแบบการส่งออกอื่นๆ หรือไม่
A3: ใช่ Aspose.Slides สำหรับ .NET รองรับรูปแบบการส่งออกที่หลากหลาย รวมถึง PDF รูปแบบรูปภาพ และอื่นๆ

### คำถามที่ 4: ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 A4: คุณสามารถค้นหาการสนับสนุนและถามคำถามได้ในฟอรัม Aspose[ที่นี่](https://forum.aspose.com/).

### คำถามที่ 5: ฉันจะซื้อใบอนุญาตสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
 A5: คุณสามารถซื้อใบอนุญาตได้จาก[ลิงค์นี้](https://purchase.aspose.com/buy).

เมื่อคุณเสร็จสิ้นบทช่วยสอนนี้แล้ว คุณมีทักษะในการส่งออกไฟล์สื่อเป็น HTML จากงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET เพลิดเพลินกับการแบ่งปันการนำเสนอมัลติมีเดียที่หลากหลายของคุณทางออนไลน์!