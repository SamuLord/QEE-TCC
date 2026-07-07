ANÁLISE DE DESEMPENHO DO SISTEMA FOTOVOLTAICO
ESTACIONAMENTO SOLAR DA UFRJ
Anderson Victor Videira Dantas
Projeto de Graduação apresentado ao Curso
de Engenharia Elétrica da Escola Politécnica,
Universidade Federal do Rio de Janeiro, como
parte dos requisitos necessários à obtenção do
título de Engenheiro.
Orientadores: Amaro Olímpio Pereira Júnior
Marlon Max Huamani Bellido
Rio de Janeiro
Julho de 2024
ANÁLISE DE DESEMPENHO DO SISTEMA FOTOVOLTAICO
ESTACIONAMENTO SOLAR DA UFRJ
Anderson Victor Videira Dantas
PROJETO DE GRADUAÇÃO SUBMETIDO AO CORPO DOCENTE DO
CURSO DE ENGENHARIA ELÉTRICA DA ESCOLA POLITÉCNICA
DA UNIVERSIDADE FEDERAL DO RIO DE JANEIRO COMO PARTE
DOS REQUISITOS NECESSÁRIOS PARA A OBTENÇÃO DO GRAU DE
ENGENHEIRO ELETRICISTA.
Examinado por:
Prof. Amaro Olímpio Pereira Júnior, D.Sc.
Prof. Marlon Max Huamani Bellido, D.Sc.
Prof. Robson Francisco da Silva Dias, D.Sc.
Bruno Allevato Martins da Silva, M.Sc.
RIO DE JANEIRO, RJ – BRASIL
JULHO DE 2024
Victor Videira Dantas, Anderson
Análise de Desempenho do Sistema Fotovoltaico
Estacionamento Solar da UFRJ/Anderson Victor Videira
Dantas. – Rio de Janeiro: UFRJ/ Escola Politécnica, 2024.
XI, 57 p.: il.; 29, 7cm.
Orientadores: Amaro Olímpio Pereira Júnior
Marlon Max Huamani Bellido
Projeto de Graduação – UFRJ/ Escola Politécnica/
Curso de Engenharia Elétrica, 2024.
Referências Bibliográficas: p. 45 – 48.
1. Sistemas Fotovoltaicos. 2. Geração Distribuída. 3.
Energia Sustentável. I. Olímpio Pereira Júnior, Amaro
et al. II. Universidade Federal do Rio de Janeiro, Escola
Politécnica, Curso de Engenharia Elétrica. III. Título.
iii
“A humildade é o primeiro
degrau para a sabedoria” (Santo
Tomás de Aquino)
iv
Agradecimentos
Primeiramente, gostaria de agradecer a Deus, pois tudo que tenho vem dEle.
Dedico este trabalho a Ele, reconhecendo Sua onipresença em minha vida.
Aos meus pais, Adilson e Vânia, que me ensinaram o valor dos estudos e da
excelência e cujo amor e apoio incondicional foram meu alicerce ao longo de toda
essa jornada. A vocês, expresso minha eterna gratidão.
Gostaria de agradecer à minha família, em especial, à minha irmã, Ana Beatriz, e
ao meu sobrinho, Miguel, que me mostraram que a vida deve ser vivida intensamente
e aproveitada em todos os seus momentos. Suas palavras de esperança e incentivo
foram fundamentais.
Ao amor da minha vida, Esther, sou imensamente grato pela confiança, pelo amor
e pelo apoio incondicional nos momentos mais difíceis. Sua fé em mim foi essencial
para que eu pudesse concluir esta jornada.
Aos professores que tive durante o curso de Engenharia Elétrica, por transmitirem seu conhecimento e por contribuírem para a minha formação acadêmica e
profissional, em especial aos meus orientadores, Professores Amaro Pereira e Marlon
Bellido.
Aos meus colegas de curso, que estiveram ao meu lado durante esses anos, compartilhando experiências, dificuldades e conquistas. Em especial, agradeço aos meus
amigos Antonio Dottori, Phelipe Francesco, Victoria Castello e Wesley Jupter, pela
amizade, apoio e colaboração nos momentos mais desafiadores.
Por fim, agradeço a todos que de alguma forma contribuíram para a conclusão
desta jornada acadêmica.
v
Resumo do Projeto de Graduação apresentado à Escola Politécnica/ UFRJ como
parte dos requisitos necessários para a obtenção do grau de Engenheiro Eletricista.
ANÁLISE DE DESEMPENHO DO SISTEMA FOTOVOLTAICO
ESTACIONAMENTO SOLAR DA UFRJ
Anderson Victor Videira Dantas
Julho/2024
Orientadores: Amaro Olímpio Pereira Júnior
Marlon Max Huamani Bellido
Curso: Engenharia Elétrica
Este trabalho de conclusão de curso apresenta a análise de desempenho do primeiro sistema fotovoltaico, com potência de 99 kWp, instalado no campus da Cidade
Universitária da Universidade Federal do Rio de Janeiro (UFRJ). O sistema faz parte
do Programa Fundo Verde da UFRJ e visa promover a geração distribuída (GD).
Durante o período de janeiro de 2016 a novembro de 2019, foram monitorados parâmetros como geração de energia, radiação solar incidente nos painéis fotovoltaicos,
temperatura e velocidade do vento. Foram avaliados rendimento de referência, rendimento do conjunto, razão de desempenho, entre outros. Os resultados demonstram
o potencial do campus da UFRJ como exemplo de sucesso de GD e incentivam o
desenvolvimento da tecnologia na região.
vi
Abstract of Undergraduate Project presented to POLI/UFRJ as a partial fulfillment
of the requirements for the degree of Engineer.
PERFORMANCE ANALYSIS OF THE SOLAR PARKING PHOTOVOLTAIC
SYSTEM AT UFRJ
Anderson Victor Videira Dantas
July/2024
Advisors: Amaro Olímpio Pereira Júnior
Marlon Max Huamani Bellido
Course: Electrical Engineering
This work presents the performance analysis of the first photovoltaic (PV) system, with a power of 99 kWp, installed at the University City campus of the Federal
University of Rio de Janeiro (UFRJ). The system is part of UFRJ’s Green Fund
Program and aims to promote distributed generation (GD). During the period from
January 2016 to November 2019, parameters such as energy generation, incident
solar radiation on PV panels, temperature, and wind speed were monitored. Performance metrics, including reference yield, array yield, and performance ratio, among
others, were evaluated. The results demonstrate the potential of the UFRJ campus
as a successful example of GD and encourage the development of the technology in
the region.
vii
Sumário
Lista de Figuras x
1 Introdução 1
1.1 Objetivos . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2
1.2 Metodologia . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2
1.3 Organização do trabalho . . . . . . . . . . . . . . . . . . . . . . . . . 3
2 Conceitos Básicos 4
2.1 Energia Solar . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 4
2.1.1 Geometria Solar . . . . . . . . . . . . . . . . . . . . . . . . . . 5
2.2 Radiação Solar . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 7
2.3 Sistemas Fotovoltaicos . . . . . . . . . . . . . . . . . . . . . . . . . . 9
2.3.1 Efeito Fotovoltaico . . . . . . . . . . . . . . . . . . . . . . . . 9
2.3.2 Semicondutores . . . . . . . . . . . . . . . . . . . . . . . . . . 9
2.3.3 Célula Fotovoltaica . . . . . . . . . . . . . . . . . . . . . . . . 10
2.3.4 Características Elétricas . . . . . . . . . . . . . . . . . . . . . 10
2.3.5 Associação de células e módulos fotovoltaicos . . . . . . . . . 11
2.4 Índices de Mérito . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 14
2.4.1 Rendimento . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
2.4.2 Taxa de Desempenho (PR - Performance Ratio) . . . . . . . . 15
2.4.3 Fator de Capacidade (CF - Capacity Factor ) . . . . . . . . . . 15
2.4.4 Perdas Específicas da Planta . . . . . . . . . . . . . . . . . . . 16
2.4.5 Eficiência . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
3 Descrição do Estacionamento Solar da UFRJ 18
3.1 Fundo Verde da UFRJ . . . . . . . . . . . . . . . . . . . . . . . . . . 19
3.1.1 Impacto Acadêmico e Social . . . . . . . . . . . . . . . . . . . 19
3.1.2 Investimentos em Energia Fotovoltaica . . . . . . . . . . . . . 19
3.2 Arranjo Fotovoltaico . . . . . . . . . . . . . . . . . . . . . . . . . . . 21
3.3 Estrutura metálica . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
3.4 Inversores . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
viii
3.5 Datalogger . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
3.6 Medidor de Energia . . . . . . . . . . . . . . . . . . . . . . . . . . . . 23
3.7 Estação Meteorológica . . . . . . . . . . . . . . . . . . . . . . . . . . 24
3.8 Diagrama Unifilar . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 25
3.8.1 Componentes Principais . . . . . . . . . . . . . . . . . . . . . 25
3.9 Obra do Estacionamento Solar . . . . . . . . . . . . . . . . . . . . . . 27
4 Coleta, Tratamento e Disponibilização dos Dados 28
4.1 Coleta de Dados . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 28
4.2 Tratamento dos Dados . . . . . . . . . . . . . . . . . . . . . . . . . . 28
4.3 Armazenamento de Dados no Zenodo . . . . . . . . . . . . . . . . . . 30
5 Análise de Desempenho do Sistema Fotovoltaico 31
5.1 Radiação Solar . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
5.2 Temperatura . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 32
5.3 Comportamento da Temperatura para Diferentes níveis de radiação . 33
5.4 Rendimento Final e Rendimento de Referencia . . . . . . . . . . . . . 35
5.5 Eficiência do Sistema . . . . . . . . . . . . . . . . . . . . . . . . . . . 37
5.6 Taxa de Desempenho e Fator de Capacidade . . . . . . . . . . . . . . 39
5.7 Dados Mensais do Sistema . . . . . . . . . . . . . . . . . . . . . . . . 39
5.8 Comparação com Outros Sistemas FV . . . . . . . . . . . . . . . . . 42
5.8.1 Rendimento Final . . . . . . . . . . . . . . . . . . . . . . . . . 42
5.8.2 Taxa de Desempenho . . . . . . . . . . . . . . . . . . . . . . . 42
6 Conclusão 43
Referências Bibliográficas 45
7 Anexos 49
ix
Lista de Figuras
2.1 Geometria do sistema Sol-Terra. Fonte: [4] . . . . . . . . . . . . . . . 5
2.2 (a) Geometria solar com os principais ângulos. (b) Vista plana mostrando o Ângulo Azimutal do Sol. Fonte: [6] . . . . . . . . . . . . . . 5
2.3 Componentes da radiação solar sobre um painel fotovoltaico. Fonte: [7] 7
2.4 Variação da irradiação no hemisfério sul ao longo do ano. Fonte: [6] . 9
2.5 Semicondutor do tipo P. Fonte: [8] . . . . . . . . . . . . . . . . . . . 10
2.6 Semicondutor do tipo N. Fonte: [8] . . . . . . . . . . . . . . . . . . . 10
2.7 Curva I − V e P − V de um módulo fotovoltaico. Fonte: [6] . . . . . 11
2.8 Associação em série dos módulos fotovoltaicos. Fonte: [4] . . . . . . . 12
2.9 Associação em paralelo dos módulos fotovoltaicos. Fonte: [4] . . . . . 12
2.10 Curva I − V para diferentes níveis de radiação. Fonte: [6] . . . . . . 13
2.11 Curva I − V para modulo à 0 ◦C e 75 ◦C. Fonte: [6] . . . . . . . . . . 13
3.1 Estacionamento Solar. Fonte: Elaboração Própria . . . . . . . . . . . 18
3.2 Mapa da Cidade Universitária da UFRJ com a localização dos sistema
fotovoltaicos. Fonte: [17] . . . . . . . . . . . . . . . . . . . . . . . . . 20
3.3 Curva I-V para diferentes níveis de radiação e temperatura. Fonte: [18] 22
3.4 Estrutura para estacionamento de carros. Fonte: [19] . . . . . . . . . 22
3.5 Medidor de energia ION8650A. Fonte: [22] . . . . . . . . . . . . . . . 24
3.6 Sensor de temperatura ambiente Campbell, modelo CS215. Fonte: [23] 24
3.7 Sensor de temperatura dos módulos solares Campbell, modelo 110PV.
Fonte: [24] . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 24
3.8 Piranômetro da marca Campbell, modelo CMP21. Fonte: [25] . . . . 25
3.9 Anemômetro da marca Campbell, modelo 03101-L. Fonte: [26] . . . . 25
3.10 Datalogger da marca Delta Ohm, modelo HD32MT. Fonte: [27] . . . 25
3.11 Estacionamento solar antes e após a obra. Fonte: Elaboração Própria 27
5.1 Média mensal da radiação solar diária e temperatura ambiente. Fonte:
Elaboração Própria . . . . . . . . . . . . . . . . . . . . . . . . . . . . 31
5.2 Temperatura média mensal. Fonte: Elaboração Própria . . . . . . . . 33
5.3 Temperatura média mensal. Fonte: Elaboração Própria . . . . . . . . 34
x
5.4 Média diária ao longo do período de monitoramento para o rendimento final e rendimento de referência. Fonte: Elaboração Própria . . 35
5.5 Média diária mensal da eficiência do sistema. Fonte: Elaboração
Própria . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 37
5.6 Eficiência do Sistema x Temperatura do Módulo FV. Fonte: Elaboração Própria . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 38
5.7 Eficiência do Sistema x Radiação. Fonte: Elaboração Própria . . . . . 38
5.8 Taxa de desempenho e fator de capacidade durante o período monitorado. Fonte: Elaboração Própria . . . . . . . . . . . . . . . . . . . 39
xi
Capítulo 1
Introdução
A energia é um dos pilares fundamentais para o desenvolvimento sustentável de
uma sociedade moderna. O desenvolvimento sustentável pode ser entendido como
aquele que atende as necessidades do presente, sem comprometer a capacidade das
gerações futuras satisfazerem as suas próprias necessidades. Uma das questões inerentes ao desenvolvimento sustentável está na busca por novas tecnologias e o aproveitamento dos recursos energéticos naturais [1].
O Brasil destaca-se por ser um país com alto percentual de fontes renováveis na
matriz elétrica, com níveis acima de 70% ao longo do últimos 20 anos. Entretanto,
a parcela de renováveis da matriz elétrica brasileira é historicamente dependente
das fontes hidráulicas. Entre os anos de 2011 e 2014, observou-se uma redução da
parcela de renováveis na oferta total devido à situação hidrológica enfrentada pelo
país durante o período, tendo uma redução de 88% em 2011 para 74% em 2014 [2].
Diante da necessidade de garantir um futuro energético sustentável, é fundamental
investigar as fontes de energia renováveis. A energia solar tem se destacado como
uma das alternativas mais promissoras. Nos últimos anos, essa fonte de energia
apresentou o maior crescimento em capacidade instalada em escala global, impulsionado pela redução dos custos e pela ausência de emissões de gases de efeito estufa
durante seu funcionamento. Essas características a tornam uma opção vantajosa
tanto do ponto de vista ambiental quanto econômico. Além disso, a energia solar converte diretamente a luz solar em eletricidade, oferecendo uma solução limpa
e abundante. Diversificar as fontes de energia é essencial para aumentar a segurança energética e reduzir a dependência de recursos hídricos, que são suscetíveis às
mudanças climáticas e às variações sazonais [3].
O Programa Fundo Verde da UFRJ foi criado pelo decreto estadual N°
43.903/2012. O fundo é uma iniciativa estratégica voltada para a promoção da
1
sustentabilidade e a inovação em energia no campus da Cidade Universitária da
UFRJ. Este programa tem como objetivo a elaboração de projetos de infraestrutura
sustentável nos setores de geração e racionalização do uso de energia e de mobilidade urbana. Através de seus investimentos em energia renovável e na promoção da
pesquisa e capacitação acadêmica, o fundo não apenas aprimora a infraestrutura da
universidade, mas também prepara uma nova geração de profissionais conscientes e
comprometidos com a sustentabilidade. O projeto do estacionamento solar fotovoltaico, com uma capacidade instalada de 99 kWp, é um dos exemplos concretos dos
esforços do programa para transformar o campus em um modelo de sustentabilidade
e eficiência energética.
1.1 Objetivos
O principal objetivo deste trabalho é apresentar uma análise detalhada do desempenho do sistema fotovoltaico instalado no estacionamento do Centro de Tecnologia
da UFRJ, que foi monitorado de janeiro de 2016 até novembro de 2019. Durante este
período, diversos parâmetros foram acompanhados, incluindo a geração de energia,
a radiação solar incidente nos painéis fotovoltaico (PV), a temperatura ambiente e
a velocidade do vento. A avaliação inclui métricas como rendimento de referência,
rendimento do conjunto e taxa de desempenho, proporcionando uma compreensão
abrangente da eficácia e da eficiência do sistema.
1.2 Metodologia
Para alcançar os objetivos estabelecidos, inicialmente, coletaram-se os dados do
sistema fotovoltaico. Os dados extraídos da estação meteorológica eram registrados
em intervalos de um minuto e possuíam registros de radiação solar, velocidade do
vento, temperatura ambiente e temperatura dos módulos. Além disso, utilizaramse os dados do medidor de energia para extrair os dados de energia na saída do
sistema fotovoltaico e do Prolog para extrair os dados na saída dos inversores. O
estudo abrange o período de janeiro de 2016 a novembro de 2019. Esse intervalo foi
selecionado devido à indisponibilidade de dados após novembro de 2020.
Para a análise dos dados, utilizamos o Python 3.11.3 com as bibliotecas Pandas,
NumPy e Matplotlib. A biblioteca Pandas, empregada na manipulação e análise de
dados tabulares, facilitou a limpeza e preparação dos dados. NumPy, utilizado para
operações numéricas e estatísticas, possibilitou os cálculos dos índices de mérito,
fundamentais na avaliação do desempenho do sistema durante o período de estudo.
A visualização dos dados ocorreu por meio da biblioteca Matplotlib.
2
1.3 Organização do trabalho
No Capítulo 1, o projeto é apresentado, ressaltando sua motivação, objetivos e as
metodologias empregadas para alcançá-los.
No Capítulo 2, é realizada a apresentação dos conceitos fundamentais relacionados
a energia solar, radiação solar, efeito fotovoltaico e índices de mérito, estabelecendo
a base teórica necessária para o entendimento do trabalho.
No Capítulo 3, é fornecida uma análise detalhada do sistema fotovoltaico instalado
no estacionamento do Centro de Tecnologia da UFRJ e apresentado o Fundo Verde.
No Capítulo 4, é apresentada o processos de coleta, tratamento e disponibilização
dos dados do operação do sistema fotovoltaico em estudo.
No Capítulo 5, é apresentada a análise de desempenho proposta para estudo, juntamente com comparações realizadas com outros sistemas fotovoltaicos em diversas
localidades ao redor do mundo.
Por fim, no Capítulo 6, serão apresentadas as conclusões do estudo, incluindo as
limitações encontradas e possíveis temas para futuras pesquisas.
3
Capítulo 2
Conceitos Básicos
Este capítulo introduz conceitos que permitem a compreensão do estudo proposto.
Uma vez que o nosso objetivo é a analise do desempenho de um sistema fotovoltaico, é necessário introduzir alguns conceitos básicos. Na seção 2.1, é apresentado
o conceito de energia solar e a geometria do Sol. Na seção 2.2 é apresentado a radiação solar. Na seção 2.3 são aprofundados os principais conceitos sobre os sistemas
fotovoltaicos. Por fim, na seção 2.4 é abordado o conceito dos índices de mérito.
2.1 Energia Solar
O Sol é a principal fonte de energia para a Terra, sendo fundamental para a manutenção da vida. A radiação solar é uma fonte energética inesgotável em escala
humana. Dessa forma, a exploração da energia solar, seja na forma de energia térmica ou elétrica, é uma excelente alternativa para atender às necessidades energéticas
humanas [4].
No movimento anual da terra ao redor do sol, ela contorna em uma trajetória
elíptica de excentricidade ϵ ≈ 1, 7%. O seu eixo, em relação ao plano normal a
elipse, apresenta uma inclinação de ± 23, 45◦
, chamada de declinação solar (δ),
como ilustrado na Figura 2.1. O movimento de translação junto com a declinação
solar, dão origem as estações do ano [4].
4
Figura 2.1: Geometria do sistema Sol-Terra. Fonte: [4]
2.1.1 Geometria Solar
O desempenho dos painéis fotovoltaicos é fortemente influenciado pela geometria
solar, que determina a quantidade de radiação solar incidente sobre a superfície dos
painéis. A compreensão dos ângulos solares é crucial para otimizar a eficiência na
captação da energia solar. Os principais ângulos da geometria solar são: o ângulo
de incidência, o ângulo zenital, elevação solar, o ângulo de inclinação, o ângulo de
azimute e o ângulo horário [4, 5].
Figura 2.2: (a) Geometria solar com os principais ângulos. (b) Vista plana mostrando o Ângulo Azimutal do Sol. Fonte: [6]
1. Ângulo de Zenital (θZ): É o ângulo entre os raios solares e a vertical do local
(Zênite). Ele complementa o ângulo de elevação e é um dos parâmetros mais
fundamentais na geometria solar, pois ajuda a determinar a posição do sol
no céu. A relação entre o ângulo zenital e outros ângulos solares é dada pela
5
equação 2.1 [4].
cos(θz) = sin(ϕ) sin(δ) + cos(ϕ) cos(δ) cos(ω) (2.1)
Onde, ϕ é a latitude do local.
2. Elevação Solar (αS): É o ângulo formado entre a linha do horizonte e os raios
de sol. Ele é o complemento do ângulo zenital como mostrado na equação 2.2
[4].
αS = 90◦ − θz (2.2)
Este ângulo é importante para determinar a quantidade de radiação solar
disponível em diferentes horários do dia e em diferentes épocas do ano.
3. Ângulo Azimutal do Sol (γs): É o ângulo entre a projeção da direção do sol no
plano horizontal e a direção Norte-Sul (horizonte do observador). O azimute
solar varia ao longo do dia e é essencial para determinar a orientação ideal dos
painéis fotovoltaicos [4].
4. Ângulo Azimutal da Superfície (γ): É o ângulo entre a projeção no plano
horizontal da normal à superfície e o meridiano local, sendo zero para o sul,
negativo para leste e positivo para oeste [6].
−180◦ ≤ γ ≤ 180◦
(2.3)
5. Inclinação da Superfície de Captação (β): É formado pelo ângulo entre o plano
da superfície e o plano horizontal.
6. Ângulo de Incidência (θ): É o ângulo entre a radiação solar direta e a normal
à superfície do painel fotovoltaico. Este ângulo é crucial, pois a eficiência
da conversão da energia solar em elétrica é máxima quando os raios solares
incidem perpendicularmente à superfície do painel [4].
7. Ângulo Horário do Sol (ω) O ângulo horário (ω) é o ângulo entre o meridiano
do local e o meridiano solar, medido no plano equatorial. Ele varia 15 graus
por hora, sendo 0° ao meio-dia solar, negativo antes do meio-dia e positivo
após [4].
ω = 15◦ × (tsolar − 12) (2.4)
onde tsolar é o tempo solar em horas.
6
2.2 Radiação Solar
O termo radiação solar é utilizado de forma ampla e pode ser especificado em
termos de fluxo de potência, conhecido como irradiância solar, ou em termos de
energia por unidade de área, denominado irradiação solar. A irradiância solar que
atinge a Terra é chamada de irradiância extraterrestre.
Figura 2.3: Componentes da radiação solar sobre um painel fotovoltaico. Fonte: [7]
A irradiância solar incidente em uma superfície é composta por suas componentes
direta e difusa. A irradiância solar direta incide na direção da componente normal a
superfície e o Sol, representando a parcela da radiação que não sofreu processos radiativos de absorção e espalhamento na atmosfera. A parcela difusa inclui a radiação
proveniente de todas as demais direções, resultante do espalhamento pelos gases e
partículas presentes na atmosfera. Na Figura 2.3 é possível observar as componentes
da radiação solar [4, 7].
Podemos decompor a irradiação da seguintes maneira:
• Irradiância extraterrestre (G0): Representa a taxa de energia incidente por
unidade de área em um plano horizontal imaginário situado no topo da atmosfera.
7
• Irradiância no plano inclinado (Gi): É a taxa de energia total por unidade
de área incidente sobre um plano inclinado na latitude do local em relação à
superfície da Terra.
• Irradiância direta normal (Gn): Representa a parcela de energia por unidade
de área proveniente diretamente do Sol que incide perpendicularmente à superfície.
• Irradiância difusa horizontal (Gdif ): É a taxa de energia incidente sobre uma
superfície horizontal por unidade de área, decorrente do espalhamento do feixe
solar direto pelos constituintes atmosféricos.
• Irradiância direta horizontal (Gdir): É a taxa de energia por unidade de área
do feixe solar direto numa superfície horizontal.
Gdir = Gn · cos(θz) (2.5)
• Irradiância global horizontal (G): É a taxa de energia total por unidade de
área incidente numa superfície horizontal.
G = Gdif + Gdir = Gdif + Gn · cos(θz) (2.6)
Onde θz é o ângulo zenital.
A constante solar I0 é definida como o valor da irradiância extraterrestre que
incide sobre uma superfície perpendicular aos raios solares na distância média entre
a Terra e o Sol, com um valor aproximado de 1.367 W/m2
. Devido à excentricidade
do movimento elíptico da Terra, esse valor de irradiância efetiva (I0,ef ) varia ao longo
do ano conforme ilustrado na Figura 2.4, e pode ser determinada pela equação 2.7,
atingindo um mínimo de 1.322 W/m2
[4].
8
Figura 2.4: Variação da irradiação no hemisfério sul ao longo do ano. Fonte: [6]
I0,ef = I0 ·

1 + 0, 033 cos 
360
365, 25
n
 (2.7)
Onde, I0 é constante solar e n é o dia de acordo com o calendário juliano.
2.3 Sistemas Fotovoltaicos
2.3.1 Efeito Fotovoltaico
Histórico e Descoberta
O efeito fotovoltaico foi descoberto em 1839 por Becquerel. As primeiras células
fotovoltaicas foram fabricadas em selênio por C. E. Frits em 1883. Apenas em 1950,
foram fabricados nos Laboratórios Bell, as primeiras células fotovoltaicas utilizando
material semicondutor. Estas células foram desenvolvidas com base em laminas de
silício cristalino e possuíam eficiência de 6%, com potência de 5mW e área de 2 cm2
[4].
A radiação solar incidente pode ser caracterizada como discreta unidades de
energias chamadas fótons. A energia do fóton é função da frequência de radiação
(v) e da constante de Planck (h) como mostrado na equação 2.8 [6].
Ef = hv (2.8)
2.3.2 Semicondutores
A indústria eletrônica foi revolucionada pelos semicondutores, que, apesar de não
conduzirem corrente elétrica tão bem quanto os metais, podem controlar eficiente9
mente o fluxo de corrente em dispositivos pequenos. Em semicondutores intrínsecos,
as bandas de condução e valência têm energias próximas, permitindo que elétrons
se movam para a banda de condução quando aquecidos, diminuindo a resistência do
material com o aumento da temperatura [8].
A condutividade dos semicondutores pode ser aprimorada pela dopagem, que
adiciona elétrons à banda de condução ou remove elétrons da banda de valência,
criando semicondutores extrínsecos [8].
Figura 2.5: Semicondutor do
tipo P. Fonte: [8]
Figura 2.6: Semicondutor do
tipo N. Fonte: [8]
Os semicondutores do tipo P são aqueles que possuem ausência de elétrons, essa
ausência equivale a presença de "buracos", como ilustrado na Figura 2.5. Os semicondutores do tipo N são aqueles que possuem elétrons em excesso como ilustrado
na Figura 2.6.
2.3.3 Célula Fotovoltaica
A energia solar fotovoltaica é a energia obtida através da conversão direta de luz
em eletricidade. Esse fenômeno é chamado de efeito fotovoltaico. A célula fotovoltaica é um componente fabricado com material semicondutor e é o componente
responsável pelo processo de conversão.
Os conversores fotovoltaicos são componentes semicondutores que convertem uma
parcela da radiação solar incidente no painel em energia elétrica [6].
2.3.4 Características Elétricas
Curva I − V
A corrente elétrica em uma célula fotovoltaica pode ser considerada como a soma
da corrente de uma junção pn com a corrente gerada pelos fótons absorvidos da
10
radiação solar. A curva I −V é caracterizada por esta corrente em função da tensão
no dispositivo [4].
I = IL − I0

exp 
qV
nkT 
− 1

(2.9)
Figura 2.7: Curva I − V e P − V de um módulo fotovoltaico. Fonte: [6]
Os principais parâmetros das curvas apresentadas na Figura 2.7 são ISC que é
a corrente de curto-circuito, VOC representa a tensão de circuito aberto, Pmp é a
potência máxima que o sistema pode atingir, Vmp refere-se à tensão no ponto de
máxima potência e Imp indica a corrente no ponto de máxima potência.
2.3.5 Associação de células e módulos fotovoltaicos
Os módulos são construído de células, e vários módulos são utilizados em arranjos.
Cada módulo podem ter células conectadas em combinações de série e paralelo para
obter a corrente e a tensão desejadas. Da mesma forma, arranjos de módulos podem
ser organizados em série e paralelo. Para módulos ou células conectados em série,
as tensões são somadas. Quando conectados em paralelo, as correntes são somadas
como mostrada na Figura 2.8 e 2.9 [6].
11
Figura 2.8: Associação em série dos módulos fotovoltaicos. Fonte: [4]
Figura 2.9: Associação em paralelo dos módulos fotovoltaicos. Fonte: [4]
Influência da Radiação
A Figura 2.10 representa o perfil da curva I − V de um modulo fotovoltaico
operando em uma temperatura fixa e variando a radiação, além da representação
da curva de máxima potência.
12
Figura 2.10: Curva I − V para diferentes níveis de radiação. Fonte: [6]
A corrente de curto-circuito aumenta linearmente com o nível de radiação, enquanto a tensão aumenta um escala logarítmica com a radiação [6].
Influência da Temperatura
A Figura 2.11 representa o perfil da curva I − V de um modulo fotovoltaico
operando em um nível de radiação.
Figura 2.11: Curva I − V para modulo à 0 ◦C e 75 ◦C. Fonte: [6]
A temperatura ambiente e do modulo se diferem, pois as células FV podem aquecer devido a diversos fatores, como a radiação solar, resistência elétrica e temperatura
ambiente. A medida que a temperatura aumenta, a eficiência dos módulos tende a
13
diminuir, principalmente devido às características dos materiais semicondutores que
compõem as células FV. Esse efeito pode ser atribuído aos seguintes fatores: [9]
• Aumento da resistência: O aumento da resistência elétrica no material semicondutor devido ao aumento de temperatura, resultando em maiores perdas
de energia e na redução da eficiência do sistema.
• Aumento da corrente de fuga: A corrente de fuga é a corrente que flui
através do semicondutor quando não há luz presente. A medida que a temperatura aumenta, tem-se um aumento nas correntes de fuga nas células FV,
causando maiores perdas de energia.
• Mudança na largura de banda: A largura de banda determina o nível de
energia o qual os elétrons podem se mover no material semicondutor, o qual
diminui com o aumento da temperatura, causando uma redução na tensão de
saída do sistema fotovoltaico.
Além disso, um outro fator que explica a redução da eficiência é que a tensão da
célula reduz significadamente com o aumento da temperatura, enquanto a corrente
sofre um aumento desprezível. Um aumento de 100 ◦C uma célula de silício cristalino
produz uma variação de -30% na tensão de circuito aberto e +0.2% na corrente de
curto-circuito [4].
2.4 Índices de Mérito
Os índices de mérito são essenciais na avaliação da eficiência de sistemas fotovoltaicos, permitindo uma comparação precisa entre sistemas que operam em diversas
localizações e configurações. Além de facilitar a comparação, essas métricas desempenham um papel crucial na identificação de problemas potenciais, monitoramento
contínuo do desempenho do sistema ao longo do tempo e otimização das operações
para maximizar a produção de energia [9, 10].
Para avaliar o desempenho de um painel fotovoltaico, será analisado o rendimento
final (Yf ), o rendimento de referência (Yr), o taxa de desempenho (PR), Rendimento
do arranjo (Ya), fator de capacidade (CF), perdas de captura (Lc) e perdas do sistema
(Ls), conforme definido pela Norma IEC 61724 [11]. Além disso, será avaliada a
eficiência do gerador fotovoltaico e do inversor.
14
2.4.1 Rendimento
Rendimento de Referência (Yr - Reference Yield)
O rendimento de referência é a razão entre o total de irradiação solar no painel (Ht),
e a radiação de referência Gref = 1kW/m2
, esse parâmetro representa o número
equivalente de horas por dia em que a irradiância solar está em seu nível máximo
(1kW/m2
). Para calcular o rendimento de referência, utiliza-se a seguinte equação
[12]:
Yr =
Ht
Gref
(2.10)
Rendimento do Arranjo (Ya - Array yield)
O rendimento do painel é definido como a razão entre a energia gerada CC (ECC) e
a potência nominal do sistema fotovoltaico (PG). Isso representa quantas horas por
dia o arranjo opera na máxima potência para gerar energia [12]:
Ya =
ECC
PG
(2.11)
Rendimento Final (Yf - Final Yield)
O rendimento final é definido como a energia energia gerada CA (ECA), dividida
pela potência nominal do sistema fotovoltaico (PG). Para calcular o rendimento de
final, utiliza-se a seguinte equação [12].
Yf =
EAC
PG
(2.12)
2.4.2 Taxa de Desempenho (PR - Performance Ratio)
A taxa de desempenho representa a quantidade de energia solar disponível que foi
convertida em energia elétrica utilizada. O fator de desempenho é a razão entre o
rendimento de final e o rendimento de referência. As perdas típicas de um painel
fotovoltaico são degradação do painel (ηdeg), temperatura (ηtemp), poeira (ηpoeira),
inversor (ηinv) [12, 13].
P R =
Yf
Yr
= ηdeg · ηtemp · ηpoeira · ηinv (2.13)
2.4.3 Fator de Capacidade (CF - Capacity Factor)
O fator de capacidade é definido pela razão entre a geração de energia elétrica efetiva
e a geração de energia teórica se o sistema operasse 24h do dia em sua potência
15
nominal em condição padrão [12].
CF =
ECA
PG · (24 · 365) =
ECA
PG · 8760
(2.14)
2.4.4 Perdas Específicas da Planta
As perdas de energia podem ocorrer em diversos componentes que estão conectados
ao sistema fotovoltaico. As principais perdas são as perdas de captura do arranjo e
perdas do sistemas [14].
Perdas de Captura do Arranjo (LC - Array Capture Losses)
As perdas de captura do arranjo podem ser separadas em perdas de captura térmica
e perda de captura diversas [15].
Lc = Yr − Ya (2.15)
• Perda de Captura Térmica (LCT ): As perdas causadas pela temperatura
da célula acima de 25 °C são chamadas de perdas térmicas [14].
• Perda de Captura Diversa (LCM): As perdas causadas pelo cabeamento,
baixa irradiância, sombreamento, erros de rastreamento de potência máxima,
poeira e perdas geradas pela condução de energia nos módulos fotovoltaicos
[14].
Perdas do sistema (LS - System Losses)
Essas perdas são causadas pelo inversor, condução e perdas dos elementos passivos
do circuito [14].
Ls = Yr − Ya (2.16)
2.4.5 Eficiência
A eficiência de um sistema fotovoltaico é uma medida crucial de seu desempenho.
Dessa forma, vamos avaliar os seguintes rendimentos:
Rendimento do Gerador Fotovoltaico (ηG)
A eficiência do gerador fotovoltaico é uma medida da eficiência com que o sistema
converte a irradiância solar recebida em energia CC.
ηG =
EDC
HG × AG
(2.17)
16
Rendimento do Inversor (ηinv)
A eficiência do inversor é a razão entre a potência CA gerada pelo inversor e a
potência CC gerada pelo sistema fotovoltaico.
ηinv =
EAC
EDC
(2.18)
Rendimento do Sistema (ηsys)
A eficiência do sistema é dada pelo produto da eficiência do módulo fotovoltaico
pela eficiência do inversor.
ηsys = ηG × ηinv (2.19)
17
Capítulo 3
Descrição do Estacionamento Solar
da UFRJ
Um dos projetos de destaque financiados pelo Fundo Verde é o estacionamento
solar, inaugurado em 2016. Com uma capacidade instalada de 99 kWp, este projeto
tem uma geração de energia estimada em 140 MWh anuais. Além de oferecer uma
solução sustentável para a geração de energia, o estacionamento também serve como
uma plataforma prática para a comunidade acadêmica, proporcionando oportunidades para o estudo e o monitoramento em tempo real de sistemas fotovoltaicos.
Figura 3.1: Estacionamento Solar. Fonte: Elaboração Própria
A Figura 3.1 representa o painel fotovoltaico instalado no estacionamento do Centro de Tecnologia da Universidade Federal do Rio de Janeiro (CT-UFRJ) sob a forma
de carpots.
18
3.1 Fundo Verde da UFRJ
O Fundo Verde de Desenvolvimento e Energia para a Cidade Universitária da
Universidade Federal do Rio de Janeiro, também conhecido como Fundo Verde da
UFRJ, é uma iniciativa que visa promover a sustentabilidade e a eficiência energética
no campus da Cidade Universitária da UFRJ. O fundo é um exemplo de como
políticas públicas podem ser direcionadas para o desenvolvimento sustentável e o
uso de energias renováveis em instituições de ensino [16].
3.1.1 Impacto Acadêmico e Social
Até o momento, o Fundo Verde da UFRJ já financiou mais de 80 bolsas para
técnicos administrativos, professores, e estudantes de graduação e pós-graduação.
Esses projetos, majoritariamente voltados para as áreas de energia e mobilidade, não
só fomentam a pesquisa e o desenvolvimento sustentável, mas também capacitam
os alunos a pensar de forma sustentável e eficiente. O treinamento oferecido através
dessas bolsas prepara os alunos para o mercado de trabalho, incorporando o conceito
social da sustentabilidade em suas ações [16].
3.1.2 Investimentos em Energia Fotovoltaica
Desde 2014, o Fundo Verde investiu aproximadamente R$ 8 milhões na instalação
de seis sistemas fotovoltaicos no campus, as quais estão descritas na Tabela 3.1,
somando uma potência total de mais de 800 kWp. Na Figura é possível observar a
localização dos sistema na Cidade Universitária [16].
A escolha pela geração fotovoltaica foi motivada pela baixa necessidade de manutenção e recursos humanos para sua operação. Cada sistema instalado é responsável
por abastecer seu respectivo centro dentro da universidade. Quando a geração de
energia excede o consumo local, um crédito é gerado, permitindo que o valor excedente seja abatido de outras contas da UFRJ [16].
19
Tabela 3.1: Projetos Fotovoltaicos do Fundo Verde. Fonte: [16]
Projeto Ano Potência (kWp) Geração de Energia
Estimada (MWh/ano)
Estacionamento Solar 2016 99,0 140,0
Zona Industrial 2020 192,0 271,0
CT-M 2019 100,0 140,0
CPMR 2021 92,0 128,0
Hospital Universitário 2022 171,6 133,0
CT2 2022 150,0 210,0
Total 804,6 1.022,0
Figura 3.2: Mapa da Cidade Universitária da UFRJ com a localização dos sistema
fotovoltaicos. Fonte: [17]
20
3.2 Arranjo Fotovoltaico
Vinte e dois arranjos de painéis fotovoltaicos foram montados, cada um composto por dezoito módulos policristalinos do modelo KD250GH-4FB2 fabricados
pela Kyocera. No total, o sistema conta com 396 módulos fotovoltaicos instalados,
resultando em uma potência total de 99 kWp. A área ocupada por esses painéis é
de aproximadamente 651,57 m2
.
Tabela 3.2: Especificações do Modulo Fotovoltaico KD250GH-4FB2. Fonte: [18]
Fabricante Kyocera
Modelo KD250GH-4FB2
Especificações Elétricas a 1000 W/m² (STC)
Potência Máxima [W] 250
Tensão de Máxima Potência (Vmp) [V] 29,8
Corrente de Máxima Potência (Imp) [A] 8,39
Tensão de Circuito Aberto (Voc) [V] 36,9
Corrente de Curto Circuito (Isc) [A] 9,09
Eficiência [%] 15,1
Coeficiente de Temperatura da (Voc) [%/°C] -0,36
Coeficiente de Temperatura da (Isc) [%/°C] 0,06
Coeficiente de Temperatura de Potência Máxima [%/°C] -0,46
Características do Módulo
Comprimento [mm] 1662 (± 2,5)
Largura [mm] 990 (± 2,5)
Profundidade (incluindo caixa de junção) [mm] 46
Peso [kg] 20
Células por módulo 60
Tecnologia das Células Policristalino
Dimensões das Células (Quadrado) [mm] 156 x 156
Valores elétricos medidos sob condições padrão de teste (standard test conditions
- STC): radiação de 1.000 W/m2
, massa de ar AM 1,5 e temperatura de célula de
25 ◦C.
21
Figura 3.3: Curva I-V para diferentes níveis de radiação e temperatura. Fonte: [18]
A Figura 3.3 apresenta as curvas I-V do módulo estudado semelhantes as abordados nas seções de conceitos básicos 2.3.5 e 2.3.5.
3.3 Estrutura metálica
Conjuntos de estruturas metálicas, especialmente projetadas para cobrir a área
do estacionamento com vagas de estacionamento padrão, internacionalmente conhecidas como carports, para a fixação dos módulos fotovoltaicos com uma inclinação
de 10◦
e uma orientação de 46◦ para o oeste, fabricadas na Alemanha pela Schletter
com o projeto presente no Anexo B. A inclinação adotada não é a ideal para a localização, que seria de 22◦
, mas foi escolhida para atender aos requisitos arquitetônicos
do projeto.
Figura 3.4: Estrutura para estacionamento de carros. Fonte: [19]
3.4 Inversores
Seis inversores fotovoltaicos do tipo On-Grid, do fabricante Kaco Energy, modelo
Powador 20TL3, com uma potência de saída de 17 kW, trifásicos 380 V/220 V, e dois
conversores de entrada MPPT, 1.000 Vcc - 18,6 A. Esses inversores são responsáveis
por converter a energia gerada pelos módulos fotovoltaicos de corrente contínua
22
(CC) para corrente alternada (CA), adequada para o uso na rede elétrica. Além
disso, a presença de dois rastreadores de ponto de máxima potência (MPPT).
Tabela 3.3: Especificações do inversores Powador 20TL3. Fonte: [20]
Fabricante Kaco
Modelo Powador 20TL3
Características
Entrada CC
Tensão Máxima [V] 1000
Faixa de Operação MPPT [V] 460 - 800
Corrente Máxima [A] 2 x 18.6
Saída CA
Potência Máxima Pca [VA] 17000
Tensão Nominal [V] 380 / 200 VFN
Faixa de Operação [V] 304 - 418
Frequência Nominal [Hz] 60
Faixa de Frequência [Hz] 57 - 65
Corrente Máxima [A] 3 x 24.6
Fator de Potência 0.8
Eficiência [%] 98
3.5 Datalogger
Um datalogger da Kaco Energy, modelo ProLog, para a aquisição e armazenamento dos dados de geração elétrica dos 6 inversores, com interface de comunicação
RS485 e análise de dados via internet. Esse dispositivo é essencial para monitorar
o desempenho do sistema fotovoltaico, permitindo a coleta e o armazenamento contínuos de informações detalhadas sobre a produção de energia. A interface RS485
garante uma comunicação eficiente entre o datalogger e os inversores, enquanto a
capacidade de análise de dados pela internet facilita o acesso remoto e a avaliação
do desempenho do sistema em tempo real [21].
3.6 Medidor de Energia
Um medidor de energia, modelo ION8650A da Schneider, para medir a energia
total proveniente de 6 inversores, acumulada em kWh, com interface de comunicação
RS485 e acesso via internet.
23
Figura 3.5: Medidor de energia ION8650A. Fonte: [22]
3.7 Estação Meteorológica
A estação meteorológica é um componente crucial em sistemas fotovoltaicos, fornecendo dados ambientais vitais para otimizar a eficiência e a operação dos módulos
solares. Fixada em uma das colunas da estrutura metálica dos módulos fotovoltaicos, esta estação é composta por um gabinete metálico e está equipada com um
datalogger Delta Ohm-HD32MT para a aquisição e armazenamento de dados ambientais. Entre os instrumentos presentes estão um piranômetro da marca Campbell,
modelo CMP21, instalado com a mesma inclinação dos painéis solares para medir a
radiação solar incidente, um anemômetro da marca Campbell, modelo 03101-L, para
registrar a velocidade e a direção do vento, além de sensores de temperatura ambiente e dos módulos solares, ambos da marca Campbell, modelos CS215 e 110PV,
respectivamente.
Figura 3.6: Sensor de temperatura ambiente Campbell, modelo
CS215. Fonte: [23]
Figura 3.7: Sensor de temperatura dos módulos solares Campbell, modelo 110PV. Fonte: [24]
24
Figura 3.8: Piranômetro da
marca Campbell, modelo
CMP21. Fonte: [25]
Figura 3.9: Anemômetro da
marca Campbell, modelo 03101-
L. Fonte: [26]
Figura 3.10: Datalogger da marca Delta Ohm, modelo HD32MT. Fonte: [27]
3.8 Diagrama Unifilar
O diagrama unifilar do Anexo A é uma representação esquemática do sistema
de microgeração fotovoltaica com capacidade de 99 kWp. Esse sistema é composto
por 396 módulos fotovoltaicos Kyocera KD 250, organizados em 22 arranjos de 18
módulos em série, instalados sobre uma estrutura de estacionamento. O diagrama
detalha os componentes principais do sistema, suas interconexões e especificações
técnicas.
3.8.1 Componentes Principais
Gerador Fotovoltaico
• Potência Instalada: 99,0 kWp.
• Módulos Fotovoltaicos: 396 módulos Kyocera KD 250.
• Configuração dos Arranjos: 22 arranjos FV de 18 módulos KD 250 em
série.
25
Inversores
O sistema utiliza seis inversores Kaco 20KTL, cada um com capacidade de 17 kW,
conectados em 220/380V.
• INV 01 a INV 06: Cada inversor é conectado a uma String Box, que agrega
as conexões dos módulos fotovoltaicos.
• String Boxes: Seis String Boxes, cada uma agregando um conjunto de módulos conforme a configuração do sistema.
Proteção e Desconexão
• DPS Classe I e II (PRF1 12.5r 3P+N): Dispositivo de proteção contra
surtos.
– Un: 230/400V.
– Up: 1,5kV.
– Imax: 50kA.
• DJ de Desconexão (NG 125N - 80A): Disjuntor de desconexão para
segurança do sistema.
26
3.9 Obra do Estacionamento Solar
Figura 3.11: Estacionamento solar antes e após a obra. Fonte: Elaboração Própria
A Figura 3.11 ilustra o antes e depois da implementação do estacionamento solar.
Na imagem a esquerda, observa-se um estacionamento simples, com piso de terra
batida e veículos expostos ao sol, sem qualquer tipo de cobertura. Na imagem a
direita, nota-se uma transformação significativa: foi instalado um sistema de painéis
solares sobre as vagas, proporcionando sombra e proteção aos veículos.
A instalação do sistema fotovoltaico não só oferece uma solução sustentável para a
geração de energia, mas também melhora o conforto dos usuários, mantendo os veículos protegidos das intempéries. Esta transformação evidencia o impacto positivo
de iniciativas sustentáveis do fundo verde, promovendo tanto a eficiência energética
quanto o bem-estar dos estudantes, professores e funcionários.
27
Capítulo 4
Coleta, Tratamento e
Disponibilização dos Dados
Para realizar a análise de desempenho do sistema fotovoltaico Estacionamento
Solar instalado no campus da UFRJ, foi realizada uma coleta, tratamento e disponibilização dos dados de operação, a fim de possibilitar o presente trabalho e tornar
possível que futuros estudos utilizem o conjunto de dados.
4.1 Coleta de Dados
A coleta de dados brutos foi conduzida por meio de uma colaboração direta com
o escritório do Programa Fundo Verde da UFRJ, possibilitando a restauração e
organização das arquivos históricos de operação do sistema de janeiro de 2016 até
novembro de 2019 para o sistema.
Os dados fotovoltaicos foram extraídos em formato CSV, com base diária e
frequência de aquisição de 15 minutos. Os dados dos inversores, armazenados em
formato TXT, também foram coletados com uma frequência de 15 minutos, mas
organizados em arquivos mensais. Adicionalmente, os dados meteorológicos provenientes da estação meteorológica foram armazenados em formato D32, com uma
frequência de aquisição de 1 minuto e armazenamento diário.
4.2 Tratamento dos Dados
Os dados de operação do sistema foram organizados em dois conjuntos distintos,
ambos no formato Parquet. Esse formato de arquivo foi escolhido por sua eficiência
em armazenamento e processamento de grandes volumes de dados. Ele utiliza compressão de dados colunar, o que reduz o tamanho dos arquivos e acelera a leitura e
28
escrita. Além disso, o Parquet é amplamente suportado por bibliotecas de análise de
dados, como Pandas, tornando-o ideal para manipulação eficiente de conjuntos de
dados grandes e heterogêneos, como os de monitoramento de sistemas fotovoltaicos
[28].
• Dados Semi Estruturados: Esse conjunto contém os dados brutos ajustados
para formatos consistentes e convertidos para o formato Parquet, abrangendo
todas as variáveis coletadas durante o período de monitoramento. Para realizar
essa preparação, foi utilizado um código python presente no Anexo C.
• Dados Limpos: Derivado dos dados brutos, este conjunto inclui apenas os
dados de interesse para esse trabalho, sendo eles:
1. Dados Fotovoltaicos:
Tabela 4.1: Metadado do conjunto de dados fotovoltaicos
Dado Coluna Unidade
Data/Hora datetime -
Energia CC ee_dc Wh
2. Dados da Estação Meteorológicos:
Tabela 4.2: Metadado do conjunto de dados da estação meteorológica
Dado Coluna Unidade
Data/Hora datetime -
Radiação rad W/m2
Temperatura do Módulo temp_modulo ◦C
Temperatura Ambiente temp_ambiente ◦C
Velocidade do Vento wind m/s
3. Dados do Inversor:
Tabela 4.3: Metadado do conjunto de dados do inversor
Dado Coluna Unidade
Data/Hora datetime -
Energia CA ee_ac kWh
29
4.3 Armazenamento de Dados no Zenodo
Após a análise e preparação, os dados gerados foram armazenados no repositório
Zenodo, uma plataforma de acesso aberto que permite o armazenamento de dados
científicos de forma permanente e segura. Essa plataforma é amplamente utilizada
pela comunidade acadêmica e oferece DOI (Digital Object Identifier) para cada
conjunto de dados, garantindo sua rastreabilidade e citação adequada [29].
Dessa forma, os dados do sistema ficam acessíveis possibilitando replicar ou expandir o estudo, promovendo a transparência científica. O conjunto de dados pode
ser acessado através do link https://doi.org/10.5281/zenodo.13334703 [30].
Para facilitar a replicação da análise, foi incluído um código de exemplo está
presente no Anexo D. Este código exemplifica o processo utilizado para a análise
de desempenho do sistema fotovoltaico, demonstrando passo a passo como os dados
foram carregados, transformados e visualizados utilizando as bibliotecas Pandas,
Numpy e Matplotlib.
30
Capítulo 5
Análise de Desempenho do Sistema
Fotovoltaico
5.1 Radiação Solar
O desempenho de sistemas fotovoltaicos está intrinsecamente ligado às condições
meteorológicas, sendo a radiação solar um dos fatores determinantes para o desempenho do sistema [31]. A Figura 5.1 apresenta a radiação solar mensal do sistema
em estudo.
!"'

'
 
"
!"'
'
 
"
!"'
'

 

"

!"'

'
 
"
!"'







""%

""%


	




 #$%&$ !%
◦ 
 #$%&$ !%
Figura 5.1: Média mensal da radiação solar diária e temperatura ambiente. Fonte:
Elaboração Própria
De acordo com os dados coletados pelo piranômetro da estação meteorológica, a
Tabela 5.1 apresenta os valores de radiação média diária e total mensal por ano.
31
Tabela 5.1: Média diária da radiação solar e total acumulado por mês em [kWh/m2
].
Fonte: Elaboração Própria
2016 2017 2018 2019
Diária Mensal Diária Mensal Diária Mensal Diária Mensal
Janeiro 5,35 165,84 6,20 192,18 5,32 165,07 7,25 224,73
Fevereiro 5,92 165,64 6,39 178,86 5,06 141,79 5,30 148,33
Março 5,07 157,14 5,30 164,20 5,48 170,01 5,28 163,61
Abril 4,89 146,84 4,30 129,05 5,16 154,87 5,16 154,82
Maio 3,32 102,77 3,81 118,11 4,22 130,89 4,00 123,95
Junho 3,00 90,03 3,79 113,60 3,22 96,55 4,13 123,86
Julho 3,72 115,43 4,25 131,64 4,07 126,26 4,17 129,25
Agosto 4,50 139,53 3,67 113,66 3,67 113,85 3,98 123,35
Setembro 4,38 131,52 5,82 174,73 5,22 156,51 3,86 115,88
Outubro 4,71 146,00 5,10 158,13 3,96 122,87 5,33 165,19
Novembro 5,30 159,00 5,18 155,55 4,98 149,51 4,40 131,94
Dezembro 5,87 181,98 5,28 163,56 5,98 185,35 − −
Média Anual 4,67 141,81 4,92 149,44 4,69 142,79 4,80 145,89
Total Anual∗ 1.701,71 1.793,26 1.713,54 1.604,90
* Para o ano de 2019, o sistema foi o monitoriado até o mês de novembro
A radiação solar mensal variou de 90,3 kWh/m2
em junho de 2016 até
224,72 kWh/m2
em janeiro de 2019, com média mensal de 144,96 kWh/m2
. A
mediana dos valores foi de 146,84 kWh/m2
e o percentil 75% de 163,90 kWh/m2
.
Os níveis de radiação diária apresentaram uma média de 4,77 kWh/m2
. A mediana indica que metade dos dias registram uma radiação superior a 4,91 kWh/m2
,
enquanto o máximo observado atinge 8,45 kWh/m2
.
5.2 Temperatura
A temperatura média diária ambiente e a temperatura nos módulos fotovoltaicos
ao longo do período monitorado são mostradas na Figura 5.2. A temperatura média
mensal do ambiente variou entre 20,35 ◦C em junho de 2016 e 29,67 ◦C em janeiro
de 2019, enquanto a temperatura dos módulos fotovoltaicos variou entre 21,82 ◦C
em junho de 2016 e 34,94 ◦C em janeiro de 2019, como é possível observar na Tabela
5.2. Esses dados ilustram a variação significativa das temperaturas ao longo do
período de monitoramento, destacando a influência das condições ambientais nas
temperaturas operacionais dos módulos fotovoltaicos.
32
"	
"





"

"


"
"


"
"





"










 !
◦ 
 !!  ! 
Figura 5.2: Temperatura média mensal. Fonte: Elaboração Própria
Tabela 5.2: Média de temperatura ambiente e do modulo fotovoltaico mensal em
◦C. Fonte: Elaboração Própria
2016 2017 2018 2019
Ambiente Modulo Ambiente Modulo Ambiente Modulo Ambiente Modulo
Janeiro 26,82 29,96 28,94 33,62 27,09 30,97 29,67 34,94
Fevereiro 28,29 31,69 28,34 32,06 26,46 29,54 27,56 30,81
Março 27,40 30,29 26,44 29,29 27,41 30,71 26,87 30,07
Abril 27,00 29,44 24,42 26,77 25,13 28,11 26,34 29,20
Maio 22,70 24,35 22,56 24,30 22,91 24,96 24,63 26,82
Junho 20,35 21,82 21,89 23,57 22,13 23,70 23,18 25,16
Julho 21,59 23,28 20,65 22,56 22,25 23,99 21,34 23,07
Agosto 22,28 24,34 20,97 22,68 21,38 23,29 21,37 23,46
Setembro 23,16 25,45 23,62 26,45 23,48 26,22 23,09 25,31
Outubro 24,06 26,78 25,11 27,90 24,14 26,55 25,18 28,39
Novembro 24,81 28,28 24,85 28,07 25,28 28,83 24,69 27,62
Dezembro 27,01 31,25 26,19 29,98 26,89 31,07 − −
Média 24,62 27,24 24,50 27,27 24,55 27,33 24,90 27,71
* Para o ano de 2019, o sistema foi o monitoriado até o mês de novembro
5.3 Comportamento da Temperatura para Diferentes níveis de radiação
Durante o período de análise, o mês de janeiro de 2019 se destacou por apresentar
as temperaturas mais elevadas. Nesse contexto, propomos uma análise minuciosa
do comportamento das temperaturas e da radiação solar, considerando um intervalo
33
de amostragem de cada 15 minutos, conforme registrado pelo sistema meteorológico
em questão. Com base nos dados fornecidos por este sistema, foi possível elaborar a
Tabela 5.3, que apresenta os registros de temperatura e radiação solar para o referido
mês.
Tabela 5.3: Temperatura ambiente e do modulo fotovoltaico para diferentes níveis
de radiação solar. Fonte: Elaboração Própria
Radiação
Solar [W/m2
]
Temperatura
Ambiente [◦C]
Temperatura
Modulo Fotovoltaico [◦C]
Fração da
Radiação (%)
0-100 28,0 28,0 22,3
100-200 29,9 32,3 7,7
200-300 30,4 34,9 6,2
300-400 30,8 36,9 5,9
400-500 31,0 39,2 6,1
500-600 31,6 42,0 6,5
600-700 32,0 44,4 7,2
700-800 32,6 46,7 6,7
800-900 33,3 56,1 8,0
900-1000 34,0 53,6 11,4
1000-1100 34,2 50,2 11,3
1100-1200 33,7 48,8 0,6
1200-1300 32,8 47,9 0,1
A radiação solar total incidente estava abaixo de 1200 W/m², com a temperatura
média máxima do módulo atingindo 55 ◦C. A Figura 5.3 apresenta a temperatura
ambiente e do módulo solar em relação aos diferentes níveis de radiação solar incidente. As temperaturas ambiente e dos módulos tende a subir conforme o nível de
radiação solar aumenta [13].
  	 
   







◦ 



Figura 5.3: Temperatura média mensal. Fonte: Elaboração Própria
34
5.4 Rendimento Final e Rendimento de Referencia
A Figura 5.4 ilustra o histórico mensal de valores de rendimento final e rendimento
de referência para o sistema estudado. O rendimento de referência variou de 3.3−7.25
atingindo seu valor de mínimo em junho de 2016 e máximo em 2019. O rendimento
final entre 2.62 − 5.78 com seus mínimos e máximos na mesma data. Vale ressaltar
que o mês de janeiro de 2019, como exposto no seção 5.2 e 5.3, foi o que apresentou
maior nível de temperatura, e junho 2016 o de menores níveis térmicos. Assim,
indicando que o sistema é afetado pelas condições climáticas.

	












	

















	



















	









!




	




! 
! 
!
Figura 5.4: Média diária ao longo do período de monitoramento para o rendimento
final e rendimento de referência. Fonte: Elaboração Própria
35
Tabela 5.4: Valores mensais e anuais de parâmetros meteorológicos, energias, rendimentos e perdas de energia, índice de desempenho e eficiências. Fonte: Elaboração
Própria
2016 2017 2018 2019
Yr Yf Yr Yf Yr Yf Yr Yf
Janeiro - - 6,20 4,88 5,32 3,87 7,25 5,77
Fevereiro - - 6,39 4,99 5,06 3,64 5,30 4,36
Março 5,07 3,96 - - 5,48 4,08 5,28 4,37
Abril 4,89 3,95 4,23 3,31 5,16 4,00 5,16 4,21
Maio 3,32 2,90 3,81 3,01 4,22 3,48 4,00 3,34
Junho 3,00 2,62 3,79 2,98 - - 4,13 3,35
Julho 3,72 2,63 4,25 3,42 4,07 3,33 4,17 3,27
Agosto 4,50 3,40 3,67 3,00 3,67 3,10 3,98 3,34
Setembro 4,38 3,50 5,82 4,45 5,22 4,40 3,86 3,26
Outubro 4,71 3,76 5,10 4,05 3,96 3,37 5,33 4,40
Novembro 5,30 4,03 5,18 4,01 4,98 4,15 4,40 3,70
Dezembro 5,87 4,49 5,28 3,87 5,98 4,85 - -
36
5.5 Eficiência do Sistema
Na Figura 5.5 é possível observar os valores de eficiência do sistema separados
por estação do ano. Os valores variaram entre 10,6% e 13,1%, com seus valores de
mínimo e máximo em julho de 2016 e maio de 2016 respectivamente. A eficiência
média do sistema durante o período de analise foi de 11,9%.
Figura 5.5: Média diária mensal da eficiência do sistema. Fonte: Elaboração Própria
De acordo com a Figura 5.5, observa-se uma relação inversa entre a temperatura
do módulo e a eficiência do sistema fotovoltaico. Nos períodos em que a temperatura
do módulo aumenta (linha vermelha), a eficiência do sistema tende a diminuir (linha
azul).
Além disso, pode observar-se uma variação sazonal no comportamento. A temperatura do módulo é mais alta durante o verão, o que corresponde aos pontos mais
baixos na eficiência do sistema. Por exemplo, durante o mês de dezembro de 2017 e
janeiro de 2019, a temperatura do módulo atinge picos acima de 34 ◦C, e a eficiência
cai para cerca de 11-12%. Durante o inverno, a temperatura do módulo é mais
baixa, geralmente abaixo de 30 ◦C, e a eficiência do sistema tende a ser mais alta.
Isso é visível em períodos como junho de 2016 e junho de 2018, onde a eficiência
está em torno de 13-14%.
37
 
  

!" " ◦ 








	
#!
Figura 5.6: Eficiência do Sistema x Temperatura do Módulo FV. Fonte: Elaboração
Própria
Na Figura 5.6 é possível observar uma tendência de queda na eficiência do sistema
a medida o painel fotovoltaico assume temperaturas maiores, como abordado na
seção 2.3.5.
  	 
   
 










! 
Figura 5.7: Eficiência do Sistema x Radiação. Fonte: Elaboração Própria
Ademais, vale ressaltar que que em dias com maio nível de radiação, ocorre uma
queda na taxa de desempenho do sistema devido, principalmente, a diminuição da
eficiência dos módulos como abordado na Seção 2.3.5. Além disso, é possível observar
esse fenômeno na Figura 5.7.
38
5.6 Taxa de Desempenho e Fator de Capacidade
A Figura 5.8 apresenta os valores de média diária por mês para a taxa de desempenho e o fator de capacidade do sistema. A taxa de desempenho variou entre
71,1% e 87,2%, com média em 80,9%. Enquanto o fator de capacidade ficou entre
10,9% e 24,0% com média em 15,7%.
   
 




	







 
 

Figura 5.8: Taxa de desempenho e fator de capacidade durante o período monitorado. Fonte: Elaboração Própria
5.7 Dados Mensais do Sistema
Nas tabelas 5.5, 5.6, 5.7 e 5.8 são apresentadas as médias mensais e a média anual
para os principais indicadores monitorados nesse estudo.
2016
No ano de 2016, o sistema fotovoltaico apresentou uma temperatura média de 24,0 ◦C
e uma radiação solar média de 4,5 kWh/m2
/dia. A média mensal de energia de saída
do módulo (ECC) foi de 353,50 kWh, enquanto a energia de saída do inversor (ECA)
foi de 348,60 kWh. Os rendimentos de referência (Yr) e final (Yf ) foram de 3,50
kWh/kWp/dia e 4,50 kWh/kWp/dia, respectivamente. A taxa de desempenho (PR)
foi de 79,9%, e o fator de capacidade (CF) foi de 14,7%. A eficiência do sistema
ficou em 11,9%, enquanto a eficiência do módulo foi de 12,1%.
39
Tabela 5.5: Média dos dados meteorológicos, energia, índices de mérito e eficiência
do sistema para o ano de 2016. Fonte: Elaboração Própria
Mês Meteorologia Energia Perdas e Rendimentos Eficiência
Ta Hi ECC,d ECA,d Yr,d Yf,d Ya,d LC,d LS,d PR CF ηsys ηinv ηG
Março 27,40 5,10 396,90 391,60 4,00 5,10 4,00 1,10 0,10 78,80 16,50 11,80 98,50 12,00
Abril 27,00 4,90 395,80 390,60 3,90 4,90 4,00 0,90 0,10 80,60 16,40 12,10 98,40 12,20
Maio 22,70 3,30 291,40 287,10 2,90 3,30 2,90 0,40 0,00 87,30 12,10 13,00 98,20 13,30
Junho 20,40 3,00 264,30 260,30 2,60 3,00 2,70 0,30 0,00 86,70 11,00 12,90 98,20 13,20
Julho 21,70 3,70 262,30 258,20 2,60 3,70 2,60 1,00 0,00 71,00 10,90 10,60 98,10 10,80
Agosto 22,20 4,50 345,70 341,10 3,40 4,50 3,50 1,00 0,00 76,80 14,40 11,50 98,30 11,70
Setembro 23,20 4,40 351,70 346,80 3,50 4,40 3,60 0,80 0,00 81,40 14,60 12,20 98,20 12,40
Outubro 24,00 4,60 372,70 367,40 3,70 4,60 3,80 0,90 0,10 81,70 15,50 12,20 98,30 12,40
Novembro 24,80 5,30 404,10 398,60 4,00 5,30 4,10 1,20 0,10 77,90 16,80 11,60 98,30 11,80
Dezembro 27,00 5,90 450,30 444,30 4,50 5,90 4,50 1,30 0,10 77,10 18,70 11,50 98,40 11,70
Média Mensal 24,00 4,50 353,50 348,60 3,50 4,50 3,60 0,90 0,00 79,90 14,70 11,90 98,30 12,10
2017
Em 2017, a temperatura média foi ligeiramente superior, registrando 24,3 ◦C, com
uma radiação solar média de 4,9 kWh/m2
/dia. A energia de saída do módulo aumentou para 383,90 kWh e a do inversor para 378,30 kWh. O rendimento de referência
ficou em 3,80 kWh/kWp/dia, enquanto o rendimento final foi de 4,90 kWh/kWp/dia.
O PR manteve-se estável em 79,5%, e o CF foi de 15,9%. As eficiências do sistema
e do módulo foram de 11,9% e 12,1%, respectivamente.
Tabela 5.6: Média dos dados meteorológicos, energia, índices de mérito e eficiência
do sistema para o ano de 2017. Fonte: Elaboração Própria
Mês Meteorologia Energia Perdas e Rendimentos Eficiência
Ta Hi ECC,d ECA,d Yr,d Yf,d Ya,d LC,d LS,d PR CF ηsys ηinv ηG
Janeiro 28,90 6,20 489,90 483,50 4,90 6,20 4,90 1,30 0,10 79,40 20,30 11,90 98,60 12,10
Fevereiro 28,40 6,40 501,50 495,10 5,00 6,40 5,10 1,30 0,10 78,70 20,80 11,80 98,60 12,00
Abril 24,50 4,20 332,70 328,10 3,30 4,20 3,40 0,90 0,00 79,70 13,80 11,90 98,30 12,10
Maio 22,60 3,80 301,80 297,80 3,00 3,80 3,00 0,80 0,00 79,90 12,50 11,90 98,40 12,10
Junho 21,90 3,80 299,20 295,20 3,00 3,80 3,00 0,80 0,00 79,20 12,40 11,90 98,50 12,00
Julho 20,70 4,20 342,40 338,30 3,40 4,20 3,50 0,80 0,00 81,30 14,20 12,20 98,70 12,40
Agosto 21,00 3,70 306,50 302,40 3,10 3,70 3,10 0,60 0,00 83,70 12,70 12,50 98,20 12,70
Setembro 23,60 5,80 446,60 440,10 4,40 5,80 4,50 1,30 0,10 77,10 18,50 11,50 98,40 11,70
Outubro 25,10 5,10 407,50 400,50 4,00 5,10 4,10 1,00 0,10 81,10 16,90 12,00 97,80 12,30
Novembro 24,80 5,20 403,80 396,90 4,00 5,20 4,10 1,10 0,10 78,90 16,70 11,70 97,90 12,00
Dezembro 26,20 5,30 390,50 383,40 3,90 5,30 3,90 1,30 0,10 75,00 16,10 11,20 98,00 11,40
Média Mensal 24,30 4,90 383,90 378,30 3,80 4,90 3,90 1,00 0,10 79,50 15,90 11,90 98,30 12,10
2018
Durante o ano de 2018, a temperatura média observada foi de 24,8 ◦C, com uma
radiação solar média de 4,8 kWh/m2
/dia. Houve um pequeno aumento na energia
de saída do módulo, que foi de 388,30 kWh, e na energia de saída do inversor, que foi
de 381,60 kWh. O rendimento de referência foi de 3,90 kWh/kWp/dia e o rendimento
40
final foi de 4,80 kWh/kWp/dia. O PR aumentou para 81,1%, e o CF foi de 16,1%.
A eficiência do sistema foi de 12,1%, enquanto a do módulo foi de 12,3%.
Tabela 5.7: Média dos dados meteorológicos, energia, índices de mérito e eficiência
do sistema para o ano de 2018. Fonte: Elaboração Própria
Mês Meteorologia Energia Perdas e Rendimentos Eficiência
Ta Hi ECC,d ECA,d Yr,d Yf,d Ya,d LC,d LS,d PR CF ηsys ηinv ηG
Janeiro 27,10 5,30 390,50 383,60 3,90 5,30 3,90 1,40 0,10 74,10 16,10 11,00 97,90 11,30
Fevereiro 26,50 5,10 369,90 363,30 3,70 5,10 3,70 1,40 0,10 73,60 15,30 11,00 98,00 11,20
Março 27,40 5,50 410,80 403,70 4,10 5,50 4,10 1,30 0,10 75,30 17,00 11,20 98,00 11,40
Abril 25,10 5,20 402,90 395,80 4,00 5,20 4,10 1,10 0,10 77,60 16,70 11,60 98,10 11,80
Maio 22,90 4,20 350,00 344,20 3,50 4,20 3,50 0,70 0,10 82,90 14,50 12,40 98,10 12,60
Julho 22,30 4,10 335,40 329,70 3,30 4,10 3,40 0,70 0,10 82,30 13,90 12,30 98,00 12,50
Agosto 21,40 3,80 320,40 314,70 3,20 3,80 3,20 0,50 0,10 85,90 13,20 12,70 97,40 13,10
Setembro 23,50 5,20 442,40 435,50 4,40 5,20 4,50 0,70 0,10 85,00 18,30 12,70 98,30 12,90
Outubro 24,10 4,00 340,10 333,40 3,40 4,00 3,40 0,50 0,10 86,90 14,00 12,90 97,60 13,20
Novembro 25,30 5,00 421,50 414,30 4,20 5,00 4,30 0,80 0,10 86,00 17,40 12,80 97,90 13,10
Dezembro 26,90 6,00 487,50 479,80 4,80 6,00 4,90 1,10 0,10 82,60 20,20 12,30 98,20 12,50
Média Mensal 24,80 4,80 388,30 381,60 3,90 4,80 3,90 0,90 0,10 81,10 16,10 12,10 98,00 12,30
2019
Em 2019, a temperatura média foi de 24,9 ◦C e a radiação solar média foi de 4,8
kWh/m2
/dia. A média mensal de energia de saída do módulo foi a mais alta dos
quatro anos, com 397,6 kWh, e a energia de saída do inversor foi de 391,60 kWh. O
rendimento de referência foi de 4,00 kWh/kWp/dia e o rendimento final foi de 4,80
kWh/kWp/dia. O PR aumentou significativamente para 83,5%, e o CF subiu para
16,5%. A eficiência do sistema foi de 12,4% e a do módulo foi de 12,7%, indicando
um desempenho aprimorado em relação aos anos anteriores.
Tabela 5.8: Média dos dados meteorológicos, energia, índices de mérito e eficiência
do sistema para o ano de 2019. Fonte: Elaboração Própria
Mês Meteorologia Energia Perdas e Rendimentos Eficiência
Ta Hi ECC,d ECA,d Yr,d Yf,d Ya,d LC,d LS,d PR CF ηsys ηinv ηG
Janeiro 29,70 7,20 579,10 571,20 5,80 7,20 5,80 1,40 0,10 79,80 24,00 12,00 98,60 12,10
Fevereiro 27,50 5,30 435,90 430,10 4,30 5,30 4,40 0,90 0,10 84,40 18,10 12,60 98,50 12,80
Março 26,90 5,30 438,00 432,50 4,40 5,30 4,40 0,90 0,10 83,80 18,20 12,60 98,60 12,70
Abril 26,30 5,20 421,60 416,70 4,20 5,20 4,30 0,90 0,10 82,10 17,50 12,30 98,70 12,50
Maio 24,60 4,00 334,90 330,40 3,30 4,00 3,40 0,60 0,00 84,30 13,90 12,60 98,50 12,80
Junho 23,20 4,10 337,30 331,50 3,30 4,10 3,40 0,70 0,10 81,30 14,00 12,10 98,20 12,40
Julho 21,30 4,10 334,90 329,20 3,30 4,10 3,40 0,80 0,10 81,00 13,90 12,10 98,10 12,30
Agosto 21,40 4,00 336,80 330,90 3,30 4,00 3,40 0,60 0,10 85,10 13,90 12,60 97,40 12,90
Setembro 23,10 3,90 328,60 322,50 3,30 3,90 3,30 0,50 0,10 86,20 13,60 12,80 97,50 13,10
Outubro 25,30 5,40 453,10 446,10 4,50 5,40 4,60 0,80 0,10 84,00 18,80 12,50 98,20 12,80
Novembro 24,70 4,40 373,00 366,00 3,70 4,40 3,80 0,60 0,10 86,00 15,40 12,80 97,60 13,10
Média Mensal 24,90 4,80 397,60 391,60 4,00 4,80 4,00 0,80 0,10 83,50 16,50 12,40 98,20 12,70
41
5.8 Comparação com Outros Sistemas FV
A fim de comparar o sistema em estudos com outros sistemas ao redor do mundo,
utilizaremos as métricas de rendimento final e taxa de desempenho, uma vez que
são medidas normalizadas, tornando-as possíveis de comparação independentemente
da localização da planta [32]. A Tabela 5.9 apresenta os valores os parâmetros de
desempenho para diferentes sistemas.
Tabela 5.9: Média diária do rendimento final e da taxa de desempenho de diferentes
sistemas fotovoltaicos. Fonte: Elaboração Própria
Localização Início de Operação Período de Estudo PR [%] Yf [h/d] Referência
Ilha de Creta, Grécia 2002 2007 67,36 1,90 - 5,00 [12]
Universidade de Batna, Argélia 2003 2013 57,00 3,03 [32]
Universidade de Pristina, Kosovo - abr/2013 - mar/2014 81.50 1,10 - 4,86 [13]
Ramagundam, India - abr/2014 - mar/2015 76,20 1,96 - 5,07 [14]
Universidade Federal de Santa Catarina, Brasil 1997 1997 - 2012 80,00 - [33]
Universidade de Naresuan, Tailândia - nov/2008 - out/2009 73,45 3,84 [34]
Centro de Tecnologia da UFRJ, Brasil 2016 jan/2016 - nov/2019 80,90 3,78 (2,61 - 5,77) Presente Estudo
5.8.1 Rendimento Final
Comparando o rendimento final (Yf ) dos sistemas fotovoltaicos, o sistema do
Centro de Tecnologia da UFRJ destaca-se com um Yf médio diário de 3,78 h/d,
variando entre 2,61 e 5,77 h/d. Em comparação com o sistema da Ilha de Creta,
da Universidade de Batna e da Universidade de Pristina, o estacionamento solar
operou em uma faixa de rendimento mais elevado. Por outro lado, a Universidade
de Naresuan, na Tailândia, possui um Yf de 3,84 h/d, ligeiramente superior ao
sistema da UFRJ. Esses dados ressaltam que o sistema da UFRJ apresenta um
desempenho robusto e competitivo em relação aos demais sistemas analisados.
5.8.2 Taxa de Desempenho
Em relação à taxa de desempenho, o sistema fotovoltaico analisado demonstrou
resultados satisfatórios quando comparado a sistemas de outras regiões, como é
possível observar na Tabela 5.9. O estacionamento solar registrou uma média diária
de 80,9% durante o período de análise. Esse valor supera os níveis observados na
Universidade de Batna, no parque instalado na ilha de Creta, na Universidade de
Naresuan e no parque solar de Ramagundam. O desempenho foi similar ao do
sistema instalado na Universidade de Pristina e ao do Laboratório de Energia Solar
da Universidade Federal de Santa Catarina.
42
Capítulo 6
Conclusão
O sistema fotovoltaico estacionamento solar instalado no campus da Cidade Universitária da Universidade Federal do Rio de Janeiro (UFRJ) como parte do Programa Fundo Verde demonstrou um desempenho robusto e eficiente ao longo do período de análise. Com uma potência instalada de 99 kWp, o sistema foi monitorado
de janeiro de 2016 a novembro de 2019, período durante o qual foram observados
diversos parâmetros, incluindo a geração de energia, radiação solar incidente nos
painéis, temperatura e velocidade do vento.
Os resultados obtidos mostram que o rendimento final (Yf ) médio diário do sistema
foi de 3,78 h/d, com variações entre 2,61 e 5,77 h/d. Comparado a outros sistemas
fotovoltaicos em diferentes regiões do mundo, o desempenho do sistema da UFRJ foi
competitivo, destacando-se especialmente quando comparado a sistemas instalados
em locais como a Ilha de Creta, Universidade de Batna, Universidade de Pristina e
Universidade de Naresuan.
Além disso, a taxa de desempenho (PR) média diária do estacionamento solar foi
de 80,9%, um valor superior aos observados em muitos outros sistemas, como os da
Universidade de Batna, Ilha de Creta, Universidade de Naresuan e parque solar de
Ramagundam. Este desempenho evidencia a eficiência do sistema e a adequação
das condições locais para a geração de energia fotovoltaica.
A análise do sistema fotovoltaico da UFRJ não apenas confirma o potencial do
campus como um exemplo de sucesso na implementação de geração distribuída, mas
também incentiva o desenvolvimento e adoção dessa tecnologia para demais universidades. A experiência adquirida e os dados coletados servem como referência para
futuros projetos de energia sustentável, destacando a importância de investimentos
contínuos em infraestrutura e tecnologia fotovoltaica.
43
Por fim, o sistema fotovoltaico do Fundo Verde da UFRJ provou ser um projeto
eficaz e bem-sucedido, contribuindo significativamente para a geração de energia
limpa e renovável, alinhando-se aos objetivos de sustentabilidade e inovação tecnológica da universidade.
44
Referências Bibliográficas
[1] COMISSÃO MUNDIAL SOBRE O MEIO AMBIENTE E DESENVOLVIMENTO. Nosso futuro comum. 2 ed. Rio de Janeiro, FGV, 1991. ISBN:
BN00144934-6. Tradução de: Our common future.
[2] Relatório Síntese do Balanço Energético Nacional – BEN. EPE,
2023. Disponível em: <https://www.epe.gov.br/sites-pt/
publicacoes-dados-abertos/publicacoes/PublicacoesArquivos/
publicacao-748/topico-681/BEN_S%C3%ADntese_2023_PT.pdf>.
[3] Plano Nacional de Energia, 2050. Empresa de Pesquisa Energética. Brasília: MME/EPE, 2020. Disponível em: <https://www.epe.
gov.br/sites-pt/publicacoes-dados-abertos/publicacoes/
PublicacoesArquivos/publicacao-227/topico-563/Relatorio%
20Final%20do%20PNE%202050.pdf>.
[4] E MARCO ANTONIO GALDINO, J. T. P. Manual de Engenharia para Sistemas
Fotovoltaicos. Cresesb, 2014.
[5] ETUKUDOR, C., OROVWODE, H., WARA, S., et al. “Optimum Tilt and
Azimuth Angles for Solar Photovoltaic Systems in South-West Nigeria”.
In: 2018 IEEE PES/IAS PowerAfrica, pp. 348–353, 2018. doi: 10.1109/
PowerAfrica.2018.8521047.
[6] DUFFIE, J., BECKMAN, W. Solar Engineering of Thermal Processes. Wiley,
2013. ISBN: 9781118415412. Disponível em: <https://books.google.
com.br/books?id=5uDdUfMgXYQC>.
[7] PEREIRA, E. B., MARTINS, F. R., GONÇALVES, A. R., et al. Atlas brasileiro
de energia solar. 2 ed. São José dos Campos, INPE, 2017. Disponível em:
<http://doi.org/10.34024/978851700089>.
[8] ATKINS, P., JONES, L., LAVERMAN, L. Princípios de Química - 7.ed.: Questionando a Vida Moderna e o Meio Ambiente. Bookman Editora, 2018.
ISBN: 9788582604625. Disponível em: <https://books.google.com.
br/books?id=_05yDwAAQBAJ>.
45
[9] MOTAHHIR, S., ASSAD, M. Performance Enhancement and Control of Photovoltaic Systems. Elsevier Science, 2024. ISBN: 9780443133930. Disponível
em: <https://books.google.com.br/books?id=UBHtEAAAQBAJ>.
[10] MARION, B., ADELSTEIN, J., BOYLE, K., et al. “Performance parameters for
grid-connected PV systems”, pp. 1601–1606, 2005. doi: 10.1109/PVSC.
2005.1488451.
[11] CODE, P. “Photovoltaic system performance monitoring–Guidelines for measurement, data exchange and analysis”, 1998.
[12] KYMAKIS, E., KALYKAKIS, S., PAPAZOGLOU, T. M. “Performance analysis of a grid connected photovoltaic park on the island of Crete”, Energy
Conversion and Management, v. 50, n. 3, pp. 433–438, 2009. ISSN:
0196-8904. doi: https://doi.org/10.1016/j.enconman.2008.12.009. Disponível em: <https://www.sciencedirect.com/science/article/pii/
S0196890408004615>.
[13] KOMONI, V., KRASNIQI, I., LEKAJ, A., et al. “Performance analysis of
3.9 kW grid connected photovoltaic systems in Kosova”. In: 2014 5th
International Renewable Energy Congress (IREC), pp. 1–6, 2014. doi:
10.1109/IREC.2014.6826947.
[14] SHIVA KUMAR, B., SUDHAKAR, K. “Performance evaluation of 10 MW
grid connected solar photovoltaic power plant in India”, Energy Reports,
v. 1, pp. 184–192, 2015. ISSN: 2352-4847. doi: https://doi.org/10.1016/
j.egyr.2015.10.001. Disponível em: <https://www.sciencedirect.com/
science/article/pii/S2352484715000311>.
[15] PADMAVATHI, K., DANIEL, S. A. “Performance analysis of a 3MWp grid
connected solar photovoltaic power plant in India”, Energy for Sustainable
Development, v. 17, n. 6, pp. 615–625, 2013. ISSN: 0973-0826. doi: https:
//doi.org/10.1016/j.esd.2013.09.002. Disponível em: <https://www.
sciencedirect.com/science/article/pii/S0973082613000744>.
[16] UNIVERSIDADE FEDERAL DO RIO DE JANEIRO. “Fundo Verde – UFRJ”.
https://fundoverde.ufrj.br/. Acessado: 2024-06-11.
[17] GOOGLE. “Localização no Google Maps: Cidade Universitária da
UFRJ”. 2024. Disponível em: <https://maps.app.goo.gl/
vKkMAZyWVqw2AhRK7>. [Acessado em: 10-ago-2024].
46
[18] KYOCERA. “Documentação Técnica”. Disponível em: <https:
//www.sicleanenergy.com.au/wp-content/uploads/2013/07/
Kyocera-250w.pdf>. Acesso em: 13 jun. 2024.
[19] GMBH, S. “Layout - Estrutura 36x3 módulos”. Desenho técnico, setembro 2014.
Projeto: 17-L130215-005-KYC.
[20] ENERGY, K. N. “Documentação Técnica”. Disponível em: <https:
//kaco-newenergy.com/index.php?eID=dumpFile&t=f&f=328&token=
a9362f27e0fd9b35671e2a0dd8ae60a22baf3e82>. Acesso em: 13 jun.
2024.
[21] EUROPE SOLAR STORE. Powador-proLOG Kompletthandbuch. Europe Solar Store, no date. Disponível em: <https://www.europe-solarstore.
com/download/kaco/HB_Powador-proLOG_Kompletthandbuch_EN.
pdf>.
[22] ELECTRIC, S. ION8650: Manual Técnico. Disponível em:
<https://www.se.com/br/pt/product/M8650A0C0H6C1B0A/
medidor-ion8650a-9s-5a-60hz-ethmodem-4s3e/>. Acesso em:
13 jun. 2024.
[23] SCIENTIFIC, C. CS215 Thermocouple Input Module. Campbell Scientific,
Inc., . Disponível em: <https://s.campbellsci.com/documents/us/
manuals/cs215.pdf>.
[24] SCIENTIFIC, C. 110PV Temperature Probe: Instruction Manual. Campbell Scientific, Inc., . Disponível em: <https://s.campbellsci.com/
documents/us/manuals/110pv.pdf>. Acesso em: 13 jun. 2024.
[25] CAMPBELL SCIENTIFIC, I. CMP6, CMP11, and CMP21 Pyranometer.
Campbell Scientific, Inc. Disponível em: <https://s.campbellsci.
com/documents/us/manuals/cmp6-cmp11-cmp21.pdf>.
[26] CAMPBELL SCIENTIFIC, I. 03101-L Wind Sentry Anemometer. Campbell
Scientific, Inc., 2015. Disponível em: <https://s.campbellsci.com/
documents/us/manuals/03002.pdf>.
[27] SENSECAP ENVIRONMENTAL. HD32MT-1 Programmable
Data Logger. SenseCAP Environmental, 2024. Disponível em: <https://environmental.senseca.com/product/
hd32mt-1-programmable-data-logger/#tab-dw_tab>.
47
[28] APACHE SOFTWARE FOUNDATION. “Apache Parquet Documentation”. 2024. Disponível em: <https://parquet.apache.org/docs/
overview/>. Acessado: 2024-08-02.
[29] CERN AND OPENAIRE. “Zenodo”. 2024. Disponível em: <https://zenodo.
org>. Acessado: 2024-08-02.
[30] VIDEIRA DANTAS, A. V. “Dados de Operação do Sistema Fotovoltaico Estacionamento Solar da UFRJ de 2016-2019”. ago. 2024. Disponível em:
<https://doi.org/10.5281/zenodo.13334703>.
[31] GHAZI, S., IP, K. “The effect of weather conditions on the efficiency of
PV panels in the southeast of UK”, Renewable Energy, v. 69, pp. 50–
59, 2014. ISSN: 0960-1481. doi: https://doi.org/10.1016/j.renene.2014.
03.018. Disponível em: <https://www.sciencedirect.com/science/
article/pii/S096014811400161X>.
[32] GHOUARI, A., HAMOUDA, C., CHAGHI, A., et al. “Data monitoring and
performance analysis of a 1.6 kWp grid connected PV system in Algeria”,
Int. J. Renew. Energy Res, v. 6, n. 1, pp. 34–42, 2016.
[33] VIANA, T., NASCIMENTO, L. R., MONTENEGRO, A. A., et al. “Sistema
fotovoltaico de 2kWp integrado a edificação: análise do desempenho de
14 anos de operação”. In: IV Congresso Brasileiro de Energia Solar – IV
CBENS e V Conferência Latino Americana da International Solar Energy
Society – ISES, v. 1, pp. 1–8, São Paulo, SP, 2012. ABENS – Associação
Brasileira de Energia Solar.
[34] CHIMTAVEE, A., KETJOY, N. “PV Generator Performance Evaluation and Load Analysis of the PV Microgrid System in Thailand”, Procedia Engineering, v. 32, pp. 384–391, 2012. ISSN: 1877-
7058. doi: https://doi.org/10.1016/j.proeng.2012.01.1283. Disponível em: <https://www.sciencedirect.com/science/article/pii/
S187770581201332X>. ISEEC.
48
Capítulo 7
Anexos
49
SUBESTAÇÃO INTERMEDIÁRIA
Ø 3/8”
MUFLA
3x
400A - 15KV
HH 30A
TRAFO 2
500 KVA
13.8KV
220/380V
400A - 15KV
TRAFO 1
500 KVA
13.8KV
127/22OV
HH 30A
4 x ( 4x 240,0 mm²) EPR - 1KV
4 x ( 4x 240,0 mm²) EPR - 1KV
K K
IN = 1600A IN = 1600A
TIPO: 3VT5716
D3NF
D2NF
3Ø + N + T - 220/ 127V 60 Hz IN = 2250A ICC= 42KA 3Ø + N + T - 380/ 220V 60 Hz IN = 2250A ICC= 42KA
86
63
23
49
86
63
23
49
CHAVE SECCIONADORA
KS 15KV
150A CARGA TOTAL: 48.520VA - CONDUTORES (4X150,0mm²) (3P + N) + 1x95,0mm² (T)
QGDN-2 - 100m
50ACARGA TOTAL: 13.420VA - CONDUTORES (4X16,0mm²) (3P + N) + 1x25,0mm² (T)
QGDN-3 - 150m
100A CARGA TOTAL: 23.960VA - CONDUTORES (4X95,0mm²) (3P + N) + 1x50,0mm² (T)
QGDN-1 - 150m
60ACARGA TOTAL: 4.360VA - CONDUTORES (5X16,0mm²) (3P + N + T)
QGDN-5 - 100m
400A CARGA TOTAL: 99.610VA - CONDUTORES (4X240,0mm²) (3P + N) + 1x120,0mm² (T)
QGDN-6 - 50m
RESERVA
RESERVA
RESERVA
RESERVA
RESERVA
RESERVA
RESERVA
630A
3VT3763
9L
125A
(1)
15kA
10 -350µA
60kA
150@n -8/20µA
(1)
9L
125A
(1)
15kA
10 -350µA
60kA
150@n -8/20µA
(1)
9L
125A
(1)
15kA
10 -350µA
60kA
150@n -8/20µA
(1)
50ACARGA TOTAL: 5.600VA - CONDUTORES (5X16,0mm²) (3P + N + T)
QGDE-2 - 100m
50ACARGA TOTAL: 2.820VA - CONDUTORES (5X10,0mm²) (3P + N + T)
QGDE-3 - 150m
80ACARGA TOTAL: 3.920VA - CONDUTORES (5X16,0mm²) (3P + N + T)
QGDE-1 - 150m
60ACARGA TOTAL: 12.704VA - CONDUTORES (4X35,0mm²) (3P + N) + 1x16mm² (T)
QGDE-4 - 100m
80ACARGA TOTAL: 1.200VA - CONDUTORES (5X16,0mm²) (3P + N + T)
QGDE-5 - 100m
RESERVA
RESERVA
RESERVA
RESERVA
9L
125A
(1)
15kA
10 -350µA
60kA
150@n -8/20µA
(1)
9L
125A
(1)
15kA
10 -350µA
60kA
150@n -8/20µA
(1)
9L
125A
(1)
15kA
10 -350µA
60kA
150@n -8/20µA
(1)
RESERVA
RESERVA
RESERVA
RESERVA
50A 80A 300A CARGA TOTAL: 2.160VA - CONDUTORES (5X10,0mm²) (3P + N +T)
QGDE-6 - 50m
125A 250A 60A
QGDN/E-1 - 150m
100A 150A 40A 1200A NF
3Ø + N + T - 220/ 127V 60 Hz IN = 2250A ICC= 42KA QGDN/E-2 - 100m QGDN/E-3 - 150m QGDN/E-4 - 100m QGDN/E-5 - 100m CARGA TOTAL: 3.600VA - CONDUTORES (5X16,0mm²) (3P + N + T) QGDN/E-6 - 50m
50ACARGA TOTAL: 2.000VA - CONDUTORES (5X10,0mm²) (3P + N +T)
PF-1- AR CONDICIONADO - 50m
PF-2- AR CONDICIONADO - 120m
PF-3- AR CONDICIONADO - 30m
RESERVA
CARGA TOTAL: 7.400VA - CONDUTORES (4X50,0mm²) (3P + N) + 1x25mm² (T)
CARGA TOTAL: 43.400VA - CONDUTORES (4X150,0mm²) (3P + N) + 1x150mm² (T)
CARGA TOTAL: 11.000VA - CONDUTORES (4X95,0mm²) (3P + N) + 1x50mm² (T)
CARGA TOTAL: 37.200VA - CONDUTORES (4X240,0mm²) (3P + N) + 1x120mm² (T)
CARGA TOTAL: 30.000VA - CONDUTORES (4X35,0mm²) (3P + N) + 1x16mm² (T)
CARGA TOTAL: 45.000VA - CONDUTORES (4X240,0mm²) (3P + N) + 1x120mm² (T)
CARGA TOTAL: 9.000VA - CONDUTORES (5X6,0mm²) (3P + N + T)
3(1x210,0 mm²) EPR - 1KV
QUADRO
PARTIDA
AUTOMÁTICA
E
 PROTEÇÃO
IN = 1600A
D1NF
G GERADOR - 500KVA
3Ø - 127/ 220V
QTA
4 x ( 4x 240,0 mm²) EPR - 1KV
QGBT - 220/ 127V
50
51
50
51N
52
MF CUBÍCULO MEDIÇÃO
FATURAMENTO
I
CABINE DE MEDIÇÃO
PROTEÇÃO BLINDADA CONFORME REGULAMENTO LIGHT (RECON MT)
RAMAL SUBTERRÂNEO
LINHA PRINCIPAL RAMAL SUBTERRÂNEO
LINHA RESERVA
ID- IDENTIFICAÇÃO LUMINOSA DO ID DO CABO PRINCIPAL
DE
ID- IDENTIFICAÇÃO LUMINOSA DO ID DO CABO RESERVA
TERMINAÇÃO
 17,5 KV ( 3x)
TERMINAÇÃO
 17,5 KV ( 3x)
CHAVE SECCIONADORA COMANDO EM GRUPO
 17,5 KV - 400A - ABERTURA
EM CARGA
CHAVE SECCIONADORA COMANDO EM GRUPO
 17,5 KV - 400A - ABERTURA
EM CARGA
CHAVE SECCIONADORA COMANDO EM GRUPO
 17,5 KV - 400A - ABERTURA
SEM CARGA
CHAVE SECCIONADORA COMANDO EM GRUPO
 17,5 KV - 400A - ABERTURA
SEM CARGA
TRANSFORMADOR DE
 CORRENTE 150 / 5A
DISJUNTOR PVO BEGHIM
17,5KV - 630A - 350MVA RELÉ DE PROTEÇÃO
SECUNDÁRIA PEXTRON
TERMINAÇÃO
 17,5 KV ( 3x)
3 x ( 1x 70,0 mm²) EPR - 12/ 20KV
SFCR- SISTEMA FOTOVOLTAICO
 CONECTADO A REDE LIGHT-MT
CONFORME PROCEDIMENTO DE CONEXÃO
DE MICRO E MIGERAÇÃO LIGHT IT DTE/DTP 01/12 E REGULAMENTO RECON-MT
VIDE DIAGRAMA
TRIFILAR DETALHADO
W-060115-002-KYC
PROJ.
APROV. DATA
EXEC.
ESCALA
VERIF.
FOLHA
de
N°
TÍTULO:
LOCAL DA INSTALAÇÃO:
CLIENTE:
 DIAGRAMA UNIFILAR DE CONEXÃO DO MICROGERADORFOTOVOLTAICO A REDE EM BAIXA TENSÃO 380/220V
FUNDAÇÃO COOPETEC
Claudio Cittadino
06/01/2015 SEM ESCALA 01 01
André Luis Patrício Claudio Cittadino
Claudio Cittadino
W 060115-001-KYC
KYOCERA SOLAR DO BRASIL
REV. DESCRIÇÃO DATA EXEC. VERIF. APROV.
00 Emissão inicial 06/01/15 André Claudio Claudio
 ILHA DO FUNDÃO - RIO DE JANEIRO -RJ
CHAVE SECCIONADORA
SCHNEIDER - INTERPACT
INS 250- 3 POLOS - 250A-440V
GERADOR FOTOVOLTAICO: POTENCIA INSTALADA 99,0 kWp
 396 MÓDULOS KYOCERA KD 250 INSTALADOS SOBRE ESTRUTURA ESTACIONAMENTO
CONFIGURAÇÃO:22 ARRANJOS FV DE 18 x KD 250 EM SÉRIE
DC1 DC2
INV 01
QDCA
STRING BOX 01
4x18 KD 250
STRING BOX 02
4x18 KD 250
STRING BOX 03
4x18 KD 250
STRING BOX 04
4x18 KD 250
STRING BOX 05
4x18 KD 250
STRING BOX 06
2x18 KD 250
DC1 DC2
INV 03
DC1 DC2
INV 02
DC1 DC2
INV 04 Kaco 20KTL
220/380V
17kW
Kaco 20KTL
220/380V
17kW
Kaco 20KTL
220/380V
17kW
Kaco 20KTL
220/380V
17kW
40A 40A 40A 40A
250A 80A
DPS Classe I e II PRF1 12.5r 3P+N
Un=230/400V Up=1,5kV
Imax=50kA
DJ de Desconexão NG 125N - 80A
SALA ELÉTRICA DOS INVERORES
 EM CONTAINER C/ ISOLAMENTO
TÉRMICO
DC1
INV 05
DC2
Kaco 20KTL
220/380V
17kW
40A
DC1 DC2
INV 06Kaco 20KTL
220/380V
17kW
40A
4 x ( 2x 185,0 mm²) + (1 x 150,0 mm²)
EPR - 1KV
250A
2725
CABOS EM DUTO PEAD SUBTERRÂNEO
9L
125A
(1)
15kA
10 -350µA
60kA
150@n -8/20µA
(1)
9L
125A
(1)
15kA
10 -350µA
60kA
150@n -8/20µA
(1)
9L
125A
(1)
15kA
10 -350µA
60kA
150@n -8/20µA
(1)
630A
3VT3763
630A
3VT3763
630A
3VT3763
250A
2725
250A
2725
250A
2725
250A
2725
RESERVA
RESERVA
250A
2725
250A
2725
QDCA SOLAR: 100 m - 100.000VA - CONDUTORES (8X185,0mm²) (3P + N) + 1x150mm² (T)
QGBT - 380/ 220V
AV. PEDRO CALMON S/N° - ESTACIONAMENTO ANEXO A GEOTECNIA/LNDC
Anexo A - Diagrama Unifilar
VIEW 1 ( 1 : 35 )
A ( 1 : 175 )
B-B ( 1 : 35 )
1
1
2
2
3
3
4
4
A A
B B
C C
D D
SCHLETTER GMBH
GEWERBEGEBIET AN DER B15
ALUSTRASSE 1
83527 KIRCHDORF / HAAG I. OB
GERMANY
WWW.SCHLETTER.DE
REV.
02 01_Rio-de-Janeiro_CS3V-(-10°)-36_B1
DRAWING NAME
Schletter GmbH reserves the right to make modifications to the
construction, choice of materials, specification and design even after
order confirmation and approval and release of the drawings, and those
modifications are permissible provided that such changes serve the
technical improvement of manufacturing or products and are reasonable
for the customer.
SCALE
1:40
DATE
DRAWN BY
AUDITED BY
SCHLETTER JOB NUMBER
RACK INFORMATION
PROJECT ADDRESS PROJ. METHOD
STAMP, SIGNATURE OF APPROVAL
29.09.2014
fisc.ch
140915_2.Änderung
CS3V
20000 Rio de Janeiro
Brasilien
CLIENT
Kyocera Solar do Br
Av. das Américas 20007
22790-851
Brasilien
SHEET SIZE
A3
A
B
B
(4996)
(2734)
(3016)
(2795)
3368 `100
3700 `100
600 `30
10° `1°
2500 `100
2833 `100
(1400)
(500) (1900) (500)
(2900)
2739 `30
(1000) (600)
(600)
(250)
36445 `50
(36890)
281 `2 1100 `2 567 `2 1100 `2 567 `2 1100 `2 281 `2
(1898)
(2868)
(150)(80)
70 `30 5250 `30 5250 `30 5250 `30 5250 `30 5250 `30 5250 `30 5250 `30 70 `30
(6370) (8400) (7350) (8400) (6370)
MODULE
PURLIN
GIRDER
STRUTS
1662x990x46
S2
C1-100
100x100x8
PURLIN DIVISIONS:
LENGTH 1, mm
6370
LENGTH 2, mm
8400
LENGTH 3, mm LENGTH 4, mm
7350 8400
LENGTH 5, mm
6370
NO.
01
DRAWN BY
FiscCh
DESCRIPTION OF REVISION
Stützenabstand 5000mm
DATE
02.10.14
AUDITED BY
02 FiscCh Stützenabstand 5250mm 14.10.14
Anexo B - Projeto da Estrutura dos Módulos
Anexo C - Código para Processamento dos Dados
Brutos
1 import os
2 import glob
3 import pandas as pd
4 import pyarrow as pa
5 import datetime as dt
6 import pyarrow.parquet as pq
7
8 ## Fotovoltaico
9 def process_pv_raw_data(date: dt.date):
10 base_date = date.strftime('%y%m%d')
11 data_base_path = fr"dados_fotovoltaicos\\{date.year}\\{date.month}\\Prolog"
12
13 df = pd.read_csv(
14 os.path.join("dados_brutos\\estacionamento_solar", data_base_path,
,→ f'int_kwr_{base_date}formatado.csv'),
15 sep=';',
16 encoding='latin',
17 )
18 df = df[df.columns[~df.isna().all()]]
19 df = df.drop(columns=[base_date])
20 df = df.iloc[1:]
21 df = df.rename(columns={'Unnamed: 0': 'time'})
22
23 df = df[df['time'] != 'Info']
24 df['date'] = date
25 df['year'] = date.year
26 df['month'] = date.month
27 df['day'] = date.day
28
29 float_columns = ['U_DC_0', 'I_DC_0', 'P_DC_WR', 'U_AC_0', 'I_AC_0',
'P_AC_WR', 'T_WR', 'E_D_WR', 'U_DC_1', 'I_DC_1', 'P_DC_1', 'U_DC_2',
'I_DC_2', 'P_DC_2', 'U_DC_3', 'I_DC_3', 'P_DC_3', 'U_AC_1', 'I_AC_1',
'P_AC_1', 'U_AC_2', 'I_AC_2', 'P_AC_2', 'U_AC_3', 'I_AC_3', 'P_AC_3',
'COS_PHI', 'C_PROT', 'C_PROT_OK', 'C_QUALITY']
,→
,→
,→
,→
30 df[float_columns] = df[float_columns].astype(float)
31
32 table = pa.Table.from_pandas(df)
33 pq.write_to_dataset(
34 table, root_path='raw-data/dados_fotovoltaicos/',
35 basename_template='part-{i}.parquet',
36 partition_cols=['year', 'month', 'day'],
37 existing_data_behavior='overwrite_or_ignore'
38 )
52
1
2 ## Estacao Meteorologica
3 def read_weather_raw_data(f):
4 df = pd.read_csv(f, header=None)
5 df = df[df[0]!='[sdcard]']
6 df = df.iloc[:, 0:6]
7 df.columns = df.iloc[0]
8 df = df.iloc[1:]
9 return df
10
11 def process_weather_raw_data(year: int, month: int):
12 base_date = dt.date(year, month, 1)
13
14 all_files = glob.glob(
15 os.path.join(
16 "dados_brutos\\estacionamento_solar",
,→ fr"dados_meterologicos\\{year}\\{base_date.strftime('%Y-%m')}\\*.LOG\\*.D32"
17 )
18 )
19
20 df = pd.concat(list(map(lambda f: read_weather_raw_data(f), all_files)))
21
22 df['Date'] = pd.to_datetime(df['Date'], format='%y/%m/%d %H:%M:%S')
23
24 df['Piranometro (W/m2)'] = df['Piranometro (W/m2)'].astype(float)
25 df['Temp A (deg C)'] = df['Temp A (deg C)'].astype(float)
26 df['Temp C (deg C)'] = df['Temp C (deg C)'].astype(float)
27 df['Vento (m/s)'] = df['Vento (m/s)'].astype(float)
28 df['Err Code'] = df['Err Code'].astype(str)
29
30 df.columns.name = None
31
32 df['year'] = pd.to_datetime(df['Date']).dt.year
33 df['month'] = pd.to_datetime(df['Date']).dt.month
34 df['day'] = pd.to_datetime(df['Date']).dt.day
35
36 table = pa.Table.from_pandas(df)
37
38 pq.write_to_dataset(
39 table,
40 root_path='raw-data/dados_meterologicos/',
41 basename_template='part-{i}.parquet',
42 partition_cols=['year', 'month', 'day'],
43 existing_data_behavior='overwrite_or_ignore'
44 )
53
1 ## Dados do Inversor
2 def process_inv_raw_data(year: int, month: int):
3 base_date = dt.date(year, month, 1)
4
5 df = pd.read_csv(
6 fr"dados_brutos\\estacionamento_solar\\dados_medidor\\{year}\\Medidor de
,→ energia {year}.{base_date.strftime('%m')}.txt",
7 sep='\t',
8 header=None,
9 dtype='str'
10 )
11 df = df.sort_values(0)
12 df = df.reset_index(drop=True)
13
14 df[0] = df[0].str.replace(':00.000', '')
15 df[0] = pd.to_datetime(df[0], format='%d/%m/%Y %H:%M')
16 df[1] = df[1].str.replace('.', '').astype(float) / 1000
17
18 df = df[[0, 1]]
19
20 df.columns = ['Date/Time','kWh del']
21 df.columns.name = None
22
23 df['year'] = pd.to_datetime(df['Date/Time']).dt.year
24 df['month'] = pd.to_datetime(df['Date/Time']).dt.month
25 df['day'] = pd.to_datetime(df['Date/Time']).dt.day
26
27 table = pa.Table.from_pandas(df)
28
29 pq.write_to_dataset(
30 table,
31 root_path='raw-data/dados_medidor/',
32 basename_template='part-{i}.parquet',
33 partition_cols=['year', 'month', 'day'],
34 existing_data_behavior='overwrite_or_ignore'
35 )
54
Anexo D - Código para Analise dos Dados Limpos
1 import pandas as pd
2 import matplotlib.pyplot as plt
3 import matplotlib.dates as mdates
4 import scienceplots
5 import locale
6
7 # Configurações de estilo de plot
8 plt.style.use(['science', 'no-latex']) # Estilo de gráfico científico sem
,→ uso de LaTeX
9 plt.rcParams['font.serif'] = ['Times New Roman'] # Define a fonte Times New
,→ Roman como padrão para gráficos
10
11 # Define a localidade para exibição de datas em português
12 locale.setlocale(locale.LC_TIME, 'pt_BR.UTF-8')
13
14 # Obtém as cores padrão usadas nos gráficos
15 ALL_COLORS = plt.rcParams['axes.prop_cycle'].by_key()['color']
16
17 # Carrega os dados de meteorologia do arquivo parquet
18 weather_df = pd.read_parquet('clean-data\\weather', columns=['datetime',
,→ 'rad', 'temp_ambiente', 'temp_modulo', 'wind'])
19
20 ##------------------------------
21 ## Temperatura Ambiente / Módulo
22 ##------------------------------
23
24 # Calcula a temperatura média diária (ambiente e módulo)
25 daily_temperature =
weather_df.groupby(weather_df['datetime'].dt.date)[['temp_ambiente',
'temp_modulo']].mean()
,→
,→
26 daily_temperature.index.name = 'date' # Nomeia o índice como 'date'
27 daily_temperature = daily_temperature.reset_index() # Reseta o índice para
,→ facilitar o agrupamento por mês
28
29 # Calcula a média mensal da temperatura ambiente e do módulo
30 temp_monthly_avg =
daily_temperature.groupby(pd.to_datetime(daily_temperature['date']).dt.strftime('%Y-%m'))['temp_modulo']].mean()
,→
,→
31
32 # Cria a figura e o eixo para o gráfico de temperatura
33 fig, ax = plt.subplots(figsize=(10, 5))
34
35 # Define os dados do eixo x (datas formatadas como datetime)
36 xaxis_data = pd.to_datetime(temp_monthly_avg.index)
37
55
38 # Plota as temperaturas média mensal do módulo e ambiente
39 ax.plot(xaxis_data, temp_monthly_avg['temp_modulo'], label='Temperatura do
,→ Módulo')
40 ax.plot(xaxis_data, temp_monthly_avg['temp_ambiente'], label='Temperatura
,→ Ambiente')
41
42 # Define o rótulo do eixo y
43 ax.set_ylabel('Temperatura ($^\circ$C)')
44
45 # Ajusta o layout da figura para evitar sobreposição
46 fig.tight_layout()
47
48 # Formata o eixo x para mostrar os meses e anos
49 fig.gca().xaxis.set_major_formatter(mdates.DateFormatter('%b-%Y'))
50 fig.gca().xaxis.set_major_locator(mdates.MonthLocator(interval=3))
51
52 # Adiciona a legenda na parte inferior do gráfico
53 fig.legend(loc='lower center', ncol=2)
54
55 # Ajusta a exibição das datas no eixo x
56 plt.gcf().autofmt_xdate()
57
58 # Salva o gráfico em formato EPS
59 plt.savefig('temp-media-mensal.eps')
60
61 # Exibe o gráfico
62 plt.show()
63
64 ##--------------------------------------
65 ## Temperatura Ambiente / Radiação Solar
66 ##--------------------------------------
67
68 # Copia o dataframe para uma nova variável
69 met_df = weather_df.copy()
70
71 # Calcula a radiação total mensal e a temperatura ambiente média mensal
72 met_df =
,→ met_df.groupby(pd.to_datetime(met_df['datetime']).dt.strftime('%Y-%m')).agg({
73 'rad': 'sum', # Soma total da radiação
74 'temp_ambiente': 'mean', # Média da temperatura ambiente
75 }).reset_index()
76
77 # Define o índice como 'datetime' para facilitar o plot
78 rad_temp_monthly_avg = met_df.set_index('datetime').copy()
79
80 # Cria a figura e o eixo para o gráfico de radiação e temperatura
81 fig, ax = plt.subplots(figsize=(12, 5))
56
82
83 # Define os dados do eixo x (datas formatadas como datetime)
84 xaxis_data = pd.to_datetime(rad_temp_monthly_avg.index)
85
86 # Plota a radiação total mensal usando um gráfico de barras
87 ax.bar(xaxis_data, rad_temp_monthly_avg['rad'], label='Radiação Total',
,→ width=12, linewidth=1, color=ALL_COLORS[0])
88 ax.set_ylabel('Radiação Total (kWh/m$^2$)')
89 ax.legend(loc=2) # Coloca a legenda no canto superior esquerdo
90
91 # Cria um segundo eixo y compartilhando o eixo x (temperatura ambiente)
92 ax2 = ax.twinx()
93
94 # Plota a temperatura ambiente mensal usando um gráfico de linha
95 ax2.plot(xaxis_data, rad_temp_monthly_avg['temp_ambiente'],
,→ label='Temperatura Ambiente', marker='o', color=ALL_COLORS[3])
96 ax2.set_ylabel('Temperatura Ambiente (${ }^\circ$C)')
97 ax2.legend(loc=0) # Coloca a legenda no canto superior direito
98
99 # Formata o eixo x para mostrar os meses e anos
100 fig.gca().xaxis.set_major_formatter(mdates.DateFormatter('%b-%Y'))
101 fig.gca().xaxis.set_major_locator(mdates.MonthLocator(interval=3))
102
103 # Ajusta a exibição das datas no eixo x
104 plt.gcf().autofmt_xdate()
105
106 # Ajusta o layout da figura para evitar sobreposição
107 plt.tight_layout()
108
109 # Salva o gráfico em formato EPS (opcional)
110 # plt.savefig('radiacao-temp-ano.eps')
111
112 # Exibe o gráfico
113 plt.show()
114
57