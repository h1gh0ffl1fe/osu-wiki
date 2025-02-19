---
no_native_review: true
outdated: true
outdated_since: a4e45cf0738ff0ce2327cba8b9efe89d53e1ef9f
---

# Команды управления турниром

Далее следует список команд чата, предоставляемых для удалённого управления мультиплеерными комнатами турниров:

- `!mp make <name>` — Создаёт комнату турнира с указанным именем. Можно создать до 4 таких комнат.
  - Эта комната особенна тем, что она не закрывается при покидании её всеми игроками и защищена паролем от тех игроков, что попытаются войти в эту комнату самостоятельно.
  - Когда комната завершена, используйте `!mp close`, чтобы закрыть её.
- `!mp invite <username>` — Приглашает игрока в комнату.
  - Обратите внимание, что это *не* обходит любые блокировки личных сообщений, доступные в клиенте osu!, поэтому сотрудники вашего турнира должны будут сказать игрокам отключить опцию «Блокировать личные сообщения не от друзей» в osu!.
- `!mp lock` — Блокирует комнату, не позволяя игрокам менять команды и слоты.
- `!mp unlock` — Отменяет команду выше.
- `!mp size <size>` — Устанавливает количество доступных слотов (1—16) в комнате.
- `!mp set <teammode> [<scoremode>] [<size>]` — Устанавливает различные параметры комнаты.
  - `teammode` — 0: Head To Head, 1: Tag Coop, 2: Team Vs, 3: Tag Team Vs
  - `scoremode` — 0: Счёт, 1: Точность, 2: Комбо, 3: Score V2
- `!mp move <username> <slot>` — Перемещает игрока в комнате в указанный слот.
- `!mp host <username>` — Переносит роль хоста на указанного игрока.
- `!mp clearhost` — Сбрасывает хоста комнаты.
- `!mp settings` — Отображает полную информацию о комнате.
- `!mp start [<time>]` — Начинает матч посте поставленного таймера (в секундах) или незамедлительно, если время не указано.
- `!mp abort` — Прерывает матч.
- `!mp team <username> <colour>` — Перемещает игрока в указанную команду.
  - `colour` — red (красная), blue (синяя)
- `!mp map <mapid> [<playmode>]` — Изменяет карту и режим игры комнаты.
  - `playmode` — 0: osu!, 1: osu!taiko, 2: osu!catch, 3: osu!mania
- `!mp mods <mod> [<mod>] [<mod>] …` — Убирает все применённые моды и применяет к комнате указанные.
  - Может быть введено любое количество.
  - `mod` — HR, DT, FL, HD, FI, Freemod, None
- `!mp timer [<time>]` — Запускает таймер обратного отсчёта.
  - `time` по умолчанию: 30 сек.
  - Оповещения таймера появляются каждую минуту, 30 сек., 10 сек., 5 сек. и ранее.
- `!mp aborttimer` — Останавливает текущий таймер (и обычные, и таймеры начала матча)
- `!mp kick <username>` — Выгоняет игрока из комнаты.
- `!mp password [<password>]` — Изменяет пароль комнаты. Пароль будет убран, если значение `<password>` не указано.
- `!mp addref <username> [<username>] …` — Добавляет судью в комнату. Максимальное количество, которое можно добавить: 8. Только создатель комнаты может добавить судью.
  - Судьи должны присоединиться к лобби комнаты из игры или войти в канал чата комнаты через `/join #mp_<room_id>` в IRC.
  - Судьи могут управлять комнатой так же, как и создатель, однако они не могут самостоятельно добавлять или убирать других судей.
  - [Клиент osu!tourney](/wiki/osu!tourney) покажет чат комнаты для судьи.
- `!mp removeref <username> [<username>] …` — Убирает судью из комнаты. Только создатель комнаты может убрать судью.
- `!mp listrefs` — Показывает списк всех судей в комнате.
- `!mp close` — Закрывает комнату.

Команды можно отобразить, отправив `!mp help` BanchoBot'у.

Значения, окружённые угловыми скобками, ( `<>` ) назначают «параметры» команд. Параметры, окружённые квадратными скобками, ( `[]` ) опциональны. Пробелы в именах игроков должны быть заменены нижним подчёркиванием ( `_` ). `#<userid>` может заменить `<username>` во всех командах.

## Использование

Команды могут использоваться, как из osu!, так и из IRC-клиентов вроде mIRC, HexChat или HydraIRC.

Изначальный хост мультиплеерной комнаты также может использовать данные команды. Если он покидает комнату, следующий хост не получает команды по наследству. Изначальный хост получит возможность снова использовать команды, как только заново присоединится к комнате.

## Примеры использования

Далее следуют примеры использования команд:

- `!mp invite Zallius` — Пригласить Zallius в комнату.
- `!mp move Loctav 4` — Переместить Loctav в 4-й слот комнаты.
- `!mp team Zallius blue` — Переместить Zallius в синюю команду.
- `!mp team Loctav red` — Переместить Loctav в красную команду.
- `!mp set 0 2` — Поставить режим команды на «Head To Head», режим результата на «Комбо».
- `!mp start` — Начать матч немедленно.

Мы ожидаем от Вас профессионализма и ответственности в управлении своим турниром. Любое злоупотребление командами, чтобы нарушить игру других пользователей, будет рассматриваться как грубое нарушение наших [правил сообщества](/wiki/Rules).
