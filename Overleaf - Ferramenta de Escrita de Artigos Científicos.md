# **📘 Tutorial: Como Utilizar o Overleaf para Escrever Artigos Científicos (LaTeX)**

## **1️⃣ Introdução ao Overleaf**

O **Overleaf** é uma plataforma online que permite escrever, editar e compilar documentos em LaTeX de forma colaborativa, sem a necessidade de instalar programas no computador. É amplamente utilizado para a produção de artigos científicos, relatórios e trabalhos acadêmicos.

### **<img src="https://images.ctfassets.net/nrgyaltdicpt/2fJT673XY7Jyx0hnloYH5u/e8ab3a07b40ed4b9c18756d7741ef4dc/overleaf-o-logo-primary.png" width="20"> Onde Encontrar o Overleaf?**

- Acesse: [https://www.overleaf.com](https://www.overleaf.com)
- Crie uma conta gratuita (ou faça login com Google, ORCID, etc.).

---

## **2️⃣ Como Usar um Template da SBC no Overleaf**

A **Sociedade Brasileira de Computação** (SBC) fornece templates oficiais para artigos científicos. Veja como encontrá-los e usá-los:

### **📄 Localizando o Template da SBC**

1. **No site da SBC**  
   - Acesse: [https://www.sbc.org.br/wp-content/uploads/2024/07/modelosparapublicaodeartigos.zip](https://www.sbc.org.br/wp-content/uploads/2024/07/modelosparapublicaodeartigos.zip)  
   - Baixe o template em LaTeX (`.zip`).

2. **No Overleaf**  
   - Após logar, clique em **"New Project"** → **"Upload Project"** e envie o `.zip` baixado.  
   - Ou use o template direto no Overleaf:  
     - No Overleaf, vá em **"New Project"** → **"Browse Templates"** e pesquise por **"SBC"** (pode não estar disponível, então o upload manual é mais garantido).

---

## **3️⃣ Comandos Básicos do LaTeX**

Aqui estão os principais comandos para escrever seu artigo:

### **📑 Estrutura Básica**

```latex
\documentclass{sbc-template} % Classe do template SBC
\usepackage[utf8]{inputenc} % Permite acentuação
\usepackage[brazil]{babel} % Texto em português

\title{Título do Artigo}
\author{Autor 1\inst{1}, Autor 2\inst{2}}
\address{Instituto 1\inst{1}, Instituto 2\inst{2}}

\begin{document}
\maketitle % Gera o título, autores e afiliações

\begin{abstract}
    Resumo do artigo.
\end{abstract}

\section{Introdução}
Texto da introdução.

\section{Referencial Teórico}
Mais texto aqui.

\bibliographystyle{sbc} % Estilo SBC para referências
\bibliography{referencias} % Arquivo .bib com as referências

\end{document}
```

### **📋 Listas**

As listas em LaTeX podem ser de dois tipos: não ordenadas (`itemize`) e ordenadas (`enumerate`).

- **Listas não ordenadas (`itemize`)**
  - São listas onde os itens não possuem uma numeração específica.
  - Cada item é representado com um marcador.

```latex
\begin{itemize}
    \item Primeiro item da lista
    \item Segundo item da lista
    \item Terceiro item da lista
\end{itemize}
```

- **Listas ordenadas (`enumerate`)**
  - São listas numeradas automaticamente.
  - Os números são gerados de forma sequencial.

```latex
\begin{enumerate}
    \item Primeiro item da lista
    \item Segundo item da lista
    \item Terceiro item da lista
\end{enumerate}
```

Caso precise criar sublistas, basta aninhar `itemize` ou `enumerate` dentro da lista principal.

---

### **📊 Tabelas**

O ambiente `tabular` é utilizado para criar tabelas no LaTeX. A estrutura básica de uma tabela é:

```latex
\begin{table}[h]
\centering
\caption{Título da Tabela}
\begin{tabular}{|l|c|r|} % Define três colunas: esquerda (l), centro (c) e direita (r)
\hline
Nome & Idade & País \\ \hline
João & 25 & Brasil \\ \hline
Maria & 30 & Portugal \\ \hline
\end{tabular}
\end{table}
```

- O comando `\hline` adiciona linhas horizontais.
- As colunas são separadas por `&`, e as linhas são finalizadas com `\\`.
- `|l|c|r|` define o alinhamento das colunas:
  - `l` (left) – alinhado à esquerda.
  - `c` (center) – centralizado.
  - `r` (right) – alinhado à direita.

Se desejar adicionar títulos às colunas, basta incluí-los na primeira linha, separados por `&`, e adicionar um `\hline` abaixo.

---

### **🖼️ Figuras**

Para inserir imagens no LaTeX, utilizamos o pacote `graphicx` e o comando `\includegraphics`.

```latex
\begin{figure}[h]
\centering
\includegraphics[width=0.5\textwidth]{imagem.png}
\caption{Legenda da Figura}
\label{fig:exemplo}
\end{figure}
```

Explicação dos comandos:

- `\begin{figure}[h]` – Cria um ambiente para a figura e indica que ela deve aparecer na posição `h` (here, ou seja, no local mais próximo possível).
- `\centering` – Centraliza a imagem.
- `\includegraphics[width=0.5\textwidth]{imagem.png}` – Insere a imagem `imagem.png` com largura de 50% do texto.
- `\caption{Legenda da Figura}` – Adiciona uma legenda abaixo da imagem.
- `\label{fig:exemplo}` – Cria uma referência interna para a figura, que pode ser usada no texto com `\ref{fig:exemplo}`.

Caso a imagem não seja carregada, verifique se o arquivo está no diretório correto e com a extensão suportada (como `.png` ou `.jpg`).

---

## **4️⃣ Como Fazer Citações no LaTeX**

### **📌 Citação Direta**
Citação fiel ao texto original, colocada entre aspas:

```LaTeX
Segundo Autor (2020), "o uso do LaTeX melhora a qualidade dos artigos".
```

Ou utilizando o pacote `cite` e BibTeX:

```LaTeX
Segundo Autor \cite{autor2020}, "o uso do LaTeX melhora a qualidade dos artigos".
```

### **📌 Citação Indireta**
Parafraseando a ideia do autor sem aspas:

```LaTeX
De acordo com Autor \cite{autor2020}, o LaTeX é uma ferramenta poderosa para escrita acadêmica.
```

### **📌 Citação Longa**
Citações com mais de 3 linhas devem ser destacadas com o ambiente `quote`:

```latex
\begin{quote}
    "O LaTeX permite uma formatação profissional e bem estruturada para artigos acadêmicos, oferecendo vantagens como referenciamento automático e fácil gestão de bibliografias." \cite{autor2020}
\end{quote}
```

---

## **5️⃣ Como Adicionar Referências com BibTeX**

### **Criando um arquivo BibTeX**
Crie um arquivo chamado `referencias.bib` e adicione suas fontes no formato:

```latex
@article{autor2020,
    author = {Nome do Autor},
    title = {Título do Artigo},
    journal = {Nome do Periódico},
    year = {2020},
    volume = {10},
    number = {2},
    pages = {1--10}
}
```

Para referenciar no texto, use `\cite{autor2020}`.

---

## **6️⃣ Ferramentas Externas úteis**

### **📄 Geradores de Tabelas LaTeX**
- [https://www.tablesgenerator.com/](https://www.tablesgenerator.com/)
  - Facilita a criação de tabelas no formato LaTeX.

### **🔖 Geradores de BibTeX**
- [Google Scholar](https://scholar.google.com.br/)
  - Procure um artigo, clique em `Citar` e copie o formato BibTeX.
  
- [Zotero](https://www.zotero.org/)
  - Gerencia referências e exporta arquivos `.bib` facilmente.

>[!WARNING]
>Lembre-se sempre de verificar se a ferramenta gerou corretamente o BibTeX.

### **🌐 Extensões para Navegador**
- [BibTeX entry from URL](https://chromewebstore.google.com/detail/bibtex-entry-from-url/mgpmgkhhbjgkpnanlmlhibjfgpdpgjec?hl=pt-BR)
  - Cria um BibTeX para qualquer site visitado.

>[!CAUTION]
>É necessário preencher manualmente informações de `autor` e `data`.
>
>A extensão classifica todas as entradas como `@misc` ou `@online`, o que não é o mais adequado para artigos científicos.

## **✅ Conclusão**

Agora você está pronto para escrever seu artigo científico no Overleaf usando o template da SBC! Pratique os comandos LaTeX, faça citações corretamente e utilize ferramentas externas para melhorar seu fluxo de trabalho.

>[!IMPORTANT]
>Sempre revise o PDF gerado antes de submeter seu artigo!  

🚀 **Boa escrita acadêmica!**
