---
title: "Глава 4: Майнинг"
h1: "Глава 4: Майнинг"
tags: ["книга", "новичкам", "основы"]
description: "Майнинг — это процесс розыгрыша лотереи Proof of Work. “Джек-пот” в каждом раунде — право добавить свой блок в реестр сети Биткоин"
url: izobretaem-bitkoin/glava-4
aliases: ['/book-inventing-bitcoin-chapter-4']
date: 2019-06-17
bookFlatSection: false
bookToc: true
weight: 5
---

{{< details "Оглавление" "..." >}}

[Главная страница](/izobretaem-bitkoin)

[Вступление](/izobretaem-bitkoin/vstuplenie)  

[Глава 1: Что такое Биткоин](/izobretaem-bitkoin/glava-1)

[Глава 2: Отказываемся от посредника](/izobretaem-bitkoin/glava-2)

[Глава 3: Proof of Work](/izobretaem-bitkoin/glava-3)

[Глава 4: Майнинг](/izobretaem-bitkoin/glava-4)

[Глава 5: Обеспечение безопасности реестра](/izobretaem-bitkoin/glava-5)

[Глава 6: Форки и атаки 51%](/izobretaem-bitkoin/glava-6)

[Глава 7: Учетные записи, не идентифицирующие личность](/izobretaem-bitkoin/glava-7)

[Глава 8: Кто устанавливает правила?](/izobretaem-bitkoin/glava-8)

[Глава 9: Что дальше?](/izobretaem-bitkoin/glava-9)

{{< /details >}}

Майнинг — это процесс розыгрыша лотереи Proof of Work. “Джек-пот” в каждом раунде — право добавить свой блок в реестр сети Биткоин. Вот как это работает:

1. Участвовать может каждый. Все, что нужно сделать — это присоединиться к сети Биткоин, подключив свой компьютер к сети, и начать проверять транзакции.

2. Элис объявляет о своем намерении отправить несколько монет Бобу. Компьютеры в сети делятся друг с другом информацией, чтобы оповестить всю сеть об этой транзакции.

3. Все компьютеры, которые хотят участвовать в лотерее, начинают хешировать известные им транзакции. Для этого они добавляют нонс к списку транзакций и используют хеш-функции sha256.

4. В среднем примерно каждые десять минут какой-то компьютер находит полученное из этих транзакций хеш-число, меньшее текущего целевого числа, и выигрывает в лотерею.

5. Этот компьютер объявляет найденное им выигрышное число, а также введенные данные (транзакции и нонс), которые он использовал для получения этого числа. Это могло занять у него несколько часов, а могло и несколько минут. Эта информация, собранная воедино (транзакции, нонс и хеш Proof of Work) называется блоком.

6. Все остальные ноды подтверждают валидность блока, предварительно убедившись, что транзакции в блоке вместе с нонсом действительно соответствуют заявленному хешу, что хеш действительно меньше целевого числа, что блок не содержит недопустимых транзакций и что история в нем не конфликтует с предыдущими блоками.

7. Каждый записывает блок в свою копию реестра, добавляя его к существующей цепочке блоков, создавая тем самым блокчейн.

Вот так. Мы создали наш первый блок и первую запись в наш реестр.

Возможно, вы читали часто повторяемое в СМИ утверждение о том, что Биткоин-майнинг включает в себя решение сложных уравнений. Теперь вы понимаете, что это абсолютно неверно. Вместо того чтобы решать уравнения, лотерея Биткоин-майнинга состоит в том, чтобы многократно бросать гигантский виртуальный кубик с целью подобрать хеш в пределах определенного целевого интервала. Это просто азартная игра, которая заставляет расходовать определенное количество электроэнергии.

# Как производятся новые биткоины?

Пока что мы обсуждали как Элис может отправить Бобу 2 доллара. Сейчас мы перестанем говорить о долларах, потому что Биткоин о них ничего не знает. У нас есть сами биткоины: цифровые единицы, представляющие ценность в сети Биткоин.

Если вернуться к нашему примеру, на самом деле происходит то, что Элис отправляет Бобу 2 биткоина, объявляя, что она переводит биткоины, которые зарегистрированы под ее “учетной записью”, Бобу. Затем кто-то выигрывает лотерею Proof of Work и получает возможность записать ее транзакцию в реестр.

Но откуда Элис взяла эти 2 биткоина? Откуда появился первый биткоин, и как кто-то мог обзавестись монетами до того, как появились места для их покупки за традиционную фиатную валюту, такую ​​как доллар США?

Когда Сатоши создал Биткоин, он мог создать базу данных, в которой ему принадлежал бы весь 21 миллион монет, и попросить других людей купить их у него. Однако у людей было бы мало причин приписывать ценность системе, в которой один человек владел всем богатством. Он мог бы создать реестр, в котором люди могли бы зарегистрироваться, чтобы получить шанс выиграть несколько монет, используя адрес электронной почты, но подобная система могла бы подвергнуться _сибил-атаке_ (краже личности), поскольку создание миллионов адресов электронной почты — практически бесплатно.

Оказывается, именно процесс майнинга биткоинов, то есть процесс игры в лотерею Proof of Work и получения прав на добавление информации в реестр, является тем самым процессом, в результате которого производятся новые монеты. Создание валидного блока требует сжигания большого количества энергии для нахождения числа, которое выиграет в лотерею. Найдя это число вы получаете право записать в этот блок и, следовательно, в реестр любые транзакции, о которых вам известно. Но у вас также появляется возможность записать в реестр особую дополнительную транзакцию, называемую [_транзакцией_ _коинбэйс_](https://t.me/bitcoin21ideas/386). Эта транзакция по сути гласит: “12,5 биткоинов было создано и передано майнеру Мэри, чтобы компенсировать все ее затраты на энергию, израсходованную на майнинг этого блока”.

Так появляются новые биткоины. Этот процесс позволяет абсолютно любому, готовому оплачивать стоимость электроэнергии, начать добывать (_майнить_) биткоины. Более того, для игры в эту лотерею не требуется ни разрешение какой-либо центральной власти, ни подтверждение личности. Это делает выпуск биткоинов устойчивым к _сибил-_атаке. Если вы хотите получить монеты, вам нужно будет сжечь энергию и заплатить тем самым за их  производство.

# Вознаграждение за блок

Победивший в очередном раунде лотереи может наградить себя небольшим количеством новых монет. Почему это именно 12,5 биткоинов, а не 1000? Почему победитель не может обмануть систему и начислить себе любую сумму?

Биткоин — это система _распределенного консенсуса_. Это означает, что каждый должен согласиться с тем, что валидно, а что нет. Для этого участники сети запускают на своем компьютере ПО, которое обеспечивает выполнение хорошо известного набора правил, известных как правила Биткоин-консенсуса. Ноды проверяют соответствует ли каждый произведенный майнерами блок этим правилам. Если блок проходит проверку, каждый делает пометку в своем реестре и принимает данные транзакции за правду. Если нет, то блок отклоняется.

Так как полный список правил консенсуса довольно развернутый, предлагаю обратить внимание на некоторые примеры:

• Валидный блок может создавать определенное количество биткоинов в соответствии с графиком производства, отображенном в программном обеспечении.

• У транзакций должны быть правильные подписи, указывающие на то, что люди, тратящие эти монеты, должным образом санкционировали данные расходы.

• Не должно проводиться транзакций с использованием монет, потраченных ранее в этом или любом предыдущем блоке.

• Объем данных в блоке не должен превышать определенного значения.

• Хеш блока Proof of Work должен быть ниже текущего целевого числа. Это свидетельствует о статистической невозможности майнинга этого блока любым другим способом помимо сжигания определенного количества электроэнергии.

Если Мэри майнит блок и решает вознаградить себя чем-то большим, компьютер другого пользователя отклонит этот блок как _недействительный_, потому что внутри клиентского программного обеспечения Биткоин, которое все запускают, есть фрагмент кода, который говорит: “Текущее вознаграждение за блок равно 12,5 биткоинам. Если вы видите блок, который дает кому-то больше, не принимайте его”.

Если Мэри попытается обмануть и создать _недействительный_ блок, он не будет записан в чей-либо реестр. Вместо этого она просто потратит тысячи долларов на электричество, работая над чем-то никому не нужным: над подделкой. Это дает Биткоину _неподдельную дороговизну_ (unforgeable costliness) — термин, предложенный пионером в области цифровой валюты Ником Сзабо в его эссе _Shelling Out_. Интуитивно мы знаем, что если бы деньги было очень легко подделать, они не были бы очень полезны в качестве денег. Биткоин на самом деле невозможно подделать, так как его можно проанализировать с помощью простой математической проверки.

Сатоши создал самый первый из когда-либо произведенных блоков — _генезис_ _блок_, сгенерировав первые когда-либо произведенные биткоины. Исходный код является открытым, следовательно, любой может взглянуть на то, как Биткоин работает и подтвердить, что за кулисами не происходит ничего подозрительного. Даже Сатоши не мог произвести подделку, притворившись, что израсходовал необходимое количество электричества, хоть он и был создателем системы. Чтобы добыть первый блок он должен был провести миллиарды вычислений и сыграть в лотерею Proof of Work.

Любой, кто присоединился к сети после него, может проверить сгенерированный им хеш, сравнить этот хеш с исходной целью и данными транзакций. Таким образом, можно быть уверенным, что Сатоши действительно достиг статистически редкой цели, потратив определенное количество энергии. Представьте себе возможность проверить, как традиционная система фиат-банкинга печатает деньги таким точным способом в режиме реального времени!

# Халвинг

В процессе майнинга появляются новые биткоины. Но Сатоши хотел систему, которую невозможно было бы _обесценить_. Он не хотел, чтобы монетарное предложение постоянно увеличивалось. Вместо этого он разработал график эмиссии, которая началась быстро и постепенно замедляется, стремясь к нулю новых монет в год.

Вначале награда за блок составляла 50 биткоинов. Столько и получил Сатоши за майнинг первого блока, так же как и другие участники, которые одними из первых присоединились к сети и создали первые блоки.

Биткоин-код предусматривает [халвинг вознаграждения за блок](https://www.bitcoinblockhalf.com/), что уменьшает вознаграждение вдвое примерно каждые четыре года. Это событие привязано к количеству добытых блоков, а не к конкретному времени. Но оба этих способа измерения дают почти одинаковый результат в связи с тем, что Биткоин-блоки стабильно производятся в среднем каждые 10 минут.

Награда за блок в 2008 году составляла 50 биткоинов, в 2012 году — 25, в 2016 году — 12,5. На сегодняшний день, 8 июня 2019 года, с начала истории Биткоина было добыто 579 856 блоков, и вознаграждение составляет 12,5 биткоинов за блок.

Через 50 144 блоков или примерно в конце мая 2020 года вознаграждение будет снижено до 6,25 биткоинов за блок, что приведет к уменьшению годового потока до приблизительно 1,8% от запаса. Десять лет спустя, после еще двух халвингов, будет добыто более 99% всех биткоинов, и будет производиться менее 1 биткоина за блок. Вы можете следить за ходом уменьшения вознаграждения за блок на сайте [bitcoinblockhalf.com](https://www.bitcoinblockhalf.com/).  

{{% image "/img/ib-459.png" %}}
_В конце концов, около 2140 года, награда за блок полностью сойдет на нет, и майнеры будут стимулироваться только за счет сборов за подтверждение транзакций._
{{% /image %}}

Эти показатели производства и вознаграждения за блок прописаны в коде Биткоина, который, повторюсь, является полностью открытым исходным кодом и может быть проверен любым пользователем. Это гарантирует, что блок, который не будет следовать правилам, прописанным в коде, будет отклонен всеми, руководствующимися теми же правилами.

# Управление выпуском и интервалом майнинга

Для майнинга требуется вычислительное оборудование и электричество. Следовательно, чем больше оборудования и электричества вы контролируете, тем выше вероятность того, что вы найдете выигрышное число быстрее других участников. Например, если в сети 100 компьютеров одинаковой мощности и вы контролируете 10 из них, то вы сможете находить валидный блок примерно в 10% случаев. Однако майнинг — это процесс, основанный на шансе и случайности, поэтому вполне возможно, что часы или даже дни могут проходить без того, чтобы вы нашли блок.

Из предыдущего раздела мы знаем, что майнеры не могут просто присваивать себе произвольные награды за создание блока, иначе они будут отклонены другими нодами. Но что, если они будут сжигать целую кучу энергии, чтобы ускорить майнинг блоков и получить в свои руки целую кучу биткоинов?  Они тем самым нарушат ограничение дизайна, согласно которому график выпуска должен быть известен заранее.

Давайте снова обратимся к примеру, в котором существует только 1000 возможных хешей, а наше целевое число равно 100. Это означает, что в 10% случаев мы будем получать число, которое меньше 100 и находить блок.

Допустим, нам требуется 1 секунда для вычисления каждого хеша. Если каждую секунду мы “бросаем наш кубик” путем хеширования текущих транзакций и нонса и в 10% случаев получаем число, меньшее целевого значения, логично ожидать, что в среднем нам потребуется около 10 секунд, чтобы найти подходящий хеш.

Что произойдет, если два компьютера играют в лотерею? Они будут выполнять работу в два раза быстрее, поэтому мы ожидаем, что правильный хеш будет найден в течение 5 секунд. Что если 10 компьютеров играют? Один из них будет находить выигрышный хеш примерно каждую секунду.

Это создает проблему: если больше людей занимается майнингом, то блоки будут производиться слишком быстро. Это влечет за собой два результата, которые нас не устраивают:

1. Это противоречит идее иметь заранее определенный график производства. Мы хотим, чтобы каждый час выпускалось относительно стабильное количество биткоинов. Это позволит нам выпустить их все к 2140 году, а не раньше.

2. Это приводит к проблемам в сети: если блоки будут создаваться слишком быстро, то они не будут успевать распространяться по всей сети до того, как будет создан следующий блок. Тогда мы не сможем поддерживать консенсус по линейной истории транзакций, поскольку несколько майнеров могут повторно включать уже подтвержденные транзакция в свои блоки. Это приведет к появлению большого количества недействительных блоков, поскольку они содержат транзакции, которые уже были использованы в других блоках.

_Если меньше людей занимается майнингом, мы сталкиваемся с противоположной проблемой:_

1. Биткоины создаются слишком медленно, что опять-таки противоречит графику выпуска.

2. Система может стать невостребованной, так как пользователи будут вынуждены ожидать записи своих транзакций в реестр часами, днями или даже дольше.

Общее число хешей в секунду, выполняемое всеми майнерами сети Биткоин, называется _скоростью хеширования._

{{% image "/img/ib-460.png" %}}
_Время между блоками варьируется в зависимости от скорости хеширования, а также в некоторой степени подвержено воле случая._
{{% /image %}}

# Корректировки сложности: согласование целей

Поскольку Биткоин — это добровольная и не требующая разрешения система без контролирующего органа, в которой каждый может участвовать по своему усмотрению, количество майнеров в любой момент времени будет значительно варьироваться. Нам нужен способ поддерживать стабильное производство блоков, а не ускорять или замедлять его каждый раз, когда к сети присоединяются новые майнеры, или активные майнеры приостанавливают свою деятельность.

Как мы можем усложнить поиск валидных хешей, если все больше игроков присоединяется к лотерее, и упростить, если игроки покидают лотерею, чтобы стабилизировать скорость производства блоков?

Напомню, что майнинг биткоинов — это лотерея, в которой мы пытаемся получить случайное число меньше целевого:  

{{% image "/img/ib-461.png" %}}
_Мы пытаемся попасть в эту небольшую цель. Количество возможных результатов чрезвычайно велико, поэтому нам потребуется очень много времени, чтобы получить подходящий результат посредством случайных бросков кубика._
{{% /image %}}

Биткоин решает эту проблему _корректировкой сложности майнинга_. Все используют один и тот же протокол, который применяет одни и те же правила, и у каждого есть копия всей истории блоков на данный момент. Следовательно, каждый может независимо рассчитать насколько быстро создаются блоки.

Каждые 2016 блоков, майнинг которых занимает примерно две недели [^1], мы оцениваем сколько времени нам потребовалось для производства этих блоков. Затем мы корректируем наш целевой показатель, чтобы ускорить или замедлить производство блоков.

Каждый берет последние 2016 блоков и делит их на время, затраченное на их создание, чтобы высчитать среднее арифметическое. Майнинг каждого блока занял в среднем более десяти минут? Мы двигаемся слишком медленно. Менее десяти минут? Мы двигаемся слишком быстро.

Теперь мы можем откорректировать целевое число, чтобы оно увеличивалось или уменьшалось пропорционально тому, насколько быстрее или медленнее мы хотим двигаться, основываясь на 10-и минутном интервале, который записан в открытый исходный код.

Мы можем поднять целевое число до большего значения, создавая большее пространство для валидных хешей. Тем самым мы предоставляем майнерам больше шансов найти выигрышный хеш, затрачивая при этом меньше энергии на каждый найденный блок. Это называется понижением сложности.

{{% image "/img/ib-462.png" %}}
_Повышение значения целевого числа увеличивает размер самой цели. Это повышает вероятность попадания в нее при меньшем количестве попыток, что делает процесс дешевле._
{{% /image %}}

В противном случае мы можем уменьшить целевое число, уменьшая количество валидных хешей, и майнеры должны будут тратить больше энергии на поиск валидного хеша блока. Это называется _повышением сложности_.

Это означает, что для любого из 2016 блоков мы точно знаем значение целевого числа. Это позволяет нам выяснить “магический” предел, который не должен превышаться хеш-кодом Proof of Work в выигрышном лотерейном билете для любого блока, произведенного за этот период.

Корректировка сложности и вычисление целей, возможно, является ключевым нововведением Биткоина. Оно позволяет каждому независимо проверять лотерейные номера на соответствие цели, которую они, как и все остальные, могут самостоятельно рассчитать. Именно это позволяет нам проводить лотерею, не нуждаясь в третьем лице, сообщающем о выигрышных комбинациях.

Диаграмма ниже отражает скорость хеширования в виде линии, а сложность — в виде свечей. Сложность выглядит как лестница, потому что она корректируется с шагом в 2016 блоков. Обратите внимание, что каждый раз, когда скорость хеширования поднимается выше сложности, сложность повышается, чтобы догнать скорость хеширования. Когда скорость хеширования падает, как в период с октября по декабрь 2018 года, сложность снижается. Регулировка сложности всегда отстает от скорости хеширования в течение периода в 2016 блоков (две недели).

{{% image "/img/ib-463.png" %}}
_Скорость и сложность хеширования_
{{% /image %}}

Существующая задержка корректировки сложности размером в 2016 блоков может приводить к огромным колебаниям. Это, в свою очередь, приводит к повышению либо к понижению скорости хеширования до чрезмерной или недостаточной. Это, в свою очередь, вызывает перепроизводство или недопроизводство биткоинов в течение этих 2016 блоков, слегка нарушая график эмиссии.

Поскольку повышение скорости хеширования обычно означает увеличение количества нового оборудования, всплески являются относительно редкими и не слишком сильно влияют на ситуацию. Любые подобные колебания ограничены окном в 2016 блоков, в котором они возникают. Следующая корректировка сложности возвращает нас к среднему значению в десять минут на блок.

# Скорость хеширования и стоимость биткоинов в долларах США

Биткоин автоматически пересчитывает сложность на основе общей вычислительной мощности всех участников лотереи, которые являются майнерами, расходующими энергию посредством хеширования. Здесь реальный мир начинает пересекаться с нашим цифровым миром. Цена Биткоина, цена оборудования и энергии, а также уровень сложности целевого числа создают петли обратной связи:

1. Спекулянты покупают биткоин, потому что думают, что он растет в цене, повышая цену до $X.

2. Майнеры готовы нести затраты на оборудование и электричество вплоть до суммы в $X, чтобы попытаться добыть биткоин.

3. Высокий спрос со стороны покупателей вызывает рост цен и побуждает все больше участников сети майнить биткоин, получая при этом солидную прибыль.

4. Больше майнеров означает бóльшую скорость хеширования и больше энергии, затрачиваемой на производство биткоина, а значит сеть становится еще более безопасной. Покупатели уверены в безопасности Биткоина, что иногда приводит к появлению обратной связи, которая повышает цену.

5. По прошествии 2016 блоков, повышенная скорость хеширования вызывает увеличение сложности.

6. Более высокая сложность означает меньшее целевое число — майнеры реже находят блоки, в результате чего (по крайней мере, некоторые из них) тратят больше $X на эксплуатационные расходы для добычи монеты.

7. Некоторые майнеры терпят убытки, тратя больше энергии на производство, чем они могут заработать, продавая биткоин. Они отключают свое оборудование и общая скорость хеширования падает.

8. Спустя еще 2016 блоков сложность пересчитывается в меньшую сторону, так как некоторые майнеры приостановили свою работу. Значение целевого числа увеличивается.

9. Более низкая сложность означает, что майнеры, которые были ранее убыточными, могут вернуться и снова майнить, либо новые майнеры могут присоединиться к сети.

10. Возвращаемся к первому пункту.

В условиях нисходящего рынка цикл может идти в противоположном направлении: пользователи сбрасывают монеты, что приводит к снижению цены, а майнеры становятся убыточными.

Алгоритм корректировки сложности гарантирует, что между ценой и хешрейтом всегда будет равновесие. Даже если цена резко упадет и сбросит половину текущей скорости хеширования, последующая корректировка сложности снова сделает майнинг прибыльным при новой уравновешенной цене.

Характер корректировки сложности отторгает неэффективных майнеров в пользу тех, которые используют самую дешевую энергию и, соответственно, несут наименьшие эксплуатационные затраты. Со временем это вынуждает биткоин-майнеров переносить производство в более отдаленные уголки мира, используя источники энергии, которые не реализуют весь свой потенциал или не используются вовсе. Согласно отчету CoinShares от 2019 года [^2], примерно 75% майнинга биткоина используют возобновляемые источники энергии.

За последние несколько лет как цена, так и общая скорость хеширования стремительно выросли. А чем выше скорость хеширования, тем труднее атаковать сеть, потому что для управления даже тем, что записывается в следующем блоке, вам нужно иметь под контролем более половины энергии и оборудования всей сети. На сегодняшний день количество энергии, затрачиваемой сетью майнеров Биткоин, эквивалентна затратам страны среднего размера.

# Комиссия и вознаграждение за создание блока

Если вознаграждение за создание блока в конце концов сойдет на нет, как мы сможем стимулировать майнеров продолжать сжигать энергию и защищать реестр? Ответ Биткоина — комиссия за транзакции. Они не только постепенно приходят на смену вознаграждению за блок, но и, как правило, дают майнерам стимул включать транзакции в блоки, вместо того, чтобы майнить пустые блоки сугубо для получения вознаграждения.

Тарифы определяются системой свободного рынка, где пользователи предлагают цену за ограниченное пространство в блоке. Пользователи, отправляющие транзакции, указывают, сколько комиссионных они готовы платить майнерам. Майнеры же, в зависимости от размера комиссии, решают включать данные транзакции в блок или нет. Когда транзакций, ожидающих подтверждения, немного, сборы, как правило, очень низкие, поскольку конкуренция отсутствует. По мере заполнения пространства блоков, пользователи готовы платить более высокие сборы за свои транзакции, чтобы те были подтверждены быстрее (в следующем блоке). Те, кто не хочет платить, всегда могут установить низкие комиссионные и ждать подтверждения дольше, пока пространство блока станет более доступным.

В традиционных финансовых системах комиссия, как правило, основана на проценте от суммы перевода. В Биткоине стоимость переводимых средств не влияет на размер комиссионных. Вместо этого плата пропорциональна ограниченному ресурсу, который потребляет транзакция: свободное место в блоке. Тарифы измеряются в сатоши на байт (8 бит) потребляемого пространства. Таким образом, транзакция, которая отправляет миллион биткоинов от одного человека другому, на самом деле может быть дешевле транзакции, которая отправляет 1 биткоин десяти получателям, поскольку для последней требуется больше места в блоке для отражения.

В прошлом были периоды, когда Биткоин пользовался очень высоким спросом, например, массивный рост в конце 2017 года. В это время сборы стали чрезвычайно высокими. С тех пор было реализовано несколько новых функций для снижения платы за пользование сетью.

Одна из них называется _Segregated Witness_, обновление реорганизовало отражение данных в блоке. Транзакции, пользующиеся этим преимуществом, получают возможность использовать больше, чем первоначальный 1 МБ свободного места в блоке благодаря некоторым хитрым уловкам, находящимися за рамками материала этой книги.

Другое снижение комиссии появилось благодаря группированию: биржи и другие крупные игроки в экосистеме начали объединять транзакции биткоинов для нескольких пользователей в одну транзакцию. В отличие от традиционного платежа в вашем банке или PayPal, который осуществляется от одного человека к другому, транзакция Биткоин может объединять большое количество вводов и производить большое количество выводов. Таким образом, биржа, которая должна отправить биткоин для вывода 100 людям, может сделать это за одну операцию. Это гораздо более эффективное использование пространства блоков, превращающее то, что якобы представляет собой лишь горстку транзакций биткоинов в секунду, в тысячи платежей в секунду.

Segregated Witness и группирование уже проделали большую работу по сокращению спроса на пространство в блоках. Дальнейшие улучшения, находящиеся сейчас в разработке, делают использование пространства блоков еще более эффективным. Тем не менее, наступит момент, когда комиссии за передачу биткоина снова станут высокими, так как спрос на место в блоках повышается.

_Мы почти закончили изобретать все, связанное с Биткоином:_

1. Заменили центральный банк распределенным реестром.

2. Учредили ​​систему лотереи для выбора того, кто обновляет записи реестра.

3. Вынудили участников лотереи сжигать энергию, чтобы купить билеты посредством хеширования и позволили каждому легко проверить выигрышные билеты, сравнив хеш-числа, полученные игроками, с независимо рассчитанным целевым числом.

4. Проинформировали игроков лотереи, что если они не будут играть по правилам, мы отклоним их блоки, в том числе, транзакции _коинбэйс_ и они не получат оплату в случае выигрыша; таким образом, мы создали фактор, экономически сдерживающий мошенничество, и экономический стимул играть по правилам.

5. Проконтролировали временны́е рамки и выбор целевого числа для лотереи, позволяя каждому рассчитать, каким должно быть целевое число, основываясь на жестко закодированных правилах и истории предыдущих 2016 блоков.

6. Обеспечили выполнение графика выпуска, используя корректировки сложности, которые приспосабливаются к увеличению или уменьшению скорости хеширования.

7. Использовали открытый исходный код, чтобы каждый мог лично проверить, что он применял те же правила в отношении валидности транзакции, вознаграждения за блок и расчета сложности.

Мы избавились от центрального органа управления. У нас полностью распределенная и децентрализованная система. Мы практически видим полную картину. Остается одна проблема. Когда кто-то присоединяется к сети и запрашивает копии реестра, он может получить разные истории от разных нод. Как нам обеспечить соблюдение единой линейной истории и как мы можем предотвратить майнеров от того, чтобы переписывать прошлое?

{{< details "Оглавление" "..." >}}

[Главная страница](/izobretaem-bitkoin)

[Вступление](/izobretaem-bitkoin/vstuplenie)  

[Глава 1: Что такое Биткоин](/izobretaem-bitkoin/glava-1)

[Глава 2: Отказываемся от посредника](/izobretaem-bitkoin/glava-2)

[Глава 3: Proof of Work](/izobretaem-bitkoin/glava-3)

[Глава 4: Майнинг](/izobretaem-bitkoin/glava-4)

[Глава 5: Обеспечение безопасности реестра](/izobretaem-bitkoin/glava-5)

[Глава 6: Форки и атаки 51%](/izobretaem-bitkoin/glava-6)

[Глава 7: Учетные записи, не идентифицирующие личность](/izobretaem-bitkoin/glava-7)

[Глава 8: Кто устанавливает правила?](/izobretaem-bitkoin/glava-8)

[Глава 9: Что дальше?](/izobretaem-bitkoin/glava-9)

{{< /details >}}

[^1]: Период корректировки с интервалом в 2016 блоков был выбран исходя из желаемого десятиминутного интервала блоков. 10 минут x 2016 блоков — две недели. Интервал блока был выбран Сатоши, чтобы быть достаточно большим, позволяя большинству нод синхронизироваться с последним блоком. Двухнедельный период корректировки отчасти был выбран произвольно, но он был разработан так, чтобы предотвращать слишком быструю смену скорости хеширования в системе.

[^2]: Узнайте больше о текущем состоянии майнинга на сайте [https://coinshares.co.uk/bitcoin-mining-cost-june-2019/](https://coinshares.co.uk/bitcoin-mining-cost-june-2019/)
