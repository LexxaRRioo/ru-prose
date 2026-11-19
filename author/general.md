# Author's conventions: all texts

The author's own conventions, on top of SKILL.md and the medium file. They win over both where
they conflict. Someone adopting the skill replaces the `author/` folder with their own
conventions or deletes it.

## Address form by project

The DE system design course uses «ты» everywhere: video scripts, slides, handouts, program.
Vacancies and channel-facing texts use «ты». Labs and older course materials use «вы».

## Workflow

Before editing an existing file, check whether it sits in a git repo. If it does and has
uncommitted changes or is untracked, commit that file alone first («<file>: draft before edit»),
so the author sees the edit as a clean diff. Commit only that file, never other changes in the
repo.

## Claims

- The author's own experience over other companies' cases and numbers. No namedropping to back a
  point («Авито», «Магнит»): state the fact, or ask the author for their story.
- No self-promotion the author did not ask for: no plugs for their labs or products, no hints
  that steer toward the author's course.

## Banned vocabulary

| Banned | Use instead |
|---|---|
| «данные легли», «данные лягут», «результат ляжет» | «сохранились», «попали на шард», «оказались на», «находятся» |
| «завести таблицу», «заведём таблицу» | «создать таблицу», «создадим таблицу» |
| «прибитый к ноде» | «прикреплённый к ноде» |
| «цена», «чем платите» for cost in general, including table columns | «затраты» |
| «старый стек» about the reader's setup | «привычный стек» |
| «переиграть данные» | «повторно обработать» |
| «смежники» | «смежные команды» |
| «если не так» as a label | «альтернатива» |
| «Схемка» and other diminutives for artefacts | «Карточка», «схема» |
| «мимо» about writing past a table or interface | «в обход» |
| «переезжает», «переехал» about data or state | name the movement: «строки попадают на другой шард» |

## Typography

- Use «-» (hyphen with spaces), never the em dash «—», in every position Russian typography would
  put a тире.
- Write «ё» consistently.
- No hyphen between an abbreviation or loanword and the noun it modifies: «OLTP базы», «батч
  загрузка», «дата инженер», «дата инженерный».
- «ёлочки» only for citing a section or stage title; straight quotes for everything else: "нода".
- No emojis. Posts have one exception, see `author/posts.md`.
