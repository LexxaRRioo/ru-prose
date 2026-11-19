# Course materials

For text a student reads and carries out: lessons, labs, exercises, homework, hints. Reader by
default: intermediate Data Engineer who already writes SQL. Ask if the audience differs.

## The student is the actor

Instructions are imperative and addressed to the student. Never the impersonal third-person plural
(«удаляют», «поднимают», «смотрят»): it describes what unnamed people do and leaves the reader
unsure which sentences are theirs to carry out.

- До: «сначала удаляют слот, потом поднимают задачу» -> После: «сначала удалите слот, потом
  поднимите задачу»
- До: «Проверять результат стоит в трёх местах» -> После: «Результат проверьте в трёх местах»
- До: «Вы регистрируете коннектор заново на ту же таблицу» -> После: «Зарегистрируйте коннектор
  заново на ту же таблицу»

The fix is the imperative itself, not «вы» plus a present-tense verb: that form still describes.
Impersonal plural stays only where the sentence is about specific other people: «В реальных
компаниях проверку вешают и на строку задачи, и на слот». "How the industry does it" in handouts
does not qualify: use the forms from "One sentence template" in SKILL.md. Where the actor is a mechanism, name it:
«сегмент, в который пишут сейчас» -> «сегмент, в который идёт запись».

A UI element is the object, never the actor: not «Разворачивает его кнопка слева от логотипа»
but «разверните его кнопкой слева от логотипа».

Imperative for UI actions: «Откройте боковую панель». Spoken DE jargon is welcome: «Смержите
`test` обратно в `dev`», «Откройте merge request».

## Explanation

- **Fail-first.** When a topic has a natural wrong way, the student runs it first, sees the error
  or wrong result, then gets the fix, then the explanation of the failure.
- **Predict-then-verify.** Before a revealing step, the student commits to an expectation:
  «Прежде чем открыть вкладку `Airflow PROD`, предположите, что там произойдёт в ближайшую
  минуту». The answer never follows as the next paragraph: it goes into a collapsible block
  titled «Ответ», or is left to what the student sees on screen.
- **Explain what the student already saw.** Send them to look first, then explain. Never narrate
  a result they have not seen: «`schema_check` упадёт», «в логе будет строка», «вы увидите». A
  fact about how the system works may come first, in the present tense: «Задача `schema_check`
  теперь проверяет два контракта. Откройте её лог...».
- **The system's point of view.** Say what the system tracks and when it picks up a change, then
  why that does or does not trigger the action:
  - До: «Витрина не изменилась: её запуск за вчера уже прошёл, и Airflow сам его не повторит»
  - После: «Airflow не отслеживает изменения данных в `trips_enriched` и отвечает только за
    запуски по расписанию. Запуск витрины за вчера прошёл ещё до исправления, поэтому для Airflow
    задача уже выполнена»
- **Realistic mini-scenarios.** Breakage is a plausible workplace event: «считайте, что его
  случайно выполнил коллега, перепутав знак в условии».
- **Anchor to what a RU DE already knows**: Greenplum, Kafka, HDFS, layer analogies («Аналог
  DDS»), production contrast with «В проде…» / «В реальных компаниях…».
- **The student-facing consequence**, not the internal mechanism, for rules that exist for the
  course's own plumbing: «только на такие имена вам выданы права» -> «только с таким названием
  тесты самопроверки сработают».
- **Expected result** before or right after each verification step, in concrete numbers: «Должно
  получиться чуть больше 10 миллионов».
- **Odd-looking code** gets one sentence of explanation right next to it.
- Never explain SQL syntax or basic engine concepts; always explain distributed behaviour,
  defaults and version caveats.
- Interchangeable terms are declared once at first use, then used freely.
- No wall-clock figures as facts («загрузка идёт около 45 секунд»): say what to watch, or give
  the order of magnitude.

## Structure

- Exercises: a scenario, a numbered task list, then a collapsible hint titled «Подсказка». The
  hint gives the reasoning path and the key function name, never the finished answer.
- Each page ends with a one-line bridge to the next that hints without giving away the twist:
  «Дальше - изменение коллеги, которое попало в PROD в обход TEST».
- Headings say what and where; an English term the student will meet goes in brackets: «Срочное
  исправление в PROD (hotfix)».
- Cross-references cite the section title in «ёлочках» with the number the student can see.
- Product naming: «лаба» (informal) or «лабораторный стенд» (formal), never «песочница»,
  «sandbox», «demo», «лаборатория».
- Diagrams carry no prose and no note boxes; the text around them explains.

## Self-check questions and handouts

- Questions test only what the text above explained. No technical depth the handout never
  covered.
- A tool class gets several examples, so one tool does not read as the class: OLTP is not
  "always Postgres".
- No recommendations that "happen" to lead to the author's course.
- Sources go inline where they support a point, not as a "дополнительная литература" list.
