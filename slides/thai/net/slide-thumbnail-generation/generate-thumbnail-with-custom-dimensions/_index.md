---
"description": "เรียนรู้วิธีการสร้างรูปภาพขนาดย่อแบบกำหนดเองจากงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปรับปรุงประสบการณ์และการใช้งานของผู้ใช้"
"linktitle": "สร้างภาพขนาดย่อด้วยขนาดที่กำหนดเอง"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "สร้างภาพขนาดย่อในสไลด์ด้วยมิติที่กำหนดเอง"
"url": "/th/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพขนาดย่อในสไลด์ด้วยมิติที่กำหนดเอง


การสร้างภาพขนาดย่อที่กำหนดเองสำหรับงานนำเสนอ PowerPoint ของคุณนั้นถือเป็นทรัพยากรที่มีค่า ไม่ว่าคุณจะกำลังสร้างแอปพลิเคชันแบบโต้ตอบ ปรับปรุงประสบการณ์ของผู้ใช้ หรือปรับแต่งเนื้อหาให้เหมาะกับแพลตฟอร์มต่างๆ ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการสร้างภาพขนาดย่อที่กำหนดเองจากงานนำเสนอ PowerPoint โดยใช้ไลบรารี Aspose.Slides สำหรับ .NET ไลบรารีอันทรงพลังนี้ช่วยให้คุณสามารถจัดการ แปลง และปรับปรุงไฟล์ PowerPoint ในแอปพลิเคชัน .NET ได้ด้วยโปรแกรม

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเริ่มสร้างภาพขนาดย่อที่กำหนดเอง ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

### 1. Aspose.Slides สำหรับ .NET

คุณต้องติดตั้งไลบรารี Aspose.Slides สำหรับ .NET ไว้ในโปรเจ็กต์ของคุณ หากยังไม่ได้ติดตั้ง คุณสามารถค้นหาเอกสารที่จำเป็นและลิงก์ดาวน์โหลด [ที่นี่](https://reference-aspose.com/slides/net/).

### 2. การนำเสนอ PowerPoint

ตรวจสอบให้แน่ใจว่าคุณมีการนำเสนอ PowerPoint ที่คุณต้องการสร้างภาพขนาดย่อแบบกำหนดเอง การนำเสนอนี้ควรสามารถเข้าถึงได้จากไดเร็กทอรีโครงการของคุณ

### 3. สภาพแวดล้อมการพัฒนา

หากต้องการทำตามบทช่วยสอนนี้ คุณต้องมีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม .NET โดยใช้ C# และตั้งค่าสภาพแวดล้อมการพัฒนา เช่น Visual Studio

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นแล้ว มาแบ่งกระบวนการสร้างภาพขนาดย่อที่กำหนดเองเป็นคำแนะนำทีละขั้นตอนกัน

## นำเข้าเนมสเปซ

ขั้นแรก คุณต้องรวมเนมสเปซที่จำเป็นไว้ในโค้ด C# ของคุณ เนมสเปซเหล่านี้ช่วยให้คุณทำงานกับ Aspose.Slides และจัดการการนำเสนอ PowerPoint ได้

```csharp
using Aspose.Slides;
using System.Drawing;
```

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

ในการเริ่มต้น ให้โหลดงานนำเสนอ PowerPoint ที่คุณต้องการสร้างรูปภาพขนาดย่อแบบกำหนดเอง ซึ่งทำได้โดยใช้ไลบรารี Aspose.Slides

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์การนำเสนอ
using (Presentation pres = new Presentation(srcFileName))
{
    // โค้ดของคุณสำหรับการสร้างภาพขนาดย่อจะอยู่ที่นี่
}
```

## ขั้นตอนที่ 2: เข้าถึงสไลด์

ภายในงานนำเสนอที่โหลดแล้ว คุณต้องเข้าถึงสไลด์ที่ต้องการสร้างภาพขนาดย่อแบบกำหนดเอง คุณสามารถเลือกสไลด์ตามดัชนีได้

```csharp
// เข้าถึงสไลด์แรก (คุณสามารถเปลี่ยนดัชนีได้ตามต้องการ)
ISlide sld = pres.Slides[0];
```

## ขั้นตอนที่ 3: กำหนดขนาดภาพขนาดย่อที่กำหนดเอง

ระบุขนาดที่ต้องการสำหรับภาพขนาดย่อที่คุณกำหนดเอง คุณสามารถกำหนดความกว้างและความสูงเป็นพิกเซลได้ตามข้อกำหนดของแอปพลิเคชันของคุณ

```csharp
int desiredX = 1200; // ความกว้าง
int desiredY = 800;  // ความสูง
```

## ขั้นตอนที่ 4: คำนวณปัจจัยการปรับขนาด

เพื่อรักษาอัตราส่วนภาพของสไลด์ ให้คำนวณปัจจัยการปรับขนาดสำหรับมิติ X และ Y ตามขนาดของสไลด์และมิติที่คุณต้องการ

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## ขั้นตอนที่ 5: สร้างภาพขนาดย่อ

สร้างภาพสไลด์ขนาดเต็มด้วยขนาดที่กำหนดเองตามที่กำหนด และบันทึกลงในดิสก์ในรูปแบบ JPEG

```csharp
// สร้างภาพขนาดเต็ม
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// บันทึกภาพลงในดิสก์ในรูปแบบ JPEG
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

เมื่อคุณทำตามขั้นตอนเหล่านี้แล้ว คุณควรจะสร้างภาพขนาดย่อที่กำหนดเองจากงานนำเสนอ PowerPoint ได้สำเร็จ

## บทสรุป

การสร้างภาพขนาดย่อแบบกำหนดเองจากงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ถือเป็นทักษะอันมีค่าที่สามารถเพิ่มประสบการณ์การใช้งานและฟังก์ชันการทำงานของแอปพลิเคชันของคุณได้ โดยทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณก็สามารถสร้างภาพขนาดย่อแบบกำหนดเองที่ตรงตามความต้องการเฉพาะของคุณได้อย่างง่ายดาย

---

## คำถามที่พบบ่อย (FAQs)

### Aspose.Slides สำหรับ .NET คืออะไร?
Aspose.Slides สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับการนำเสนอ PowerPoint ด้วยโปรแกรมในแอปพลิเคชัน .NET ได้

### ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
คุณสามารถค้นหาเอกสารประกอบได้ [ที่นี่](https://reference-aspose.com/slides/net/).

### Aspose.Slides สำหรับ .NET ใช้ได้ฟรีหรือไม่
Aspose.Slides สำหรับ .NET เป็นไลบรารีเชิงพาณิชย์ คุณสามารถค้นหาข้อมูลเกี่ยวกับราคาและใบอนุญาตได้ [ที่นี่](https://purchase-aspose.com/buy).

### ฉันจำเป็นต้องมีทักษะการเขียนโปรแกรมขั้นสูงเพื่อใช้ Aspose.Slides สำหรับ .NET หรือไม่
แม้ว่าความรู้บางประการเกี่ยวกับการเขียนโปรแกรม .NET จะมีประโยชน์ แต่ Aspose.Slides สำหรับ .NET ก็มี API ที่ใช้งานง่ายซึ่งช่วยให้ทำงานกับการนำเสนอ PowerPoint ได้ง่ายขึ้น

### มีการสนับสนุนด้านเทคนิคสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
ใช่ คุณสามารถเข้าถึงการสนับสนุนด้านเทคนิคและฟอรัมชุมชนได้ [ที่นี่](https://forum-aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}