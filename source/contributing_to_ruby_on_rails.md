Вносим вклад в Ruby on Rails
============================

Это руководство раскрывает способы, с помощью которых _ты_ можешь стать частью продолжающейся разработки Ruby on Rails.

После прочтения этого руководства, вы узнаете:

* Как использовать GitHub для сообщения о проблемах.
* Как клонировать master и запустить тестовый набор.
* Как помочь в решении существующих проблем.
* Как внести вклад в документацию Ruby on Rails.
* Как внести вклад в код Ruby on Rails.

Ruby on Rails — это не "чей-то там фреймворк". На протяжение лет тысячи людей вносили вклад в Ruby on Rails, от одиночного символа до огромных архитектурных изменений или значимой документации — и все это с целью сделать Ruby on Rails лучше для каждого. Даже если пока не готовы писать код или документацию, имеется ряд других способов, которыми можно внести вклад, от сообщений о проблемах до тестирования новых изменений.

Как упомянуто в [Rails README](https://github.com/rails/rails/blob/master/README.md), от каждого, участвующего в коде Rails и его подпроектах, системах отслеживания ошибок, чатах и списках рассылок, ожидается следование [нормам поведения](http://rubyonrails.org/conduct/) Rails.

--------------------------------------------------------------------------------

Сообщение о проблеме
--------------------

Ruby on Rails использует [GitHub Issue Tracking](https://github.com/rails/rails/issues) для отслеживания проблем (в основном, программных ошибок и нового кода). Если вы нашли программную ошибку в Ruby on Rails, нужно начать отсюда. Чтобы сообщить о проблеме, прокомментировать ее или создавать пул-реквесты, необходимо создать аккаунт (бесплатный) на GitHub.

NOTE: Программным ошибкам в самой последней версии Ruby on Rails уделяется наибольшее внимание. Также основная команда Rails всегда заинтересована в обратной связи от тех, у кого есть время потестировать _edge Rails_ (код версии Rails, которая разрабатывается в текущий момент). Позже в этом руководстве будет рассказано, как получить edge Rails для тестирования.

### Создание отчета о программной ошибке

Если вы обнаружили проблему в Ruby on Rails, не несущую риск безопасности, произведите поиск по [Issues](https://github.com/rails/rails/issues), о ней уже может быть сообщено. Если вы не обнаружили какую-либо открытую проблему на GitHub, посвященную ошибке, которую вы нашли, вашим следующим действием будет [открыть новую проблему](https://github.com/rails/rails/issues/new). (Смотрите следующий раздел, посвященный вопросам безопасности.)

Ваш отчет о проблеме должен, как минимум, содержать заголовок и ясное описание проблемы. Следует включить как можно больше релевантной информации, и следует опубликовать пример кода, демонстрирующего проблему. Будет даже лучше, если вы включите юнит-тест, демонстрирующий не произошедшее ожидаемое поведение. Вашей целью должно быть упрощение для себя — и для других — в воспроизведении программной ошибки и понимании, как ее починить.

А затем, не теряйте надежды! Если у вас некритичная программная ошибка, вы создаете этот отчет о проблеме в надежде, что другие с той же проблемой смогут взаимодействовать с вами, чтобы ее решить. Не ожидайте, что этот отчет о проблеме автоматически увидит какую-либо активность, или что другие переключатся на нее, чтобы починить. Создание отчета о подобной проблеме является больше помощью самому себе на пути к починке проблемы и другим для подтверждения ее с помощью комментария "I'm having this problem too".

### Создание исполняемого тестового случая

Наличие способа воспроизвести вашу проблему будет очень полезным для других, чтобы подтвердить, исследовать и, в конечном счете, починить вашу проблему. Это можно сделать с помощью исполняемого тестового случая. Чтобы упростить этот процесс, мы подготовили для вас несколько шаблонов отчетов об ошибке, которые можно использовать в качестве отправной точки:

* Шаблон для проблем с Active Record (модели, база данных): [gem](https://github.com/rails/rails/blob/master/guides/bug_report_templates/active_record_gem.rb) / [master](https://github.com/rails/rails/blob/master/guides/bug_report_templates/active_record_master.rb)
* Шаблон для тестирования проблем с Active Record (миграции): [gem](https://github.com/rails/rails/blob/master/guides/bug_report_templates/active_record_migrations_gem.rb) / [master](https://github.com/rails/rails/blob/master/guides/bug_report_templates/active_record_migrations_master.rb)
* Шаблон для проблем с Action Pack (контроллеры, роутинг): [gem](https://github.com/rails/rails/blob/master/guides/bug_report_templates/action_controller_gem.rb) / [master](https://github.com/rails/rails/blob/master/guides/bug_report_templates/action_controller_master.rb)
* Шаблон для проблем с Active Job: [gem](https://github.com/rails/rails/blob/master/guides/bug_report_templates/active_job_gem.rb) / [master](https://github.com/rails/rails/blob/master/guides/bug_report_templates/active_job_master.rb)
* Шаблон для других проблем: [gem](https://github.com/rails/rails/blob/master/guides/bug_report_templates/generic_gem.rb) / [master](https://github.com/rails/rails/blob/master/guides/bug_report_templates/generic_master.rb)

Эти шаблоны включают шаблонный код для настройки тестового случая для либо выпущенной версии Rails (`*_gem.rb`), либо разрабатываемого Rails (`*_master.rb`).

Просто скопируйте содержимое подходящего шаблона в файл `.rb` и сделайте необходимые изменения, чтобы продемонстрировать проблему. Его можно запустить в терминале с помощью `ruby the_file.rb`. Если все получилось, вы должны увидеть, что ваш тестовый случай падает.

Затем можно поделиться своим исполняемым тестовым случаем через [gist](https://gist.github.com), или просто вставить содержимое в issue описания.

### Особая трактовка проблем безопасности

WARNING: Пожалуйста, не сообщайте об уязвимостях в безопасности с помощью публичных отчетов о проблеме на GitHub. [Страница о политике безопасности Rails](http://rubyonrails.org/security) подробно излагает процедуру для проблем безопасности.

### Что насчет запросов о новой особенности?

Пожалуйста не складывайте "feature request" в GitHub Issues. Если имеется новая особенность, которую вы бы хотели видеть добавленной в Ruby on Rails, вам необходимо написать код самим, или убедить кого-то другого помочь вам с написанием кода. Позже в этом руководстве будут даны подробные инструкции по предложению патча в Ruby on Rails. Если вы опубликуете список пожеланий в GitHub Issues без кода, будьте уверены, он будет помечен "invalid", как только будет рассмотрен.

Иногда грань между 'программная ошибка' и 'особенность' трудно провести. Как правило, особенность — это все, что добавляет новое поведение, в то время как программная ошибка — это все, что вызывает неправильное поведение. Иногда основной команде приходиться делать очень непростой выбор. Тем не менее, различие, как правило, влияет лишь на то, в какой релиз попадет патч; им нравится рассматривать особенности! Они просто не будут бэкпортировать в поддерживаемые ветки.

Если вы хотите получить обратную связь на идею особенности до того, как начнете работать над изменениями, напишите письмо в [список рассылки rails-core](https://groups.google.com/forum/?fromgroups#!forum/rubyonrails-core). Вы можете не получить откликов, что означает, что всем безразлично. Вы можете найти кого-то, кто так же заинтересован в создании этой особенности. Вы можете получить "This won't be accepted." Но это подходящее место для обсуждения новых идей. GitHub Issues являются не особо хорошим местом для проведения длительных и обширных обсуждений новых особенностей.

Помощь в разрешении существующих проблем
----------------------------------------

В качестве следующего шага после сообщения о проблемах, вы можете помочь основной команде разрешить существующие проблемы, предоставив обратную связь о них. Если вы новичок в разработке ядра Rails, это отличный способ сделать первые шаги, познакомиться с кодовой базой и процессами.

Если посмотреть на [список проблем](https://github.com/rails/rails/issues) в GitHub Issues, можно обнаружить множество проблем, требующих внимания прямо сейчас. Что можно с ними сделать? Фактически, немного:

### Подтвердить сообщение о программной ошибке

Начинающие могут помочь только в подтверждении сообщений о программных ошибках. Сможете ли вы воспроизвести сообщенную проблему на своем компьютере? Если так, можете добавить комментарий к проблеме, что вы наблюдали то же самое.

Если проблема очень расплывчатая, сможете ли вы помочь сузить ее до чего-то конкретного? Может быть вы сможете предоставить дополнительную информацию, чтобы помочь воспроизвести программную ошибку, или помочь в устранении ненужных шагов, не требуемых для демонстрации проблемы.

Если обнаружили сообщение о программной ошибке без теста, было бы полезным внести вклад, написав падающий тест. Это также отличный способ исследования исходного кода: глядя на существующие файлы тестов, научитесь как писать больше тестов. Новые тесты лучше всего вносить в виде изменений, как объяснено позже в разделе "[Вносим вклад в код Rails](#vnosim-vklad-v-kod-rails)".

Все, что вы сможете сделать, чтобы отчеты о программной ошибке стали более краткими и более простыми для воспроизведения, поможет ребятам, пытающимся починить эти программные ошибки — независимо от того, дойдете вы до написания кода, или нет.

### Протестировать изменения

Также можно помочь, изучая пул-реквесты, которые были отправлены в Ruby on Rails с помощью GitHub. Для того, чтобы применить чьи-то изменения, вам сначала необходимо создать отдельную ветку:

```bash
$ git checkout -b testing_branch
```

Затем вы можете использовать их удаленную ветку для обновления кода в своей. Например, скажем, что на GitHub пользователь JohnSmith форкнул и запушил в ветку "orange", расположенную в https://github.com/JohnSmith/rails.

```bash
$ git remote add JohnSmith https://github.com/JohnSmith/rails.git
$ git pull JohnSmith orange
```

После применения его ветки, протестируйте ее! Вот несколько вещей, о которых стоит подумать:

* Работает ли фактически это изменение?
* Довольны ли вы тестами? Сможете ли вы выполнить то, что они тестируют? Нет ли отсутствующих тестов?
* Имеется ли достаточное покрытие документацией? Должна ли быть обновлена документация где-то еще?
* Нравится ли вам реализация? Можете подумать о более красивом или быстром способе реализации части его изменений?

Как только вы будете довольны тем, что пул-реквест содержит хорошее изменение, прокомментируйте на GitHub, что вы одобряете. Ваш комментарий должен показать, что вам нравится изменение, и что вы думаете о нем. Что-то вроде:

>I like the way you've restructured that code in generate_finder_sql - much nicer. The tests look good too.

Если ваш комментарий просто содержит "+1", есть шанс, что прочие ревьюверы не воспримут его серьезно. Покажите, что вы потратили время на обзор этого пул-реквеста.

Вносим вклад в документацию Rails
---------------------------------

В Ruby on Rails имеется два главных набора документации: руководства, помогающие изучить Ruby on Rails, и API, также служащее в качестве эталона.

Вы можете помочь в улучшении руководств по Rails, сделав их более последовательными или читаемыми, добавив отсутствующую информацию, исправив имеющиеся ошибки, скорректировав описки или обновив их в соответствие крайней версии Rails.

Для этого внесите изменения в исходные файлы руководств Rails ([расположенные](https://github.com/rails/rails/tree/master/guides/source) на GitHub). Затем откройте пул-реквест, чтобы применить изменения к ветке master.

При работе с документацией принимайте во внимание [Рекомендации по документированию API](/api_documentation_guidelines) и [Рекомендации для руководств по Ruby on Rails](/ruby_on_rails_guides_guidelines).

NOTE: Чтобы помочь нашим серверам CI, следует добавлять [ci skip] в сообщения вашего коммита в документацию, чтобы они игнорировали этот коммит. Пожалуйста, используйте его для коммитов, содержащих только изменения документации.

Перевод руководств Rails
------------------------

Мы счастливы, что находятся волонтеры, переводящие руководства Rails, просто следуйте этим шагам:

* Сделайте форк https://github.com/rails/rails.
* Добавьте папку исходников для вашего языка, например: *guides/source/it-IT* для итальянского.
* Скопируйте содержимое *guides/source* в директорию для вашего языка и переведите их.
* НЕ переводите файлы HTML, так как они генерируются автоматически.

Обратите внимание, что переводы не передаются в репозиторий Rails. Как подробно описано выше, ваша работа находится в форке. Это происходит из-за того, что на практике изменения в документацию вносятся только для английского языка.

Чтобы сгенерировать руководства в формате HTML, войдите в директорию *guides* и запустите (например, для it-IT):

```bash
$ bundle install
$ bundle exec rake guides:generate:html GUIDES_LANGUAGE=it-IT
```

Это сгенерирует руководства в директории *output*.

NOTE: Эти инструкции для Rails > 4. Гем Redcarpet не работает с JRuby.

Деятельность по переводу, о которой мы знаем (разные версии):

* **Итальянский**: [https://github.com/rixlabs/docrails](https://github.com/rixlabs/docrails)
* **Испанский**: [https://github.com/gramos/docrails/wiki](https://github.com/gramos/docrails/wiki)
* **Польский**: [https://github.com/apohllo/docrails](https://github.com/apohllo/docrails)
* **Французский** : [https://github.com/railsfrance/docrails](https://github.com/railsfrance/docrails)
* **Чешский** : [https://github.com/rubyonrails-cz/docrails/tree/czech](https://github.com/rubyonrails-cz/docrails/tree/czech)
* **Турецкий** : [https://github.com/ujk/docrails](https://github.com/ujk/docrails)
* **Корейский** : [https://github.com/rorlakr/rails-guides](https://github.com/rorlakr/rails-guides)
* **Упрощенный китайский** : [https://github.com/ruby-china/guides](https://github.com/ruby-china/guides)
* **Традиционный китайский** : [https://github.com/docrails-tw/guides](https://github.com/docrails-tw/guides)
* **Русский** : [https://github.com/morsbox/rusrails](https://github.com/morsbox/rusrails)
* **Японский** : [https://github.com/yasslab/railsguides.jp](https://github.com/yasslab/railsguides.jp)

Вносим вклад в код Rails
------------------------

### Настраиваем среду разработки

Чтобы продвинуться от подтверждения программных ошибок к помощи в разрешении существующих проблем или внесения собственного кода в Ruby on Rails, вы _должны_ уметь запускать его тестовый набор. В этом разделе руководства вы изучите, как настроить тесты на своем компьютере.

#### Простой способ

Простейшим и рекомендованным способом получить среду разработки, готовую для программирования, является использование [rails-dev-box](https://github.com/rails/rails-dev-box).

#### Сложный способ

В случае, если вы не можете использовать Rails development box, смотрите руководство [Установка зависимостей для разработки](/development_dependencies_install).

### Клонирование репозитория Rails

Чтобы вносить изменения в код, необходимо клонировать репозиторий Rails:

```bash
$ git clone https://github.com/rails/rails.git
```

и создать отдельную ветку:

```bash
$ cd rails
$ git checkout -b my_new_branch
```

Не имеет значения, какое имя вы используете, так как эта ветка существует только на вашем локальном компьютере и вашем персональном репозитории на GitHub. Она не будет частью гит-репозитория Rails.

### Bundle install

Установите требуемые гемы.

```bash
$ bundle install
```

### (running-an-application-against-your-local-branch) Запуск приложения на вашей локальной ветке

Если вам нужно приложение Rails для тестирования изменений, флажок `--dev` для `rails new` создаст приложение, использующее вашу локальную ветку:

```bash
$ cd rails
$ bundle exec rails new ~/my-test-app --dev
```

Приложение, сгенерированное в `~/my-test-app` запускается на вашей локальной ветке, и, в частности, видит любые модификации после перезагрузки сервера.

### Пишите свой код

Пора заняться делом и добавить/отредактировать код. Раз вы в своей ветке, вы можете писать все, что хотите (убедитесь, что вы в правильной ветке с помощью `git branch -a`). Но если вы планируете отправить ваше изменение для включения в Rails, имейте в виду несколько вещей:

* Пишите правильный код.
* Используйте идиомы и хелперы Rails.
* Включайте тесты, которые падают без вашего кода, и проходят с ним.
* Обновляйте документацию, примеры и руководства: все, что было затронуто вашим вкладом.

TIP: Изменения, которые по природе косметические, и не добавляют ничего ощутимого в стабильность, функциональность или тестируемость Rails, обычно не принимаются (читайте подробнее об [обоснованиях этого решения](https://github.com/rails/rails/pull/13771#issuecomment-32746700)).

#### (follow-the-coding-conventions) Следуйте соглашениям по программированию

Rails следует простому набору соглашений о стиле кода:

* Два пробела, нет табуляции (для отступов).
* Нет конечных пробелов. Пустые строчки не должны иметь пробелов.
* Отступ после private/protected.
* Используйте синтаксис Ruby >= 1.9 для хэшей. Предпочитайте `{ a: :b }` над `{ :a => :b }`.
* Предпочитайте `&&`/`||` над `and`/`or`.
* Предпочитайте `class << self` над `self.method` для методов класса.
* Используйте `my_method(my_arg)`, а не `my_method( my_arg )` или `my_method my_arg`.
* Используйте `a = b`, а не `a=b`.
* Используйте методы `assert_not` вместо отрицаний.
* Предпочитайте `method { do_stuff }` вместо `method{do_stuff}` для однострочных блоков.
* Следуйте соглашениям в исходном коде, которые вы уже видели.

Что касается вышеприведенных рекомендаций - пожалуйста, поступайте по своему усмотрению при использовании их.

Помимо этого у нас имеются определенные правила [RuboCop](https://www.rubocop.org/) для систематизации некоторых из наших соглашений по кодированию. Вы можете запустить RuboCop локально для файла, который вы изменили, до отправки пул реквеста:

```bash
$ rubocop actionpack/lib/action_controller/metal/strong_parameters.rb
Inspecting 1 file
.

1 file inspected, no offenses detected
```

Для файлов `rails-ujs` CoffeeScript и JavaScript можно запустить `npm run lint` в папке `actionview`.

### Тестируйте производительность своего кода

Для изменений, способных повлиять на производительность, пожалуйста, тестируйте производительность вашего кода и измеряйте влияние. Пожалуйста, покажите используемый. Следует рассмотреть включение этой информации в сообщении вашего коммита, позволяющее будущим контрибьюторам с легкостью проверить ваши выводы и определить, являются ли они по прежнему уместными. (Например, будущие оптимизации в виртуальной машине Ruby могут привести к ненужности определенных оптимизаций.)

Очень просто сделать оптимизацию, улучшающую быстродействие для нужного вам определенного сценария, но ухудшающую для других распространенных случаев. Следовательно, необходимо тестировать ваше изменение на списке репрезентативных сценариев. В идеале они должны быть основаны на реальных сценариях, извлеченных из настоящих приложений.

В качестве отправной точки можно использовать [шаблон теста производительности](https://github.com/rails/rails/blob/master/guides/bug_report_templates/benchmark.rb). Он включает шаблонный код для настройки теста с помощью гема [benchmark-ips](https://github.com/evanphx/benchmark-ips). Шаблон разработан для тестирования относительно самодостаточных изменений, которые можно встроить в скрипт.

### Запуск тестов

В Rails не является необходимым запускать полный тестовый набор перед отправкой изменений. В частности, тестовый набор railties занимает много времени, и особенно долго, если исходный код монтирован в `/vagrant`, как происходит в рекомендованном рабочем процессе с помощью [rails-dev-box](https://github.com/rails/rails-dev-box).

В качестве компромисса, тестируйте то, на что ваш код явно влияет, и, если изменение не в railties, запускайте полный тестовый набор затронутого компонента. Если все тесты проходят, этого достаточно, чтобы предложить ваш вклад. У нас есть [Travis CI](https://travis-ci.org/rails/rails) в качестве безопасной сети для отлова неожиданных поломок где-то еще.

#### Весь Rails:

Чтобы запустить все тесты, выполните:

```bash
$ cd rails
$ bundle exec rake test
```

#### Для определенного компонента

Можно запустить тесты только для определенного компонента (такого как Action Pack). Например, чтобы запустить тесты Action Mailer:

```bash
$ cd actionmailer
$ bundle exec rake test
```

#### Запуск отдельного теста

С помощью ruby можно запустить отдельный тест. К примеру:

```bash
$ cd actionmailer
$ bundle exec ruby -w -Itest test/mail_layout_test.rb -n test_explicit_class_layout
```

Опция `-n` позволяет запустить отдельный метод вместо всего файла.

#### Запуск тестов с определенным порождающим элементом

Запуск тестов случайнен с помощью порождающего элемента. Если вы испытываете случайные ошибки в тесте, можно более аккуратно воспроизвести сценарий падающего теста, установив порождащий элемент.

Запуск всех тестов для компонента:

```bash
$ cd actionmailer
$ SEED=15002 bundle exec rake test
```

Запуск отдельного тестового файла:

```bash
$ cd actionmailer
$ SEED=15002 bundle exec ruby -w -Itest test/mail_layout_test.rb
```

#### Тестирование Active Record

Сначала создайте необходимые вам базы данных. Список необходимых имен таблиц, имен пользователей и паролей можно находится в `activerecord/test/config.example.yml`.

Для MySQL и PostgreSQL необходим запуск выражений SQL `create database activerecord_unittest` и `create database activerecord_unittest2`. Для SQLite3 это необязательно.

Вот как можно запустить тестовый набор Active Record только для SQLite3:

```bash
$ cd activerecord
$ bundle exec rake test:sqlite3
```

Теперь вы можете запускать тесты, как вы делали для `sqlite3`. Соответствующие задачи:

```bash
test:mysql2
test:postgresql
```

Наконец,

```bash
$ bundle exec rake test
```

запустит все три по очереди.

Также можно запустить любой одиночный тест отдельно:

```bash
$ ARCONN=sqlite3 bundle exec ruby -Itest test/cases/associations/has_many_associations_test.rb
```

Чтобы запустить одиночный тест на всех адаптерах, используйте:

```bash
$ bundle exec rake TEST=test/cases/associations/has_many_associations_test.rb
```

Также можно вызвать `test_jdbcmysql`, `test_jdbcsqlite3` или `test_jdbcpostgresql`. Информацию по запуску нацеленных на базу данных тестов смотрите в файле `activerecord/RUNNING_UNIT_TESTS.rdoc`, а по запуску тестового набора на сервере CI в файле `ci/travis.rb`.

### Предупреждения

Тестовый набор запускается с включенными предупреждениями. В идеале, Ruby on Rails не должен выдавать предупреждения, но их может быть несколько, в том числе от сторонних библиотек. Пожалуйста, игнорируйте (или почините!) их, если имеются, и отправляйте изменения, не имеющих новых предупреждений.

### Обновление CHANGELOG

CHANGELOG — это важная часть каждого релиза. Он содержит список изменений для каждой версии Rails.

Вам следует добавить запись **в самый верх** CHANGELOG того фреймворка, который вы модифицировали, если вы добавили или убрали особенность, исправили программную ошибку или добавили предупреждения об устаревании. Рефакторинг и изменения документации обычно не идут в CHANGELOG.

Запись в CHANGELOG должна кратко описывать то, что было изменено, и заканчиваться именем автора. Можно использовать несколько строчек, если необходимо место, а также можно прикрепить примеры кода с отступом в 4 пробела. Если изменение относится к определенной проблеме, следует прикрепить номер проблемы. Вот пример записи в CHANGELOG:

```
*   Summary of a change that briefly describes what was changed. You can use multiple
    lines and wrap them at around 80 characters. Code examples are ok, too, if needed:

        class Foo
          def bar
            puts 'baz'
          end
        end

    You can continue after the code example and you can attach issue number. Fixes #1234.

    *Your Name*
```

Ваше имя может быть добавлено непосредственно после последнего слова, если нет примеров кода или нескольких параграфов. В противном случае, лучше добавить его как новый параграф.

### Апгрейд Gemfile.lock

Некоторые изменения требуют апгрейда зависимостей. В таких случаях убедитесь, что вы запустили `bundle update`, чтобы получить правильную версию зависимости и сделайте коммит с файлом `Gemfile.lock` со своими изменениями.

### Коммит ваших изменений

Когда вы довольны своим кодом на своем компьютере, необходимо отправить коммит с изменениями в Git:

```bash
$ git commit -a
```

Это должно запустить ваш редактор, чтобы написать сообщение для этого коммита. После завершения, сохраните и закройте его, чтобы продолжить.

Хорошо отформатированное и содержательное сообщение коммита очень полезно для остальных для понимания, зачем было сделано изменение, поэтому найдите время написать его.

Хорошее сообщение коммита должно выглядеть так:

```
Краткое содержание (в идеале до 50 символов)

Более детальное описание, если необходимо. Оно должно переноситься по
72 символа. Попытайтесь быть как можно более наглядным. Даже если вы
думаете, что содержание комита очевидно, оно может быть неочевидным для
остальных. Добавьте любое описание, уже присутствующее в
соответствующих описаниях проблем; должно быть необязательным посещение
веб-страницы чтобы посмотреть историю.

Раздел описания может иметь несколько параграфов.

Можно встраивать примеры кода, отступив их на 4 пробелами:

    class ArticlesController
      def index
        render json: Article.limit(10)
      end
    end

Можно добавить маркированные списки:

- создав пункт списка, начав строчку с черточки (-) или звездочки (*)

- перенося длинные строчки по 72 символа и отступая дополнительные строчки
  на 2 символа для читаемости
```

TIP. Пожалуйста, склеивайте свои коммиты в один коммит, когда это уместно. Это упрощает будущий черри-пикинг и поддерживает чистоту лога.

### Обновление вашей ветки

Очень вероятно, что были сделаны другие изменения в master, пока вы работали. Получите их:

```bash
$ git checkout master
$ git pull --rebase
```

Теперь можно применить ваш патч на последних изменениях:

```bash
$ git checkout my_new_branch
$ git rebase master
```

Нет конфликтов? Тесты все еще проходят? Изменения еще актуальны? Продолжайте.

### Форк

Перейдите в репозиторий Rails [на GitHub](https://github.com/rails/rails) и нажмите "Fork" в верхнем правом углу.

Добавьте новый удаленный репозиторий к вашему локальному:

```bash
$ git remote add fork https://github.com/<your user name>/rails.git
```

Возможно, у вас есть клонированный форк-репозиторий, и вы хотите добавить удаленным оригинальный репозиторий Rails, в этом случае вот что вам нужно сделать.

В директории, в которую вы клонировали свой форк:

Вы можете склонировать свой локальный репозиторий от rails/rails, или можете склонировать свой форк-репозиторий. Чтобы избежать избыточности, следующие команды git предполагают, что вы сделали удаленный репозиторий "rails", указывающий на rails/rails.

```bash
$ git remote add rails https://github.com/rails/rails.git
```

Скачать новые коммиты и ветки из официального репозитория:

```bash
$ git fetch rails
```

Слить новое содержимое:

```bash
$ git checkout master
$ git rebase rails/master
$ git checkout my_new_branch
$ git rebase rails/master
```

Обновить ваш форк:

```bash
$ git push fork master
$ git push fork my_new_branch
```

### Создание пул-реквеста

Перейдите в репозиторий Rails, в который вы только что отправили код (т.е. https://github.com/your-user-name/rails) и нажмите на "Pull Requests" в правой панели. На следующей странице нажмите "New pull request" в верхнем правом углу.

Нажмите на "Edit", если необходимо изменить сравниваемые ветки (по умолчанию он сравнивает "master") и нажмите "Click to create a pull request for this
comparison".

Убедитесь, что включены изменения, которые вы представили. Заполните некоторыми подробностями о вашем потенциальном патче, включая осмысленный заголовок. Когда закончите, нажмите "Send pull request". Основная команда Rails будет уведомлена о вашем изменении.

### Получение обратной связи

Большая часть пул-реквестов пройдут через ряд итераций до того, как они будут слиты. У разных контрибьюторов иногда разные мнения, и часто изменения нуждаются в пересмотре до того, как их можно слить.

У некоторых контрибьюторов в Rails включены уведомления по email с GitHub, у некоторых нет. Более того, (почти) все, кто работает над Rails, являются добровольцами, поэтому может пройти несколько дней до того, как вы получите первую обратную связь на пул-реквест. Не отчаивайтесь! Иногда это быстро, иногда это медленно. Такова жизнь открытого ПО.

Если прошло больше недели, и никто не ответил, можно попытаться немного ускорить процесс. Для этого используйте [рассылку rubyonrails-core](https://groups.google.com/forum/#!forum/rubyonrails-core). Также можно оставить комментарий в своем пул-реквесте.

ПОка вы ждете обратную связь на свой пул-реквест, откройте несколько чужих пул-реквестов и дайте обратную связь кому-то еще! Мы уверены, они будут признательны за это не меньше, чем вы были бы признательны за обратную связь на ваши изменения.

### Повторение по необходимости

Очень вероятно, что полученная обратная связь предложит изменения. Не отчаивайтесь: весь смысл вклада в активный проект с открытым кодом заключается в том, чтобы использовать знания сообщества. Если люди призывают подправить ваш код, то стоит внести правки и отправить заново. Если обратная связь говорит, что ваш код не нужен в ядре, вы можете подумать о выпуске его в качестве гема.

#### Склеивание коммитов

Одной из вещей, которая может быть попрошена, является "squash your commits", которая объединит все ваши коммиты в один. Мы предпочитаем пул-реквесты с одним коммитом. Это упрощает бэкпортирование в стабильные ветки, склеивание (squashing) позволяет легко откатывать плохие коммиты, слежение за историей git. Rails — это большой проект, и ряд множество сторонних коммитов может добавить много шума.

```bash
$ git fetch rails
$ git checkout my_new_branch
$ git rebase -i rails/master

< Выберите 'squash' для всех ваших коммитов, кроме первого. >
< Отредактируйте сообщение коммита, чтобы оно было осмысленным, и опишите все свои изменения. >

$ git push fork my_new_branch --force-with-lease
```

Далее вам необходимо обновить пул-реквест на GitHub и посмотреть, что он был изменен.

#### Обновление пул-реквеста

Иногда вас попросят внести некоторые изменения в код, который уже был закоммичен. Это может включать исправление существующих коммитов. В этом случае Git не позволит отправить изменения, так как удаленная и локальная ветки не соответствуют друг другу. Вместо открытия нового пул-реквеста, можно принудить отправку в вашу ветку на GitHub, как описано ранее в разделе про склеивание коммитов:

```bash
$ git push fork my_new_branch --force-with-lease
```

Это позволит обновить ветку и пул-реквест на GitHub вашим новым кодом. Принудительно отправив с помощью `--force-with-lease`, git более безопасно обновит удаленный репозиторий, чем с помощью обычного `-f`, который может стереть работу с удаленного репозитория, которой у вас уже нет.

### Старшие версии Ruby on Rails

Если вы хотите добавить исправление в старшие версии Ruby on Rails, необходимо настроить и переключить свою локальную отслеживаемую ветку. Вот пример, как переключиться на ветку 4-0-stable:

```bash
$ git branch --track 4-0-stable rails/4-0-stable
$ git checkout 4-0-stable
```

TIP: Возможно, вы захотите [выводить имя ветки Git в строке ввода консоли](http://qugstart.com/blog/git-and-svn/add-colored-git-branch-name-to-your-shell-prompt/) чтобы было проще вспомнить, над какой версией кода вы работаете.

#### Бэкпортирование

Изменения, слитые в master, предназначены для следующего главного релиза Rails. Иногда полезно, чтобы ваши изменения попали в поддерживаемые релизы для старших стабильных веток. Как правило, хорошими кандидатами для бэкпортирования являются исправления безопасности и исправления программных ошибок, в то время как новые особенности и исправления, представляющие изменения в поведении, не принимаются. Когда сомневаетесь, лучше всего проконсультироваться с членом основной команды Rails до бэкпортирования ваших изменений, чтобы избежать потери времени.

Для простых изменений, легчайшим способом бэкпортировать ваши изменения является [извлечь diff ваших изменений в master и применить его в целевой ветке](http://ariejan.net/2009/10/26/how-to-create-and-apply-a-patch-with-git).

Сначала убедитесь, что только ваши изменения составляют разницу между вашей текущей веткой и master:

```bash
$ git log master..HEAD
```

Затем извлеките diff:

```bash
$ git format-patch master --stdout > ~/my_changes.patch
```

Переключитесь в целевую ветку и примените ваши изменения:

```bash
$ git checkout -b my_backport_branch 4-2-stable
$ git apply ~/my_changes.patch
```

Это хорошо работает для простых изменений. Однако, если изменения сложные, или если код в master сильно отличается от целевой ветки, это потребует большей работы с вашей стороны. Сложность бэкпортирования отличается от случая к случаю, и даже иногда не стоит усилий.

Как только вы разрешили все конфликты и убедились, что проходят все тесты, отправьте свои изменения и откройте отдельный пул-реквест для своего порта. Также важно отметить, что старшие ветки могут иметь другой список целевых версий, чем в master. По возможности, лучше до от отправки пул-реквеста протестировать бэкпорт локально на версиях Ruby, перечисленных в `.travis.yml`.

А затем... подумайте о следующем вкладе!

Авторы Rails
------------

Все внесшие вклад восхваляются в [Rails Contributors](http://contributors.rubyonrails.org).
