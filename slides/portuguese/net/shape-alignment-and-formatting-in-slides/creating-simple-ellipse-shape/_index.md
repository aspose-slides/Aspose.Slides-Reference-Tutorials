---
title: Crie facilmente uma forma de elipse com Aspose.Slides .NET
linktitle: Criando forma de elipse simples em slides de apresentação com Aspose.Slides
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda como criar formas elipses impressionantes em slides de apresentação usando Aspose.Slides for .NET. Etapas fáceis para design dinâmico!
weight: 11
url: /pt/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
No mundo dinâmico do design de apresentações, incorporar formas como elipses pode adicionar um toque de criatividade e profissionalismo. Aspose.Slides for .NET oferece uma solução poderosa para manipular arquivos de apresentação programaticamente. Este tutorial irá guiá-lo através do processo de criação de uma forma de elipse simples em slides de apresentação usando Aspose.Slides for .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Aspose.Slides para .NET: Certifique-se de ter instalado a biblioteca Aspose.Slides para .NET. Você pode baixá-lo no[página de lançamentos](https://releases.aspose.com/slides/net/).
- Ambiente de Desenvolvimento: Configure um ambiente de desenvolvimento .NET em sua máquina.
## Importar namespaces
No seu projeto .NET, comece importando os namespaces necessários:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Esses namespaces fornecem as classes e métodos essenciais necessários para trabalhar com slides e formas de apresentação.
## Etapa 1: configurar a apresentação
Comece criando uma nova apresentação e acessando o primeiro slide. Adicione o seguinte código para conseguir isso:
```csharp
// O caminho para o diretório de documentos.
string dataDir = "Your Document Directory";
// Crie um diretório se ainda não estiver presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Instanciar classe de apresentação
using (Presentation pres = new Presentation())
{
    // Obtenha o primeiro slide
    ISlide sld = pres.Slides[0];
```
Este código inicializa uma nova apresentação e seleciona o primeiro slide para manipulação posterior.
## Etapa 2: adicionar forma de elipse
 Agora, vamos adicionar uma forma de elipse ao slide usando o`AddAutoShape` método:
```csharp
// Adicionar forma automática do tipo elipse
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Esta linha de código cria uma forma de elipse nas coordenadas (50, 150) com largura de 150 unidades e altura de 50 unidades.
## Etapa 3: salve a apresentação
Finalmente, salve a apresentação modificada em disco com um nome de arquivo especificado usando o seguinte código:
```csharp
// Grave o arquivo PPTX no disco
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Esta etapa garante que suas alterações sejam mantidas e que você possa visualizar a apresentação resultante com a forma de elipse recém-adicionada.
## Conclusão
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## Perguntas frequentes
### Posso personalizar ainda mais a forma da elipse?
Sim, você pode modificar várias propriedades da forma da elipse, como cor, tamanho e posição, para atender aos seus requisitos específicos de projeto.
### O Aspose.Slides é compatível com os frameworks .NET mais recentes?
Sim, o Aspose.Slides é atualizado regularmente para garantir compatibilidade com os frameworks .NET mais recentes.
### Onde posso encontrar mais tutoriais e exemplos para Aspose.Slides?
 Visite a[documentação](https://reference.aspose.com/slides/net/) para guias e exemplos completos.
### Como posso obter uma licença temporária para Aspose.Slides?
 Segue o[link de licença temporária](https://purchase.aspose.com/temporary-license/) para solicitar uma licença temporária para fins de teste.
### Precisa de ajuda ou tem dúvidas específicas?
 Visite a[Fórum de suporte Aspose.Slides](https://forum.aspose.com/c/slides/11) para obter ajuda da comunidade e de especialistas.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
