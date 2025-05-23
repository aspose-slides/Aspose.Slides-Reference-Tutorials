---
"date": "2025-04-15"
"description": "Aprenda a criar e personalizar facilmente gráficos de rosca em apresentações do PowerPoint usando o Aspose.Slides para .NET. Aprimore sua apresentação de dados visuais com este guia completo."
"title": "Como criar um gráfico de rosca no PowerPoint usando o Aspose.Slides para .NET - um guia passo a passo"
"url": "/pt/net/charts-graphs/create-doughnut-chart-aspose-slides-dot-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar um gráfico de rosca no PowerPoint usando o Aspose.Slides para .NET: um guia passo a passo

## Introdução

Aprimorar suas apresentações do PowerPoint com gráficos de rosca visualmente atraentes pode melhorar significativamente a forma como você apresenta dados. O Aspose.Slides para .NET oferece uma maneira eficiente de criar e personalizar esses gráficos. Este tutorial guiará você pelas etapas de uso do Aspose.Slides para .NET para adicionar um gráfico de rosca personalizável, incluindo o ajuste do tamanho dos furos, aos seus slides do PowerPoint.

**O que você aprenderá:**
- Configurando o Aspose.Slides para .NET
- Etapas para adicionar um gráfico de rosca ao seu slide
- Técnicas para configurar o tamanho do furo do seu gráfico de rosca
- Aplicações práticas e considerações de desempenho

Vamos começar com o que você precisa antes de mergulhar!

## Pré-requisitos

Antes de começar, certifique-se de que você tenha os seguintes requisitos:

### Bibliotecas e versões necessárias
- Aspose.Slides para .NET (versão mais recente)
- Visual Studio ou qualquer IDE compatível que suporte desenvolvimento .NET

### Requisitos de configuração do ambiente
- Um ambiente Windows com .NET Framework instalado
- Conhecimento básico de programação C#

## Configurando o Aspose.Slides para .NET

Para começar, você precisa instalar a biblioteca Aspose.Slides. Veja como fazer isso usando diferentes métodos:

**Usando o .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Usando o Console do Gerenciador de Pacotes:**
```powershell
Install-Package Aspose.Slides
```

**Interface do Gerenciador de Pacotes NuGet:**
Procure por "Aspose.Slides" e instale a versão mais recente diretamente pela interface NuGet do seu IDE.

### Etapas de aquisição de licença
1. **Teste gratuito:** Comece baixando uma avaliação gratuita para avaliar os recursos.
2. **Licença temporária:** Se precisar de mais tempo, solicite uma licença temporária da Aspose.
3. **Comprar:** Para uso a longo prazo, considere comprar a versão completa.

Após a instalação, inicialize seu projeto com esta configuração básica:
```csharp
using Aspose.Slides;

// Inicializar um novo objeto de apresentação
Presentation presentation = new Presentation();
```

## Guia de Implementação

Vamos dividir o processo de criação de um gráfico de rosca usando o Aspose.Slides para .NET em etapas gerenciáveis.

### Crie um gráfico de rosca

#### Visão geral
Começaremos adicionando um gráfico de rosca ao seu slide do PowerPoint, definindo sua posição e tamanho.

**Adicionando o gráfico:**
```csharp
using Aspose.Slides.Charts;

// Acesse o primeiro slide da apresentação (por padrão, um é criado)
ISlide slide = presentation.Slides[0];

// Adicione um gráfico de rosca ao slide na posição (50, 50) com largura e altura de 400 unidades
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 50, 50, 400, 400);
```
- **Parâmetros:** `ChartType.Doughnut`, posição x: 50, posição y: 50, largura: 400, altura: 400.

### Defina o tamanho do furo

#### Visão geral
Em seguida, configuraremos o tamanho do furo do gráfico de rosca para torná-lo visualmente atraente.

**Configurando o tamanho do furo:**
```csharp
// Defina o tamanho do furo para o gráfico de rosca para 90%
chart.ChartData.SeriesGroups[0].DoughnutHoleSize = 90;
```
- **Configuração de teclas:** `DoughnutHoleSize` determina quanto do centro é "recortado". Um valor entre 0 e 100 representa porcentagem.

### Salve sua apresentação

Por fim, salve suas alterações em um novo arquivo do PowerPoint:
```csharp
// Defina o caminho onde a apresentação será salva
string outputPath = \@"YOUR_OUTPUT_DIRECTORY\DoughnutHoleSize_out.pptx";

// Salvar a apresentação modificada no formato PPTX
presentation.Save(outputPath, SaveFormat.Pptx);
```
- **Observação:** Substituir `YOUR_OUTPUT_DIRECTORY` com o local de arquivo desejado.

### Dicas para solução de problemas

- Certifique-se de que o Aspose.Slides esteja instalado e importado corretamente.
- Verifique se o caminho do diretório de saída existe antes de salvar a apresentação.

## Aplicações práticas

Os gráficos de rosca criados com o Aspose.Slides para .NET podem ser usados em vários cenários:

1. **Relatórios de negócios:** Ilustre dados financeiros, como alocações de orçamento ou distribuições de vendas.
2. **Análise de marketing:** Exibir porcentagens de participação de mercado entre diferentes marcas.
3. **Material Educacional:** Use para explicar conceitos estatísticos de uma forma visualmente envolvente.

Integre o Aspose.Slides com outros sistemas para geração e distribuição automatizadas de relatórios em ambientes corporativos.

## Considerações de desempenho

Ao trabalhar com apresentações grandes ou vários gráficos, considere as seguintes dicas:

- Otimize o processamento de dados antes de adicioná-los aos slides.
- Reutilize objetos de apresentação sempre que possível para conservar memória.
- Atualize regularmente sua biblioteca Aspose.Slides para se beneficiar de melhorias de desempenho.

## Conclusão

Você aprendeu a criar e personalizar um gráfico de rosca usando o Aspose.Slides para .NET. Esta ferramenta versátil aprimora o apelo visual das suas apresentações, facilitando a compreensão dos dados rapidamente.

**Próximos passos:**
Explore outros tipos de gráficos disponíveis no Aspose.Slides ou explore recursos avançados, como animações.

Pronto para experimentar? Acesse a seção de recursos abaixo e comece a experimentar!

## Seção de perguntas frequentes

1. **Para que é usado o Aspose.Slides para .NET?**  
   É uma biblioteca para criar, modificar e converter apresentações do PowerPoint programaticamente.

2. **Como posso alterar a cor dos segmentos do donut?**  
   Usar `chart.ChartData.SeriesGroups[0].Series[i].Format.Fill.FillType` para ajustar as propriedades de preenchimento.

3. **Posso criar vários gráficos em uma apresentação?**  
   Sim, adicione quantos gráficos forem necessários repetindo as etapas de criação do gráfico em diferentes slides ou posições.

4. **Como licencio o Aspose.Slides for .NET para uso comercial?**  
   Compre uma licença através do site oficial da Aspose para usá-la comercialmente.

5. **O que devo fazer se minha apresentação não for salva corretamente?**  
   Verifique as permissões do caminho do arquivo e certifique-se de que as referências do seu projeto estejam atualizadas.

## Recursos

- [Documentação do Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Baixe Aspose.Slides para .NET](https://releases.aspose.com/slides/net/)
- [Comprar uma licença](https://purchase.aspose.com/buy)
- [Versão de teste gratuita](https://releases.aspose.com/slides/net/)
- [Solicitação de Licença Temporária](https://purchase.aspose.com/temporary-license/)
- [Fórum de Suporte](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}