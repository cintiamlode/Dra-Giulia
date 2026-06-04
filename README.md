[README.md](https://github.com/user-attachments/files/28613184/README.md)
# Painel de Conciliação Bancária — Dra. Giuliane
**C2B Contabilidade e Finanças**

Painel web para conciliação bancária mensal. Processa extratos bancários (Excel/CSV + PDF) e relatórios de NFs emitidas, gerando o arquivo Excel formatado para contabilidade.

---

## Como publicar no Render (Static Site — gratuito)

### Passo 1 — Subir no GitHub
1. Crie um repositório no GitHub (pode ser privado)
2. Faça upload da pasta `conciliacao-bancaria/` com o arquivo `index.html`
3. Confirme o commit

### Passo 2 — Criar o Static Site no Render
1. Acesse [render.com](https://render.com) e faça login
2. Clique em **New → Static Site**
3. Conecte seu repositório GitHub
4. Configure:
   - **Name:** `conciliacao-bancaria-dra-giu` (ou outro nome)
   - **Branch:** `main`
   - **Root Directory:** `conciliacao-bancaria` (ou deixe em branco se for a raiz)
   - **Build Command:** *(deixar vazio)*
   - **Publish Directory:** `.`
5. Clique em **Create Static Site**
6. Aguarde o deploy (cerca de 1 minuto)
7. Copie o link gerado (ex: `https://conciliacao-bancaria-dra-giu.onrender.com`)

---

## Como usar o painel

### Mensalmente, a secretária deve:
1. Acessar o link do painel
2. Selecionar o **mês** no canto superior direito
3. Fazer upload dos arquivos:
   - **Extrato Excel/CSV** — exportado do banco
   - **Extrato PDF** — arquivo PDF do banco (para referência)
   - **NFs Emitidas PDF/Excel** — relatório do sistema de NF
4. Clicar em **Processar conciliação**
5. Revisar os lançamentos na aba **Extrato** — todas as células são editáveis
6. Ajustar status, NFs e observações conforme necessário
7. Clicar em **Exportar Excel** para baixar o arquivo final

---

## Regras de classificação automática

| Condição | Status atribuído |
|---|---|
| Descrição contém "CONTAMAX", "Aplicação automática", "Resgate" | Lançamento Contábil |
| Descrição contém "PRONAMPE" ou "GIRO PRONAMPE" | Empréstimo Pronampe |
| Descrição contém "Tarifa", "Taxa", "IOF" | Lançamento Contábil |
| Favorecido: Giuliane Jesus Lajos | Pró-labore/Retirada |
| Favorecido: José Antônio Coelho Junior | Esposo |
| Favorecido: Instituto Darsin | Pagamento aluguel sala |
| CNPJ 40.177.506/0006-08 | Lançamento Contábil |
| Campo NF contém "?" ou obs. contém "verificar" | ⚠ Verificar, não localizado NF |
| Campo NF preenchido sem "?" | ✓ Conciliado |

---

## Formato esperado do extrato Excel/CSV

Para leitura automática, o arquivo deve ter colunas com estes nomes (aceita variações):

| Coluna | Nomes aceitos |
|---|---|
| Data | Data, data, DATA |
| Descrição | Descrição, Historico, Histórico |
| CPF/CNPJ | CPF, CNPJ, CPF/CNPJ |
| Crédito | Crédito, credito, Valor |
| Débito | Débito, debito |
| Favorecido | Favorecido, Nome |

---

## Estrutura do Excel exportado

O arquivo exportado contém duas abas:
- **Extrato [Mês] 2026** — todos os lançamentos com status de conciliação
- **NFs Emitidas** — todas as NFs do período

Linhas com status "⚠ Verificar" são coloridas em rosa (`FFD7D7`).

---

## Suporte técnico
C2B Contabilidade e Finanças
