# RETRON

### Sistema automatizado de recolha e valorização de desperdícios de solas

> **Do desperdício de sola a uma matéria-prima valorizada.**

O **RETRON** é um conceito de automação industrial destinado a
automatizar a recolha, pesagem, transporte e processamento dos
desperdícios gerados durante a injeção de solas termoplásticas para
calçado.

O projeto abrange seis extrusoras e procura reduzir tarefas manuais,
evitar interrupções desnecessárias da produção e preparar os resíduos
para reprocessamento pelo fornecedor.

------------------------------------------------------------------------

## Índice

1.  [O problema](#1-o-problema)
2.  [Objetivos](#2-objetivos)
3.  [Visão geral](#3-visão-geral)
4.  [Funcionamento](#4-funcionamento)
5.  [Equipamentos](#5-equipamentos)
6.  [Sensores e atuadores](#6-sensores-e-atuadores)
7.  [Supervisão e registo](#7-supervisão-e-registo)
8.  [Segurança](#8-segurança)
9.  [Benefícios esperados](#9-benefícios-esperados)
10. [Próximas etapas](#10-próximas-etapas)
11. [Notas técnicas](#11-notas-técnicas)

## 1. O problema

A produção de solas gera desperdícios como solas defeituosas, pontas dos
canais de injeção e sobras de material provenientes dos moldes.

No processo convencional considerado, os resíduos são colocados em sacos
junto às extrusoras. No final do turno, um operador transporta os sacos
para uma zona de armazenamento, tarefa que pode ocupar os últimos **5 a
10 minutos de produção**. Posteriormente, outro trabalhador trata do
material acumulado, alimentando a trituradora e preparando-o para envio
ao fornecedor.

O RETRON pretende automatizar estas operações e tornar o fluxo de
resíduos contínuo e controlado.

## 2. Objetivos

-   Automatizar a recolha de desperdícios em **6 extrusoras**.
-   Pesar continuamente o material em cada posto.
-   Trocar automaticamente caixas industriais cheias por caixas vazias.
-   Separar o transporte de caixas cheias do retorno das vazias.
-   Encaminhar os resíduos para pré-trituração e trituração.
-   Controlar o armazenamento e o acondicionamento do material
    triturado.
-   Registar operadores, turnos, ordens de fabrico e quantidades
    produzidas.
-   Reduzir tarefas manuais e melhorar a organização da área produtiva.

## 3. Visão geral

Cada extrusora dispõe de uma plataforma elevatória com uma caixa
industrial e uma célula de carga. Quando a caixa atinge aproximadamente
**20 a 20,5 kg**, a plataforma eleva-a até à zona de transferência.

Um robô superior retira a caixa cheia e coloca-a no transportador de
cheios. Em seguida, recolhe uma caixa vazia no transportador paralelo e
coloca-a na plataforma. A plataforma desce e o posto fica novamente
disponível.

  -----------------------------------------------------------------------
  Percurso                            Função
  ----------------------------------- -----------------------------------
  Transportador de cheios             Levar caixas com resíduos ao
                                      reservatório de pré-trituração

  Transportador de vazios             Repor caixas vazias nos seis postos
  -----------------------------------------------------------------------

Os dois percursos são elevados, aproveitando o espaço vertical da
fábrica.

## 4. Funcionamento

### 4.1 Recolha e pesagem

1.  O operador coloca os desperdícios na caixa junto à extrusora.
2.  A célula de carga mede continuamente o peso.
3.  Ao atingir 20--20,5 kg, é solicitada a troca.
4.  A plataforma eleva a caixa para a posição de transferência.

### 4.2 Troca automática

1.  O robô superior recolhe a caixa cheia.
2.  Coloca-a no transportador de cheios.
3.  O sistema confirma a transferência e a disponibilidade da
    plataforma.
4.  O robô recolhe uma caixa vazia no percurso de retorno.
5.  Coloca-a na plataforma.
6.  Após confirmação da presença e posição, a plataforma desce.

### 4.3 Descarga no reservatório

Um segundo robô recolhe a caixa cheia na zona de descarga. A caixa é
pesada através de uma célula de carga integrada na garra e o conteúdo é
despejado no reservatório de pré-trituração, com capacidade prevista de
**500 kg**. A caixa vazia é confirmada e devolvida ao transportador de
retorno.

### 4.4 Fim de turno

O supervisor pode selecionar **FIM DE TURNO** no ecrã central. Se o
comando não for efetuado, o conceito prevê uma rotina de recolha das
caixas que ainda contenham material após o início do turno seguinte e a
verificação do horário anterior.

A trituração só deverá arrancar depois de concluída a recolha e
confirmadas as condições de segurança e disponibilidade do sistema.

### 4.5 Trituração e embalagem

O material é alimentado à trituradora e encaminhado para um reservatório
de embalagem com capacidade prevista de **1000 kg**. Este reservatório
alimenta **10 saídas de dosagem**, configuradas para sacos de
aproximadamente **20 kg**.

O trabalhador coloca um saco na saída pretendida. Um sensor confirma a
presença do saco antes de permitir a dosagem. Depois do enchimento, o
saco é fechado e paletizado para expedição.

## 5. Equipamentos

  Equipamento                        Quantidade/configuração prevista
  -------------------------------- ----------------------------------
  Extrusoras abrangidas                                             6
  Plataformas elevatórias                                           6
  Células de carga nos postos                                       6
  Robô superior de troca                                            1
  Robô de descarga                                                  1
  Transportadores elevados                                2 percursos
  Reservatório de pré-trituração                               500 kg
  Reservatório de embalagem                                   1000 kg
  Saídas de dosagem                                        10 × 20 kg

A divisão dos transportadores em zonas motorizadas e o número de caixas
em circulação deverão ser confirmados após o desenho do layout e o
estudo dos tempos de ciclo.

## 6. Sensores e atuadores

### Sensores nos seis postos

  ------------------------------------------------------------------------
  Sensor                                  Quantidade Função
  --------------------- ---------------------------- ---------------------
  Célula de carga                                  6 Medir o peso da caixa

  Presença de caixa                                6 Confirmar caixa na
                                                     plataforma

  Posição inferior                                 6 Confirmar plataforma
                                                     em baixo

  Posição superior                                 6 Confirmar plataforma
                                                     elevada

  Caixa na posição de                              6 Confirmar
  transferência                                      posicionamento para a
                                                     troca
  ------------------------------------------------------------------------

### Outros sensores

-   Sensores fotoelétricos de presença e posicionamento nos
    transportadores;
-   Sensores de posição nos mecanismos e comportas;
-   Deteção de caixa agarrada e confirmação da posição dos robôs;
-   Célula de carga na garra do robô de descarga;
-   Pesagem dos dois reservatórios;
-   Sensores de nível, quando necessários;
-   Monitorização de rotação, temperatura e sobrecarga da trituradora;
-   Sensores de presença de saco nas dez saídas;
-   Paragens de emergência e interbloqueios de segurança.

### Principais atuadores

-   6 sistemas de elevação das plataformas;
-   6 motores/zonas motorizadas como base inicial (3 para cheios e 3
    para vazios);
-   Sistemas de retenção e posicionamento de caixas;
-   2 robôs;
-   1 atuador de comporta;
-   1 mecanismo de alimentação da trituradora;
-   1 motor da trituradora;
-   1 mecanismo de descarga para o reservatório de embalagem;
-   10 atuadores de dosagem.

A estimativa conceptual anterior considera cerca de **34 sistemas de
atuação**, tratando cada robô como um sistema lógico e sem contar
individualmente os seus eixos internos. A contagem final deve distinguir
motores, válvulas, cilindros, eixos e equipamentos integrados.

## 7. Supervisão e registo

O sistema prevê um ecrã central para o supervisor e um ecrã tátil em
cada posto de extrusão.

### Ecrã central

O supervisor poderá iniciar e terminar turnos, acompanhar o estado da
linha, consultar os pesos dos reservatórios, comandar a trituradora,
supervisionar as saídas de dosagem e consultar alarmes e registos.

O início do turno deverá registar o horário, o nome do supervisor e o
código de funcionário.

### Ecrãs locais

Em cada extrusora, o operador poderá introduzir: - Nome e código de
funcionário; - Ordem de fabrico (OF); - Referência do molde; - Tamanho
produzido.

No final da OF ou do turno, poderá registar a quantidade de pares
produzidos. Cada nova OF deverá gerar uma nova ficha de registo.

## 8. Segurança

A solução envolve plataformas elevatórias, transportadores, robôs e uma
trituradora. A conceção deverá contemplar:

-   Paragens de emergência acessíveis;
-   Proteções físicas e portas com interbloqueio;
-   Cortinas ou scanners de segurança quando justificados;
-   Proteção contra esmagamento e entalamento;
-   Prevenção de acesso às zonas de movimento dos robôs;
-   Monitorização de sobrecarga e condições anormais;
-   Bloqueio de movimentos quando as condições de segurança não
    estiverem confirmadas;
-   Procedimentos de isolamento de energia para manutenção e
    desobstrução.

A avaliação de riscos e a validação das funções de segurança devem ser
realizadas por profissionais competentes, segundo as normas e legislação
aplicáveis.

## 9. Benefícios esperados

-   **Redução de tarefas manuais:** menos transporte e movimentação de
    sacos.
-   **Menos tempo improdutivo:** evitar a recolha manual nos últimos
    minutos do turno.
-   **Organização:** fluxos independentes para caixas cheias e vazias.
-   **Rastreabilidade:** associação dos registos aos operadores, turnos
    e OF.
-   **Controlo:** pesagem nos postos e nos reservatórios.
-   **Valorização:** preparação dos resíduos para reprocessamento.
-   **Aproveitamento do espaço:** utilização de transportadores
    elevados.

## 10. Próximas etapas

1.  Finalizar o fluxograma geral.
2.  Desenvolver o diagrama de sequência com sensores e atuadores.
3.  Definir o layout dos seis postos, transportadores e robôs.
4.  Estudar tempos de ciclo e circulação de caixas.
5.  Fechar a arquitetura de controlo, comunicação e módulos I/O.
6.  Desenvolver a supervisão central e os ecrãs locais.
7.  Criar uma simulação 3D do funcionamento.
8.  Realizar a análise de riscos e validar a solução técnica.

## 11. Notas técnicas

O RETRON encontra-se em fase de desenvolvimento conceptual e
académico/técnico. As capacidades, quantidades e sequências descritas
são preliminares e devem ser confirmadas por cálculos, seleção de
componentes, desenhos técnicos, análise de riscos e testes.

A possibilidade de reprocessar o material depende do polímero,
pigmentos, aditivos, contaminação, histórico térmico e requisitos de
qualidade definidos pelo fornecedor e pelo produto final.

------------------------------------------------------------------------

::: {align="center"}
**RETRON**\
*Automatizar a recolha. Valorizar o desperdício. Melhorar o processo.*
:::
