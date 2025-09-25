# Metodologia e pipeline de dados (ANEEL)

Este repositório contém dados da ANEEL relacionados à geração distribuída (GD) em Goiás, com foco na conformidade com a NBR17193 e regulamentações de segurança para instalações fotovoltaicas.

## Período de Extração dos Dados
**Entre 02/04/2025 a 31/07/2025** - Após publicação da NBR17193

## Classificação dos Dados

### 2.1 - Usinas urbanas com MLPE (REGULARES)
- **Arquivo**: `2.2 Usinas urbanas com MLPE (REGULARES).json`
- **Descrição**: Usinas localizadas em área urbana que utilizam tecnologia MLPE (Module Level Power Electronics)
- **Status de Conformidade**: **REGULARES** - Já estão em conformidade com:
  - Item 7.4 da NBR17193
  - Item específico da NT 44 de Goiás

### 2.2 - Usinas urbanas com inversor convencional (ALTA PROBABILIDADE IRREGULARES)
- **Arquivo**: `2.1 Usinas urbanas com inversor convencional (ALTA PROBABILIDADE IRREGULARES).json`
- **Descrição**: Usinas localizadas em área urbana (não são usinas de solo) com inversores convencionais
- **Status de Conformidade**: **NECESSITAM RSD EXTERNO**
- **Observação**: Alta probabilidade de não possuírem RSD devido ao alto custo e falta de disponibilidade no mercado

### 2.3 - Usinas com probabilidade de serem rurais
- **Arquivo**: `2.3 Usinas rurais(PROBABILIDADE DE SEREM RURAIS).json`
- **Descrição**: Usinas fotovoltaicas com probabilidade de estarem em área rural
- **Status**: Para evitar falsos positivos, não foram classificadas como irregulares

### 2.4 - Resumo gráfico
- **Arquivo**: `2.4 infografico_GO.png`
- **Descrição**: Infográfico com resumo gráfico dos dados classificados

## Metodologia Técnica

### Modelos de Machine Learning
- **XGBoost**: Utilizado para classificação das usinas em MLPE ou não
- **Acurácia**: Não é de 100% - considere margem de erro nas classificações

### APIs Utilizadas
- **OpenAI API**: Classificação de imagem do terreno da localização
- **Google Cloud API**: Extração de imagens de localização geográfica

## Arquivos Anexos

1. **Metodologia e pipeline de dados (ANEEL).pdf** - Documentação detalhada da metodologia
2. **ABNT-CB-024-CE 024 102 007_Relatorio_acidente_MTE_SIT (2).pdf** - Laudo pericial (fatalidade por eletrocussão)
3. **Preços de kits.pdf** - Análise de preços de equipamentos
4. **ABNT NBR 17193 - 2025 (9).pdf** - Norma técnica de referência
5. **PV-FF_SafetyFinalReport.pdf** - Firefighter Safety and Photovoltaic Installations Research Project - November 29, 2011
6. **Análise de Acidentes e Instalações Solares no Brasil.pdf** - Dados de sinistros envolvendo sistemas fotovoltaicos coletados pela ABRACOPEL em 2025

## Resumo Estatístico (summary__GO.json)
- **Total de registros**: 7.977 usinas
- **MLPE (Regulares)**: 765 sistemas
- **Inversores convencionais (Necessitam RSD)**: 4.505 sistemas  
- **Rurais (Possível isenção)**: 2.700 sistemas

## Observações Importantes

⚠️ **Disclaimer de Acurácia**: A precisão da classificação não é de 100%. Os resultados devem ser validados antes de ações regulatórias.

📋 **Retrofit Obrigatório**: A lista completa de estabelecimentos é muito maior. Todos os estabelecimentos que necessitam de alvará devem realizar o retrofit para conformidade com a NBR17193.

## Conformidade Regulatória
- **NBR17193**: Norma brasileira para sistemas fotovoltaicos
- **NT 44 de Goiás**: Norma técnica específica do estado de Goiás
- **Item 7.4**: Requisitos específicos para sistemas MLPE
