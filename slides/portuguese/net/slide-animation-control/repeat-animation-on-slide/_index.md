---
title: Dominando animações do PowerPoint com Aspose.Slides .NET
linktitle: Repetir animação no slide
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprimore apresentações em PowerPoint usando Aspose.Slides for .NET. Controle as animações sem esforço, cative o seu público e deixe uma impressão duradoura.
type: docs
weight: 12
url: /pt/net/slide-animation-control/repeat-animation-on-slide/
---
## Introdução
No mundo dinâmico das apresentações, a capacidade de controlar animações desempenha um papel fundamental no envolvimento e na captura da atenção do público. Aspose.Slides for .NET permite que os desenvolvedores assumam o controle dos tipos de animação nos slides, permitindo uma apresentação mais interativa e visualmente atraente. Neste tutorial, exploraremos como controlar os tipos de animação em um slide usando Aspose.Slides for .NET, passo a passo.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1.  Biblioteca Aspose.Slides for .NET: Baixe e instale a biblioteca em[aqui](https://releases.aspose.com/slides/net/).
2. Ambiente de desenvolvimento .NET: Configure um ambiente de desenvolvimento .NET em sua máquina.
## Importar namespaces
Em seu projeto .NET, comece importando os namespaces necessários para aproveitar as funcionalidades fornecidas pelo Aspose.Slides:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Etapa 1: configurar o projeto
Crie um novo diretório para seu projeto e instancie a classe Presentation para representar o arquivo de apresentação.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Seu código vai aqui
}
```
## Etapa 2: acessar a sequência de efeitos
Recupere a sequência de efeitos do primeiro slide usando a propriedade MainSequence.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Etapa 3: acesse o primeiro efeito
Obtenha o primeiro efeito da sequência principal para manipular suas propriedades.
```csharp
IEffect effect = effectsSequence[0];
```
## Etapa 4: modificar as configurações de repetição
Altere a propriedade Timing/Repeat do efeito para “Até o final do slide”.
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Etapa 5: salve a apresentação
Salve a apresentação modificada para visualizar as alterações.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Repita essas etapas para efeitos adicionais ou personalize-os de acordo com seus requisitos de apresentação.
## Conclusão
Incorporar animações dinâmicas em suas apresentações do PowerPoint nunca foi tão fácil com Aspose.Slides for .NET. Este guia passo a passo fornece conhecimento para controlar os tipos de animação, garantindo que seus slides deixem uma impressão duradoura em seu público.
## perguntas frequentes
### Posso aplicar essas animações a objetos específicos em um slide?
Sim, você pode direcionar objetos específicos acessando seus efeitos individuais dentro da sequência.
### O Aspose.Slides é compatível com as versões mais recentes do PowerPoint?
Aspose.Slides oferece suporte para uma ampla variedade de versões do PowerPoint, garantindo compatibilidade com versões antigas e novas.
### Onde posso encontrar exemplos e recursos adicionais?
 Explore o[documentação](https://reference.aspose.com/slides/net/) para exemplos abrangentes e explicações detalhadas.
### Como posso obter uma licença temporária para Aspose.Slides?
 Visita[aqui](https://purchase.aspose.com/temporary-license/) para obter informações sobre como obter uma licença temporária.
### Precisa de ajuda ou tem mais dúvidas?
 Envolva-se com a comunidade Aspose.Slides no[Fórum de suporte](https://forum.aspose.com/c/slides/11).