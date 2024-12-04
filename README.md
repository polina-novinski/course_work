#  Публикация совестких текстов в эмиграции: база данных, статистика, литературный канон
## Общая характеристика данных
Датасет представляет собой роспись советских текстов, опубликованных в эмигрантской прессе в период с 1918 по 1940 гг. на основе материалов, представленных в двух издательствах: З. И. Гржебина, «Петрополис» и 15 журналах: «Версты», «Возрождение», «Воля России», «Голос России», «Иллюстрированная Россия», «Литература и жизнь», «Молва», «Накануне», «Новая газета», «Последние известия», «Руль», «Русский голос», «Сегодня», «Современные записки», «Эпоха». Помимо этого в корпус вошли литературные произведения, упомянутые в рекламных листовках издательств, которые встречались на страницах анализируемых журналов. В силу специфики таких данных подобные случаи были вынесены на отдельный лист таблицы и имеют несколько иные графы для заполнения.

## Особенности подготовки данных
**Отбор материалов для исследования осуществлялся в несколько этапов:**
1) выписка всех периодических изданий из «Литературной энциклопедии русского зарубежья» (Т. 2) с краткой характеристикой содержания и перечисление упомянутых советских текстов, если они указывались в энциклопедии. На этом этапе в таблицу были занесены 108 элементов: 47— в которых есть более одной публикации, 45— нет данных нужного типа, 16 — вызывающие сомнения (упоминание об одном тексте);
2) анализ составленной таблицы и предварительное определение издательств, с которыми будет вестись работа, по трем основным критериям: аудитория журнала, объем подходящих нам произведений, содержащихся в нем, и разнообразие выборки по городам публикации, чтобы была возможность сравнить издательский процесс в разных странах. В итоге для первоначальной работы были выбраны 17 элементов, так как, на наш взгляд, они могут быть наиболее репрезентативными;
3) работа непосредственно с пулом издательств и занесение текстов в базу данных.
   
**Первоначальные критерии отбора произведений:**
+Текст написан в период с 1918 по 1940 и опубликован в эмигрантском журнале в этот же отрезок времени;
*В жанровом плане текст представляет собой художественное произведение/эго-документ. В базу данных не были включены литературоведческие, искусствоведческие и философские статьи, поскольку нашей основной задачей было посмотреть именно на бытование текстов советских писателей, предназначенных для широкой аудитории. В большинстве случаев это литературные произведения и переписка писателей;
*В базу данных включались тексты тех авторов, которые занимаются на постоянной основе писательской деятельностью, эго-документы политических деятелей, печатаемые в газетах, и подобные случаи добавлены не были;
*При отборе текстов учитывалось, где именно произведение было написано, а не местоположение автора на момент его публикации, по этому критерию определялось, можно ли идентифицировать текст как советский или нет. Если писатель во время выхода произведения находился за границей, но само оно было создано в советской России, то оно вносилось в базу данных. Если автор издавал что-то оригинальное во время заграничной поездки, то такие случаи в корпус не включены. Главным фактором выборки была публикация текста в СССР, если она отсутствует, то произведение могло быть отобрано только в исключительных случаях — обычно такая ситуация была с письмами, поскольку они изначально не предназначены для издания. Особый интерес представляют случаи, когда автор по приезде в Европу сам передает свои сочинения, как, например, в ситуации с С. А. Есениным, тогда мы опирались на то, насколько писатель воспринимался современниками как советский. Для всех остальных текстов критерием было наличие пре-текста.

## Состав датасета и структура данных
В набор данных входят файлы:
Readme.txt — описание данных и принципов их подготовки;
Sovet_publications.xlxs — таблица с данными о публикации советских текстов в эмиграции.
Таблица состоит из двух листов: 1) база с текстами, которые появлялись на страницах журналов полностью или отрывками;2) выписка названий издаваемых книг из рекламных объявлений.

**Поля для первого листа:**
*number  — порядковый номер произведение в таблице;
*author_in_publication — имя автора текста в унифицированном формате: фамилия, инициалы (без пробелов), разделенные точкой. В этом столбце используется то имя, которым подписана публикация, псевдонимы не заменены на реальные имена;
*author_real_name  — реальное имя автора текста в том же формате;
*text  —название текста;
*name  — название журнала/издательства, в котором опубликовано;
*city  —  город, в котором выходит журнал;
*type  — тип места публикации в формате select multiple. Значения: Журнал, Издательство, Литературное приложение (в журнале);
*political orientation — направленность журнала;
*issue   — номер журнала. Для «литературного приложения» дается двойная нумерация: выпуск журнала + сквозная нумерация приложений в скобках;
*year_publ_in_emigration  — год выхода журнала/книги;
*date_publ_in_emigration  — число-месяц выхода журнала/книги, если есть;
*taken_from  — указание на источник, если есть;
*description  — тип текста в формате select multiple. Значения: стихи, проза, эго-документ;
*peculiarity  — полнота представления текста в формате select multiple. Значения: полный текст, отрывок;
*name_part  — название отрывка, если есть;
*pages  — номера страниц, на которых опубликовано произведение;
*year_first_in_russia  — дата первой публикации в СССР;
*source   — как произведение поступило в редакцию (опционально);
*pages  — номера страниц, на которых опубликовано произведение;

**Поля для второго листа:** 
*number  — порядковый номер произведение в таблице;
*author_in_publication — имя автора текста в унифицированном формате: фамилия, инициалы (без пробелов), разделенные точкой. В этом столбце используется то имя, которым подписана публикация, псевдонимы не заменены на реальные имена;
*author_real_name  — реальное имя автора текста в том же формате;
*text — название текста, если есть, или указание на тип (стихи или проза) и количество в квадратных скобках, если упомянуто. Пример: стихи [2];
*name  — название журнала/издательства, в котором опубликована реклама;
*city  —  город, в котором выходит журнал;
*year — год выхода журнала/книги;
*issue   — номер журнала;
*page  — номер страницы;
*publishing_house  — издательство, которое публикует рекламу текста;
*repeat  — повторяется ли объявление в формате select multiple. Значения: true, false. При значении true в скобках перечисляются даты всех повторных публикаций.

