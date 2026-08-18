# 📋 Documento de Requisitos - EcoLastro

## 1. Introdução

Este documento descreve os **requisitos funcionais** e **não funcionais** do sistema EcoLastro, uma plataforma de rastreamento de resíduos recicláveis que conecta catadores, cooperativas e empresas parceiras.

---

## 2. Requisitos Funcionais

| Código | Descrição |
|--------|-----------|
| RF01 | O sistema deve permitir o cadastro de catadores, cooperativas e empresas parceiras |
| RF02 | O sistema deve permitir o registro de coleta com geolocalização e tipo de material |
| RF03 | O sistema deve gerar um QR code único para cada lote coletado |
| RF04 | O sistema deve rastrear as etapas do material (coleta, triagem, venda, reciclagem) |
| RF05 | O sistema deve emitir um certificado digital de reciclagem por lote |
| RF06 | O sistema deve disponibilizar um marketplace para empresas comprarem créditos de reciclagem |
| RF07 | O sistema deve exibir um painel de impacto ambiental por catador e por cooperativa |
| RF08 | O sistema deve possuir um sistema de pontuação e recompensas para catadores |

---

## 3. Requisitos Não Funcionais

| Código | Descrição |
|--------|-----------|
| RNF01 | O sistema deve ter interface simples, usável até por pessoas com pouca familiaridade digital |
| RNF02 | O sistema deve permitir funcionamento offline parcial, sincronizando os dados quando houver conexão |
| RNF03 | O sistema deve garantir segurança e integridade dos dados de rastreamento |
| RNF04 | O sistema deve ser escalável para suportar múltiplas cooperativas simultaneamente |

---

## 4. Regras de Negócio

- **RN01** - Cada lote coletado deve estar vinculado a um catador ou cooperativa responsável
- **RN02** - Um certificado de reciclagem só pode ser emitido após a confirmação de todas as etapas do processo
- **RN03** - Empresas só podem comprar créditos de lotes com certificado emitido

---

## 5. Tecnologias Previstas

- **Front-end:** React Native e React
- **Back-end:** Node.js
- **Banco de dados:** PostgreSQL
- **Versionamento:** Git e GitHub
