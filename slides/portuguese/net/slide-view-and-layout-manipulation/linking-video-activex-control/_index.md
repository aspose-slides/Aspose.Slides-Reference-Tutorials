---
"description": "Aprenda a vincular vídeos a slides do PowerPoint usando o Aspose.Slides para .NET. Este guia passo a passo inclui código-fonte e dicas para criar apresentações interativas e envolventes com vídeos vinculados."
"linktitle": "Vinculando vídeo via controle ActiveX"
"second_title": "API de processamento de PowerPoint Aspose.Slides .NET"
"title": "Vinculando vídeo via controle ActiveX no PowerPoint"
"url": "/pt/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vinculando vídeo via controle ActiveX no PowerPoint

Vinculando um vídeo via controle ActiveX em uma apresentação usando Aspose.Slides para .NET

No Aspose.Slides para .NET, você pode vincular programaticamente um vídeo a um slide de apresentação usando o controle ActiveX. Isso permite criar apresentações interativas nas quais o conteúdo do vídeo pode ser reproduzido diretamente no slide. Neste guia passo a passo, mostraremos o processo de vinculação de um vídeo a um slide de apresentação usando o Aspose.Slides para .NET.

## Pré-requisitos:
- Visual Studio (ou qualquer outro ambiente de desenvolvimento .NET)
- Biblioteca Aspose.Slides para .NET. Você pode baixá-la em [aqui](https://releases.aspose.com/slides/net/).

## Etapa 1: Criar um novo projeto
Crie um novo projeto no seu ambiente de desenvolvimento .NET preferido (por exemplo, Visual Studio) e adicione referências à biblioteca Aspose.Slides para .NET.

## Etapa 2: Importar os namespaces necessários
No seu projeto, importe os namespaces necessários para trabalhar com o Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Etapa 3: Carregar apresentação
Carregue a apresentação do PowerPoint onde você deseja adicionar o vídeo vinculado:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Seu código para adicionar o vídeo vinculado será colocado aqui
}
```

## Etapa 4: adicionar controle ActiveX
Crie uma instância do `IOleObjectFrame` interface para adicionar o controle ActiveX ao slide:

```csharp
ISlide slide = presentation.Slides[0]; // Selecione o slide onde deseja adicionar o vídeo
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

No código acima, estamos adicionando um quadro de controle ActiveX com dimensões de 640x480 ao slide. Estamos especificando o ProgID para o controle ActiveX ShockwaveFlash, comumente usado para incorporar vídeos.

## Etapa 5: Definir propriedades do controle ActiveX
Defina as propriedades do controle ActiveX para especificar a fonte de vídeo vinculada:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Substituir pelo caminho real do arquivo de vídeo
oleObjectFrame.AlternativeText = "Linked Video";
```

Substituir `"YourVideoPathHere"` com o caminho real para o seu arquivo de vídeo. O `AlternativeText` propriedade fornece uma descrição para o vídeo vinculado.

## Etapa 6: Salvar apresentação
Salve a apresentação modificada:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Perguntas frequentes:

### Como posso especificar o tamanho e a posição do vídeo vinculado no slide?
Você pode ajustar as dimensões e a posição do quadro de controle ActiveX usando os parâmetros do `AddOleObjectFrame` método. Os quatro argumentos numéricos representam as coordenadas X e Y do canto superior esquerdo e a largura e altura do quadro, respectivamente.

### Posso vincular vídeos de diferentes formatos usando essa abordagem?
Sim, você pode vincular vídeos de vários formatos, desde que o controle ActiveX apropriado esteja disponível para cada formato. Por exemplo, o controle ActiveX ShockwaveFlash usado neste guia é adequado para vídeos em Flash (SWF). Para outros formatos, pode ser necessário usar ProgIDs diferentes.

### Existe um limite para o tamanho do vídeo vinculado?
O tamanho do vídeo vinculado pode afetar o tamanho geral e o desempenho da sua apresentação. É recomendável otimizar seus vídeos para reprodução na web antes de vinculá-los à apresentação.

### Conclusão:
Seguindo os passos descritos neste guia, você pode facilmente vincular um vídeo via controle ActiveX a uma apresentação usando o Aspose.Slides para .NET. Este recurso permite criar apresentações envolventes e interativas que incorporam conteúdo multimídia perfeitamente.

Para mais detalhes e opções avançadas, você pode consultar o [Documentação do Aspose.Slides para .NET](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}