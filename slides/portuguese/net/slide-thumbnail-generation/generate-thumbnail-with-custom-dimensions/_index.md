---
title: Gere miniaturas em slides com dimensões personalizadas
linktitle: Gerar miniatura com dimensões personalizadas
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como gerar imagens em miniatura personalizadas de apresentações em PowerPoint usando Aspose.Slides for .NET. Melhore a experiência e a funcionalidade do usuário.
weight: 13
url: /pt/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Criar imagens em miniatura personalizadas de suas apresentações do PowerPoint pode ser um recurso valioso, esteja você criando um aplicativo interativo, aprimorando a experiência do usuário ou otimizando conteúdo para diversas plataformas. Neste tutorial, iremos guiá-lo através do processo de geração de imagens em miniatura personalizadas de apresentações em PowerPoint usando a biblioteca Aspose.Slides for .NET. Esta poderosa biblioteca permite manipular, converter e aprimorar arquivos PowerPoint programaticamente em aplicativos .NET.

## Pré-requisitos

Antes de começarmos a gerar imagens em miniatura personalizadas, certifique-se de ter os seguintes pré-requisitos em vigor:

### 1. Aspose.Slides para .NET

 Você precisa ter a biblioteca Aspose.Slides for .NET instalada em seu projeto. Se ainda não o fez, você pode encontrar a documentação necessária e links para download[aqui](https://reference.aspose.com/slides/net/).

### 2. Uma apresentação em PowerPoint

Certifique-se de ter a apresentação do PowerPoint a partir da qual deseja gerar uma imagem em miniatura personalizada. Esta apresentação deve estar acessível no diretório do seu projeto.

### 3. Ambiente de Desenvolvimento

Para seguir este tutorial, você deve ter conhecimento prático de programação .NET usando C# e um ambiente de desenvolvimento configurado, como Visual Studio.

Agora que cobrimos os pré-requisitos, vamos dividir o processo de geração de miniaturas personalizadas em instruções passo a passo.

## Importar namespaces

Primeiro, você precisa incluir os namespaces necessários em seu código C#. Esses namespaces permitem que você trabalhe com Aspose.Slides e manipule apresentações do PowerPoint.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Etapa 1: carregar a apresentação

Para começar, carregue a apresentação do PowerPoint a partir da qual deseja gerar uma imagem em miniatura personalizada. Isso é conseguido usando a biblioteca Aspose.Slides.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Instancie uma classe Presentation que representa o arquivo de apresentação
using (Presentation pres = new Presentation(srcFileName))
{
    // Seu código para geração de miniaturas irá aqui
}
```

## Etapa 2: acesse o slide

Dentro da apresentação carregada, você precisa acessar o slide específico a partir do qual deseja gerar a imagem em miniatura personalizada. Você pode escolher o slide pelo seu índice.

```csharp
// Acesse o primeiro slide (você pode alterar o índice conforme necessário)
ISlide sld = pres.Slides[0];
```

## Etapa 3: definir dimensões de miniaturas personalizadas

Especifique as dimensões desejadas para sua imagem em miniatura personalizada. Você pode definir a largura e a altura em pixels de acordo com os requisitos da sua aplicação.

```csharp
int desiredX = 1200; // Largura
int desiredY = 800;  // Altura
```

## Etapa 4: calcular fatores de escala

Para manter a proporção do slide, calcule os fatores de escala para as dimensões X e Y com base no tamanho do slide e nas dimensões desejadas.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Etapa 5: gerar a imagem em miniatura

Crie uma imagem em escala real do slide com as dimensões personalizadas especificadas e salve-a em disco no formato JPEG.

```csharp
// Crie uma imagem em escala real
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Salve a imagem no disco no formato JPEG
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Agora que seguiu essas etapas, você deve ter gerado com êxito uma imagem em miniatura personalizada de sua apresentação do PowerPoint.

## Conclusão

Gerar imagens em miniatura personalizadas de apresentações em PowerPoint usando Aspose.Slides for .NET é uma habilidade valiosa que pode aprimorar a experiência do usuário e a funcionalidade de seus aplicativos. Seguindo as etapas descritas neste tutorial, você pode criar facilmente miniaturas personalizadas que atendam aos seus requisitos específicos.

---

## FAQs (perguntas frequentes)

### O que é Aspose.Slides para .NET?
Aspose.Slides for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com apresentações do PowerPoint programaticamente em aplicativos .NET.

### Onde posso encontrar a documentação do Aspose.Slides for .NET?
 Você pode encontrar a documentação[aqui](https://reference.aspose.com/slides/net/).

### O uso do Aspose.Slides for .NET é gratuito?
 Aspose.Slides for .NET é uma biblioteca comercial. Você pode encontrar informações sobre preços e licenciamento[aqui](https://purchase.aspose.com/buy).

### Preciso de conhecimentos avançados de programação para usar o Aspose.Slides for .NET?
Embora algum conhecimento de programação .NET seja benéfico, Aspose.Slides for .NET fornece uma API amigável que simplifica o trabalho com apresentações em PowerPoint.

### O suporte técnico está disponível para Aspose.Slides for .NET?
 Sim, você pode acessar suporte técnico e fóruns da comunidade[aqui](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
