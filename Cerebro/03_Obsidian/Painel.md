# 🏠 Painel

Página inicial do vault. As listas abaixo usam os plugins da comunidade **Tasks** e **Dataview** (opcionais). Sem eles, aparece só o código.

Tarefa com data aparece aqui: `- [ ] gravar vídeo 📅 2026-12-01`

## 🔥 Atrasadas e de hoje
```tasks
not done
due before tomorrow
sort by due
```

## 📥 Inbox para organizar
```dataview
LIST
FROM "Inbox"
SORT file.ctime DESC
```

## 🚀 Projetos
```dataview
TABLE status, atualizado
FROM "Projetos"
SORT file.name ASC
```

## 📅 Últimos dias
```dataview
LIST
FROM "Diario"
SORT file.name DESC
LIMIT 7
```

---

## Legenda das pastas
O Claude usa esta tabela para decidir onde salvar cada nota.

| Pasta | Para que serve |
|---|---|
| 📥 Inbox | Nota sem lugar claro nasce aqui. Arquivar na pasta certa depois. |
| 📅 Diario | Uma nota por dia (AAAA-MM-DD). |
| 🚀 Projetos | Uma página por projeto: status, decisões, próximos passos. |
| 🎓 Estudos | Cursos, faculdade, resumos de livros e aulas. |
| 🙂 Pessoal | Listas e coisas pessoais. |
| 🧠 Claude | Memória do Claude. Ele lê e escreve aqui. |
| 🧩 Modelos / 📎 Anexos | Modelos de nota e arquivos colados. |
