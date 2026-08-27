# Relatório de Arquitetura e Modelagem - EcoLastro CTBJ

## 1. Introdução

Este documento apresenta a modelagem inicial da solução EcoLastro, incluindo o fluxo de funcionamento do sistema e o modelo de dados que sustenta os requisitos definidos na Etapa 1.

## 2. Fluxograma do Processo

Fluxo principal do ciclo de vida de um lote de material reciclável, do cadastro à emissão do certificado.

```mermaid
flowchart TD
    A[Catador ou cooperativa se cadastra] --> B[Registro de coleta com geolocalizacao]
    B --> C[Sistema gera QR code do lote]
    C --> D[Lote passa por triagem]
    D --> E[Lote e vendido para reciclagem]
    E --> F[Etapa de reciclagem confirmada]
    F --> G{Todas as etapas confirmadas?}
    G -- Nao --> D
    G -- Sim --> H[Emissao do certificado digital]
    H --> I[Certificado disponivel no marketplace]
    I --> J[Empresa compra credito de reciclagem]
```

## 3. Modelo de Dados (Diagrama Entidade-Relacionamento)

```mermaid
erDiagram
    USUARIO ||--o{ LOTE : registra
    USUARIO {
        int id
        string nome
        string email
        string tipo
    }
    LOTE ||--|| QRCODE : possui
    LOTE ||--o{ ETAPA : passa_por
    LOTE {
        int id
        string tipo_material
        float geolocalizacao_lat
        float geolocalizacao_lng
        string status
    }
    QRCODE {
        int id
        string codigo_unico
        int lote_id
    }
    ETAPA {
        int id
        string nome_etapa
        date data_confirmacao
        int lote_id
    }
    LOTE ||--o| CERTIFICADO : gera
    CERTIFICADO {
        int id
        date data_emissao
        int lote_id
    }
    EMPRESA ||--o{ CERTIFICADO : compra
    EMPRESA {
        int id
        string nome
        string cnpj
    }
```

## 4. Protótipo de Interface (descrição textual)

Telas previstas para a primeira versão navegável (a serem prototipadas em Figma):

- Tela de login e cadastro (catador, cooperativa, empresa)
- Tela de registro de coleta (com captura de geolocalização)
- Tela de QR code gerado
- Tela de acompanhamento das etapas do lote
- Tela de marketplace de créditos (visão empresa)
- Painel de impacto ambiental (visão catador/cooperativa)

## 5. Ferramentas utilizadas na modelagem

- Mermaid.js: fluxograma e diagrama entidade-relacionamento
- Figma (previsto): protótipo de interface de alta fidelidade
