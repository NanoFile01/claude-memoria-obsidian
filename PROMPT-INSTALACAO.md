# Prompt de instalação

Copie tudo dentro do bloco abaixo e cole num chat novo do **Claude Code**. Ele vai te fazer algumas perguntas e montar tudo sozinho.

```text
Quero configurar o sistema "Cérebro": uma pasta única onde fica tudo de importante com que eu trabalho, separado por categorias, e a memória permanente do Claude Code dentro de um vault do Obsidian.

Template: https://github.com/NanoFile01/claude-memoria-obsidian (pasta `Cerebro/` do repositório).

Siga estas etapas, nesta ordem. Não pule nenhuma.

## 1. Entrevista
Antes de criar qualquer coisa, me faça estas perguntas numa mensagem só e espere eu responder:
1. Meu nome.
2. Em que idioma você deve me responder.
3. O que eu faço (trabalho, estudo, projetos, hobbies) e meu horário, se eu quiser contar.
4. Meu nível técnico, para você ajustar as explicações (iniciante, intermediário, avançado).
5. Onde criar a pasta `Cerebro` (sugira `~/Cerebro`; se eu tiver um HD de dados, sugira a raiz dele).
6. Quais categorias de trabalho eu tenho. Sugira as padrão do template (`00_Claude`, `01_Projetos`, `02_Codigo`, `03_Obsidian`, `04_Estudos`) e proponha trocas com base no que eu respondi na pergunta 3 (ex.: `01_Videos` para quem cria conteúdo, `01_Clientes` para freelancer). `00_Claude` e `03_Obsidian` são obrigatórias e mantêm o nome.
7. Se eu já uso o Obsidian e quais pastas quero dentro do vault além das padrão (`Inbox`, `Diario`, `Projetos`, `Estudos`, `Pessoal`, `Claude`, `Modelos`, `Anexos`).

## 2. Baixar o template
- Clone o repositório numa pasta temporária (`git clone --depth 1`). Sem git, me peça para baixar o ZIP pelo botão "Code > Download ZIP" e me dizer onde ficou.
- Se a pasta `Cerebro` de destino já existir e não estiver vazia, pare e me pergunte o que fazer. Nunca sobrescreva arquivo meu.

## 3. Montar a pasta
- Copie `Cerebro/` do template para o destino escolhido.
- Renomeie e crie as pastas de categoria conforme a pergunta 6, mantendo o padrão `NN_Nome`. Remova os `.gitkeep`.
- Em `00_Claude/CLAUDE.md`, troque todos os campos `{{...}}` pelas minhas respostas:
  - `{{CAMINHO_CEREBRO}}`: caminho absoluto com barras normais (`/`), ex.: `C:/Users/ana/Cerebro` ou `/home/ana/Cerebro`. Nunca use `~` aqui.
  - `{{CATEGORIAS}}`: uma linha por pasta no formato ``- `NN_Nome/` — para que serve``.
  - `{{IDIOMA}}`, `{{NOME}}`, `{{QUEM_SOU}}` (2 a 4 frases curtas), `{{NIVEL}}`.
- Em `03_Obsidian/Claude/voce.md`, preencha `{{NOME}}`, `{{QUEM_SOU}}` e `{{DATA_HOJE}}` (AAAA-MM-DD).
- Atualize a tabela "Legenda das pastas" de `03_Obsidian/Painel.md` com as pastas finais do vault.
- Não mexa em `03_Obsidian/Modelos/`: os campos `{{date:...}}` de lá são do Obsidian.

## 4. Ligar no Claude Code
- O arquivo global é `~/.claude/CLAUDE.md` (no Windows: `C:\Users\<usuario>\.claude\CLAUDE.md`).
- Se ele já existir com conteúdo, faça um backup (`CLAUDE.md.bak`), me mostre o conteúdo e pergunte se quero mover essas regras para `00_Claude/CLAUDE.md`.
- No fim, `~/.claude/CLAUDE.md` deve ter só esta linha:
  `@<CAMINHO_CEREBRO>/00_Claude/CLAUDE.md`

## 5. Migrar memória antiga (se existir)
- Procure arquivos `.md` em `~/.claude/projects/*/memory/`.
- Se achar, me mostre a lista e pergunte se quero migrar. Se sim, transforme cada fato útil numa nota em `03_Obsidian/Claude/` no formato do modelo `Modelos/nota-memoria.md`, atualize `_indice.md` e deixe os arquivos antigos onde estão (eu apago depois, se quiser).

## 6. Conferir
- Procure `{{` em `00_Claude/` e `03_Obsidian/Claude/` e `Painel.md`. Não pode sobrar nenhum.
- Confirme que o caminho do `@import` existe de verdade (abra o arquivo por ele).
- Me mostre a árvore final de pastas (2 níveis) e o `00_Claude/CLAUDE.md` pronto.
- Apague a pasta temporária do clone.

## 7. Me diga o que falta eu fazer
Em passos curtos e numerados:
1. Abrir o Obsidian > "Abrir pasta como cofre" > escolher `<CAMINHO_CEREBRO>/03_Obsidian`.
2. Opcional: instalar os plugins da comunidade "Tasks" e "Dataview" para o Painel funcionar.
3. Fechar e abrir o Claude Code e, num chat novo, perguntar "o que você sabe sobre mim?" para testar.

Regras durante toda a instalação:
- Nunca apague nem sobrescreva arquivo meu sem perguntar.
- Nunca salve senha, token ou chave de API em nenhum arquivo.
- Se algo der erro (ex.: caminho com acento ou espaço), me explique em uma frase e proponha a correção antes de continuar.
```
