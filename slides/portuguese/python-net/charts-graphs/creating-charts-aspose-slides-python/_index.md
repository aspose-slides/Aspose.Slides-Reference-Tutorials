---
"date": "2025-04-23"
"description": "Aprenda a criar e configurar gráficos impressionantes usando o Aspose.Slides para Python. Siga este guia passo a passo para uma visualização de dados eficaz em apresentações."
"title": "Criando gráficos em Python com Aspose.Slides&#58; um guia completo"
"url": "/pt/python-net/charts-graphs/creating-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Criando gráficos em Python com Aspose.Slides: um guia completo

## Introdução
Criar gráficos visualmente atraentes em suas apresentações pode tornar os dados mais fáceis de entender, permitindo que você transmita informações complexas sem esforço. Este tutorial guiará você na criação e configuração de gráficos usando o Aspose.Slides para Python — uma biblioteca robusta que transforma a maneira como você cria apresentações, oferecendo recursos poderosos para manipulação de gráficos.

**O que você aprenderá:**
- Como criar um gráfico de colunas empilhadas em uma apresentação
- Adicionar e formatar séries de dados com rótulos personalizados
- Salvando sua apresentação configurada

Ao final deste tutorial, você terá adquirido experiência prática com o Aspose.Slides Python para aprimorar suas apresentações. Vamos nos aprofundar na configuração do seu ambiente antes de começarmos a criar gráficos incríveis!

## Pré-requisitos
Antes de começar, certifique-se de que você atende aos seguintes pré-requisitos:

1. **Ambiente Python:** Você deve ter o Python instalado no seu sistema (versão 3.x recomendada).
2. **Aspose.Slides para Python:** Isso pode ser instalado via pip.
3. **Aquisição de licença:** Embora um teste gratuito esteja disponível, considere adquirir uma licença temporária ou completa para desbloquear todos os recursos.

## Configurando Aspose.Slides para Python
Para começar a usar o Aspose.Slides em seus projetos, você precisa instalar a biblioteca e entender como configurar seu ambiente:

**Instalação:**
```bash
pip install aspose.slides
```

Após a instalação, você pode inicializar e usar o Aspose.Slides importando-o para o seu script. Para utilizar todos os seus recursos, adquira uma licença. Um teste gratuito está disponível ou, para uso mais prolongado, considere adquirir ou solicitar uma licença temporária.

## Guia de Implementação

### Recurso 1: Criar e configurar uma apresentação com gráficos
**Visão geral:** Esta seção explica como configurar um slide de apresentação e adicionar um gráfico a ele usando o Aspose.Slides Python.

#### Etapa 1: Inicializar a apresentação
Comece criando um novo objeto de apresentação. Use o `with` declaração para gerenciamento automático de recursos:
```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Acesse o primeiro slide da apresentação
    slide = presentation.slides[0]
```

#### Etapa 2: adicione um gráfico ao slide
Aqui, adicionamos um gráfico de colunas empilhadas em uma posição especificada com dimensões definidas:
```python
# Adicionar um gráfico de colunas empilhadas ao slide
chart = slide.shapes.add_chart(slides.charts.ChartType.PERCENTS_STACKED_COLUMN, 20, 20, 500, 400)
```

#### Etapa 3: Configurar eixos do gráfico
Configure o formato numérico do eixo vertical para melhor representação de dados:
```python
# Configurar o formato do número do eixo vertical
chart.axes.vertical_axis.is_number_format_linked_to_source = False
chart.axes.vertical_axis.number_format = "0.00%"
```

### Recurso 2: Adicionar e formatar séries de dados no gráfico
**Visão geral:** Esta seção se concentra em adicionar uma série de dados, preenchê-la com valores e personalizar sua aparência.

#### Etapa 1: Definir a pasta de trabalho de dados
Inicialize a pasta de trabalho de dados do seu gráfico:
```python
default_worksheet_index = 0
workbook = chart.chart_data.chart_data_workbook
```

#### Etapa 2: Adicionar e preencher séries de dados
Adicione uma nova série chamada "Vermelhos" ao seu gráfico e preencha-o com pontos de dados:
```python
# Adicione uma nova série e preencha com pontos de dados
series = chart.chart_data.series.add(workbook.get_cell(default_worksheet_index, 0, 1, "Reds"), chart.type)

for i in range(1, 5):
    series.data_points.add_data_point_for_bar_series(
        workbook.get_cell(default_worksheet_index, i, 1, [0.30, 0.50, 0.80, 0.65][i-1])
    )
```

#### Etapa 3: formatar a aparência da série
Personalize a cor de preenchimento e o formato do rótulo de dados:
```python
# Definir preenchimento da série para vermelho
series.format.fill.fill_type = slides.FillType.SOLID
series.format.fill.solid_fill_color.color = drawing.Color.red

# Configurar rótulos de dados para exibição de porcentagem
series.labels.default_data_label_format.show_value = True
series.labels.default_data_label_format.number_format = "0.0%"
```

### Recurso 3: Adicionar e formatar a segunda série de dados no gráfico
**Visão geral:** Esta seção expande a adição de uma segunda série de dados com seu próprio estilo.

#### Etapa 1: adicione a segunda série
Adicione outra série chamada "Blues":
```python
# Adicione uma segunda série chamada "Blues"
series2 = chart.chart_data.series.add(workbook.get_cell(default_worksheet_index, 0, 2, "Blues"), chart.type)
```

#### Etapa 2: preencher e formatar a série
Preencha-o com pontos de dados e aplique formatação:
```python
# Popular a segunda série
for i in range(1, 5):
    series2.data_points.add_data_point_for_bar_series(
        workbook.get_cell(default_worksheet_index, i, 2, [0.70, 0.50, 0.20, 0.35][i-1])
    )

# Defina o preenchimento como azul e configure os rótulos
series2.format.fill.fill_type = slides.FillType.SOLID
series2.format.fill.solid_fill_color.color = drawing.Color.blue

series2.labels.default_data_label_format.show_value = True
```

### Recurso 4: Salvar apresentação em disco
**Visão geral:** Depois que seu gráfico estiver configurado, salve a apresentação.

#### Etapa 1: Salve seu trabalho
Use o `save` método para armazenar seu arquivo:
```python
# Salvar a apresentação no disco
directory = "YOUR_OUTPUT_DIRECTORY"
presentation.save(f"{directory}/charts_set_data_labels_percentage_sign_out.pptx", slides.export.SaveFormat.PPTX)
```

## Aplicações práticas
Usando o Aspose.Slides para Python, você pode aprimorar apresentações em vários domínios:
1. **Relatórios de negócios:** Crie relatórios trimestrais detalhados com gráficos dinâmicos.
2. **Conteúdo educacional:** Crie materiais educacionais envolventes com representação visual de dados.
3. **Apresentações de vendas:** Ilustre tendências e previsões de vendas de forma eficaz.

Esses exemplos demonstram como o Aspose.Slides pode ser integrado a fluxos de trabalho existentes para fornecer apresentações refinadas.

## Considerações de desempenho
Para garantir um desempenho ideal:
- Gerencie a memória com eficiência, especialmente ao lidar com grandes conjuntos de dados em gráficos.
- Utilize as melhores práticas para gerenciamento de recursos Python com Aspose.Slides.
- Atualize sua biblioteca regularmente para se beneficiar de melhorias de desempenho.

Seguindo essas dicas, você pode manter operações tranquilas e eficientes ao trabalhar com apresentações complexas.

## Conclusão
Neste tutorial, exploramos como criar e configurar gráficos em apresentações usando o Aspose.Slides para Python. Agora você tem o conhecimento necessário para integrar visualizações de dados visualmente atraentes aos seus projetos. Para aprimorar ainda mais suas habilidades, explore recursos adicionais da biblioteca ou experimente diferentes tipos de gráficos.

**Próximos passos:** Tente implementar esses conceitos em um projeto do mundo real para solidificar sua compreensão.

## Seção de perguntas frequentes
1. **Como instalo o Aspose.Slides para Python?**
   - Usar `pip install aspose.slides` para baixar e instalar facilmente.
2. **Posso usar o Aspose.Slides sem comprar uma licença?**
   - Sim, você pode começar com um teste gratuito ou solicitar uma licença temporária.
3. **É possível personalizar ainda mais os rótulos de dados do gráfico?**
   - Com certeza! Você pode explorar mais opções de formatação fornecidas pela API da biblioteca.
4. **Quais são alguns problemas comuns ao criar gráficos?**
   - Certifique-se de que todos os pontos de dados estejam formatados corretamente e vinculados à série apropriada.
5. **Como integro o Aspose.Slides com outros sistemas?**
   - Use sua API abrangente para integração perfeita em seus projetos Python existentes.

## Recursos
- [Documentação](https://reference.aspose.com/slides/python-net/)
- [Download](https://releases.aspose.com/slides/python-net/)
- [Comprar](https://purchase.aspose.com/buy)
- [Teste grátis](https://releases.aspose.com/slides/python-net/)
- [Licença Temporária](https://purchase.aspose.com/temporary-license/)
- [Fórum de Suporte](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}