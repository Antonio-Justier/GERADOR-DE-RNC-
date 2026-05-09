# Gerador de RNC — Relatório de Não Conformidade

Aplicação web para preenchimento e geração automática de Relatórios de Não Conformidade (RNC) em PDF, desenvolvida para substituir o fluxo manual baseado em planilhas Excel.

## 📋 Sobre o projeto

No fluxo anterior, o preenchimento da RNC era feito manualmente em uma planilha Excel, com inserção de imagens e exportação via "Microsoft Print to PDF". Esse processo é lento, propenso a erros de formatação e dependente do computador onde a planilha está salva.

Esta aplicação resolve isso oferecendo um formulário web simples onde o usuário preenche os campos, anexa as imagens e gera o PDF com um clique — direto do navegador, sem instalações.

## ✨ Funcionalidades

- Formulário responsivo com todos os campos da RNC
- Upload de até 2 imagens com pré-visualização
- Geração de PDF em formato A4 paisagem com layout idêntico ao modelo original
- Validação básica de campos obrigatórios
- Preenchimento automático da data atual
- Funciona em qualquer dispositivo com navegador (computador, tablet, celular)

## 🚀 Como usar

1. Acesse a aplicação pelo link de hospedagem (ver seção "Acesso" abaixo).
2. Preencha os campos do formulário:
   - **Identificação**: número da RNC, setor, produto, marca, datas, lote, fornecedor etc.
   - **Ocorrência**: descrição do problema e causa.
   - **Anexos**: selecione até 2 imagens do produto ou da não conformidade.
   - **Responsável**: quem registrou a RNC e a ação corretiva tomada.
3. Clique em **Gerar PDF**.
4. O arquivo será baixado automaticamente com o nome `RNC_<numero>.pdf`.

## 🔗 Acesso

O site está hospedado no GitHub Pages e pode ser acessado em:

**`https://antonio-justier.github.io/GERADOR-DE-RNC-/`**

## 🛠️ Tecnologias

- **HTML5** — estrutura do formulário e do template do PDF
- **CSS3** — estilização e responsividade
- **JavaScript (Vanilla)** — lógica do formulário e geração do PDF
- **[html2canvas](https://html2canvas.hertzen.com/)** — captura do template como imagem
- **[jsPDF](https://github.com/parallax/jsPDF)** — geração do arquivo PDF

Todas as bibliotecas são carregadas via CDN, dispensando instalação local.

## 📁 Estrutura do projeto

```
gerador-rnc/
├── index.html      # Aplicação completa (HTML + CSS + JS)
└── README.md       # Este arquivo
```

O projeto é intencionalmente simples: um único arquivo HTML autocontido, fácil de editar e hospedar.

## 💻 Rodando localmente

Não há build nem instalação. Basta:

1. Clonar o repositório:
   ```bash
   git clone https://antonio-justier.github.io/GERADOR-DE-RNC-/
   ```
2. Abrir o arquivo `index.html` em qualquer navegador moderno (Chrome, Edge, Firefox).

## 🔧 Personalização

Para alterar campos, cores ou layout, edite diretamente o `index.html`:

- **Cor de destaque**: procure por `--accent: #b91c1c` no CSS.
- **Campos do formulário**: cada campo é um bloco `<div class="field">` no HTML.
- **Template do PDF**: a `<div id="pdf-template">` define o layout final.

Se adicionar um novo campo, lembre-se de:
1. Inserir o input no formulário.
2. Inserir o `<span id="p-nomedocampo"></span>` no template do PDF.
3. Adicionar a linha correspondente na função `gerarPDF()`.

## 🗺️ Roadmap

Próximas evoluções planejadas:

- [ ] Numeração automática sequencial das RNCs
- [ ] Histórico de RNCs geradas (com Firebase ou Supabase)
- [ ] Sistema de autenticação por usuário
- [ ] Exportação adicional em formato Excel
- [ ] Versão como aplicativo mobile (PWA)
- [ ] Dashboard com indicadores de não conformidade

## 👥 Créditos

- **Desenvolvido por**: Antonio Aguilera

## 📄 Licença

Projeto de uso interno. Para uso externo, consultar os responsáveis.
