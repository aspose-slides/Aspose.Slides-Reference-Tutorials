---
"description": "เรียนรู้วิธีเชื่อมโยงวิดีโอกับสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนนี้ประกอบด้วยโค้ดต้นฉบับและเคล็ดลับในการสร้างงานนำเสนอแบบโต้ตอบและน่าสนใจด้วยวิดีโอที่เชื่อมโยง"
"linktitle": "การเชื่อมโยงวิดีโอผ่าน ActiveX Control"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การเชื่อมโยงวิดีโอผ่าน ActiveX Control ใน PowerPoint"
"url": "/th/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การเชื่อมโยงวิดีโอผ่าน ActiveX Control ใน PowerPoint

การเชื่อมโยงวิดีโอผ่าน ActiveX Control ในงานนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET

ใน Aspose.Slides สำหรับ .NET คุณสามารถเชื่อมโยงวิดีโอเข้ากับสไลด์การนำเสนอโดยใช้โปรแกรมควบคุม ActiveX วิธีนี้ช่วยให้คุณสร้างการนำเสนอแบบโต้ตอบที่สามารถเล่นเนื้อหาวิดีโอได้โดยตรงภายในสไลด์ ในคู่มือทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการเชื่อมโยงวิดีโอเข้ากับสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น:
- Visual Studio (หรือสภาพแวดล้อมการพัฒนา .NET อื่นๆ)
- ไลบรารี Aspose.Slides สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/net/).

## ขั้นตอนที่ 1: สร้างโครงการใหม่
สร้างโปรเจ็กต์ใหม่ในสภาพแวดล้อมการพัฒนา .NET ที่คุณต้องการ (เช่น Visual Studio) และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.Slides สำหรับ .NET

## ขั้นตอนที่ 2: นำเข้าเนมสเปซที่จำเป็น
ในโครงการของคุณ นำเข้าเนมสเปซที่จำเป็นสำหรับการทำงานกับ Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## ขั้นตอนที่ 3: โหลดงานนำเสนอ
โหลดงานนำเสนอ PowerPoint ที่คุณต้องการเพิ่มวิดีโอที่เชื่อมโยง:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // โค้ดของคุณสำหรับเพิ่มวิดีโอที่เชื่อมโยงจะอยู่ที่นี่
}
```

## ขั้นตอนที่ 4: เพิ่มตัวควบคุม ActiveX
สร้างอินสแตนซ์ของ `IOleObjectFrame` อินเทอร์เฟซสำหรับเพิ่มตัวควบคุม ActiveX ลงในสไลด์:

```csharp
ISlide slide = presentation.Slides[0]; // เลือกสไลด์ที่คุณต้องการเพิ่มวิดีโอ
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

ในโค้ดด้านบน เราเพิ่มเฟรมควบคุม ActiveX ขนาด 640x480 ลงในสไลด์ โดยระบุ ProgID สำหรับตัวควบคุม ShockwaveFlash ActiveX ซึ่งมักใช้ในการฝังวิดีโอ

## ขั้นตอนที่ 5: ตั้งค่าคุณสมบัติของ ActiveX Control
ตั้งค่าคุณสมบัติของตัวควบคุม ActiveX เพื่อระบุแหล่งวิดีโอที่เชื่อมโยง:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // แทนที่ด้วยเส้นทางไฟล์วิดีโอจริง
oleObjectFrame.AlternativeText = "Linked Video";
```

แทนที่ `"YourVideoPathHere"` ด้วยเส้นทางจริงไปยังไฟล์วิดีโอของคุณ `AlternativeText` คุณสมบัตินี้ให้คำอธิบายสำหรับวิดีโอที่เชื่อมโยง

## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไข:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## คำถามที่พบบ่อย:

### ฉันจะระบุขนาดและตำแหน่งของวิดีโอที่ลิงก์บนสไลด์ได้อย่างไร
คุณสามารถปรับขนาดและตำแหน่งของเฟรมควบคุม ActiveX ได้โดยใช้พารามิเตอร์ของ `AddOleObjectFrame` วิธีการ อาร์กิวเมนต์ตัวเลขทั้งสี่แสดงพิกัด X และ Y ของมุมบนซ้าย และความกว้างและความสูงของเฟรมตามลำดับ

### ฉันสามารถลิงก์วิดีโอรูปแบบต่างๆ โดยใช้แนวทางนี้ได้หรือไม่
ใช่ คุณสามารถลิงก์วิดีโอในรูปแบบต่างๆ ได้ตราบเท่าที่สามารถใช้ตัวควบคุม ActiveX ที่เหมาะสมสำหรับรูปแบบนั้นได้ ตัวอย่างเช่น ตัวควบคุม ActiveX ของ ShockwaveFlash ที่ใช้ในคู่มือนี้เหมาะสำหรับวิดีโอ Flash (SWF) สำหรับรูปแบบอื่นๆ คุณอาจต้องใช้ ProgID ที่แตกต่างกัน

### ขนาดของวิดีโอที่เชื่อมโยงมีจำกัดหรือไม่
ขนาดของวิดีโอที่ลิงก์อาจส่งผลต่อขนาดโดยรวมและประสิทธิภาพของงานนำเสนอของคุณ ขอแนะนำให้คุณเพิ่มประสิทธิภาพวิดีโอของคุณสำหรับการเล่นบนเว็บก่อนที่จะลิงก์วิดีโอเหล่านั้นไปยังงานนำเสนอ

### บทสรุป:
หากทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณจะสามารถเชื่อมโยงวิดีโอผ่านตัวควบคุม ActiveX ในงานนำเสนอได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสร้างงานนำเสนอที่น่าสนใจและโต้ตอบได้ซึ่งรวมเนื้อหามัลติมีเดียเข้าด้วยกันได้อย่างลงตัว

สำหรับรายละเอียดเพิ่มเติมและตัวเลือกขั้นสูง คุณสามารถดูได้ที่ [เอกสาร Aspose.Slides สำหรับ .NET](https://reference-aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}