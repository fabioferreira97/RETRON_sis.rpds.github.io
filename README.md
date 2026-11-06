# RETRON — Recolha e Processamento de Desperdícios de Solas

https://fabioferreira97.github.io/RETRON_sistema-de-recolha.github.io/

> **Economia Circular na Indústria do Calçado** · Linha integrada para recolher, separar, triturar e preparar desperdícios gerados nos postos de injeção de solas, transformando resíduos de produção num recurso controlado.

---

## 📌 Sobre o Projeto

O **RETRON** é um conceito de automação industrial projetado para eliminar a tarefa manual de ensacar e transportar resíduos de solas no final de cada turno (que pode consumir os últimos 5 a 10 minutos de produção). 

O sistema automatiza integralmente a recolha, pesagem, troca de caixas industriais, transporte aéreo e encaminhamento do material para pré-trituração e trituração.

---

## ⚙️ Fluxo da Linha

1. **Recolha:** O desperdício é colocado pelo operador numa caixa industrial junto à extrusora.
2. **Separação:** A célula de carga monitoriza o peso e sinaliza o intervalo ótimo de **20–20,5 kg**.
3. **Trituração:** A caixa cheia sobe por plataforma elevatória, é recolhida por um manipulador e transportada por via aérea até ao reservatório de pré-trituração.
4. **Granulação:** O material é triturado e encaminhado para reservatórios de armazenamento e posterior ensacamento (sacos até 20 kg).

---

## 📊 Arquitetura e Equipamentos (Dimensionamento Preliminar)

* **Extrusoras automatizadas:** 6 postos
* **Capacidade por caixa industrial:** 20 – 20,5 kg
* **Atuadores de elevação:** 6 unidades (uma por posto)
* **Motores de transporte:** 6 eixos/zonas (percursos superiores de caixas cheias e retorno de vazias)
* **Robótica partilhada:** 2 robôs (manipulador superior e descarga no reservatório)
* **Reservatório de pré-trituração:** 500 kg
* **Reservatório de embalagem:** 1000 kg (com 10 saídas de dosagem)

---

## 🛠️ Sensores e Controlo (PLC)

* **Pesagem:** Células de carga nos postos de recolha.
* **Presença e Posição:** Sensores fotoelétricos e fins de curso em pontos críticos de transferência.
* **Segurança:** Cortinas de segurança, proteções interbloqueadas e circuitos de paragem de emergência (conforme avaliação de riscos).
* **Lógica de Prioridade:** O PLC coordena a verificação de posições, disponibilidade de caixas vazias e interbloqueios de segurança antes de autorizar qualquer movimento.

---

## 🚀 Demonstração Conceptual (Simulação)

O projeto inclui uma interface web interativa em HTML/CSS/JavaScript que demonstra visualmente o fluxo do cesto cheio em direção à trituradora e o retorno do cesto vazio.

### Como visualizar localmente:
1. Clone este repositório ou faça o download dos ficheiros.
2. Abra o ficheiro `index.html` diretamente em qualquer browser moderno,
3. ou abra diretamente aqui https://fabioferreira97.github.io/RETRON_sistema-de-recolha.github.io/

---

## ✨ Impacto e Vantagens

* **Redução de tarefas manuais:** Eliminação do ensacamento e transporte manual no fim do turno.
* **Organização industrial:** Fluxos físicos separados e otimizados para cestos cheios e vazios (aproveitamento do espaço vertical).
* **Controlo de processos:** Sequenciamento rigoroso gerido por PLC e balanças integradas.
* **Economia circular real:** Valorização e possível reincorporação de polímeros no ciclo produtivo.

*Nota: A viabilidade técnica de reutilização depende do polímero, aditivos, cores e requisitos do produto final.*

---

## 📝 Licença

Conceito industrial desenvolvido em **2026**. Todos os direitos reservados.
