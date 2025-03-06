---
title: Alterar o estilo da forma SmartArt no PowerPoint com Java
linktitle: Alterar o estilo da forma SmartArt no PowerPoint com Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como alterar estilos SmartArt em apresentações do PowerPoint usando Java com Aspose.Slides for Java. Impulsione suas apresentações.
weight: 23
url: /pt/java/java-powerpoint-smartart-manipulation/change-smartart-shape-style-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introdução
No mundo do desenvolvimento Java, a criação de apresentações poderosas costuma ser um requisito. Seja para apresentações comerciais, fins educacionais ou simplesmente para compartilhar informações, as apresentações em PowerPoint são um meio comum. No entanto, às vezes os estilos e formatos padrão fornecidos pelo PowerPoint podem não atender totalmente às nossas necessidades. É aqui que o Aspose.Slides para Java entra em ação.
Aspose.Slides for Java é uma biblioteca robusta que permite aos desenvolvedores Java trabalhar com apresentações do PowerPoint de forma programática. Ele oferece uma ampla gama de recursos, incluindo a capacidade de manipular formas, estilos, animações e muito mais. Neste tutorial, focaremos em uma tarefa específica: alterar o estilo de forma SmartArt em apresentações do PowerPoint usando Java.
## Pré-requisitos
Antes de mergulhar no tutorial, existem alguns pré-requisitos que você precisa ter em vigor:
1. Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema. Você pode baixar e instalar a versão mais recente no site da Oracle.
2. Biblioteca Aspose.Slides para Java: você precisará baixar e incluir a biblioteca Aspose.Slides para Java em seu projeto. Você pode encontrar o link para download[aqui](https://releases.aspose.com/slides/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Escolha seu IDE preferido para desenvolvimento Java. IntelliJ IDEA, Eclipse ou NetBeans são escolhas populares.

## Importar pacotes
Antes de começarmos a codificar, vamos importar os pacotes necessários para nosso projeto Java. Esses pacotes nos permitirão trabalhar perfeitamente com as funcionalidades do Aspose.Slides.
```java
import com.aspose.slides.*;
```
## Etapa 1: carregar a apresentação
Primeiro, precisamos carregar a apresentação do PowerPoint que queremos modificar.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## Etapa 2: percorrer as formas
A seguir, percorreremos todas as formas do primeiro slide da apresentação.
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## Etapa 3: verifique o tipo de SmartArt
Para cada forma, verificaremos se é uma forma SmartArt.
```java
if (shape instanceof ISmartArt)
```
## Etapa 4: transmitir para SmartArt
 Se a forma for um SmartArt, iremos lançá-la para o`ISmartArt` interface.
```java
ISmartArt smart = (ISmartArt) shape;
```
## Etapa 5: verificar e alterar o estilo
Em seguida, verificaremos o estilo atual do SmartArt e alteraremos se necessário.
```java
if (smart.getQuickStyle() == SmartArtQuickStyleType.SimpleFill)
{
    smart.setQuickStyle(SmartArtQuickStyleType.Cartoon);
}
```
## Etapa 6: salvar a apresentação
Finalmente, salvaremos a apresentação modificada em um novo arquivo.
```java
presentation.save(dataDir + "ChangeSmartArtStyle_out.pptx", SaveFormat.Pptx);
```

## Conclusão
Neste tutorial, aprendemos como alterar o estilo de forma SmartArt em apresentações do PowerPoint usando Java e a biblioteca Aspose.Slides para Java. Seguindo o guia passo a passo, você pode personalizar facilmente a aparência das formas SmartArt para melhor atender às suas necessidades de apresentação.
## Perguntas frequentes
### Posso usar Aspose.Slides for Java com outras bibliotecas Java?
Sim, Aspose.Slides for Java pode ser integrado perfeitamente com outras bibliotecas Java para aprimorar a funcionalidade de seus aplicativos.
### Existe um teste gratuito disponível para Aspose.Slides for Java?
 Sim, você pode aproveitar uma avaliação gratuita do Aspose.Slides for Java em[aqui](https://releases.aspose.com/).
### Como posso obter suporte para Aspose.Slides para Java?
 Você pode obter suporte para Aspose.Slides for Java visitando o[fórum](https://forum.aspose.com/c/slides/11).
### Posso comprar uma licença temporária do Aspose.Slides for Java?
 Sim, você pode comprar uma licença temporária do Aspose.Slides for Java em[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso encontrar documentação detalhada para Aspose.Slides for Java?
 Você pode encontrar documentação detalhada para Aspose.Slides for Java[aqui](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
