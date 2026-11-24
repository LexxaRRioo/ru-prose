# Author's conventions: data engineering

On top of `data-engineering.md` and `author/general.md`.

- Reader by default: intermediate Data Engineer who already writes SQL.
- Anchor to what a RU DE already knows: Greenplum, Kafka, HDFS, layer analogies («Аналог DDS»),
  production contrast with «В проде…» / «В реальных компаниях…».
- Never explain SQL syntax or basic engine concepts; always explain distributed behaviour,
  defaults and version caveats.
- «DE» in running text on slides becomes «дата инженер».

## Banned vocabulary

| Banned | Use instead |
|---|---|
| «данные легли», «данные лягут», «результат ляжет» | «сохранились», «попали на шард», «оказались на», «находятся» |
| «прибитый к ноде» | «прикреплённый к ноде» |
| «переиграть данные» | «повторно обработать» |
| «переезжает», «переехал» about data or state | name the movement: «строки попадают на другой шард» |
