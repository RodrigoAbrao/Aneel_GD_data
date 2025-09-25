# 📂 Repositório Técnico – Segurança em Sistemas Fotovoltaicos

Este repositório reúne documentos, laudos e bases de dados que sustentam a análise sobre **segurança em sistemas fotovoltaicos** e a aplicação da **NBR 17193:2025**, com foco no recorte do estado de Goiás.

---

## 📑 Documentos Anexos

1. [Metodologia e pipeline de dados (ANEEL)](./1.%20Metodologia%20e%20pipeline%20de%20dados%20(ANEEL).pdf)  
   - Pipeline completo de análise e classificação de usinas fotovoltaicas:contentReference[oaicite:0]{index=0}.  
   - Inclui uso da API do Google Cloud (imagens de satélite) e da OpenAI (classificação urbana/rural).  
   - Modelos estatísticos com **XGBoost** para diferenciar usinas MLPE e string.

2. [Séries e tabelas – Recorte Goiás](./2.%20Series%20Recorte%20GO.pdf)  
   - Dados completos das instalações homologadas entre **02/04/2025 e 31/07/2025**.  
   - Subdivisão por tipo de usina e tecnologia.

3. [Laudo pericial – Fatalidade por eletrocussão](./3.%20Laudo%20Pericial%20Eletrocussao.pdf)  
   - Documento pericial real descrevendo caso fatal.  
   - Evidencia o risco em telhados sem RSD.

4. [Preços de kits fotovoltaicos](./4.%20Precos%20Kits.pdf)  
   - Comparativos econômicos entre sistemas conformes e não conformes.  
   - Demonstra como o **custo adicional do RSD** impacta na adesão.

5. [NBR 17193:2025](./5.%20NBR17193.pdf)  
   - Norma nacional que exige **Função de Desligamento Rápido (FDR/RSD)**.  
   - Item **7.4(b): ≤120 V em até 30 s** dentro do limite do arranjo.

6. [Firefighter Safety and Photovoltaic Installations Research Project (2011)](./6.%20Firefighter%20Safety%20PV.pdf)  
   - Pesquisa americana que embasa o limite de 120 V como critério fisiológico de segurança.

7. [Dados de sinistros – ABRACOPEL (2025)](./7.%20Sinistros%20Abracopel%202025.pdf)  
   - Registros de acidentes com sistemas FV no Brasil em 2025.  
   - Confirma aumento de ocorrências em telhados sem RSD.

---

## 📊 Organização dos Dados JSON

- **2.1 – Usinas urbanas com MLPE**  
  ✔️ Já em conformidade com o item 7.4 da NBR 17193 e a NT 44/2025 (GO).  

- **2.2 – Usinas urbanas com inversores convencionais**  
  ⚠️ Necessitam de **RSD externo**.  
  - Alta probabilidade de estarem **irregulares**, devido ao custo elevado e falta de disponibilidade.  

- **2.3 – Usinas em área rural**  
  🟡 Classificadas como rurais para **evitar falsos positivos** (maior chance de serem usinas solo).  

- **2.4 – Infográfico**  
  📈 Resumo visual das usinas, comparando número de sistemas que exigem RSD vs. RSD efetivamente vendidos.

---

## ⚙️ Metodologia

- **Período de análise:** 02/04/2025 a 31/07/2025 (após vigência da NBR 17193).  
- **Fonte de dados:** bases públicas da **ANEEL** (`empreendimento-geracao-distribuida` e `empreendimento-gd-informacoes-tecnicas-fotovoltaica.csv`).  
- **Classificação de área:** imagens de satélite via **Google Cloud API** + classificação com **OpenAI API**.  
- **Modelo estatístico:** **XGBoost** para diferenciar usinas MLPE e string.  
- **Categorias finais:**  
  - Usinas **urbanas com MLPE** – conformes.  
  - Usinas **urbanas com string** – exigem RSD externo.  
  - Usinas **rurais** – excluídas da irregularidade.

---

## 📌 Conclusão

- O número de sistemas **não conformes** é significativamente maior do que o volume de RSDs vendidos no período.  
- **Todos os estabelecimentos que necessitam de alvará de funcionamento** devem realizar **retrofit** para adequação à NBR 17193:2025.  
- A desconformidade é **sistêmica**, impulsionada por fatores **econômicos e de mercado**.  

---

## ⚠️ Disclaimer Metodológico

- Os resultados **não possuem acuracidade de 100%**.  
- As classificações representam **tendência e magnitude**, não um censo exato.  
- Sistemas tipicamente rurais foram excluídos para reduzir falsos positivos.  
- A ausência de RSD foi inferida indiretamente (com base em tipo de inversor e volume de vendas).  
- O estudo não substitui fiscalização oficial pelos **Corpos de Bombeiros** ou **ANEEL**.

---
