# 🧠 Cérebro: memória permanente pro Claude Code com Obsidian

Toda IA esquece tudo quando você fecha o chat. Com este template, o Claude Code passa a lembrar quem você é, em que você trabalha e o que vocês combinaram, em **qualquer chat novo**.

E a memória dele fica num vault do Obsidian: você abre, lê, corrige e vê tudo conectado no Graph View.

## Como funciona

```
~/.claude/CLAUDE.md                 (1 linha: aponta pro Cérebro)
        │
        ▼
Cerebro/00_Claude/CLAUDE.md         (suas regras: idioma, honestidade, organização)
        │
        ▼
Cerebro/03_Obsidian/Claude/_indice.md   (1 linha por assunto, lido em todo chat)
        │
        ▼
Cerebro/03_Obsidian/Claude/*.md     (notas completas, abertas só quando o assunto aparece)
```

1. O Claude Code lê `~/.claude/CLAUDE.md` em todo chat, em qualquer pasta.
2. Esse arquivo importa as suas regras, que importam o índice da memória.
3. O índice é curto (até ~50 linhas), então não pesa no contexto. As notas completas só são abertas quando precisa.
4. Quem escreve as notas é o próprio Claude. Diga "lembra que eu prefiro X" e ele cria ou atualiza a nota e o índice.

Além da memória, o `CLAUDE.md` organiza o seu computador: tudo de importante nasce dentro da pasta `Cerebro`, separado por categoria, e todo texto que você vai ler (planos, resumos, roteiros) vai direto para o Obsidian.

## Estrutura

```
Cerebro/
├── 00_Claude/        regras do Claude (CLAUDE.md) e prompts reutilizáveis
├── 01_Projetos/      projetos que não são código (troque pelo que fizer sentido)
├── 02_Codigo/        um projeto de código por pasta
├── 03_Obsidian/      o vault
│   ├── Painel.md     página inicial + legenda das pastas
│   ├── Claude/       memória do Claude (_indice.md + uma nota por assunto)
│   ├── Inbox/  Diario/  Projetos/  Estudos/  Pessoal/
│   └── Modelos/  Anexos/
└── 04_Estudos/       cursos, faculdade, materiais
```

As categorias são só um ponto de partida. O prompt de instalação adapta para o que você faz.

## Instalação

**Precisa de:** [Claude Code](https://claude.com/claude-code) e [Obsidian](https://obsidian.md) (grátis).

### Jeito fácil (recomendado)

Abra o [PROMPT-INSTALACAO.md](PROMPT-INSTALACAO.md), copie o prompt e cole num chat novo do Claude Code. Ele te faz umas perguntas e monta tudo.

### Jeito manual

1. Copie a pasta `Cerebro/` para onde quiser (ex.: `C:/Users/voce/Cerebro`).
2. Abra `Cerebro/00_Claude/CLAUDE.md` e troque todos os `{{...}}` pelos seus dados. Faça o mesmo em `03_Obsidian/Claude/voce.md`.
3. Crie (ou edite) `~/.claude/CLAUDE.md` com uma linha só, usando o caminho absoluto com `/`:
   ```
   @C:/Users/voce/Cerebro/00_Claude/CLAUDE.md
   ```
4. No Obsidian: "Abrir pasta como cofre" e escolha `Cerebro/03_Obsidian`.
5. Abra um chat novo no Claude Code e pergunte: "o que você sabe sobre mim?".

## Dicas pra tirar o máximo

- **Mantenha o índice curto.** Ele é lido em todo chat. Índice grande = contexto gasto à toa.
- **Corrija a memória.** Ele pode anotar coisa errada. Abra a pasta `Claude/` de vez em quando e edite ou apague.
- **Ensine com frases simples:** "lembra que...", "esquece que...", "atualiza a nota do projeto X".
- **Regra de honestidade:** o `CLAUDE.md` pede pra ele discordar de você quando você estiver errado e dizer "não sei" em vez de inventar. Não tire essa parte.
- **Plugins opcionais:** Tasks e Dataview deixam o `Painel.md` com listas automáticas de tarefas, projetos e dias.

## ⚠️ Cuidados

- **Nunca** deixe o Claude salvar senha, token ou chave de API na memória. São arquivos de texto comuns.
- Se você sincroniza o vault (Obsidian Sync, Google Drive, OneDrive, git), a memória vai junto para a nuvem.
- Antes de mostrar o vault em vídeo ou print, confira se não tem dado pessoal nas notas.

## Licença

MIT. Use, copie e adapte à vontade.
