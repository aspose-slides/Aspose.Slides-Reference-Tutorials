---
title: การเชื่อมโยงวิดีโอผ่านการควบคุม ActiveX ใน PowerPoint
linktitle: การเชื่อมโยงวิดีโอผ่านการควบคุม ActiveX
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีการเชื่อมโยงวิดีโอไปยังสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนนี้ประกอบด้วยซอร์สโค้ดและเคล็ดลับในการสร้างงานนำเสนอเชิงโต้ตอบและน่าดึงดูดด้วยวิดีโอที่เชื่อมโยง
weight: 12
url: /th/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเชื่อมโยงวิดีโอผ่านการควบคุม ActiveX ใน PowerPoint

การเชื่อมโยงวิดีโอผ่านการควบคุม ActiveX ในการนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET

ใน Aspose.Slides สำหรับ .NET คุณสามารถลิงก์วิดีโอไปยังสไลด์การนำเสนอโดยทางโปรแกรมโดยใช้ตัวควบคุม ActiveX สิ่งนี้ช่วยให้คุณสร้างการนำเสนอแบบโต้ตอบซึ่งสามารถเล่นเนื้อหาวิดีโอได้โดยตรงภายในสไลด์ ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการลิงก์วิดีโอไปยังสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น:
- Visual Studio (หรือสภาพแวดล้อมการพัฒนา .NET อื่น ๆ )
-  Aspose.Slides สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/net/).

## ขั้นตอนที่ 1: สร้างโครงการใหม่
สร้างโครงการใหม่ในสภาพแวดล้อมการพัฒนา .NET ที่คุณต้องการ (เช่น Visual Studio) และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.Slides สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในโปรเจ็กต์ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นสำหรับการทำงานกับ Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## ขั้นตอนที่ 3: โหลดการนำเสนอ
โหลดงานนำเสนอ PowerPoint ที่คุณต้องการเพิ่มวิดีโอที่เชื่อมโยง:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // รหัสของคุณสำหรับเพิ่มวิดีโอที่เชื่อมโยงจะอยู่ที่นี่
}
```

## ขั้นตอนที่ 4: เพิ่มการควบคุม ActiveX
 สร้างอินสแตนซ์ของ`IOleObjectFrame` อินเทอร์เฟซเพื่อเพิ่มตัวควบคุม ActiveX ลงในสไลด์:

```csharp
ISlide slide = presentation.Slides[0]; // เลือกสไลด์ที่คุณต้องการเพิ่มวิดีโอ
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

ในโค้ดด้านบน เรากำลังเพิ่มเฟรมควบคุม ActiveX ขนาด 640x480 ลงในสไลด์ เรากำลังระบุ ProgID สำหรับตัวควบคุม ShockwaveFlash ActiveX ซึ่งมักใช้สำหรับการฝังวิดีโอ

## ขั้นตอนที่ 5: ตั้งค่าคุณสมบัติของการควบคุม ActiveX
ตั้งค่าคุณสมบัติของตัวควบคุม ActiveX เพื่อระบุแหล่งวิดีโอที่เชื่อมโยง:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // แทนที่ด้วยเส้นทางไฟล์วิดีโอจริง
oleObjectFrame.AlternativeText = "Linked Video";
```

 แทนที่`"YourVideoPathHere"` พร้อมเส้นทางจริงไปยังไฟล์วิดีโอของคุณ ที่`AlternativeText` คุณสมบัติให้คำอธิบายสำหรับวิดีโอที่เชื่อมโยง

## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไข:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## คำถามที่พบบ่อย:

### ฉันจะระบุขนาดและตำแหน่งของวิดีโอที่ลิงก์บนสไลด์ได้อย่างไร
คุณสามารถปรับขนาดและตำแหน่งของกรอบควบคุม ActiveX ได้โดยใช้พารามิเตอร์ของ`AddOleObjectFrame` วิธี. อาร์กิวเมนต์ตัวเลขสี่ตัวแสดงถึงพิกัด X และ Y ของมุมซ้ายบนและความกว้างและความสูงของเฟรม ตามลำดับ

### ฉันสามารถเชื่อมโยงวิดีโอที่มีรูปแบบต่างกันโดยใช้วิธีนี้ได้หรือไม่
ได้ คุณสามารถลิงก์วิดีโอในรูปแบบต่างๆ ได้ตราบใดที่มีตัวควบคุม ActiveX ที่เหมาะสมสำหรับรูปแบบนั้น ตัวอย่างเช่น ตัวควบคุม ShockwaveFlash ActiveX ที่ใช้ในคู่มือนี้เหมาะสำหรับวิดีโอ Flash (SWF) สำหรับรูปแบบอื่นๆ คุณอาจต้องใช้ ProgID ที่แตกต่างกัน

### มีการจำกัดขนาดของวิดีโอที่เชื่อมโยงหรือไม่?
ขนาดของวิดีโอที่เชื่อมโยงอาจส่งผลต่อขนาดโดยรวมและประสิทธิภาพการนำเสนอของคุณ ขอแนะนำให้ปรับวิดีโอของคุณให้เหมาะสมสำหรับการเล่นเว็บก่อนที่จะลิงก์ไปยังงานนำเสนอ

### บทสรุป:
ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณสามารถลิงก์วิดีโอผ่านตัวควบคุม ActiveX ในงานนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET ได้อย่างง่ายดาย คุณลักษณะนี้ช่วยให้คุณสร้างการนำเสนอที่น่าสนใจและโต้ตอบได้ซึ่งรวมเนื้อหามัลติมีเดียไว้อย่างลงตัว

 สำหรับรายละเอียดเพิ่มเติมและตัวเลือกขั้นสูง คุณสามารถดูได้ที่[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
