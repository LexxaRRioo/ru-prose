# Slides

Two texts with different rules: what is on the slide, and what the speaker says (notes, video
script). Speaker notes and scripts follow SKILL.md in full. Slide text follows SKILL.md except
where this file says otherwise.

## Slide text reads like speech, not like a label

A short, abrupt, "optimized" slide loses the idea and costs the author a manual rewrite. Write
slide text the way the speaker would say it, only shorter.

- Bullets are short phrases with a finite verb:
  - До: «события в raw постоянно» -> После: «события постоянно пишутся в raw»
  - До: «итог: решилось за пару дней» -> После: «проблема решилась за пару дней»
  - До: «Минус, часто решающий» -> После: «Минус, который часто решает исход секции»
- One bullet may carry a cause and its effect joined by «поэтому»:
  - До: «Kafka доставляет хотя бы один раз → дубли: тест» -> После: «Kafka доставляет "at least
    once", поэтому нужен тест на дубли»
- No «X: Y» label pairs or participles in place of a verb:
  - До: «Одна компания: один вариант на блок. Разные задачи: несколько» -> После: «В одной
    компании видишь один вариант на блок, на разных задачах - несколько»
  - An arrow is fine between two full actions: «пропускаешь вопросы → решаешь другую задачу».
- Show the items themselves, not abstract group labels for them:
  - До: «Объём и рост: вопрос 1 / Потребители: вопрос 2» -> После: «1. Сколько данных сейчас и
    сколько прибавляется в месяц? 2. Кто пользуется данными: 3 аналитика или 150 подключений?»
- Bare nouns get the scale or qualifier that makes them concrete: «банковские проекты» ->
  «банковские проекты с миллиардами строк и тысячами таблиц».
- Numbers concrete and with units: «10 млн строк за 4 с», not «быстро на больших объёмах».
- At most five bullets, each up to two lines. No paragraphs. Bullets in one list share a
  grammatical shape.
- Neutral step labels in a story: «04 проблема», «05 решение», not «тупик», «спасение».

## Titles

Short and plain. Any of these shapes works:

- a topic label: «Data lake vs Lakehouse», «Ingest: Сравнение способов загрузки», «Связанные
  хранение и вычисления»;
- a «Что / Для кого» clause: «Что теряется из-за неполных требований», «Что будет при росте в 10
  и в 100 раз», «Для кого курс»;
- a plain sentence when the slide makes one claim: «На систем дизайне нужно понять проблему и
  решать именно её»;
- «Опыт:» in front of a story slide: «Опыт: Отдельная реплика для аналитиков».

Never a compressed "generalized fact" that packs the whole argument into one noun phrase:

- До: «Свежесть около суток и невидимые удаления при загрузке по расписанию» -> После: «Ingest:
  Сравнение способов загрузки»
- До: «Свойства инструментов важнее их названий» -> После: «На систем дизайне нужно понять
  проблему и решать именно её»

No tool enumerations or clarifying tails: «...в Hadoop, Greenplum и ClickHouse» and «...на каждом
переходе между системами» go. No witty or teaser titles. Service slides take the speaker's voice:
«О чём буду говорить следующие 50 минут», «Что в меню / Что не включено».

## Deck structure

- One idea per slide. A topic that needs a comparison, a before/after or a second example gets
  another slide, not a denser one.
- Signpost the talk: an agenda slide that sets realistic expectations, and a divider slide at
  each section boundary.
- A conclusion or "harsh truth" slide comes after the context it needs.
- A slide about a technology lists what the audience gains, not its spec:
  - До: «Row-level deletes: position и equality delete-файлы, sequence numbers» -> После:
    «UPDATE, DELETE и MERGE без перезаписи партиций: CDC и upsert прямо в озеро»
- A calculation is a table «что считаем | расчёт | итог» where each result feeds the next row.
  Plain notation: «2 млн», never «2e6», no fake terminal output.
- No closing «Выводы» slide that repeats earlier slides; the last slide is the next action or the
  contacts.
- Code on a slide: only the lines the point is about, with the key line highlighted.
- Diagrams carry labels, not sentences.

## Decoration

- No meta eyebrows, taglines or breadcrumbs: «system design · data engineer», «шаг 1 · требования»
  under the title «Шаг 1», «// собес интервьюер // работа техлид». One line saying what the video
  or section is about replaces them.
- The author's name and links are not on every slide.
- Examples: only as many as the point needs («Postgres, Oracle, MSSQL» -> «Postgres»). No minute
  counts in the talk map.

## Voice on slides

- The speaker's first person and practitioner slang belong on slides too: «Затащил офферы:»,
  «Рабочие байки», «СисДиз».
- A single «:)» is allowed for a light remark in a bullet or table cell: «Не гарантируется :)».
- Polls are spoken questions: «На чём у вас сейчас основное аналитическое хранилище?», «Ответьте
  в чате».

## Slide and notes together

- Each fact appears once: either on the slide or in the notes. The notes never read the bullets
  aloud; they add the reasoning, the example, the transition.
- A list the speaker reads aloud, or a bonus handed out at the end, does not appear on a slide
  before then.
- The notes open with the link to the previous slide when there is one («Поэтому...», «А
  теперь...»), not with an announcement of what the slide shows.
