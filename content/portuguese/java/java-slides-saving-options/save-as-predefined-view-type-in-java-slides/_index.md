---
title: Salvar como tipo de visualização predefinido em slides Java
linktitle: Salvar como tipo de visualização predefinido em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como definir tipos de visualização predefinidos em Java Slides usando Aspose.Slides for Java. Guia passo a passo com exemplos de código e perguntas frequentes.
type: docs
weight: 10
url: /pt/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

## Introdução para salvar como tipo de visualização predefinido em slides Java

Neste guia passo a passo, exploraremos como salvar uma apresentação com um tipo de visualização predefinido usando Aspose.Slides para Java. Forneceremos o código e as explicações necessárias para realizar esta tarefa com sucesso.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

- Conhecimento básico de programação Java.
- Biblioteca Aspose.Slides para Java instalada.
- Ambiente de desenvolvimento integrado (IDE) de sua escolha.

## Configurando seu ambiente

Para começar, siga estas etapas para configurar seu ambiente de desenvolvimento:

1. Crie um novo projeto Java em seu IDE.
2. Adicione a biblioteca Aspose.Slides for Java ao seu projeto como uma dependência.

Agora que seu ambiente está configurado, vamos prosseguir com o código.

## Etapa 1: Criando uma apresentação

Para demonstrar como salvar uma apresentação com um tipo de visualização predefinido, primeiro criaremos uma nova apresentação. Aqui está o código para criar uma apresentação:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Abrindo o arquivo de apresentação
Presentation presentation = new Presentation();
```

 Neste código, criamos um novo`Presentation` objeto, que representa nossa apresentação em PowerPoint.

## Etapa 2: definir o tipo de visualização

A seguir, definiremos o tipo de visualização da nossa apresentação. Os tipos de visualização definem como a apresentação é exibida quando aberta. Neste exemplo, definiremos como "Visualização do slide mestre". Aqui está o código:

```java
// Configurando o tipo de visualização
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 No código acima, usamos o`setLastView` método do`ViewProperties` classe para definir o tipo de visualização como`SlideMasterView`. Você pode escolher outros tipos de visualização conforme necessário.

## Etapa 3: salvando a apresentação

Agora que criamos nossa apresentação e definimos o tipo de visualização, é hora de salvar a apresentação. Vamos salvá-lo no formato PPTX. Aqui está o código:

```java
// Salvando apresentação
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 Neste código, usamos o`save` método do`Presentation` class para salvar a apresentação com o nome de arquivo e formato especificados.

## Código-fonte completo para salvar como tipo de visualização predefinida em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Abrindo o arquivo de apresentação
Presentation presentation = new Presentation();
try
{
	// Configurando o tipo de visualização
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Salvando apresentação
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusão

Neste tutorial, aprendemos como salvar uma apresentação com um tipo de visualização predefinido em Java usando Aspose.Slides para Java. Seguindo o código e as etapas fornecidas, você pode definir facilmente o tipo de visualização de suas apresentações e salvá-las no formato desejado.

## Perguntas frequentes

### Como altero o tipo de visualização para algo diferente de "Visualização mestre do slide"?

 Para alterar o tipo de visualização para algo diferente de "Visualização mestre do slide", basta substituir`ViewType.SlideMasterView` com o tipo de visualização desejado, como`ViewType.NormalView` ou`ViewType.SlideSorterView`, no código onde definimos o tipo de visualização.

### Posso definir propriedades de visualização para slides individuais da apresentação?

Sim, você pode definir propriedades de visualização para slides individuais usando Aspose.Slides for Java. Você pode acessar e manipular propriedades de cada slide separadamente iterando pelos slides da apresentação.

### Em quais outros formatos posso salvar minha apresentação?

Aspose.Slides for Java suporta vários formatos de saída, incluindo PPTX, PDF, TIFF, HTML e muito mais. Você pode especificar o formato desejado ao salvar sua apresentação usando o formato apropriado`SaveFormat` valor enum.

### O Aspose.Slides for Java é adequado para processamento em lote de apresentações?

Sim, Aspose.Slides for Java é adequado para tarefas de processamento em lote. Você pode automatizar o processamento de múltiplas apresentações, aplicar alterações e salvá-las em massa usando código Java.

### Onde posso encontrar mais informações e documentação sobre Aspose.Slides for Java?

 Para documentação abrangente e referências relacionadas ao Aspose.Slides for Java, visite o site de documentação:[Aspose.Slides para documentação Java](https://reference.aspose.com/slides/java/).