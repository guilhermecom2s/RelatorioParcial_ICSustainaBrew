# Modelo LaTeX para Relatórios FAPESP - Projetos Temàticos e CPA/CPE (ABNT)

Este modelo LaTeX foi desenvolvido para a elaboração de relatórios de projetos temáticos e centros de pesquisa aplicada/em engenharia (CPA/CPE) da FAPESP (Fundação de Amparo à Pesquisa do Estado de São Paulo). Ele segue as normas ABNT NBR 14724:2011, oferecendo um formato estruturado com contagem automática de orientações acadêmicas e publicações.

## Funcionalidades
- **Conformidade com ABNT**: Atende às normas para margens, fontes, títulos, tabelas e referências.
- **Contagem Automática**: Registra orientações (IC, ME, DR, PD) e publicações (artigos, livros, etc.) usando `biblatex`.
- **Metadados Personalizáveis**: Configuração fácil de detalhes do projeto, como título, coordenador e instituição.
- **Estrutura Modular**: Organizado em elementos pré-textuais, textuais e pós-textuais.
- **Suporte a Bibliografia**: Gerencia referências e publicações via arquivos `.bib` separados.

## Requisitos
- Distribuição LaTeX (e.g., TeX Live, MiKTeX)
- `biber` para processamento de bibliografia
- Pacotes necessários: `biblatex`, `titlesec`, `geometry`, `fancyhdr`, `etoolbox`, `tabularx`, `xstring`, `refcount`, `lmodern`, `fontenc`, `inputenc`, `babel`, `times`, `graphicx`, `xcolor`, `indentfirst`, `setspace`, `hyperref`, `caption`, `chngcntr`, `url`, `booktabs`, `multirow`, `multicol`, `amsmath`, `comment`, `subcaption`, `appendix`, `float`, `csquotes`, `enumitem`

## Instalação
1. Clone o repositório:
   ```bash
   git clone https://github.com/seuusuario/modelo-relatorio-fapesp.git
   ```
2. Certifique-se de que todos os pacotes LaTeX necessários estão instalados.
3. Coloque seus arquivos `.bib` no diretório `Pós-Textual/`.
4. Personalize os arquivos em `Pré-Textual/` (e.g., `capa.tex`, `resumo.tex`) com os detalhes do projeto.

## Uso
1. Edite `Pré-Textual/capa.tex` para definir metadados (e.g., `\titulo{Título do Seu Projeto}`).
2. Adicione conteúdo aos capítulos em `Textual/` (e.g., `cap1_introducao.tex`).
3. Atualize `Pós-Textual/referencias.bib` e `publicacoes.bib` com referências e publicações, usando palavras-chave (e.g., `arti`, `livro`).
4. Compile o documento:
   ```bash
   pdflatex fapesp.tex
   biber fapesp
   pdflatex fapesp.tex
   pdflatex fapesp.tex
   ```
5. Saída: `fapesp.pdf`

### Compilação no Overleaf
- O projeto pode ser importado para o Overleaf.
- **Recomendações para contas gratuitas**:
  - Desabilite a checagem de sintaxe no menu de configurações para evitar falsos positivos.
  - Use o compilador LaTeX2e de 2021 (modo legado) para garantir compatibilidade.
- Para configurar, acesse o menu do Overleaf, selecione "Compiler" e escolha "LaTeX (Legacy)".

### Compilação com TeXstudio e MiKTeX
- O projeto também pode ser compilado localmente usando TeXstudio com MiKTeX.
- Certifique-se de que o MiKTeX está atualizado e que o `biber` está instalado.
- Configure o TeXstudio para executar a sequência de compilação acima.

## Estrutura do Diretório
```
modelo-relatorio-fapesp/
├── abnt/
│   └── fapesp.sty              # Estilos e comandos personalizados
├── Pré-Textual/
│   ├── capa.tex                # Configuração da capa
│   ├── folhadeinformacoes.tex  # Página de informações do projeto
│   ├── resumo.tex              # Resumo e abstract
│   ├── pretextual.tex          # Elementos pré-textuais consolidados
├── Textual/
│   ├── cap1_introducao.tex     # Capítulo de introdução
│   ├── cap2_atividades_realizadas.tex # Capítulo de atividades realizadas
│   ├── cap3_planejamento_atividades.tex # Capítulo de planejamento
│   ├── cap4_prod_cientifica.tex # Capítulo de produção científica
│   ├── cap5_conclusao.tex      # Capítulo de conclusão
├── Pós-Textual/
│   ├── apendices.tex           # Apêndices (orientações, etc.)
│   ├── anexos.tex              # Anexos
│   ├── referencias.bib         # Bibliografia de referências
│   ├── publicacoes.bib         # Bibliografia de publicações
├── snippets.tex                # Trechos de código reutilizáveis
├── fapesp.tex                  # Arquivo LaTeX principal
├── README.md                   # Este arquivo
└── .gitignore                  # Exclui arquivos temporários LaTeX
```

## Personalização
- **Metadados**: Ajuste comandos como `\titulo`, `\coordenador` em `Pré-Textual/capa.tex`.
- **Orientações**: Use `\begin{orientacao}{tipo} ... \end{orientacao}` em `apendices.tex` (e.g., `tipo=ic` para Iniciação Científica).
- **Publicações**: Adicione entradas em `publicacoes.bib` com palavras-chave (e.g., `arti` para artigos indexados).
- **Estilos**: Modifique `fapesp.sty` para personalizar formatação (e.g., margens, títulos).

## Exemplo de Compilação
Para testar com dados de exemplo:
1. Adicione entradas em `publicacoes.bib`:
   ```bib
   @article{exemplo1,
     author = {Nome do Autor},
     title = {Artigo de Exemplo},
     journal = {Nome do Periódico},
     year = {2025},
     keywords = {arti}
   }
   ```
2. Adicione orientações em `apendices.tex`:
   ```latex
   \appendixsection{Orientações}
   \begin{orientacao}{ic}
     \item Nome do Estudante, Título do Projeto, 2025
   \end{orientacao}
   ```
3. Compile conforme descrito acima.

## Contribuições
Contribuições são bem-vindas! Por favor:
1. Envie issues para relatar bugs ou sugerir melhorias.
2. Crie pull requests com descrições claras.
3. Siga o estilo de codificação de `fapesp.sty`.

## Licença
Este projeto está licenciado sob a licença Creative Commons Zero (Uso livre e irrestrito, não é obrigado nem a referenciar o meu trabalho, mas agradeceria se o fizesse)

## Contato
Para dúvidas, entre em contato com André Lourenço em andreluizfl@gmail.com ou andreluizfl@usp.br
