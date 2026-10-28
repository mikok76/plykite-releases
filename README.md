# Plykite для Windows

**Полное руководство пользователя:** [на русском](manual/user-manual.ru.md) · [in English](manual/user-manual.en.md)

*English below.*

Plykite делит интернет компьютера между несколькими подключениями сразу: кабель, Wi‑Fi, телефон в режиме модема. Если одно подключение пропадает, Plykite переводит трафик на остальные.

Это бета-версия: программа даётся как есть, без гарантий.

## Что нужно

- 64-битная Windows 10 (версия 22H2) или Windows 11.
- Права администратора на компьютере: Windows один раз спросит разрешение.
- Установщик `Plykite-Setup-<версия>-x64.exe` — для компьютеров с процессором Intel или AMD. Он лежит в разделе Releases.

## Установка

1. Скачайте установщик из последнего выпуска (Releases) и дважды щёлкните его.
2. Если появится синее окно «Windows защитил ваш компьютер», нажмите «Подробнее», затем «Выполнить в любом случае». Так бывает потому, что программа пока не подписана сертификатом.
3. В окне установки нажмите «Далее», затем «Установить».
4. Windows спросит: «Разрешить этому приложению вносить изменения?» Нажмите «Да».
5. Подождите минуту-две: установщик ставит Plykite и проверяет, что интернет работает. Во время установки интернет может пропасть на полминуты.
6. В последнем окне должно быть написано «Plykite установлен и работает». Нажмите «Завершить».

Если Защитник Windows блокирует Plykite, запустите установщик ещё раз и поставьте галочку «Добавить папки Plykite в исключения Защитника Windows».

## Что вы увидите

- **Значок Plykite у часов.** Щёлкните по нему, чтобы увидеть меню: каналы, скорость, режим. Plykite запускается вместе с Windows.
- **Окно Plykite** — из меню значка или из меню «Пуск» → Plykite.
- **Панель в браузере** — в меню значка «Открыть панель в браузере…».

## Обновление

- Раз в день Plykite сам проверяет, вышла ли новая версия. Если вышла, у значка появится уведомление, а в меню — пункт «Обновить Plykite до …».
- Нажмите его: Plykite скачает новую версию, проверит её подпись и запустит установку. Windows спросит разрешение — нажмите «Да». Настройки сохраняются.
- Проверить сразу: меню значка → «Проверить обновления».

## Срок беты

Каждая версия работает 70 дней от выпуска; срок может продлеваться. За 14 и за 3 дня до конца срока Plykite напомнит обновиться. Если срок закончился, Plykite перестаёт делить трафик, а интернет остаётся обычным: поставьте новую версию.

## Как вернуть обычный интернет

- На время: в меню значка «Выключить Plykite (обычный интернет)». Включить снова — «Включить Plykite».
- Насовсем: удалите Plykite.

## Удаление

1. «Параметры» → «Приложения» → «Установленные приложения».
2. Найдите Plykite и нажмите «Удалить».
3. Plykite спросит, удалять ли также настройки и журналы. Если, возможно, поставите его снова, выберите «Нет».

Интернет сразу станет обычным.

## Если что-то не работает

В меню значка выберите «Собрать журналы для отчёта об ошибке…». На рабочем столе появится файл `Plykite-logs-….zip`, его можно отправить разработчику. В журналах есть имена сайтов, программ и сетевых адаптеров, названия сетей Wi‑Fi и внешние IP-адреса; паролей и ключей там нет. Посмотрите их, прежде чем отправлять.

## Какие внешние сервисы использует Plykite

- speed.cloudflare.com — замеры скорости каждого подключения;
- 1.0.0.1 (Cloudflare) — проверка, что подключение работает;
- Team Cymru — по внешнему IP каждого подключения определяется оператор;
- github.com — раз в день проверка новой версии и срока этой.

Разработчику Plykite никакие данные не отправляются.


---

# Plykite for Windows

**Full user manual:** [in English](manual/user-manual.en.md) · [на русском](manual/user-manual.ru.md)

Plykite splits the computer's internet traffic over several connections at once: cable, Wi‑Fi, a phone as a modem. When one connection drops, Plykite moves the traffic to the others.

This is a beta: the program is provided as is, without warranty.

## What you need

- 64-bit Windows 10 (version 22H2) or Windows 11.
- Administrator rights on the computer: Windows asks once.
- The setup program `Plykite-Setup-<version>-x64.exe`, for computers with an Intel or AMD processor, from Releases.

## Install

1. Download the setup program from the latest release (Releases) and double-click it.
2. If a blue window «Windows protected your PC» appears, click «More info», then «Run anyway». It appears because the program is not signed with a certificate yet.
3. In the setup window click «Next», then «Install».
4. Windows asks «Do you want to allow this app to make changes?» Click «Yes».
5. Wait a minute or two: the setup installs Plykite and checks that the internet works. The internet may drop for half a minute meanwhile.
6. The last window should say «Plykite is installed and working». Click «Finish».

If Windows Defender blocks Plykite, run the setup again and tick «Exclude Plykite's folders from Windows Defender».

## What you see

- **The Plykite icon next to the clock.** Click it for the menu: the links, the speed, the mode. Plykite starts with Windows.
- **The Plykite window** — from the icon's menu or Start → Plykite.
- **The dashboard in the browser** — the icon's menu → «Open the dashboard in the browser…».

## Updates

- Once a day Plykite checks whether a new version is out. If so, the icon shows a notice and its menu has «Update Plykite to …».
- Click it: Plykite downloads the new version, checks its signature and starts the setup. Windows asks for permission — click «Yes». The settings are kept.
- To check now: the icon's menu → «Check for updates».

## Beta term

Each version works 70 days from its release; the term may be extended. At 14 and 3 days before the end Plykite reminds you to update. After the end Plykite stops splitting the traffic and the internet stays plain: install the new version.

## Plain internet again

- For a while: the icon's menu → «Turn Plykite off (plain internet)». Back on: «Turn Plykite on».
- For good: remove Plykite.

## Remove

1. Settings → Apps → Installed apps.
2. Find Plykite and click «Uninstall».
3. Plykite asks whether to remove its settings and logs too. If you may install it again, choose «No».

The internet is plain at once.

## If something does not work

The icon's menu → «Collect logs for a bug report…». A file `Plykite-logs-….zip` appears on the desktop; you can send it to the developer. The logs hold the names of sites, programs and network adapters, Wi‑Fi network names and external IP addresses; no passwords or keys. Look through them before sending.

## External services Plykite uses

- speed.cloudflare.com — speed tests of each connection;
- 1.0.0.1 (Cloudflare) — checks that a connection works;
- Team Cymru — finds each connection's operator from its public IP;
- github.com — once a day, the check for a new version and this one's term.

Nothing is sent to Plykite's developer.
