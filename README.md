Garagem Organizada

Site de controle automotivo para organizar veículos, despesas e manutenções em um só lugar. O projeto é um painel com menu lateral e seis páginas, feito apenas com HTML e CSS.

Objetivo

Quem tem carro ou moto costuma controlar gastos e manutenções de forma espalhada: anotações soltas, notas fiscais em papel ou só de memória. Com isso, é fácil esquecer uma revisão, perder o histórico de serviços ou não saber quanto foi gasto com cada veículo.

O Garagem Organizada propõe reunir tudo em um único painel: cadastro de veículos, controle de despesas, agenda de manutenções e histórico de serviços realizados. Nesta versão, o projeto apresenta a interface completa como protótipo visual, pronta para receber a parte funcional depois.

Páginas
Página	Arquivo	O que mostra
Início	index.html	Painel com indicadores, ações rápidas, resumo de despesas e próximas manutenções
Veículos	veiculos.html	Lista dos veículos cadastrados (BMW M3 e Honda Africa Twin) com foto, marca e tipo
Despesas	despesas.html	Total gasto, média mensal e gráfico de evolução mensal
Manutenções	manutencoes.html	Próximos serviços previstos, com veículo, data e status
Histórico	historico.html	Serviços já realizados em cada veículo
Perfil	perfil.html	Formulário de dados do proprietário e resumo da garagem
Tecnologias
HTML5
CSS3, com layout feito em float e medidas em porcentagem
Nenhum framework e nenhuma biblioteca externa
Sem JavaScript
Estrutura do projeto
projeto-garagem-organizada/
├── css/
│   └── style.css
├── html/
│   ├── index.html
│   ├── veiculos.html
│   ├── despesas.html
│   ├── manutencoes.html
│   ├── historico.html
│   └── perfil.html
└── img/
    ├── Logo-Garagem Organizada.png
    ├── bmw-m3.png
    └── Africa-twin.png
Como o CSS está organizado

Todas as páginas usam o mesmo arquivo, css/style.css, dividido em blocos comentados: estilos gerais, menu lateral, conteúdo principal, cabeçalho, botões, rodapé e uma seção para cada página.

Layout com float

O layout é montado com float e larguras em porcentagem. O float tira o elemento do fluxo normal da página e o encosta à esquerda ou à direita, e o conteúdo seguinte se posiciona ao lado dele. Foi assim que o menu e o conteúdo ficaram lado a lado, e também os cartões.

Com float, a largura somada ao padding e à margin dos elementos que ficam na mesma linha precisa dar no máximo 100%. Se passar disso, o último elemento cai para a linha de baixo.

Elemento	Posição	Conta das larguras
.menu-lateral	esquerda	16% + 2% de padding de cada lado = 20%
.dashboard-conteudo	ao lado do menu	74% + 2,5% de padding de cada lado = 79% (sobra 1% de folga)

Duas regras ajudam a manter o layout em ordem:

overflow: hidden no elemento pai: elementos com float saem do fluxo normal, então o elemento pai não considera a altura deles e fica com altura zero. O overflow: hidden faz o pai enxergar a altura dos filhos com float. Exemplos no projeto: .despesas-indicadores (pai) com os .cartao-despesa (filhos), .indicadores e .dashboard-topo.
clear: both no rodapé (.rodape-dashboard): faz o rodapé ficar sempre abaixo de qualquer elemento com float.
Regras compartilhadas
Cartão genérico: toda <section> dentro de .dashboard-conteudo vira um cartão, com fundo 
#303538, borda e padding.
Cabeçalho das páginas (.dashboard-topo e .despesas-topo): o <div> com o título flutua à esquerda, e o selo (.status-sistema) ou o botão (.botao-despesa) flutua à direita.
Botões (.botoes-acoes a): links com display: inline-block, para o padding funcionar.
O que cada página usa
Página	Principais classes	Como o float é usado
Início	.indicadores, .cartao-indicador, .dashboard-inferior	4 cartões lado a lado (20% + 2% de padding + 1,5% de margin cada). Embaixo, o resumo de despesas flutua à esquerda (60%) e as próximas manutenções à direita (25%)
Veículos	.veiculo	A imagem flutua à esquerda, o texto corre ao lado e os botões ficam embaixo com clear: both
Despesas	.cartao-despesa, .grafico-despesas	2 cartões lado a lado (44% + 4% de padding + 1,5% de margin cada). No gráfico, a escala de valores ocupa 10%, a área das colunas 88% e cada mês 16%
Manutenções	.despesas-topo, .botao-despesa	Reaproveita o cabeçalho de Despesas, com o botão à direita
Histórico	.registro-historico, .registro-topo	Em cada registro, o título flutua à esquerda e o status "REALIZADO" à direita
Perfil	.perfil-principal, .perfil-painel-lateral	Formulário à esquerda (65%) e resumo da garagem à direita (25%). Os campos são estilizados pelos ids #nome, #email e #telefone
Cores

O tema é escuro, com laranja como cor de destaque.

Uso	Cor
Fundo da página	
#0b0b0b
Menu lateral e cartões	
#303538
Blocos dentro dos cartões	
#242424
Destaques e bordas laranja	
#ff6a00 e 
#ff8a00
Status "REALIZADO"	
#55b879
Como executar

Não é preciso instalar nada. Basta um navegador.

Clone o repositório:
bash
   git clone https://github.com/Victor-Hms/projeto-garagem-organizada.git
Abra o arquivo html/index.html no navegador (duplo clique ou "Abrir com").
Navegue pelas páginas usando o menu lateral.
Estado atual

O projeto é um protótipo visual:

Os números do painel, os veículos, as manutenções e o histórico são dados de exemplo escritos direto no HTML.
Os botões de adicionar, editar, excluir, visualizar e salvar ainda não têm ação, porque não há JavaScript.
O gráfico de despesas mostra apenas a escala e os meses, sem barras, pois não há despesas registradas.
O layout foi pensado para telas de computador.
