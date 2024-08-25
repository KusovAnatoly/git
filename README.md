# работа с git

## перед началом работы
в тексте команды отображены следующим образом:

`git init`

```shell
git checkout -b BRANCH-NAME
```

команды вводятся с помощью клавиатуры и выполняются с помощью клавишы Enter

если текст написан большими буквами через дефис, например, YOUR-EXAMPLE, то это условные значения, которые устанавливаются либо на ваш выбор, либо четко указаны, например, указывать электронную почту при конфигурации локального репозитория следует из учетной записи на GitHub 
- YOUR-GITHUB-NAME - имя пользователя на GitHub
- YOUR-GITHUB-REPOSITORY-NAME - имя репозитория на GitHub
- YOUR-GITHUB-EMAIL - электронная почта на GitHub и т. д. и т. п.

---

*предварительные требования*:
- вам нужно [установить](https://git-scm.com/book/ru/v2/%D0%92%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5-%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-Git) **git** на ваш ПК, если не установлено
- вам нужно [установить](https://apps.microsoft.com/detail/9N0DX20HK701?hl=ru-ru) **Windows Терминал** на ваш ПК, если не установлено
- вам нужно иметь учетную запись на сайте [github.com](https://github.com/)


## короткая информация
git — это система управления версиями (version control system).

система управления версиями — это программное обеспечение для облегчения работы с изменяющейся информацией. система управления версиями позволяет хранить несколько версий одного и того же документа, при необходимости возвращаться к более ранним версиям, определять, кто и когда сделал то или иное изменение, и многое другое.

GitHub — это веб-сервис для хостинга (удаленного и распределенного хранения) git-репозиториев.

репозиторий — это место, где хранятся и поддерживаются файлы.

git-репозиторий — это обычная папка в которой находятся файлы с которыми вы работаете, для отслеживания информации о них вместе с ними находится служебная папка .git, в которой хранятся данные репозитория

git-репозиторий может находится на сервере в интернете (например, GitHub) или у вас на компьютере.

у git-репозитория есть источник (origin) то есть основной репозиторий из которого потом делают "клоны" другие разработчики и который является основной версией файлов.

origin - удаленный репозиторий на сервере, который хранит основную (главную) версию проекта

local - локальный репозиторий на вашем компьютере

*note: удаленный репозиторий (origin) создается на сервере и обычно клонируется в локальный репозиторий на компьютере*

*note: удаленный репозиторий (origin) пополняется файлами с помощью локального репозитория*

***официальный учебник от разработчиков git по [ссылке](https://git-scm.com/book/ru/v2).***

## у вас нет удаленного репозитория и вам нужно создать новый
1. создайте **удаленный** репозиторий на сайте [github.com](https://github.com/)
2. создайте папку на вашем ПК в удобном месте (например, C:\Users\YOUR-USER\MY-PROJECTS-FOLDER)
3. создайте **локальный** ***git*** репозиторий в папке которую вы ранее создали (шаг 2) <br> для этого нажмите ПКМ (правая кнопка мыши) на папке, выберите Открыть с помощью -> Windows Terminal, открыв Терминал, выполните команду `git init`
4. добавьте конфигурацию вашей учетной записи GitHub в **локальном** репозиторий, используя следующие команды:

```pwsh
git config user.name "YOUR-GITHUB-NAME"
git config user.email "YOUR-GIHUB-EMAIL@EXAMPLE.COM"
```
*note: это делается для того, чтобы вы могли вносить изменения в ваш удаленный репозиторий на GitHub* 

5. добавьте ссылку на удаленный репозиторий на GitHub который вы создали раньше (шаг 1) с помощью команды
```pwsh
git remote add origin https://github.com/YOUR-GITHUB-NAME/YOUR-GITHUB-REPOSITORY-NAME.git
```

*note: https://github.com/YOUR-GITHUB-NAME/YOUR-GITHUB-REPOSITORY-NAME.git - ссылка на ваш репозиторий*

*note: оборатите внимание, что в адресной строке в браузере часть ".git" отсутствует, но в команде она должна быть*

6. чтобы отметить, что вы добавили/изминили/удалили файлы в вашем проекте, необходимо добавить их *staging area* с помощью команды `git add .` или `git add --all` или `git add -A`
7. создайте коммит с помощью команды `git commit -m "ANY-MESSAGE-YOU-WANT-TO-LIVE"`
8. отправьте изменения в удаленный репозиторий с помощью команды `git push -u origin BRANCH-NAME`

*note: имя ветки по умолчанию **main** (в более старых версиях master), проверить имя ветки можно через команду* `git status`



## у вас есть удаленный репозиторий и он полностью пустой

у вас есть два варинта работать с пустым удаленным репозиторием:  
1. создать новый локальный репозиторий и соединить их  
2. склонировать пустой удаленный репозиторий  

Мы будем использовать первый способ как мы делали это выше, пример второго способа вы найдете в следующем разделе

1. создайте папку на вашем ПК в удобном месте (например, C:\Users\YOUR-USER\MY-PROJECTS-FOLDER)
2. создайте **локальный** ***git*** репозиторий в папке которую вы ранее создали (шаг 1) <br> для этого нажмите ПКМ на папке, выберите Открыть с помощью -> Windows Terminal, открыв Терминал
3. добавьте ссылку на удаленный репозиторий на GitHub с помощью команды
```pwsh
git remote add origin https://github.com/YOUR-GITHUB-NAME/YOUR-GITHUB-REPOSITORY-NAME.git
```
4. добавьте конфигурацию вашей учетной записи GitHub в **локальном** репозиторий, используя следующие команды:

```pwsh
git config user.name "YOUR-GITHUB-NAME"
git config user.email "YOUR-GIHUB-EMAIL@EXAMPLE.COM"
```

*note: это делается для того, чтобы вы могли вносить изменения в ваш удаленный репозиторий на GitHub*

5. чтобы отметить, что вы добавили/изминили/удалили файлы в вашем проекте, необходимо добавить их *staging area* с помощью команды `git add .` или `git add --all` или `git add -A`
6. создайте коммит с помощью команды `git commit -m "ANY-MESSAGE-YOU-WANT-TO-LEAVE"`
7. отправьте изменения в удаленный репозиторий с помощью команды `git push -u origin BRANCH-NAME`

*note: имя ветки по умолчанию main (в более старых версиях master), проверить имя ветки можно через команду* `git status`

## у вас есть удаленный репозиторий и вам необходимо внести в него изменения
Пример клонирования репозитория - пункт 3.

Для того, чтобы внести изменения (добавление, удаление или редактирование) файлов в удаленном репозитории, вам следует:
1. создать папку на вашем ПК в удобном месте (например, C:\Users\YOUR-USER\MY-PROJECTS-FOLDER)
2. создать **локальный** ***git*** репозиторий в папке которую вы ранее создали (шаг 1) <br> для этого нажмите ПКМ на папке, выберите Открыть с помощью -> Windows Terminal, открыв Терминал
3. склонировать репозиторий с помощью команды
```
git clone https://github.com/YOUR-GITHUB-NAME/YOUR-GITHUB-REPOSITORY-NAME.git
```

*note: https://github.com/YOUR-GITHUB-NAME/YOUR-GITHUB-REPOSITORY-NAME.git - ссылка на ваш репозиторий*
4. добавьте конфигурацию вашей учетной записи GitHub в **локальном** репозиторий, используя следующие команды:

```pwsh
git config user.name "YOUR-GITHUB-NAME"
git config user.email "YOUR-GIHUB-EMAIL@EXAMPLE.COM"
```

*note: это делается для того, чтобы вы могли вносить изменения в ваш удаленный репозиторий на GitHub*

5. отметить изменения в файлах и папках в *staging area* с помощью команды `git add .`
6. выполнить комманду `git commit -m "ANY-MESSAGE-YOU-WANT-TO-LIVE"`
7. отправить изменения в удаленный репозиторий с помощью команды `git push -u origin BRANCH-NAME`

## как изменить ветку

*что нужно знать о ветках*

> Ветка в Git аналогична ветке дерева. Аналогично, ветка дерева прикрепляется к центральной части дерева, называемой стволом. Хотя ветви могут образовываться и опадать, ствол остается компактным и является единственной частью, по которой мы можем сказать, что дерево живо и стоит. Аналогичным образом, ветка в Git — это способ продолжать разработку и кодирование новой функции или модификации программного обеспечения, не затрагивая при этом основную часть проекта. Также можно сказать, что ветки создают еще одну линию развития в проекте. Основная ветка или ветвь по умолчанию в Git — это главная ветка (похожая на ствол дерева). Как только создается репозиторий, создается и основная ветка (или ветка по умолчанию).

> Ветки Git приходят на помощь в самых разных местах во время разработки проекта. Как упоминалось выше, ветки создают другую линию разработки, которая полностью отличается или изолирована от основной стабильной основной ветки. В этом есть много преимуществ.

1. вы можете сменить ветку с помощью команды `git switch BRANCH-NAME`
2. вы можете создать И сменить ветку одной командой `git checkout -b BRANCH-NAME`
3. просмотреть список веток вы можете с помощью команды git branch

