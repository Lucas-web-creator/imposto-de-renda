# 📊 Dashboard & Organizador de Imposto de Renda (IRPF)

> **Solução completa e automatizada para gestão patrimonial, controle de proventos e organização de documentos fiscais para a Declaração do Imposto de Renda Pessoa Física.**

---

## 📸 Visão Geral da Arquitetura

O **Organizador IRPF** foi projetado para transformar o processo anual de prestação de contas à Receita Federal em uma rotina fluida, organizada e previsível. O sistema consolida dados financeiros divididos em **7 módulos especializados**:

```
Organizador_IRPF/
├── 📈 Dashboard & Resumo     # KPIs, consolidação dinâmica e base PGFN
├── 💵 Rendimentos           # Entradas tributáveis, isentas e retenções
├── 🩺 Despesas Dedutíveis   # Saúde, educação, PGBL e comprovantes
├── 🏠 Bens e Direitos       # Evolução patrimonial (imóveis, veículos, contas)
├── 📊 Investimentos          # Ações, FIIs, Renda Fixa e proventos anuais
├── 🪙 Criptoativos          # Posições em BTC, ETH e apuração de isenção
└── 📉 Dívidas e Ônus        # Saldo devedor e empréstimos em 31/12
```

---

## 🚀 Principais Recursos

### 1. 🎯 Dashboard Inteligente de KPIs
- **Métricas em Tempo Real:** Cards integrados com visão geral do *Total Tributável*, *Despesas Dedutíveis*, *Patrimônio Líquido* e *Proventos Recebidos*.
- **Fórmulas Dinâmicas (`SUMIFS`):** Separação automática por categorias fiscais (ex: despesas médicas vs. educacionais).

### 2. 📋 Validação e Regras de Negócio
- **Dropdowns de Categorização:** Evita erros de digitação em categorias críticas como fonte pagadora, tipo de despesa e vínculo (Titular/Dependente).
- **Checklist de Auditoria:** Controle booleano (*Sim/Não*) de comprovantes e recibos em anexo para evitar caindo na Malha Fina.

### 3. 🎨 Design Corporativo Tech
- **Paleta Slate / Navy (`#1E293B`):** Estilização sóbria, elegante e profissional.
- **Leitura Otimizada:** Efeito zebra alternado, linhas de grade visíveis e números em formato monetário oficial (`R$ #,##0.00`).

---

## 🛠️ Guia de Uso Passo a Passo

### Fase 1: Preenchimento Contínuo (Durante o Ano)
1. **Lançamento de Despesas (`Despesas Dedutíveis`):** Sempre que realizar uma consulta médica, pagar mensalidade ou aporte em PGBL, lance na planilha e salve o PDF/foto do recibo na pasta do ano-base.
2. **Recebimento de Proventos (`Investimentos` & `Rendimentos`):** Registre os dividendos e rendimentos de FIIs/Ações recebidos mensalmente.

### Fase 2: Fechamento de Ano (Janeiro/Fevereiro)
1. **Atualização Patrimonial (`Bens e Direitos`):** Lance os aportes ou benfeitorias realizadas no ano. **Importante:** Mantenha pelo *custo de aquisição*, nunca atualize pelo valor de mercado.
2. **Atualização de Investimentos (`Investimentos` & `Criptoativos`):** Calcule o preço médio e atualize as quantidades custodiadas em 31/12.

### Fase 3: Transposição para o Programa da Receita Federal
1. Acesse a aba **`Dashboard & Resumo`**.
2. Abra o programa oficial da Receita Federal (*IRPF*).
3. Copie os valores pré-consolidados por grupo de forma direta e sem necessidade de somas manuais.

---

## 📊 Estrutura Detalhada das Abas

| Aba | Função Principal | Fórmulas Chave |
| :--- | :--- | :--- |
| **`Dashboard & Resumo`** | Consolidação e cruzamento de dados | `=SUM()`, `=SUMIFS()` |
| **`Rendimentos`** | Salários, pró-labore, serviços e IRRF | `=SUM(E8:E100)` |
| **`Despesas Dedutíveis`** | Gastos com saúde, educação e previdência | `=SUMIFS(..., "Saúde")` |
| **`Bens e Direitos`** | Variação do patrimônio acumulado | `=C8+D8` |
| **`Investimentos`** | Ações, FIIs, Tesouro e Proventos | `=Quantidade * Preço_Médio` |
| **`Criptoativos`** | Posição em moedas digitais e isenções | `=Qtd * Custo_Médio` |
| **`Dívidas e Ônus`** | Controle de empréstimos e saldo devedor | `=SUM(E8:E100)` |

---

## ⚡ Boas Práticas Fiscais

> ⚠️ **Fique atento às diretrizes da Receita Federal:**

- 💡 **Regra do Custo de Aquisição:** Bens imóveis e veículos não acompanham a valorização de mercado. O valor só altera em caso de benfeitorias/reformas comprovadas com Nota Fiscal.
- 🩺 **Despesas Médicas:** Não possuem limite de dedução, mas exigem comprovação via NF ou recibo contendo CPF/CNPJ do prestador.
- 🎓 **Despesas com Educação:** Sujeitas ao teto de dedução individual anual estipulado pela Receita.
- 🪙 **Criptoativos:** Obrigatoriedade de declaração para saldos iguais ou superiores a R$ 5.000,00 por categoria de ativo.

---

## 📂 Requisitos Técnicos

- **Microsoft Excel** 2016 ou superior (suporte a `.xlsx` e validação de dados).
- **Google Sheets** / LibreOffice Calc (totalmente compatível).

---
*Projeto desenvolvido para organização pessoal e gestão patrimonial eficiente.*
