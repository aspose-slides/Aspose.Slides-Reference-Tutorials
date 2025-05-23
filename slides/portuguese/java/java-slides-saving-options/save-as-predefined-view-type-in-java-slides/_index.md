---
"description": "Aprenda a definir tipos de visualização predefinidos em Slides Java usando o Aspose.Slides para Java. Guia passo a passo com exemplos de código e perguntas frequentes."
"linktitle": "Salvar como tipo de visualização predefinido em slides Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Salvar como tipo de visualização predefinido em slides Java"
"url": "/pt/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Salvar como tipo de visualização predefinido em slides Java


## Introdução a Salvar como Tipo de Visualização Predefinido em Slides Java

Neste guia passo a passo, exploraremos como salvar uma apresentação com um tipo de visualização predefinido usando o Aspose.Slides para Java. Forneceremos o código e as explicações necessárias para realizar essa tarefa com sucesso.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- Conhecimento básico de programação Java.
- Biblioteca Aspose.Slides para Java instalada.
- Ambiente de desenvolvimento integrado (IDE) de sua escolha.

## Configurando seu ambiente

Para começar, siga estas etapas para configurar seu ambiente de desenvolvimento:

1. Crie um novo projeto Java no seu IDE.
2. Adicione a biblioteca Aspose.Slides para Java ao seu projeto como uma dependência.

Agora que seu ambiente está configurado, vamos prosseguir com o código.

## Etapa 1: Criando uma apresentação

Para demonstrar como salvar uma apresentação com um tipo de visualização predefinido, primeiro criaremos uma nova apresentação. Aqui está o código para criar uma apresentação:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Abrindo o arquivo de apresentação
Presentation presentation = new Presentation();
```

Neste código, criamos um novo `Presentation` objeto, que representa nossa apresentação do PowerPoint.

## Etapa 2: Definindo o tipo de exibição

Em seguida, definiremos o tipo de visualização da nossa apresentação. Os tipos de visualização definem como a apresentação será exibida quando aberta. Neste exemplo, definiremos como "Visualização de Slide Mestre". Aqui está o código:

```java
// Configurando o tipo de visualização
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

No código acima, usamos o `setLastView` método do `ViewProperties` classe para definir o tipo de visualização para `SlideMasterView`. Você pode escolher outros tipos de visualização conforme necessário.

## Etapa 3: salvando a apresentação

Agora que criamos nossa apresentação e definimos o tipo de visualização, é hora de salvá-la. Vamos salvá-la no formato PPTX. Aqui está o código:

```java
// Salvando a apresentação
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

Neste código, usamos o `save` método do `Presentation` classe para salvar a apresentação com o nome de arquivo e formato especificados.

## Código-fonte completo para salvar como tipo de visualização predefinido em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Abrindo o arquivo de apresentação
Presentation presentation = new Presentation();
try
{
	// Configurando o tipo de visualização
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Salvando a apresentação
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusão

Neste tutorial, aprendemos como salvar uma apresentação com um tipo de visualização predefinido em Java usando o Aspose.Slides para Java. Seguindo o código e os passos fornecidos, você pode definir facilmente o tipo de visualização das suas apresentações e salvá-las no formato desejado.

## Perguntas frequentes

### Como posso alterar o tipo de visualização para algo diferente de "Visualização Mestre de Slides"?

Para alterar o tipo de visualização para algo diferente de "Visualização Mestre de Slides", basta substituir `ViewType.SlideMasterView` com o tipo de visualização desejado, como `ViewType.NoumalView` or `ViewType.SlideSorterView`, no código onde definimos o tipo de visualização.

### Posso definir propriedades de exibição para slides individuais na apresentação?

Sim, você pode definir propriedades de visualização para slides individuais usando o Aspose.Slides para Java. Você pode acessar e manipular as propriedades de cada slide separadamente, iterando pelos slides da apresentação.

### Em quais outros formatos posso salvar minha apresentação?

Aspose.Slides para Java suporta vários formatos de saída, incluindo PPTX, PDF, TIFF, HTML e outros. Você pode especificar o formato desejado ao salvar sua apresentação usando o botão apropriado. `SaveFormat` valor de enumeração.

### O Aspose.Slides para Java é adequado para processamento em lote de apresentações?

Sim, o Aspose.Slides para Java é ideal para tarefas de processamento em lote. Você pode automatizar o processamento de várias apresentações, aplicar alterações e salvá-las em massa usando código Java.

### Onde posso encontrar mais informações e documentação sobre o Aspose.Slides para Java?

Para documentação abrangente e referências relacionadas ao Aspose.Slides para Java, visite o site de documentação: [Documentação do Aspose.Slides para Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}