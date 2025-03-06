---
title: Adicionar propriedades de documento personalizadas em slides Java
linktitle: Adicionar propriedades de documento personalizadas em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como aprimorar apresentações do PowerPoint com propriedades personalizadas de documentos no Java Slides. Guia passo a passo com exemplos de código usando Aspose.Slides para Java.
weight: 13
url: /pt/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar propriedades de documento personalizadas em slides Java


## Introdução à adição de propriedades personalizadas de documentos em slides Java

Neste tutorial, orientaremos você no processo de adição de propriedades personalizadas de documento a uma apresentação do PowerPoint usando Aspose.Slides para Java. As propriedades personalizadas do documento permitem armazenar informações adicionais sobre a apresentação para referência ou categorização.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java instalada e configurada em seu projeto Java.

## Etapa 1: importar pacotes necessários

```java
import com.aspose.slides.*;
```

## Etapa 2: crie uma nova apresentação

Primeiro, você precisa criar um novo objeto de apresentação. Você pode fazer isso da seguinte maneira:

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";

// Instancie a classe Apresentação
Presentation presentation = new Presentation();
```

## Passo 3: Obtendo Propriedades do Documento

seguir, você recuperará as propriedades do documento da apresentação. Essas propriedades incluem propriedades integradas como título, autor e propriedades personalizadas que você pode adicionar.

```java
// Obtendo propriedades do documento
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## Etapa 4: adicionar propriedades personalizadas

Agora, vamos adicionar propriedades personalizadas à apresentação. As propriedades customizadas consistem em um nome e um valor. Você pode usá-los para armazenar qualquer informação que desejar.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## Etapa 5: obter um nome de propriedade em um índice específico

Você também pode recuperar o nome de uma propriedade customizada em um índice específico. Isto pode ser útil se você precisar trabalhar com propriedades específicas.

```java
// Obtendo o nome da propriedade em um índice específico
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## Passo 6: Removendo uma Propriedade Selecionada

Se desejar remover uma propriedade customizada, você poderá fazer isso especificando seu nome. Aqui, estamos removendo a propriedade que obtivemos na Etapa 5.

```java
// Removendo propriedade selecionada
documentProperties.removeCustomProperty(getPropertyName);
```

## Etapa 7: salvando a apresentação

Por fim, salve a apresentação com as propriedades personalizadas adicionadas e removidas em um arquivo.

```java
// Salvando apresentação
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Código-fonte completo para adicionar propriedades de documentos personalizados em slides Java

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Instancie a classe Apresentação
Presentation presentation = new Presentation();
// Obtendo propriedades do documento
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Adicionando propriedades personalizadas
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Obtendo o nome da propriedade em um índice específico
String getPropertyName = documentProperties.getCustomPropertyName(2);
// Removendo propriedade selecionada
documentProperties.removeCustomProperty(getPropertyName);
// Salvando apresentação
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Conclusão

Você aprendeu como adicionar propriedades de documento personalizadas a uma apresentação do PowerPoint em Java usando Aspose.Slides. As propriedades personalizadas podem ser valiosas para armazenar informações adicionais relacionadas às suas apresentações. Você pode estender esse conhecimento para incluir mais propriedades customizadas conforme necessário para seu caso de uso específico.

## Perguntas frequentes

### Como recupero o valor de uma propriedade personalizada?

 Para recuperar o valor de uma propriedade customizada, você pode usar o método`get_Item` método no`documentProperties` objeto. Por exemplo:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Posso adicionar propriedades personalizadas de diferentes tipos de dados?

Sim, você pode adicionar propriedades personalizadas de vários tipos de dados, incluindo números, strings, datas e muito mais, conforme mostrado no exemplo. Aspose.Slides for Java lida com diferentes tipos de dados perfeitamente.

### Existe um limite para o número de propriedades personalizadas que posso adicionar?

Não há limite estrito para o número de propriedades personalizadas que você pode adicionar. No entanto, lembre-se de que adicionar um número excessivo de propriedades pode afetar o desempenho e o tamanho do arquivo de apresentação.

### Como posso listar todas as propriedades personalizadas em uma apresentação?

Você pode percorrer todas as propriedades personalizadas para listá-las. Aqui está um exemplo de como fazer isso:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

Este código exibirá os nomes e valores de todas as propriedades personalizadas na apresentação.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
