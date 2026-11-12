# Garagem Organizada

Site de controle automotivo para organizar veículos, despesas e manutenções em um só lugar. O projeto é um painel com menu lateral e seis páginas, desenvolvido apenas com HTML e CSS.

## Objetivo

Quem tem carro ou moto costuma controlar gastos e manutenções de forma distribuída: notas soltas, notas fiscais em papel ou apenas de memória. Com isso, é fácil esquecer uma revisão, perder o histórico de serviços ou não saber quanto foi gasto com cada veículo.

O Garagem Organizada propõe reunir tudo em um único painel: cadastro de veículos, controle de despesas, agenda de manutenções e histórico de serviços realizados.

Nesta versão, o projeto apresenta uma interface completa como protótipo visual, preparada para receber a parte funcional posteriormente.

## Páginas do projeto

| Página | Arquivo | O que mostra |
|:---|:---|:---|
| Início | `index.html` | Painel com indicadores, ações rápidas, resumo de despesas e próximas manutenções. |
| Veículos | `veiculos.html` | Lista dos veículos cadastrados (BMW M3 e Honda Africa Twin), com foto, marca e tipo. |
| Despesas | `despesas.html` | Total gasto, média mensal e gráfico de evolução mensal. |
| Manutenções | `manutencoes.html` | Próximos serviços previstos, com veículo, dados e status. |
| Histórico | `historico.html` | Serviços já realizados em cada veículo. |
| Perfil | `perfil.html` | Formulário de dados do proprietário e resumo da garagem. |

## Tecnologias utilizadas

- HTML5
- CSS3
- Layout com `float` e medidas em percentual.
- Nenhum framework ou biblioteca externa.
- Sem JavaScript.

## Estrutura do projeto

```text
projeto-garagem-organizada/
│
├── css/
│   └── style.css
│
├── html/
│   ├── index.html
│   ├── veiculos.html
│   ├── despesas.html
│   ├── manutencoes.html
│   ├── historico.html
│   └── perfil.html
│
└── img/
    ├── Logo-Garagem Organizada.png
    ├── bmw-m3.png
    └── Africa-twin.png
```

## Como o CSS está organizado

Todas as páginas usam o mesmo arquivo `css/style.css`, dividido em blocos comentados:

- Estilos gerais;
- Menu lateral;
- Conteúdo principal;
- Cabeçalho;
- Botões;
- Rodapé;
- Estilos específicos de cada página.

## Layout com flutuação (`float`)

O layout é montado com `float` e larguras em percentual. O `float` tira o elemento do fluxo normal da página e o posiciona à esquerda ou à direita, permitindo que o conteúdo seguinte fique ao lado dele.

Foi assim que o menu lateral e o conteúdo principal ficaram lado a lado, assim como os cartões do painel.

Com `float`, a largura somada ao `padding` e à `margin` dos elementos que ficam na mesma linha precisa respeitar o espaço disponível. Se ultrapassar 100%, o último elemento passa para a linha de baixo.

### Exemplo das larguras utilizadas

| Elemento | Posição | Conta das larguras |
|:---|:---|:---|
| `.menu-lateral` | Esquerda | 16% + 2% de preenchimento de cada lado = 20% |
| `.dashboard-conteudo` | Ao lado do menu | 74% + 2,5% de preenchimento de cada lado = 79% |

A soma dos dois elementos é de 99%, deixando 1% de folga.

### Organização dos elementos com float

Duas regras ajudam a manter o layout em ordem:

**1. `overflow: hidden` no elemento pai**

Elementos com `float` saem do fluxo normal da página. Por isso, o elemento pai pode não considerar a altura dos filhos e acabar ficando com altura zero.

O `overflow: hidden` ajuda o elemento pai a envolver os elementos flutuantes, mantendo sua altura.

Exemplos no projeto:

- `.despesas-indicadores`: pai dos `.cartao-despesa`.
- `.indicadores`.
- `.dashboard-topo`.

**2. `clear: both` no rodapé**

A propriedade `clear: both` é utilizada no `.rodape-dashboard` para fazer com que o rodapé fique abaixo dos elementos que utilizam `float`, independentemente de estarem posicionados à esquerda ou à direita.

## Regras compartilhadas

**Cartões genéricos**

Os elementos de cartão dentro de `.dashboard-conteudo` utilizam fundo `#303538`, borda e preenchimento para manter o padrão visual.

**Cabeçalho das páginas**

As classes `.dashboard-topo` e `.despesas-topo` organizam os cabeçalhos. O título fica à esquerda, enquanto o selo `.status-sistema` ou o botão `.botao-despesa` fica à direita, utilizando `float`.

**Botões**

Os links de `.botoes-acoes a` utilizam `display: inline-block`, permitindo aplicar preenchimento e organizar melhor os botões.

## O que cada página utiliza

| Página | Principais classes | Como o float é usado |
|:---|:---|:---|
| Início | `.indicadores`, `.cartao-indicador`, `.dashboard-inferior` | Quatro cartões lado a lado. Embaixo, o resumo de despesas fica à esquerda (60%) e as próximas manutenções à direita (25%). |
| Veículos | `.veiculo` | A imagem flutua à esquerda, o texto fica ao lado e os botões ficam abaixo com `clear: both`. |
| Despesas | `.cartao-despesa`, `.grafico-despesas` | Dois cartões lado a lado. No gráfico, a escala ocupa 10%, a área das colunas 88% e cada mês 16%. |
| Manutenções | `.despesas-topo`, `.botao-despesa` | Reaproveita o cabeçalho de Despesas, com o botão à direita. |
| Histórico | `.registro-historico`, `.registro-topo` | Em cada registro, o título fica à esquerda e o status "REALIZADO" à direita. |
| Perfil | `.perfil-principal`, `.perfil-painel-lateral` | Formulário à esquerda (65%) e resumo da garagem à direita (25%). Os campos são estilizados pelos IDs `#nome`, `#email` e `#telefone`. |

## Cores

O tema é escuro, com laranja como cor de destaque.

| Uso | Cor |
|:---|:---|
| Fundo da página | `#0b0b0b` |
| Menu lateral e cartões | `#303538` |
| Blocos dentro dos cartões | `#242424` |
| Destaques e bordas | `#ff6a00` e `#ff8a00` |
| Status "REALIZADO" | `#55b879` |

## Como executar

Não é necessário instalar nada. Basta utilizar um navegador.

1. Clone o repositório:

```bash
git clone https://github.com/Victor-Hms/projeto-garagem-organizada.git
```

2. Abra o arquivo `html/index.html` no navegador (duplo clique ou opção "Abrir com").
3. Navegue pelas páginas utilizando o menu lateral.

## Estado atual do projeto

O projeto é um protótipo visual.

- Os números do painel, os veículos, as manutenções e o histórico são dados de exemplo escritos diretamente no HTML.
- Os botões de adicionar, editar, excluir, visualizar e salvar ainda não possuem ações, pois o projeto não utiliza JavaScript.
- O gráfico de despesas apresenta apenas a escala e os meses, sem barras, pois não há despesas registradas.
- O layout foi pensado para telas de computador.
