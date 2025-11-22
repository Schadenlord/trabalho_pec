
# Trabalho: Pensamento Econômico Contemporâneo (PEC)

Repositório contendo a apresentação em LaTeX preparada para a disciplina "Pensamento Econômico Contemporâneo (PEC)" do curso de Ciências Econômicas — UDESC-ESAG.

Este projeto é um modelo de slides em Beamer desenvolvido por Bruno Francisco Schaden e organizado para uso em apresentações acadêmicas. O conteúdo principal está em `main.tex` e os slides estão divididos no diretório `textual/` para facilitar a edição.

**Conteúdo principal:**
- **Título:** `main.tex` — arquivo principal da apresentação Beamer.
- **Tema:** arquivos do tema Beamer personalizados em `Theme/` (`beamerthemeoxonian.sty`, `beamercolorthemeoxonian.sty`, etc.).
- **Slides/Conteúdo:** `textual/content.tex` (conteúdo organizado por seções e subseções).
- **Referências bibliográficas:** `References.bib`.
- **Imagens:** pasta `img/` (use esta pasta para acrescentar figuras à apresentação).

**Objetivo deste repositório**
- Servir como base para o trabalho da disciplina PEC.
- Permitir compilar a apresentação em PDF via LaTeX localmente ou em serviços como Overleaf.
- Facilitar adaptação do tema e do layout para futuras apresentações acadêmicas.

## Estrutura do repositório

- `main.tex` — documento principal que inclui o tema e os arquivos de conteúdo.
- `textual/` — conteúdo dos slides dividido em arquivos (atualmente `content.tex`).
- `Theme/` — arquivos do tema (cores, fontes, logos, pacotes). Importante: manter esta pasta junto com o `main.tex` para que o tema funcione corretamente.
- `References.bib` — arquivo BibTeX com as referências citadas nos slides.
- `img/` — imagens e logos usados na apresentação.
- Arquivos auxiliares gerados pela compilação LaTeX (ex.: `main.aux`, `main.log`, `main.pdf`, etc.) não precisam ser versionados — ver `.gitignore` se quiser adicioná-lo.

## Requisitos e dependências

- Distribuição TeX completa recomendada (por exemplo, TeX Live full) para evitar falta de pacotes:

	- Em distribuições Debian/Ubuntu, uma instalação simples é:

```bash
sudo apt update
sudo apt install texlive-full
```

	- Observação: `texlive-full` é grande; se preferir uma instalação menor, instale os pacotes necessários quando um erro pedir (por exemplo `texlive-latex-recommended`, `texlive-latex-extra`, `biber`, `bibtex`, `latexmk`, etc.).

- Pacotes específicos possivelmente necessários: `beamer`, `fontawesome` (ou `fontawesome5`), `abntex2` (para estilo de bibliografia `abntex2-alf`), `graphicx`, `xcolor`, entre outros. O arquivo `Theme/Packages.tex` lista pacotes usados — verifique-o quando ocorrerem erros de compilação.

## Como compilar (local)

Opções recomendadas para gerar o PDF da apresentação:

- Usando `latexmk` (recomendado, automatiza passos):

```bash
latexmk -pdf main.tex
```

- Ou passo a passo (caso não use `latexmk`):

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

Observações:
- O projeto faz uso de `
bibliographystyle{abntex2-alf}` e `\bibliography{References}`; portanto, se estiver usando `biber` em vez de `bibtex`, adapte o fluxo conforme necessário.
- Para visualização contínua durante edição: `latexmk -pdf -pvc main.tex` (recompila automaticamente a cada salvamento).

## Como editar o conteúdo

- Edite o conteúdo dos slides em `textual/content.tex`. O arquivo já está organizado por seções e subseções; mantenha a estrutura `\section{}` / `\subsection{}` para o sumário funcionar automaticamente.
- Para adicionar imagens, coloque arquivos em `img/` e inclua-os com `\includegraphics{img/nome_da_imagem}`.
- Se precisar alterar cores, fontes ou o logo, edite os arquivos na pasta `Theme/` (principalmente `Packages.tex` e os `.sty` do tema).

## Boas práticas

- Não versionar arquivos gerados (aux, log, toc, nav, snm, bbl) — adicione um `.gitignore` para ignorá-los.
- Faça commits pequenos e descritivos: `git add` / `git commit -m "Atualiza seção de Introdução"`.
- Use ramos (`git checkout -b nome-da-feature`) para alterações maiores.

## Sugestões para apresentação

- Verifique resolução das imagens (prefira 300 dpi para impressão, 150–200 dpi para tela).
- Teste a apresentação em tela cheia antes de apresentar para garantir legibilidade das fontes.
- Caso use projeção em auditório, aumente tamanhos de fonte para textos longos.

## Licença e créditos

Este repositório contém material preparado por Bruno Francisco Schaden. Caso reutilize o tema ou partes do material, mantenha os créditos e atribua o autor original. Se quiser que eu inclua um cabeçalho de licença (por exemplo MIT), diga qual licença prefere.

Observação: os arquivos `.sty` do tema (na pasta `Theme/`) foram criados por Bruno Francisco Schaden para personalizar trabalhos acadêmicos e apresentações.

## Como contribuir

- Sugestões de conteúdo ou correções: abra uma issue descrevendo a proposta.
- Para contribuições diretas: faça um fork, crie um branch e envie um pull request com descrição clara das mudanças.

## Contato

- Autor: Bruno Francisco Schaden
- Repositório original / issues: https://github.com/Schadenlord/slide-esag

---

Se quiser, eu posso:
- adicionar um `.gitignore` sugerido para LaTeX;
- gerar automaticamente um PDF compilado e adicioná-lo ao repositório (se desejar que deixe o PDF versionado);
- ajustar o README para incluir instruções do Overleaf ou um template de commit.

