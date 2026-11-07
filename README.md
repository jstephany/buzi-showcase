# Buzi - Ecossistema Mobile de Negócios 

> **Nota de Confidencialidade:** O código-fonte deste projeto é mantido em repositório privado para proteger dados e regras comerciais da empresa. Este repositório atua como portfólio de Engenharia de Software, documentando os requisitos, regras de negócio e a interface do sistema.

## O Problema
O Buzi foi desenvolvido para digitalizar e automatizar a operação de uma microempresa (MEI) do ramo alimentício. Antes do sistema, a gestão enfrentava:
* Descentralização de informações em anotações físicas.
* Dificuldade no acompanhamento de estoque e cálculo de lucros.
* Gargalos no controle de pagamentos parciais (contas fiadas/parceladas).

## Arquitetura e Tecnologias
* **Mobile:** React, TypeScript, Expo (Multiplataforma Android/iOS).
* **Back-end & Database:** Supabase (BaaS), PostgreSQL. Em transição.
* **Paradigma:** Design Responsivo, Atualizações Reativas (Real-time) e Autenticação Segura na Nuvem.

## Regras de Negócio e Lógica de Software (Core)
O sistema foi arquitetado para garantir consistência de dados através das seguintes regras:

* **Snapshot Imutável de Vendas (RF09):** Ao fechar um pedido, o sistema salva um "retrato" do valor exato do produto naquele milissegundo. Mudanças futuras no catálogo de preços não afetam o histórico financeiro de vendas passadas.
* **Controle de Pagamentos Parciais (RN03):** O banco de dados e a interface bloqueiam entradas de pagamentos que ultrapassem o Saldo Devedor atualizado do pedido, evitando inconsistências de caixa.
* **Gatilhos de Estoque (RN01):** A baixa no inventário ocorre de forma estritamente automática e transacional no momento do registro da venda.
* **Integridade Referencial (RN02):** Bloqueio de submissão de pedidos "órfãos" (sem cliente ou sem produtos vinculados).

## Funcionalidades (Módulos)
* **Gestão de Catálogo e Estoque:** Cadastro de produtos e entrada manual de suprimentos com filtros dinâmicos de busca.
* **CRM (Gestão de Clientes):** Criação de perfis de clientes com histórico de consumo diretamente atrelado.
* **Ponto de Venda (PDV):** Seleção de produtos e cálculo automático de valores totais do pedido.
* **Financeiro:** Abatimento automático de saldo devedor a cada pagamento registrado.
* **Geração de Relatórios:** Consolidação de extratos financeiros cronológicos por cliente, com integração nativa para exportação via WhatsApp ou E-mail.

## 📸 Interface do Aplicativo

*(O design foca em usabilidade mobile e feedback visual instantâneo para operação ágil no balcão)*

<div align="center">
  <img src="./telas/home.png" width="250" alt="Tela Inicial" />
  <img src="./telas/estoque.png" width="250" alt="Tela de Estoque" />
  <img src="./telas/cadastroprod.png" width="250" alt="Tela de Cadastro Produto" />
  <img src="./telas/edicaoprod.png" width="250" alt="Tela de Edição" />
  <img src="./telas/novopedido.png" width="250" alt="Tela de Pedidos" />
  <img src="./telas/pedidoshist.png" width="250" alt="Tela de Historico" />
  <img src="./telas/perfilcliente.png" width="250" alt="Tela de Clientes" />
  <img src="./telas/notafiscal.png" width="250" alt="Extrato com export" />
</div>

---
**Engenharia e Desenvolvimento:** [Júlia Stephany F Coelho Silva](https://github.com/jstephany)