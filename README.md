# EcoLastro CTBJ — Rastreamento Digital de Resíduos Recicláveis

> **Status do Projeto:** Versão Inicial (Front-end Estruturado / Pronto para Integração)

Plataforma Web e Mobile voltada ao rastreamento completo do ciclo de vida de resíduos recicláveis gerados no Colégio Técnico de Bom Jesus (CTBJ). O sistema transforma a cadeia de reciclagem local por meio de transparência, gamificação e governança ambiental.

---

## Problema e Contexto
Catadores e cooperativas frequentemente enfrentam dificuldades para comprovar a origem, a triagem e a real qualidade do material reciclável coletado. Essa falta de rastreabilidade e dados confiáveis impede que esses trabalhadores fechem parcerias estratégicas com médias e grandes empresas interessadas em adquirir créditos ambientais legítimos para suas metas de sustentabilidade (ESG).

## Solução
O **EcoLastro CTBJ** centraliza a jornada dos resíduos em um ecossistema digital. Cada lote de material recebe um **Passaporte Digital (QR Code único)** que registra cronologicamente todas as etapas do ciclo de vida:
1. **Coleta:** Registro com pesagem e geolocalização exata no campus.
2. **Triagem:** Classificação detalhada do tipo e estado do resíduo.
3. **Venda:** Comercialização transparente para cooperativas ou indústrias.
4. **Reciclagem:** Processamento e destinação final comprovada.

---

## Requisitos do Sistema & Status de Validação

### Requisitos Funcionais (RF)
*   **RF02 (Registro de Coleta) · [CONCLUÍDO]:** Formulário operacional para inserção de materiais, peso em quilogramas (kg) e captura automática de coordenadas geográficas via GPS (`Usar minha localização`).
*   **RF08 (Sistema de Recompensas) · [CONCLUÍDO]:** Mecanismo visual de engajamento para os catadores, exibindo saldo de pontos (`0 pts`), volume acumulado (`0 kg`), barra de progresso (`Nível Semente`) e áreas reservadas para recompensas e ranking.
*   **RF03 (Passaporte Digital) · [ESTRUTURADO]:** Estrutura e container visual prontos para renderizar o QR Code do lote após o gatilho de salvamento.
*   **RF04 (Ciclo de Vida) · [PARCIAL]:** Interface de linha do tempo (*Coleta → Triagem → Venda → Reciclagem*) implementada com paginação sob demanda (`Carregar mais lotes`).
*   **RF06 & RF07 (Marketplace & Impacto) · [PARCIAL]:** Telas de negociação de créditos ambientais e painel indicador de estimativa de CO₂ evitado desenhados e aguardando dados da API.

### Requisitos Não Funcionais (RNF)
*   **RNF02 (Resiliência Offline) · [CONCLUÍDO]:** Sistema preparado para operar em áreas de baixa conectividade do campus. Banner de alerta ativo: *"Você está offline — dados dos lotes continuam disponíveis localmente. Novos registros serão sincronizados ao reconectar"*.
*   **RNF03 (Segurança e Perfis) · [CONCLUÍDO]:** Formulários protegidos por máscaras de senha ocultável (`mostrar/ocultar`) e restrição estrita por tipo de perfil de usuário (Catador, Cooperativa, Empresa).
*   **RNF04 (Escalabilidade) · [ESTRUTURADO]:** Arquitetura construída sobre paginação sob demanda no front-end para evitar sobrecarga de requisições.

---

## Stack Tecnológica

*   **Front-end:** React / React Native (Interface modular e componentes altamente reutilizáveis para Web e Mobile).
*   **Persistência Local:** Configuração de armazenamento em cache local para suporte à operação offline (RNF02).
*   **Back-end Alvo (Integração Futura):** Preparado para conexão com APIs em Node.js e banco de dados relacional PostgreSQL.

---

## Público-Alvo
*   **Catadores de materiais recicláveis:** Valorização do trabalho através de dados e gamificação.
*   **Cooperativas de reciclagem:** Gestão simplificada dos lotes recebidos e triados.
*   **Empresas compradoras:** Acesso simplificado a créditos ambientais auditáveis para conformidade ESG.
