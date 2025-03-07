---
title: "Proof of Stake – это скам"
h1: "Proof of Stake – это скам"
cover: /img/pos-655.jpg
description: "Proof of Stake (PoS) – это мошенничество. Когда я говорю это, я имею в виду, что PoS 1) заявлен как система консенсуса, и 2) фактически неспособен на самом деле обеспечить консенсус."
url: proof-of-stake-eto-skam
aliases: ['/theory-protocol-pos-is-a-scam', '/proof-of-stake–eto-skam']
date: 2021-11-09
bookFlatSection: false
bookToc: true
weight: 59
---

{{< hint btc>}}
Перевод [статьи](https://yanmaani.github.io/proof-of-stake-is-a-scam-and-the-people-promoting-it-are-scammers/) yanmaani _Proof of stake is a scam and the people promoting it are scammers_ подготовлен проектом _21идея_

[Поддержать проект](/contribute/)
{{</hint >}}

Proof of Stake (PoS) – это мошенничество. Когда я говорю это, я имею в виду, что PoS 1) заявлен как система консенсуса, и 2) фактически неспособен на самом деле обеспечить консенсус.

Чтобы понять, почему это так, мы должны сначала изучить, как работает Proof of Work (PoW) – это поможет нам осознать, почему PoS не является адекватной его заменой.

# Как работает Proof of Work

[Давным-давно](https://youtube.com/playlist?list=PLfCndTr__6HfnWzqQxso2Jh8AtlhCy3wf), еще до открытия Биткоина, многие пытались создать "[цифровую наличность](/bitcoin-zoloto-2-0)".

Они (верно) определили, что цифровые подписи являются неотъемлемой частью необходимого, но это привело их лишь к тому, что они свели проблему цифровой наличности к проблеме двойной траты. Ведь данные можно бесконечно копировать, а подпись не гарантирует того, что она не будет использована повторно.

В 2008 году Сатоши Накамото предложил решить проблему путем введения нового компонента, известного как "Proof of Work", заимствованного из известной (на тот момент) лишь в узких кругах [техники фильтрации спама в электронной почте](http://www.hashcash.org/papers/hashcash.pdf).

Идея заключалась в том, чтобы внедрить метод сжигания электричества доказуемым способом. Используемая электроэнергия не производит ничего непосредственно ценного, кроме доказательства того, что (приблизительно) определенное количество электроэнергии было потреблено тем или иным узлом (на эту работу. _прим.переводчика_).

Конкретный метод заключается в следующем: [^1]

- Все узлы могут генерировать “лотерейные билеты”.
- Эти лотерейные билеты криптографически привязаны к их решениям о том, какие транзакции они одобряют.
- Чтобы “стереть защитный слой” лотерейного билета требуется определенное количество вычислительной мощности.
- Дизайн используемых алгоритмов математически гарантирует отсутствие возможности предъявить "лотерейный билет", кроме как стереть защитный слой, затратив при этом определенное количество вычислительных ресурсов.
- Диапазон принимаемых результатов лотерейных билетов определяется сетью.
- Если узел может предъявить лотерейный билет, частота выпадания которого – один на миллион, сеть может сделать вывод, что узел в среднем проделал работу по перебору около миллиона лотерейных билетов.
- Сеть начисляет цифровую валюту узлам, представившим выигрышный лотерейный билет.
- Поскольку лотерейные билеты привязаны к решениям о валидации транзакций, узел, одобривший недобросовестные транзакции, не сможет получить свое вознаграждение.
- Если узел поступит подобным образом, он все равно понесет реальные затраты, связанные со стиранием слоя этих билетов ("майнинг"), например, электроэнергию, но не получит за это никакого вознаграждения.
- Чтобы поддерживать стабильность, сеть увеличивает редкость выигрышных лотерейных билетов (сложность), если люди выигрывают слишком часто. Например: если в настоящее время для победы требуется перебрать в среднем 10 миллиардов лотерейных билетов, а за то время, которое должно уйти на поиск десяти, найдено двадцать выигрышных билетов, сложность будет увеличена до одного к двадцати миллиардам. (Сеть пытается достичь показателя в один победитель каждые десять минут. Если производство слишком велико, сложность повышается, а если производство слишком мало, сложность снижается).

Однако это еще не все. PoW является жизненно важной деталью машины, но это не вся машина. Для осознания этого мы должны копнуть глубже.

# Истоки цифровой валюты

> “Цифровые подписи обеспечивают часть решения, но основные преимущества теряются, если для предотвращения двойных трат все еще требуется доверенная третья сторона.” — Сатоши Накамото

_[Скачать белую книгу Биткоина](/epubs/bitcoin_ru.pdf)_

Если у вас есть файл на компьютере, то, несмотря на убеждения сторонников NFT, невозможно помешать людям скопировать его. Если этот файл является вашей цифровой валютой, вы сталкиваетесь с проблемой. Если люди могут эффективно <mark style="background-color: yellow">CTRL-C -> CTRL-V</mark> вашу валюту, эта валюта бесполезна [^2].

Первый шаг к решению этой проблемы заключался в том, чтобы изменить сам подход к отправке средств. Вместо того чтобы просто отправлять компьютерный файл, пользователи отправляли цифровую валюту, подписывая ее цифровой подписью. Это был огромный шаг вперед, но этот шаг не был заключительным – он не решал проблемы двойной траты.

По сути: если у меня есть цифровая валюта на сумму $1, ничто не может помешать мне попытаться отправить тот же $1 двум разным людям, превратив его таким образом в $2. Разве что оба получателя могут сравнить свои входящие транзакции, чтобы понять, что их обманывают, решить эту проблему невозможно.

(Если уж на то пошло, чистая криптография предлагает _частичное_ решение этой проблемы. Некоторые схемы цифровой подписи приводят к утере ключа-подписи, если вы пытаетесь подписать две разные вещи одним и тем же ключом. Однако метод восстановления ключа заключается в выполнении математического расчета над двумя подписями. Чтобы это произошло, две подписи должны быть собраны в одном месте одним человеком).

До появления Биткоина люди пытались решить эту проблему на протяжении десятилетий. Система [DigiCash](https://ru.wikipedia.org/wiki/DigiCash) была предложена Дэвидом Чаумом в 1989 году, и она действительно решила эту проблему, но за это решение пришлось заплатить централизацией. Все транзакции проходили через сервер под названием "монетный двор" (хотя и в зашифрованном формате), и этот сервер, поскольку у него был полный список всех транзакций, мог проверить их на предмет двойных трат.

Таким образом, в 2007 году состояние дел в этой области в основном сводилось к следующему выбору: централизованная система без двойных трат или децентрализованная система с ними. Поскольку валютная система с двойными тратами по определению не является валютной системой, это фактически означало, что все системы цифровых валют должны были быть централизованными.

Но у Сатоши Накамото, изобретателя Биткоина, на этот счет были свои мысли:

1. Если вы требуете, чтобы все транзакции заносились в реестр, вы можете (по определению) игнорировать транзакции, которые не заносятся в этот реестр. Это означает, что вы должны заботиться о двойном расходовании средств только в пределах этого реестра.
2. Если в реестре появляется две конфликтующие транзакции, действительной всегда будет та, которая была опубликована первой.
3. Если бы у вас был так называемый "сервер временных меток", вы могли бы использовать его, чтобы выяснить, какая транзакция была первой.
4. Мы можем создать такой сервер временных меток, полагаясь на алгоритм Proof of Work, как описано выше.

Более подробно: используя локальные часы моего узла, я могу проверить, что в новых поступающих блоках (описанных как "лотерейные билеты" в моей аналогии выше) время указано верно. Имея непосредственный доступ к серии блоков ("блокчейн"), я могу угрожать отказом принятия транзакций (что сделает их деньги бесполезными) в случае, если эти временные метки не точны, т.е. не соответствуют моим (локальным) часам.Сейчас мне, похоже, стоит извиниться перед читателем за то, что описываю этот довольно обыденный процесс в таких мучительных подробностях. Но это действительно необходимо: чтобы понять, почему хорошие механические часы лучше приличной китайской копии [^3], недостаточно посмотреть на маркетинговые материалы, глянцевые брошюры, а затем закончить беглым взглядом на корпус – "выглядит примерно так же, три стрелки и циферблат" – и заметить, что они, кажется, неплохо показывают время. Мы должны разобрать их и посмотреть, что внутри.

{{% image "/img/pos-656.png" %}}
_За 2 доллара это, вероятно, неплохое приобретение._
{{% /image %}}

Ключевые моменты:  

Вся цель системы заключается в точном отображении времени. [Время здесь очень, очень важно](/21-sposob/glava-2-bitcoin-eto-vremya). Значимость этого невозможно переоценить.

PoW является жизненно важной деталью системы, но не самой системой. Есть и другие ее детали. И если вы хотите заменить одну деталь другой, это должна, по сути, быть та же деталь. Помимо этого, она должна обладать теми же или лучшими качествами.

Является ли PoS, по сути, той же самой деталью? Обладает ли PoS аналогичными свойствами?

# Как работает Proof of Stake в теории

Основная идея PoS довольно проста:

1. Вместо того чтобы покупать оборудование для майнинга за $1000, участники могут заблокировать криптовалюту на сумму, эквивалентную $1000 ("стэйкинг").
2. Вместо того чтобы через майнинг блоков указывать, какие блоки являются действительными, пользователи могут просто проголосовать за них в сети и подписать свой голос цифровой подписью.
3. Вместо того, чтобы побеждал блок, на майнинг которого было потрачено больше всего ресурсов [^4], побеждает блок, набравший наибольшее количество голосов.
4. Если поведение узлов окажется злонамеренным, вместо того, чтобы потерять вознаграждение за проделанную работу, они буквально потеряют всю свою заблокированную долю – как если бы вся их майнинг-ферма, настроенная для работы с алгоритмом PoW, сгорела при пожаре.

Адепты PoS будут утверждать, что, поскольку эти стимулы равны или превосходят стимулы системы PoW (это правда), эта система также является такой же надежной или даже превосходящей систему PoW (это ложь). Их проблема заключается в том, что помимо написания списка желаемых стимулов, также необходимо создать систему, которая эти стимулы внедрит.

Если использовать аналогию, то это сродни тому, как если бы кто-то сел проектировать здание следующим образом:

1. Сначала рисуем желаемый экстерьер.
2. Рисуем желаемый интерьер.
3. Делаем основные замеры, чтобы убедиться, что размеры интерьера не превышают размеры экстерьера.
4. Решаем, что дом готов к возведению и отправляем его строителям на постройку.

Разумеется, упущена самая важная часть – конструктивная система балок и несущих стен, без которой здание на является зданием!

Наши герои должны на практике показать, как будет работать их система, и вот тут-то и начинается самое интересное.

# “Ничего на кону”

В PoW недобросовестные участники сети подвергаются наказанию. Система, которая осуществляет это наказание, проста: они потратили электроэнергию; если они не получают ожидаемую прибыль в криптовалюте, они несут убытки. Только если система примет активное решение вознаградить их, они возместят свои затраты.

Таким образом гарантировано наказание за недобросовестное поведение: необходимость платить за электричество, не получив вознаграждения. В силу законов физики превращение энергии в тепло увеличивает энтропию, а время не повернуть вспять. **Узел не может “размайнить” блок и получить свою электроэнергию обратно.**

PoS, по своей сути, не имеет такой же системы. Как и в случае с проблемой двойной траты, любой пользователь с цифровым ключом может подписать все, что угодно, без каких-либо последствий. Поэтому им приходится воссоздавать похожую синтетическую структуру стимулов.

Здесь и появляется проблема: поскольку их наказание является синтетическим, оно существует внутри системы. Поскольку наказание существует внутри системы, оно может повлиять только на то, над чем система имеет контроль – в данном случае на заблокированные депозиты узлов. Поэтому, как только пользователи забирают свои депозиты, они становятся неприкасаемыми. В этом и заключается проблема "[ничего на кону](https://golden.com/wiki/Nothing-at-stake_problem)". Неизбежно наступит момент, когда узел сможет “разморозить” все свои вклады (стейк. _прим.переводчика_) и вывести деньги. В этот момент у сети возникает проблема:

1. Этот ключ действителен для подписи любого количества версий, скажем, блока номер 200, и нет объективного, внутрисистемного стандарта определения какая же версия является легитимной, кроме как "та, которая была опубликована первой".
2. Узел может подписывать этим ключом все, что захочет, без каких-либо последствий. Нет способа наказать его, потому что он ничем не рискует [^5].

Практически все системы пытаются решить эту проблему одним и тем же способом:

1. Если узел подписывает другую версию того же блока в течение достаточно короткого периода времени, "сократить" его депозит (т.е. наказать его внутри системы).
2. Если узел подписывает другую версию того же блока, например, через год, просто игнорировать произошедшее.

Вот в чем проблема: как вы узнаете, какая версия была первой? Если вы были там с самого начала и видели все своими глазами, то это просто. Но что, если вы только что установили клиент, а ваш узел пытается синхронизироваться? Что произойдет, если вам будут представлены два одинаковых блока, и вы должны будете решить, какой из них выбрать?

Весь смысл механизма консенсуса заключался в том, чтобы мы могли определить, какая транзакция была первой, лично ее не наблюдая. Именно поэтому важно решить проблему децентрализованной временной метки, тем самым решая проблему  упорядочивания транзакций и, соответственно, проблему двойной траты.

В этом случае кажется, что наш мнимый механизм консенсуса страдает от проблемы двойной подписи. К счастью, он решает эту проблему путем решения проблемы временной метки децентрализованного блока, поэтому он может решить проблему упорядочивания блоков.

Хахаха, шучу. На самом деле этот механизм не делает последнего. Для решения этой проблемы понадобится какой-то [другой метод](https://blog.ethereum.org/2014/11/25/proof-stake-learned-love-weak-subjectivity/):

> _“На основании всех приведенных выше аргументов мы можем смело заключить, что угроза создания злоумышленником форка с произвольно большого расстояния, к сожалению, является фундаментальной, и во всех недегенеративных реализациях эта проблема является фатальной для успеха алгоритма PoS в модели безопасности PoW. Однако мы можем обойти этот фундаментальный барьер с помощью небольшого, но все же фундаментального изменения в модели безопасности”._
> 
> _– Виталик Бутерин._

Другими словами: если оценивать PoS в рамках той же модели угроз, что и PoW, первый является фундаментально (и фатально!) небезопасным. Это признают даже его главные сторонники. Только если мы ~~понизим уровень безопасности~~ внесем "незначительные, но, тем не менее, фундаментальные изменения" в модель безопасности, ее можно будет назвать "безопасной".

# Пара вопросов

Если в схеме существует фундаментальный недостаток безопасности, который может быть "устранен" только путем снижения стандартов, по которым она оценивается, является ли эта схема "безопасной"?

Если сторонники этой, якобы, безопасной схемы знают об этом недостатке, но публично не сообщают о нем никому (кроме неоднозначных высказываний в блог-постах), следует ли считать это мошенничеством, недобросовестным отношением или просто ложью путем замалчивания?

Если, якобы, заслуживающие доверия люди знали об этой проблеме, но не сказали об этом тем, кто доверился им – как это должно отразиться на их авторитете и авторитете тех, кто, в свою очередь, их поддержал?

> _“Но если страж увидит, что идет меч, и не затрубит в рог, чтобы предупредить народ, и меч придет и лишит жизни кого-то из них, то этот человек будет взят за свой грех, а стража за эту гибель Я призову к ответу.”_
> 
> _— Иезекииль 33:6_

# Человек за занавесом

К каким можно прийти заключениям?

1. Поскольку PoS не может сам по себе привести к консенсусу, он не является механизмом консенсуса.
2. Если система все еще работает, то за ней должен стоять реальный механизм консенсуса (например, не PoS).

Так и есть, я не выдумываю:

> *“Это предположение о безопасности, идея "получить хэш блока от друга", многим может показаться неоригинальной; разработчики Биткоина часто говорят о том, что если решением долгосрочных атак (long range attack) является некий альтернативный решающий механизм X, то безопасность блокчейна в конечном итоге зависит от X, и поэтому алгоритм в действительности не более безопасен, чем использование X напрямую – подразумевая, что большинство X, включая наш подход, основанный на социальном консенсусе, небезопасны.*
> 
> *Однако эта логика игнорирует причины, по которым алгоритмы консенсуса существуют в первую очередь. ... Слабая субъективность как раз и является правильным решением".*
>
> _— Виталик Бутерин, не отрицающий утверждение, которое сам же пытается опровергнуть._

Насколько мне известно, существует три таких механизма X, предложенных для фактического консенсуса:

1. **Локальный консенсус.** Это означает, что каждый узел имеет свой собственный взгляд на происходящее. Это, действительно, очень децентрализованный подход. К сожалению, в данном случае консенсус неполон, поскольку каждый узел имеет свое собственное представление о происходящем. Пример: [Bitcoin Cash ABC](https://blog.bitmex.com/bitcoin-cash-abcs-rolling-10-block-checkpoints/).
2. **Доказательство авторитета.** Простыми словами это означает, что у вас есть доверенный орган, который подписывает блоки. Это очень эффективный метод достижения консенсуса, который даже не претендует на децентрализацию. Пример: Peercoin.
3. **Консенсус “звонок другу".** Мифическое животное, которое очень туманно описано, но, безусловно, является и децентрализованным, и эффективным механизмом консенсуса.

Очевидно, что никому не нужен ни первый, ни второй вариант. Децентрализованный консенсус – это то, к чему мы стремимся, ведь добиться одного из двух, в отличие от обоих одновременно, невероятно просто. Итак, давайте изучим этот Консенсус “звонок другу" (далее PFC, Phone a Friend Consensus), более подробно. А точнее, что делать, когда он нарушен?

В PoW нам не нужно беспокоиться о том, что "сеть" в чем-то ошибается. До тех пор, пока мы исправно подключены и проверяем каждое действие – мы знаем, что находимся на правильном пути. Мы уверены, что все остальные в конечном итоге примут общую истину. Без вариантов.

В PFC, однако, мы принимаем постмодернистский взгляд на истину. Что произойдет, если я своими глазами видел, что блок 200A был первым, но "сеть" считает, что первым был блок 200B? Пойду ли я на Reddit, чтобы попытаться их убедить? А если они не захотят слушать? Что если платформы для обсуждения подвергнутся цензуре?

Более того: что произойдет, если "сообщество" считает одно, а серьезные дяди с деньгами заявляют обратное? В теории обе эти атаки кажутся чрезвычайно надуманными, но как насчет реального мира? Два примера:

- В 2017 году в Биткоине разгорелась спорная и токсичная [дискуссия о том, что делать с ограничением размера блока в 1 МБ](/vojna-za-razmer-bloka). Во время этих дебатов многие сторонники "больших блоков" [были забанены в /r/bitcoin](https://medium.com/@johnblocke/a-brief-and-incomplete-history-of-censorship-in-r-bitcoin-c85a290fe43). В итоге победили сторонники "малых блоков" [^6]. Сыграли ли запреты какую-то роль в произошедшем?
- В Ethereum после [фиаско The DAO](https://davidgerard.co.uk/blockchain/the-dao/) Ethereum Foundation решил провести хардфорк, чтобы спасти инвесторов. В итоге Ethereum одержал победу, а Ethereum Classic (монета, не подвергшаяся хардфорку) утратила актуальность.

Итак, похоже, что в "консенсусе, основанном на сообществе", есть примерно четыре группы участников. Очевидно, что одна и та же группа не может одновременно вести или быть ведомой в одном и том же вопросе или по отношению к одной и той же проблеме противоположными способами; и поэтому **всякий раз, когда это противоречие возникает в вещах, кажущихся одинаковыми, мы знаем, что на самом деле они не одинаковые, а разные**. Это:

1. Большие дяди с деньгами и властью.
2. Люди, обладающие властью над дискуссионными площадками (форумами, чатами).
3. Широкая масса людей.
4. Вы.

Итак, что происходит, если кто-то из этих субъектов не согласен с другим? Давайте изучим этот вопрос:

1. Против любой из этих групп людей ваше мнение, в реальности, не будет иметь никакого значения.
2. Если широкие массы людей не согласны с владельцем платформы, их мнение будет изменено в соответствии с правилами, иначе они потеряют право голоса.
3. Если люди, которые фактически управляют проектом, не согласны с теми, кто управляет их платформой, эта платформа потеряет пресловутый статус "одобрения".
4. Если люди, управляющие проектом, не согласны с сообществом, у сообщества есть выбор: отделиться – потерять весь институциональный капитал и все остальное, как в Ethereum _(Classic, прим.переводчика)_, – или вернуться в строй.

Таким образом, на практике "консенсус сообщества" – это лишь запутанная и завуалированная версия "доказательства авторитета". И, как г-н Бутерин знает не понаслышке, "безопасность блокчейна в конечном итоге зависит от X".

# Если это не работает, то как же тогда получается, что оно работает?

Мы уже выяснили, что система, которая работает так, как предлагают промоутеры, буквально невозможна. Значит, система, которая действительно работает, должна пожертвовать одной из трех вещей – либо она 1) не является PoS (например, скрытый PoW), либо она 2) не децентрализована, либо 3) она не в состоянии достичь консенсуса.  

На практике, однако, между этими понятиями часто нет четкой границы. Если одни и те же люди владеют всеми токенами, контролируют все стэйкинг-пулы, управляют проектом и запустили все узлы (full node) – атака изначально невозможна. Все настолько централизовано, что на расстоянии создается ложное впечатление децентрализации.  

Вспомните [теорему CAP](https://ru.wikipedia.org/wiki/%D0%A2%D0%B5%D0%BE%D1%80%D0%B5%D0%BC%D0%B0_CAP): При наличии разделения вам приходится выбирать между согласованностью и доступностью, но отказ от принятия решения “вознаградит” вас и тем, и другим. Если каждый, кто обладает техническими средствами для проведения атаки, является приближенными владельца, корабль продолжает плыть. Или, как выразился Дэвид Джерард:

> *"Рынку наплевать на идеологию Биткоина, стоящую за децентрализацией. ... Рынок относится к централизованно управляемым токенам ICO и централизованно управляемым криптовалютам, таким как Ripple (XRP), как к объектам того же класса, что и биткоин или эфир. Рынок хочет того, чего он хочет, а не того, чего хотят от него идеологи.*
> 
> *...*  
> 
> *До тех пор, пока:*
> 
> - *сеть остается достаточно безопасной, чтобы функционировать*
> - *цена эфира не срывается в мертвое пике*
> - *токены ICO продолжают пампить и дампить*
> - *новейшие крипто котята не слишком сильно засоряют сеть*
> - *и не произойдет никаких катастроф, более затратных, чем те, что привычны в нынешней системе, такие как The DAO или катастрофа кошелька Parity*
>
> *– обновление Casper будет достаточно хорошим Proof of Stake, чтобы сообщество могло с ним жить.*
> 
> *Обновление Casper не должно быть достаточно хорошим для идеологов, оно просто должно функционировать достаточно хорошо для рынка".*

# Модерируемый на бумаге, охлаждаемый чернилами реактор

Нетрудно понять, почему люди ведутся на это. PoW обещает им, по сути, низкоэффективную систему [^7], которая дает определенный результат, используя методы, явно непостижимые для среднего пользователя. PoS обещает им хорошую систему, которая дает тот же результат, используя методы, которые примерно так же непостижимы.

Люди, продвигающие PoS, либо не знают о свойствах безопасности технологии, которую они поддерживают, и в этом случае они — клоуны (чьим рекомендациям в технологических вопросах нельзя доверять), либо они знают (но не сообщают вам), и в этом случае они — мошенники (чьим рекомендациям в технологических вопросах определенно нельзя доверять).

В любом случае, того факта, что человек продвигает PoS или серьезно относится к тем, кто это делает, должно быть достаточно, чтобы лишить его права считаться авторитетом в любом вопросе. Тот факт, что этого не происходит, а откровенные мошенники с энтузиазмом реабилитируются, является обвинительным актом в адрес предполагаемого "криптосообщества".

# Есть ли замена Proof of Work?

Я не знаю, заменим ли мы когда-нибудь PoW на какой-то другой механизм консенсуса. Возможно, лет через десять появится лучшее решение. Чтобы соответствовать модели безопасности Биткоина, новый алгоритм должен обладать следующими качествами:

1. Дороговизна – добыча блока должна создавать безвозвратные издержки, примерно эквивалентные вознаграждению за майнинг блока.
2. Необратимость – эти затраты должны возникать в реальном мире, в результате процессов, которые не могут быть без особых затрат обратимы в краткосрочной перспективе.
3. Самосертифицируемость – должна быть возможность проверки исключительно в рамках компьютерного программного обеспечения, без привязки к чему-либо еще.

PoW обладает всеми тремя характеристиками, но с некоторыми издержками.

PoS с натяжкой обладает одной из них, но не справляется с двумя другими (необратимость и самосертифицируемость).

Доказательство пространства (Proof of Space) кажется, может сработать, но только в случае бесполезности сохраняемых данных, [перенося](https://blog.dshr.org/2021/07/alternatives-to-proof-of-work.html) тем самым [трату](https://davidgerard.co.uk/blockchain/2021/05/22/news-everybody-hates-chia-defi100-rugpull-china-versus-mining-china-versus-crypto/) ресурсов [^8] с электроэнергии на электронику. Однако я не поддерживаю конкретную реализацию Чиа.

Возможно, есть небольшой проблеск надежды в объединении PoW и PoS. Таким образом, вы могли бы заменить часть майнинга ставками. Я не уверен в этом, но это моя догадка. Однако я знаю одно: когда речь идет об обещаниях будущего, которые дают криптопромоутеры, не верьте до тех пор, пока не увидите доказательств.

Людей заставляют покупать криптовалюту не реальные, уже произошедшие технологические достижения, а обещания предстоящего. На самом деле, лучшим стимулом для них является постоянное “нахождение луны на горизонте”, чтобы информировать потенциальных держателей токенов о том, что они находятся на первом этаже этого устремляющегося ввысь небоскреба.

Циничные люди заметят, что именно так на самом деле работает большинство криптовалютных проектов – это не только выгоднее, но и дешевле. Они не лгут, когда говорят, что вы попадаете на самый первый этаж только в том случае, если подразумевают, что когда-нибудь будет построен второй.

[^1]: Хотите верьте, хотите нет, но это упрощение.︎ Подробнее об алгоритме Proof of Work можно узнать [здесь](https://youtu.be/o7CwrxMFsG0), [здесь](/izobretaem-bitkoin/glava-3), [здесь](/proof-of-work) и [здесь](/suverenitet-posredstvom-matematiki/glava-5)
[^2]: Я не пытаюсь привести здесь какой-то жесткий аргумент против инфляции. Я лишь хочу сказать, что валюта, основанная на том, что можно взять любой клочок бумаги и написать на нем самое большое число, которое только можно себе представить, неэффективна.︎
[^3]: Нет ничего плохого в китайской часовой технике, есть много качественных китайских часовых брендов, и производство многих "западных" брендов также расположено в Китае. Я не утверждаю, что качество всей продукции из Восточной Азии оставляет желать лучшего, просто (практически) вся продукция низкого качества производится в Восточной Азии. (На это можно возразить, что все товары любого вида производятся в Восточной Азии)︎.
[^4]: Вероятностно.︎
[^5]: Иногда люди переопределяют "ничего на кону", чтобы обозначить что-то другое, и называют это нападением издалека.︎
[^6]: Я не поддерживаю ни одну из сторон в этом конфликте, я лишь говорю, что соц. платформы имеют силу.︎
[^7]: Например, в плане траты энергии. Как система консенсуса, она превосходна.︎
[^8]: Это не значит, что трата $100 на жесткий диск не предпочтительнее траты $100 на электричество.︎
