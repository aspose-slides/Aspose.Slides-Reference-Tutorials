---
"description": "แปลงสไลด์การนำเสนอพร้อมบันทึกของผู้บรรยายเป็น PDF ได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ .NET รักษาเนื้อหาและบริบทได้อย่างราบรื่น"
"linktitle": "แปลงสไลด์เป็น PDF ด้วย Notes"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "แปลงสไลด์เป็น PDF ด้วย Notes"
"url": "/th/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แปลงสไลด์เป็น PDF ด้วย Notes


# เขียนคำแนะนำทีละขั้นตอนในการแปลงสไลด์เป็น PDF ด้วย Notes โดยใช้ Aspose.Slides สำหรับ .NET

คุณกำลังมองหาวิธีที่เชื่อถือได้ในการแปลงสไลด์ PowerPoint ของคุณเป็นรูปแบบ PDF พร้อมเก็บรักษาบันทึกสำคัญทั้งหมดไว้หรือไม่? ไม่ต้องมองหาที่อื่นอีกแล้ว! ในบทช่วยสอนที่ครอบคลุมนี้ เราจะแนะนำคุณตลอดขั้นตอนการใช้ Aspose.Slides สำหรับ .NET เพื่อให้บรรลุภารกิจนี้ทีละขั้นตอน

## 1. บทนำ

การแปลงสไลด์ PowerPoint เป็น PDF พร้อมบันทึกย่อสามารถเป็นเครื่องมือที่มีประโยชน์สำหรับการแบ่งปันงานนำเสนอในขณะที่รับรองว่าบริบทและความคิดเห็นที่สำคัญจะยังคงอยู่ Aspose.Slides สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับงานนี้

## 2. การตั้งค่าสภาพแวดล้อมของคุณ

ก่อนที่เราจะเจาะลึกกระบวนการเขียนโค้ด ให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมที่จำเป็นแล้ว คุณจะต้องมี:

- Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET ที่คุณต้องการ
- ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว
- การนำเสนอ PowerPoint พร้อมบันทึกที่คุณต้องการแปลง

## 3. การโหลดงานนำเสนอ

ในโค้ด C# คุณต้องโหลดงานนำเสนอ PowerPoint ที่คุณต้องการแปลง นี่คือวิธีที่คุณสามารถทำได้:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. การโคลนสไลด์

หากต้องการให้แน่ใจว่า PDF ของคุณมีสไลด์พร้อมหมายเหตุที่จำเป็นทั้งหมด คุณสามารถโคลนสไลด์เหล่านั้นจากงานนำเสนอต้นฉบับได้ ดังต่อไปนี้:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. การปรับขนาดสไลด์

คุณอาจต้องการปรับขนาดสไลด์ให้พอดีกับ PDF ของคุณ Aspose.Slides สำหรับ .NET ช่วยให้คุณทำสิ่งนี้ได้อย่างง่ายดาย:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. การกำหนดค่าตัวเลือก PDF

หากต้องการควบคุมวิธีการแสดงบันทึกของคุณใน PDF คุณสามารถกำหนดค่าตัวเลือก PDF ได้ดังนี้:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. บันทึกเป็น PDF ด้วย Notes

สุดท้ายคุณสามารถบันทึกการนำเสนอของคุณเป็น PDF พร้อมหมายเหตุ:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. บทสรุป

ขอแสดงความยินดี! คุณได้แปลงสไลด์ PowerPoint เป็นรูปแบบ PDF สำเร็จแล้ว โดยยังคงบันทึกหมายเหตุสำคัญทั้งหมดไว้ Aspose.Slides สำหรับ .NET ทำให้กระบวนการนี้ตรงไปตรงมาและมีประสิทธิภาพ

## 9. คำถามที่พบบ่อย

### คำถามที่ 1: ฉันสามารถปรับแต่งเค้าโครงของบันทึกใน PDF ได้หรือไม่

ใช่ คุณสามารถปรับแต่งเค้าโครงของบันทึกได้โดยใช้ `INotesCommentsLayoutingOptions` ในตัวเลือก PDF

### คำถามที่ 2: Aspose.Slides สำหรับ .NET รองรับรูปแบบเอาต์พุตอื่นนอกเหนือจาก PDF หรือไม่

ใช่ Aspose.Slides สำหรับ .NET รองรับรูปแบบเอาต์พุตต่างๆ รวมถึง PPTX, DOCX และอื่นๆ อีกมากมาย

### คำถามที่ 3: มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides สำหรับ .NET หรือไม่

ใช่ คุณสามารถรับรุ่นทดลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรีที่ [https://releases.aspose.com/](https://releases-aspose.com/).

### คำถามที่ 4: ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน

คุณสามารถค้นหาการสนับสนุนและการสนทนาของชุมชนได้ที่ [https://forum.aspose.com/](https://forum-aspose.com/).

### คำถามที่ 5: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้หรือไม่

ใช่ คุณสามารถซื้อใบอนุญาตชั่วคราวได้ที่ [https://purchase.aspose.com/ใบอนุญาตชั่วคราว/](https://purchase-aspose.com/temporary-license/).

สรุปแล้ว การใช้ Aspose.Slides สำหรับ .NET ช่วยให้คุณสามารถแปลงสไลด์ PowerPoint เป็นรูปแบบ PDF พร้อมบันทึกย่อได้อย่างง่ายดาย ถือเป็นเครื่องมือที่มีประโยชน์สำหรับผู้เชี่ยวชาญที่ต้องการแบ่งปันงานนำเสนอกับเพื่อนร่วมงานและลูกค้า พร้อมทั้งมั่นใจได้ว่าจะไม่สูญเสียบริบทที่สำคัญ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}