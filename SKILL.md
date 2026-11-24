---
name: ru-prose
description: |
  Rules for Russian prose. Use whenever writing, editing or reviewing Russian text: slides and
  speaker notes, course and lab materials, landing and sales copy, posts, emails, docs. Covers
  voice, word order, sentence length, linking, banned vocabulary, AI-slop patterns and
  punctuation, with до/после examples taken from the author's own edits. Load the medium file
  that matches the task (slides.md, course.md, posts.md), data-engineering.md for technical text
  about data platforms, and the author's conventions in author/.
---

# Russian prose rules

Every rule comes from the author's own manual edits. When in doubt, match those edits over any
general style advice, including the humanizer skill.

Tone: polite, direct, spoken-Russian phrasing, no lecture voice («не как в учебнике»).

Load by medium, in addition to this file. Then load the author's conventions: always
`author/general.md`, plus the `author/` file for the medium if it exists. On a conflict the
author's file wins over the medium file, and the medium file wins over this one.

| Text | Medium file | Author's file |
|---|---|---|
| Slides, speaker notes, talk outlines | `slides.md` | `author/slides.md` |
| Course materials, labs, exercises, anything a student carries out | `course.md` | `author/course.md` |
| Telegram and other social posts in the author's own channel | `posts.md` | `author/posts.md` |
| Emails, landing and sales copy, docs | this file only | - |

Technical text about data engineering also loads `data-engineering.md` and
`author/data-engineering.md`, whatever the medium.

This file and the medium files hold rules that work for any Russian text. `author/` holds one
author's choices: address forms per project, typography, signature formatting, words they dislike.

## Drafting

- Write Russian directly. Never draft in English for later translation: translation is the
  source of the calques these rules ban. Never use an English calque where a normal Russian
  word exists.
- Never let editing history leak into the text. No sentence argues against a version the reader
  never saw, justifies why something was added, or emphasises a correction. Test each sentence:
  would it read the same in a from-scratch draft? If not, rewrite it as a plain statement.
  Corrections belong in the chat reply.
- Apply these rules to every derived file too: slide HTML, bonus PDFs, scripts built from a plan.

## Voice

- The address form is set per project, and one text never mixes forms. Take it from the
  project's framing doc, its existing texts or `author/general.md`. If nothing settles it, ask.
  Never use the impersonal «следует выполнить».
- First-person plural present for joint actions: «Смотрим, какие базы данных видны», «Разберём
  это дальше». First-person singular only for the author's recommendations and opinions,
  sparingly: «рекомендую нажать Ctrl+B».
- Active verbs over bureaucratic passive:
  - До: «В этом материале будет описана концепция Lakehouse, показаны многие возможности Iceberg,
    проведено сравнение с DWH.»
  - После: «Мы разберём концепцию Lakehouse, пройдём по возможностям Iceberg на реальных
    операциях и сравним всё это с DWH.»
- Natural colloquialisms where a practitioner would say them: «грабли», «раскидывает по нодам»,
  «а то и по разным каталогам». The sentence around them stays grammatical and complete.
- Code, buttons and pages do not think, see or mention: «колонки, которые упоминает ваш `SELECT`»
  -> «колонки из вашего `SELECT`».

## Word order

Direct order: subject before predicate. Inversion is legal Russian, and generated text reaches for
it sentence after sentence, which makes the result sound literary and translated.

- До: «управляют им обычными HTTP-запросами» -> После: «им управляют обычными HTTP-запросами»
- До: «Отвечает Connect всегда в JSON» -> После: «Connect всегда отвечает в JSON»
- До: «Порядок Kafka гарантирует внутри партиции» -> После: «Kafka гарантирует порядок внутри
  партиции»

Inversion stays where the fronted word links the sentence to the previous one: «Отсюда два
написания одного имени». The test: does the first word repeat something the reader just read? If
a verb was pulled forward for rhythm, put it back.

**Actor at the end, object in front.** Russian marks both with the same form here, so the reader
cannot tell which noun acts until the sentence is over.

- До: «файл закрывает таймер» -> После: «таймер закрывает файл раньше счётчика»
- До: «Позицию хранит сам консьюмер» -> После: «Сам консьюмер хранит позицию»
- До (heading): «Почему шард выбирает Greenplum» -> После: «Почему Greenplum сам выбирает шард
  для каждой строки»

Headings suffer most: they are read with no sentence before them. For any «noun verb noun», read
the first noun as the subject; if the meaning changes, put the actor first.

**A place phrase in front is not a link.**

- До: «в `test` попадают только коммиты, готовые к релизу» -> После: «Ветка `test` принимает
  только коммиты, готовые к релизу»
- До: «В `dev` лежат изменения, которые ещё не прошли TEST» -> После: «`dev` содержит изменения,
  которые ещё не прошли TEST»

A noun in front of a code span («таблица», «колонка», «ветка») gives the sentence a subject. A
concrete verb («содержит», «хранит», «описывает») replaces the dash and «это». One fronted shape
stays: «для X есть Y».

**The object never opens an instruction.**

- До: «Коммит Трофима вы перенесёте в `test`» -> После: «Перенесите коммит Трофима в `test`»

**«X говорит, что...»** about a status line, field or response is a stamp. Say what it does:
«подтверждает», «означает только, что», «в ответе видно». For a field with a value, name the
value: «в `trace` лежит причина».

**An action noun does not act.** Put the real actor back, or drop the actor:

- До: «Удаление через REST API отключает коннектор» -> После: «Через REST API вы удаляете только
  сам коннектор»
- До: «Таблица собирает всё, что сломалось» -> После: «В таблице ниже собрано всё, что сломалось»

## Sentence length

More than three marks out of comma, dash and colon in one sentence means it holds two or three
sentences' worth of clauses. Split it. A code span and a «...» title count as one name; a plain
enumeration («офсет, партиция, ключ, время и значение») is one list. Those are the only exemptions.

- До: «Первую читает ваш исходный коннектор, третью - тот, который вы подняли в упражнении, а
  `..._pub2` не принадлежит никому.» -> После: «Первую читает ваш исходный коннектор, третью -
  тот, который вы подняли в упражнении. `..._pub2` не принадлежит никому.»

Do not attach a second thought to a finished sentence with a деепричастный оборот; start a new
sentence. Split any sentence carrying more than two ideas. An in-sentence enumeration of four or
more items becomes a bullet list. Two or more parallel parts (steps, tasks) go into a list.

Vary sentence length. Short sentences are fine; telegraphic fragments are not: every sentence has
a verb unless it is a list item.

## Linking and weight

Text without links reads choppy and dry. Links go between sentences and clauses as words:
«поэтому», «а», «но», «после чего», «прежде чем». They do not go in as nesting: among correct
variants, the one with fewer words, commas and subordinate clauses wins.

Cause first, then «поэтому», then the effect. A colon after a short verdict makes the reader work
out the link:

- До: «Новый коммит для повтора проверки не нужен: код не изменился» -> После: «Код не изменился,
  поэтому новый коммит для повтора проверки не нужен»

A general rule comes before the case it explains.

A preposition phrase is lighter than a bare case form when it names the means: «с помощью кнопки
**Clear Dag Run**», «в виде копии с другим хешем» (not «копией с другим хешем»).

A risk that is likely but not certain keeps its hedge, with the subject first: «Другие DAG в PROD
тоже могут читать эту колонку».

## Claims

The author edits for substance as often as for style. These rules cover what a text claims.

- Keep the author's exact point and its limits. Do not reshape a story or argument into a neater,
  broader claim: «проблема не в том, что данные разные. Проблема в том, что КОД разный».
- Every claim about a tool or the reader's current stack must survive an expert's objection. No
  "always" where it is "often": «write 3 sql dialects - also not always true»; «свежесть около
  суток» rather than an inflated contrast.
- Unpack any compressed claim. If a sentence needs the author to ask «почему? объясни мысль», it
  is not done. A reference the reader cannot decode (a case name, a routing trick) is explained or
  cut.
- Name what the reader gains, not an abstract verdict:
  - До: «Название инструмента без этой цепочки ответом не считается» -> После: «Расширить
    кругозор и перестать предлагать инструменты по привычке»
- Neutral words for the reader's current setup: «привычный стек», never «старый стек».
- A conclusion never undercuts the text's own thesis («можно оставить всё как было»).
- Honest numbers. Hours, prices and workload are realistic, never flattering to the offer.
- A calculation shows where every number comes from, in plain notation: «2 млн», not «2e6».

## Order of sections

Each section picks up where the previous one stopped. When the first line of a section does not
make that link by itself, the previous section ends with a bridge sentence that sets up the next
one:

- «Но это не даёт автоматическое повышение. Поэтому, если вас всё никак не повысят до сеньора на
  текущей работе, есть предложение.» -> next section: «Как проверить свой уровень»

When reviewing structure, read only the headings and the first and last sentence of each section.
If that skeleton does not read as one line of thought, move or bridge the sections.

## Rearranging blocks

Rearrange sections, paragraphs and sentences when that makes the text read more smoothly and
hold together better. The rules on word order and linking work inside a sentence. This pass works
on whole blocks:

- One thought per block. A paragraph that drifts to a second topic splits, and the second half
  joins the block that already covers that topic.
- Related blocks sit next to each other. When a later paragraph picks up a thought from three
  paragraphs back, move it up next to that thought.
- Context before detail: the general claim, then the example, then the exception. A definition
  comes before the first place that needs it.
- Within a paragraph, each sentence opens with something the previous one ended on. When two
  neighbours do not connect, swap them before you add a linking word.
- The last block leads into the ending (call to action, link, question). The reader should not
  have to jump topics to reach it.

Moving a block can strand a link word («поэтому», «а», «тоже») or a pronoun whose referent is now
below it. Reread every boundary you touched. Keep the author's content and wording: rearranging
changes order, not substance. List what moved in the chat reply.

## Banned vocabulary

Replace on sight, in any position (headings, body, captions, alt text):

| Banned | Use instead |
|---|---|
| «отказ» as a noun for an error | «ошибка». The verb stays legal: «ClickHouse откажется выполнять запрос» |
| «коннекция» | «подключение» |
| «представляет собой» | plain verb or dash construction: «Лабораторный стенд - небольшой кусок реального стека» |
| «молча», «молчит», «тихо», «тихий» for "without an explicit error" | name what is absent: «без явной ошибки», «`trace` пустой», «в логе ни одного сообщения», «ответ неполный, ошибки нет» |
| «плата», «цена», «компромисс» for a trade-off | state both sides plainly: «`double` округляет до пятнадцати значащих цифр», «промежуточные версии строки не сохраняются» |
| «в данной работе», «на данный момент» | «в этой работе», «здесь», «сейчас» |

## AI-slop patterns

**One sentence template.** Generated Russian repeats one shape: subject + present-tense active
verb + object, and fills a missing subject with the impersonal plural («выгружают», «задают»,
«хранят»). Each sentence is correct; the distribution reads as non-native. The author's own text
has about 4 verbs ending in -ут/-ют per 1000 words; generated drafts had 18. Never put a
third-person plural verb in two neighbouring sentences. Pick the form by what the sentence is about:

- a process or mechanism, actor unimportant -> -ся or a short participle:
  - До: «журнал, в который дописывают сообщения» -> После: «дописываются сообщения»
  - До: «Партицию выбирает хэш ключа» -> После: «Партиция выбирается по хэшу ключа»
  - До: «Подробно Iceberg разбирает урок 1.5» -> После: «разобран в уроке 1.5»
- an option or advice -> можно / полезно / нужно / лучше / могут + infinitive:
  - До: «На него ставят алерт» -> После: «Полезно ставить алёрт на лаг…»
  - До: «число партиций задают с запасом» -> После: «число партиций лучше задать с запасом»
- what the course does -> мы: «разбирают уроки 2.6 и 3.2» -> «разберём на уроках 2.6 и 3.2»
- a state -> находиться, быть, подходить: «Пока сообщения в retention» -> «Пока сообщения
  находятся в пределах retention»; «Так хранят текущее состояние» -> «Такой топик подходит для
  текущего состояния»
- a noun instead of the verb: «данные выгружают в озеро» -> «нужна выгрузка в озеро»

"Actor first" applies when the actor is named. "Active verbs over bureaucratic passive" bans
chains of «будет описана, показаны, проведено», not -ся verbs for a process.

**Epigram endings.** No punchline sentence that wraps the paragraph in a clever bow. State the
fact and stop.

- До: «Из трёх вариантов молча ошибается ровно один - тот, который выглядит самым обычным.»
- После: (deleted; the preceding sentences already said which variant fails)

**Rhetorical «не X, а Y».** Ban the strawman negation added for drama: nobody claimed X.

- До: «$snapshots, $manifests - не чёрный ящик, а обычные запрашиваемые таблицы» / «не экзотика,
  а обычный стек» -> После: «$snapshots, $manifests - обычные запрашиваемые таблицы» / «рабочая
  альтернатива классическому DWH»
- До (heading): «Две оси, а не одна» -> После: «Шарды и реплики как две оси»

Keep the contrast when the negated half tells the reader something they might wrongly assume:
«сортировка задаётся в запросе, а не в самой витрине». The rhetorical version is copular (the
negation sits right after a dash, «это» or «Дело»): «Это не пробел, а следствие устройства». The
informative version trails the real claim: «Проверка идёт по имени реплики, а не по пути». Drop
«не просто X» with or without the «а Y» half.

**Literary flourishes and drama.** Technical facts in plain words:

- До: «запросы, которые отвечают неправдой» -> После: «запросы, которые отвечают некорректно»
- До: «Перекос - половина беды. Вторая в том, что…» -> После: «Перекос - часть проблемы. Другая в
  том, что…»
- До: «Дальше - тот самый bronze-слой» -> После: «Дальше - bronze-слой»

**Intensifiers.** Cut «именно», «ровно», «буквально», «по-настоящему» unless the sentence is wrong
without them. «прямо» stays in «прямо из S3», «прямо сейчас».

**Minimisers.** «просто» says the thing is beneath attention:

- До: «Инициатор результаты просто складывает» -> После: «Инициатор складывает результаты»
- До: «вернул правдоподобный результат, просто неполный» -> После: «вернул правдоподобный
  результат, но неполный»

**Smileys.** No «:)». The sentence carries the tone or it has none. The author's files may allow
exceptions.

**Rule of three, anaphora.** Two items or a plain sentence instead of a rhythmic triple:

- До: «Ничего не почищено, ничего не типизировано толком, трогать нельзя» -> После: «Ничего не
  типизировано и не обработано толком, работать неудобно»

**Stacked adjectives and diminutives.** До: «реальный, изолированный кусочек общей песочницы» ->
После: «изолированный кусок общего стенда»

**Trailing reassurance and over-cautious qualifiers.** The fact reassures by itself:

- До: «можно выйти и вернуться позже, ничего не потеряв» -> После: «можно выйти и вернуться позже»
- До: «Она необратимо удаляет все ваши таблицы» -> После: «Она удаляет все ваши таблицы»

**Hedging asides.** One instruction instead of a lecture about edge cases:

- До: «порядок величины важнее точной цифры, данные периодически обновляются» -> После: (deleted)

**Scene-setting openers.** Start with content, not an announcement that content is coming:

- До: «Прежде чем трогать данные - коротко о модели, на которой держится всё остальное.» ->
  После: (deleted; the text starts with the first fact)

**Dense clever compression.** A packed abstraction unpacks into what it means for the reader:

- До: «только то, что появляется, когда серверов становится больше одного» -> После: «только то,
  как меняется работа DE и какие грабли можно собрать при добавлении шардов»

**Headings.** Formal, descriptive noun phrases naming the mechanism or the object. No punchy or
would-be-witty titles.

- До: «Кто съел память», «Вставка, которая отчиталась раньше времени» -> После: «Использование
  памяти», «Очередь Distributed-таблицы»

## Punctuation and typography

- Reach for the dash only where grammar leaves no alternative: subject-predicate («Trino -
  распределённый SQL-движок»), verb gapping («совпавшие обновляем, отсутствующие - вставляем»),
  «это»-constructions, elliptical predicates. Everywhere else replace it without touching a word:
  - explanation or gloss -> `:`
  - apposition, or a «поэтому» / «если» clause -> `,`
  - two independent sentences welded together -> `.`
  - paired parenthetical -> `( )`
- No «clause - punchline» endings. Keep dash constructions at roughly 9 per 1000 words; above ~12
  the dash does work a colon, comma or full stop should do. The humanizer's "17-21 em dashes per
  1000 words is normal Russian" calibration does not apply.
- Product names keep official capitalisation and alphabet: ClickHouse, MinIO, Telegram (never
  «телеграмм»).

## Grammar

Style rules do not catch grammar errors, and style edits create new ones: a reordered or split
sentence often keeps a case ending from its old shape. Headings are the riskiest place because no
context around them prompts the reader to reparse.

- Verb government: the verb takes the case and preposition it needs.
  - До: «Один раз я тянул уход три месяца» -> После: «Один раз я тянул с уходом три месяца»
- Agreement: case, gender and number of every adjective, participle and pronoun match their noun,
  including across a comma or a moved clause.
- Collocation: words that do not go together in normal speech, even when each is correct alone.

## Self-check before handing text over

Read once for each, in this order:

1. Every heading and every «noun verb noun»: who acts? Is the actor first?
2. Any sentence with more than three commas, dashes and colons.
3. Each «не ..., а ...»: does the negated half carry information?
4. Banned vocabulary from this file and `author/`, «просто», «именно», «ровно», dash count.
   Every verb ending in -ут/-ют: is it the impersonal plural, or the second one in a row?
5. Last sentence of each paragraph: epigram? First sentence of the text: announcement?
6. Any sentence that only makes sense against an earlier draft.
7. Claims: would an expert object? Is any thought compressed past what the reader can unpack? Is
   there a flattering number? Do the claim rules in `author/general.md` hold?
8. Headings plus first and last sentence of each section: one line of thought, every transition
   bridged?
9. Block order: one thought per paragraph, related blocks adjacent, context before detail, the
   last block leading into the ending. After any move, check the link words and pronouns at the
   seams.
10. Grammar, last, on the final text: one sentence at a time, headings included. For each verb,
    does it govern its object correctly? For each adjective, participle and pronoun, does it agree
    with its noun? Any pair of words a native speaker would not put together?
