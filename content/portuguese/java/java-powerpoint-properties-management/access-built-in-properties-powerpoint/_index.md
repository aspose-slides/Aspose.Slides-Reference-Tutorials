---
title: Acesse propriedades integradas no PowerPoint
linktitle: Acesse propriedades integradas no PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como acessar propriedades integradas no PowerPoint usando Aspose.Slides para Java. Este tutorial orienta você na recuperação do autor, data de criação e muito mais.
type: docs
weight: 10
url: /pt/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---
## Introdução
Neste tutorial, exploraremos como acessar propriedades integradas em apresentações do PowerPoint usando Aspose.Slides para Java. Aspose.Slides é uma biblioteca poderosa que permite aos desenvolvedores Java trabalhar com apresentações do PowerPoint de forma programática, permitindo tarefas como leitura e modificação de propriedades de forma integrada.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1.  Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema. Você pode baixá-lo em[aqui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides para Java: Baixe e instale Aspose.Slides para Java em[esse link](https://releases.aspose.com/slides/java/).

## Importar pacotes
Primeiro, você precisa importar os pacotes necessários para o seu projeto Java. Adicione a seguinte instrução de importação no início do seu arquivo Java:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;
import com.aspose.slides.examples.RunExamples;
```
## Etapa 1: configurar o objeto de apresentação
Comece configurando o objeto Presentation para representar a apresentação do PowerPoint com a qual você deseja trabalhar. Veja como você pode fazer isso:
```java
// O caminho para o diretório que contém o arquivo de apresentação
String dataDir = "path_to_your_presentation_directory/";
// Instancie a classe Apresentação
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Passo 2: Acesse as Propriedades do Documento
Depois de configurar o objeto Presentation, você pode acessar as propriedades integradas da apresentação usando a interface IDocumentProperties. Veja como você pode recuperar várias propriedades:
### Categoria
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Status atual
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Data de criação
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Autor
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Descrição
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Palavras-chave
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Última modificação por
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Supervisor
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Data modificada
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Formato de apresentação
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Data da última impressão
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Compartilhado entre produtores
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Assunto
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Título
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Conclusão
Neste tutorial, aprendemos como acessar propriedades integradas em apresentações do PowerPoint usando Aspose.Slides para Java. Seguindo as etapas descritas acima, você pode recuperar facilmente várias propriedades, como autor, data de criação e título, de forma programática.
## Perguntas frequentes
### Posso modificar essas propriedades integradas usando Aspose.Slides para Java?
Sim, você pode modificar essas propriedades usando Aspose.Slides. Basta usar os métodos setter apropriados fornecidos pela interface IDocumentProperties.
### O Aspose.Slides é compatível com diferentes versões do PowerPoint?
Aspose.Slides oferece suporte a uma ampla variedade de versões do PowerPoint, garantindo compatibilidade entre várias plataformas.
### Posso recuperar propriedades personalizadas também?
Sim, além das propriedades integradas, você também pode recuperar e modificar propriedades personalizadas usando Aspose.Slides para Java.
### O Aspose.Slides oferece documentação e suporte?
 Sim, você pode encontrar documentação abrangente e acessar fóruns de suporte no site[Aspor site](https://reference.aspose.com/slides/java/).
### Existe uma versão de teste disponível para Aspose.Slides for Java?
 Sim, você pode baixar uma versão de avaliação gratuita em[aqui](https://releases.aspose.com/).