Рівень 1

#Феєрверк

__Передмова:__
У цьому проекті ми створюємо феєрверки над містом.

##Крок 1: Створення Ракети, що летить за рухом мишки. 

__Імпортуйте для цієї гри інші картинки__

1. Створіть новий проект у Скретч.  Видаліть кота, клікнувши правою кнопкою мишки і натиснувши "Вилучити".
2. Змініть тло (фон) на вулиця/вода над містом (outdoor/city-with-water).
3. За допомогою кнопки __новий спрайт з файлу__ додайте в проект спрайт Ракети (Resources/ Rocket.png costume).
4. Подбайте про те, щоб при натисканні зеленого прапорця, ракети не було видно.

Тепер потрібно зробити так, щоб ракета плавно рухалась (команда ковзати) за мишкою, коли мишкою клікають.

1. Додайте блок "коли натиснуто клавішу пропуск" і під ним пропишіть команди для появи ракети та її руху  в напрямку рухів мишкою:

```scratch

	коли натиснуто зелений прапорець

	сховати

	
	коли натиснуто клавішу пропуск
	показати
	ковзати 1 сек до x: мишка x y: мишка y
```
		
###Test Your Project
__Натисніть на значок із зеленим прапорцем, помістіть мишку над сценою і натисніть пробіл.__

Чи з'являється ракета, чи рухається відповідно до рухів мишкою? 
Що відбувається, коли ви рухаєте мишкою і знову натискаєте пробіл?

1. Феєрверк не повинен літати з боку в бік, тож треба переконатись, що він завжди слідує за рухом мишки із нижньої частини екрану.  Перед тим, як вивести ракету, скористайтесь блоком "переміститись в", задавши йому команду рухатись під низ екрану, але залишатись у тому ж місці в горизонтальному положенні.

```scratch

	коли натиснуто зелений прапорець

	сховати

	
	коли натиснуто клавішу пропуск
	переміститись в x: мишка x y: -200
	показати
	ковзати 1 сек до x: мишка x y: мишка y
```

###Протестуйте свій проект.
__Натисніть на значок із зеленим прапорцем, помістіть мишку над сценою і натисніть пробіл.__ 
Чи летить ракета за мишкою з нижньої частини екрану? Що відбувається, коли ви рухаєте мишкою і знову натискаєте пробіл?

1. А тепер змініть проект так, щоб він стартував не при натисканні пробілу, а при натисканні кнопки мишки. Для цього слід прописати у скрипті forever if mouse down, замінити блок  __"при натисканні клавіші пропуск"__ на __коли натиснуто зелений прапорець__ і переконатись, що ракети не видно, коли проект запускається.

```scratch

	коли натиснуто зелений прапорець
	сховати
	завжди якщо мишку натиснуто?
		переміститись в x: мишка x y: -200
		показати
		ковзати 1 сек до x: мишка x y: мишка y
	(кінець завжди)
```
###Протестуйте свій проект.
__Натисніть на значок із зеленим прапорцем і натисніть кнопку мишки, помістивши її над сценою.  Знову натисніть у іншому місці.__ 

###Спробуйте зробити так, щоб:
1. перед тим, як почати плавно рухатись за мишкою, ракета трохи вигиналась дугою.
2. деякі ракети рухались трохи повільніше або швидше, ніж інші.

Збережіть свій проект.

## Крок 2: Поява ефекту вибуху для ракети.

￼1.По-перше, для створення ефекту вибуху необхідний характерний звук("бах!",Bang ). Імпортуйте звук вибуху із вкладки Зву

```scratch

	коли натиснуто зелений прапорець
	сховати
	завжди якщо мишку натиснуто?
		переміститись в x: мишка x y: -200
		грати звук удар
		показати
		ковзати 1 сек до x: мишка x y: мишка y
		сховати
	(кінець завжди)
```
2. Потім подбайте про те, щоб ракета повідомляла, що вона вибухнула.  Пізніше ми прослухаємо це повідомлення.

```scratch

	коли натиснуто зелений прапорець
	сховати
	завжди якщо мишку натиснуто?
		переміститись в x: мишка x y: -200
		грати звук бах
		показати
		ковзати 1 сек до x: мишка x y: мишка y
		сховати
		оповістити вибух
	(кінець завжди)
```
###Протестуйте свій проект.
__Натисніть на значок із зеленим прапорцем.__ 
Переконайтесь, що ракета видає звук і зникає, коли досягає мишки.

3. Імпортуйте новий спрайт з вкладки Resources/firework1.png
4. Після отримання повідомлення про вибух він повинен щезнути, а потім перемістившись на місце ракети за допомогою команди "переміститись в", знову з'явитись і через секунду зникнути.

```scratch

	коли одержую вибух

	сховати

	переміститись в x: значення x ракети y: значення y ракети

	показати

	чекати 1 сек

	сховати
```
###Протестуйте свій проект.
__Запустіть іншу ракету.__ 
Чи з'являється графіка вибуху, коли ракета вибухає?  
Що відбувається, коли ви утримуєте натиснутою кнопку мишки, одночасно рухаючи її? (Не хвилюйтесь, зараз ми це виправимо).

Збережіть свій проект.

##Крок 3: Кожен вибух стає різним.

1. За допомогою команди set color effect та команди "вибрати випадкове" вибираємо випадковий колір від 1 до 200 перед появою кожного вибуху.

```scratch

	коли одержую вибух

	сховати

	встановити ефект колір в вибрати випадкове від 1 до 200

	переміститись в x: значення x ракети y: значення y ракети

	показати

	чекати 1 сек

	сховати
```

###Протестуйте свій проект.
__Натисніть на значок із зеленим прапорцем__ 

Чи має кожен з вибухів тепер інший колір?

2. Тепер додамо деякі інші образи вибухів із вкладок Resources/firework2.png and Resources/firework3.png та переключатимемось між ними для кожної з ракет перед їх появою.

###Протестуйте свій проект.
__Натисніть на значок із зеленим прапорцем__ 

Чи відрізняється графіка вибуху кожної ракети?

3. Зрештою, створимо ефект наростання вибуху, а не просто його появи.  Замість команди "чекати 1 сек", пропишіть команду зміни розмірів спрайту (обєкта) до його появи "встановити розмір на 5%", а потім, коли він знову з'являється, команду збільшення його розміру з допомогою "змінити розмір на 2".

```scratch

	коли одержую вибух

	сховати

	встановити ефект колір в вибрати випадкове від 1 до 200

	переміститись в x: значення x ракети y: значення y ракети

	задати розмір 5%

	показати
	
	повторити 50
		змінити розмір на 2
	(кінець повторити)

	сховати
```
###Протестуйте свій проект.
__Натисніть на значок із зеленим прапорцем.__ 

Графіка вибуху розширюється від центру ракети і повільно наростає?

###Спробуйте:
Чому б не зробити вибухи ще різноманітнішими, змінивши їх розміри та швидкість наростання вибухів?

Збережіть свій проект.

##Крок 4: Вирішення проблеми/збою з повідомленнями.
Пригадуєте раніше у нас виник збій при утриманні кнопки мишки та одночасному русі мишки?  Це відбувається через те, що після першого повідомлення про вибух ракети, команда негайно повторюється у циклі "якщо" і надсилає повідомлення про інший вибух ще до того, як попередній закінчиться.


1. Щоб виправити це, ми замінимо блок "повідомлення" на блок "повідомлення і очікування". Таким чином, цикл не повторюватиметься, поки вибух не закінчиться.

```scratch

	коли натиснуто зелений прапорець
	сховати
	завжди якщо мишку натиснуто?
		переміститись в x: мишка x y: -200
		грати звук удар
		показати
		ковзати 1 сек до x: мишка x y: мишка y
		сховати
		оповістити вибух і чекати
	(кінець звжди)
```
###Протестуйте проект.
__Натисніть на значок із зеленим прапорцем, натисніть кнопку мишки та водіть мишкою навколо сцени.__ 

Чи з'являється графіка вибуху  у належний час і в належному місці?

Збережіть свій проект.