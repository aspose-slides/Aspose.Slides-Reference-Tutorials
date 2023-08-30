---
title: Çalışma Kitabını Grafikten Kurtarma
linktitle: Çalışma Kitabını Grafikten Kurtarma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak bir çalışma kitabını grafikten nasıl kurtaracağınızı öğrenin. Grafik verilerini çıkarın ve programlı olarak Excel çalışma kitapları oluşturun.
type: docs
weight: 12
url: /tr/net/additional-chart-features/chart-recover-workbook/
---

## giriiş

Kazalar meydana gelebilir ve kendinizi bir çalışma kitabını grafikten kurtarmaya ihtiyaç duyabilirsiniz. Aspose.Slides for .NET bu gibi durumlarda imdada yetişiyor. Bu güçlü kitaplık, sunumlardaki grafiklerden veri çıkarmanıza ve bunu yeni bir çalışma kitabına dönüştürmenize olanak tanır. Bu adım adım kılavuzda, Aspose.Slides for .NET kullanarak bir çalışma kitabını grafikten kurtarma sürecinde size yol göstereceğiz.

## Önkoşullar

Başlamadan önce aşağıdakilerin yerinde olduğundan emin olun:

- Visual Studio: .NET geliştirme için gerekli olan Visual Studio'yu indirip yükleyin.
-  Aspose.Slides for .NET: Kütüphaneyi şu adresten indirebilirsiniz:[Burada](https://downloads.aspose.com/slides/net).

## Adım 1: Aspose.Slides for .NET'i yükleyin

Henüz yapmadıysanız Aspose.Slides for .NET'i indirip yükleyin. Bu kitaplık, PowerPoint sunumlarıyla programlı olarak çalışmak için kapsamlı özellikler sağlar.

## 2. Adım: Sunuyu Yükleyin

Başlamak için Visual Studio'da yeni bir C# projesi oluşturun. Gerekli Aspose.Slides derlemelerine referanslar ekleyin. Verilerini kurtarmak istediğiniz grafiği içeren PowerPoint sunumunu yükleyin.

```csharp
// Sunuyu yükle
Presentation presentation = new Presentation("your-presentation.pptx");
```

## 3. Adım: Grafiği Tanımlayın

 Verileri kurtarmak istediğiniz slaydı ve grafiği belirleyin. Slaytlara şu menüyü kullanarak erişebilirsiniz:`presentation.Slides` kullanarak koleksiyon ve grafikler`slide.Shapes` Toplamak.

```csharp
// Grafiği içeren slaydı alın
ISlide slide = presentation.Slides[0];

// Grafiği alın
IChart chart = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is IChart)
    {
        chart = (IChart)shape;
        break;
    }
}
```

## Adım 4: Grafikten Veri Çıkarma

Aspose.Slides'ın API'sini kullanarak verileri grafikten çıkarın. Grafik serilerinden ve kategorilerden değerler alabilirsiniz.

```csharp
// Grafik verilerini çıkarın
IChartData chartData = chart.ChartData;
```

## Adım 5: Yeni Bir Çalışma Kitabı Oluşturun

EPPlus veya ClosedXML gibi bir kitaplığı kullanarak yeni bir Excel çalışma kitabı oluşturun.

```csharp
// Yeni bir Excel çalışma kitabı oluşturma
using (var excelPackage = new ExcelPackage())
{
    var worksheet = excelPackage.Workbook.Worksheets.Add("Chart Data");
    // Çalışma sayfası başlıklarını doldurmak için buraya kod ekleyin
}
```

## Adım 6: Çalışma Kitabını Grafik Verileriyle Doldurun

Excel çalışma sayfasını grafikten çıkarılan verilerle doldurun.

```csharp
//Excel çalışma sayfasını grafik verileriyle doldurma
int rowIndex = 2;
foreach (var series in chartData.Series)
{
    worksheet.Cells[rowIndex, 1].Value = series.Name;
    // Çalışma sayfasını seri verileriyle doldurmak için buraya kod ekleyin
    rowIndex++;
}
```

## Adım 7: Çalışma Kitabını Kaydedin

Kurtarılan grafik verileriyle Excel çalışma kitabını kaydedin.

```csharp
// Excel çalışma kitabını kaydedin
excelPackage.SaveAs(new FileInfo("recovered-workbook.xlsx"));
```

## Çözüm

Aspose.Slides for .NET ile çalışma kitabını grafikten kurtarmak artık çok kolay. Bu adımları izleyerek, PowerPoint sunumundaki bir grafikten programlı olarak veri çıkarabilir ve kurtarılan verilerle yeni bir Excel çalışma kitabı oluşturabilirsiniz. Bu süreç, kazalar meydana geldiğinde ve verilerin kurtarılması gerektiğinde cankurtaran olabilir.

## SSS'ler

### Aspose.Slides for .NET'i nasıl yüklerim?

 Aspose.Slides for .NET'i şu adresten indirebilirsiniz:[Burada](https://downloads.aspose.com/slides/net).

### Farklı grafik türlerinden verileri kurtarabilir miyim?

Evet, Aspose.Slides for .NET; çubuk grafikler, çizgi grafikler, pasta grafikler ve daha fazlası dahil olmak üzere çeşitli grafik türlerini destekler.

### Aspose.Slides for .NET profesyonel kullanıma uygun mu?

Kesinlikle! Aspose.Slides for .NET, geliştiricilerin PowerPoint sunumlarıyla verimli bir şekilde çalışmak için kullandıkları güçlü bir kitaplıktır.

### Aspose.Slides for .NET'i kullanmak için herhangi bir lisans gereksinimi var mı?

 Evet, Aspose.Slides for .NET ticari kullanım için geçerli bir lisans gerektirir. Lisans ayrıntılarını şurada bulabilirsiniz:[Web sitesi](https://purchase.aspose.com).

### Kurtarılan Excel çalışma kitabının görünümünü özelleştirebilir miyim?

Evet, EPPlus veya ClosedXML gibi kitaplıkları kullanarak Excel çalışma kitabının görünümünü ve biçimlendirmesini özelleştirebilirsiniz.