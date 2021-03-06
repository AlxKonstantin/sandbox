# Транслитерация слов

> Нужно сделать транлитератор имен и фамилий с русского на английский и обратно. Например, Петров должен траслитерироваться в Petrov, Petroff,... Или наоборот, с английского Jurij переводится в Юрий. Файлы с таблицей траслитерации и с частотами имен/фамилий приложены к письму.
> 
> Хотелось бы, чтоб программа не выдавала заранее несуществующих имен и фамилий. Например, для имени Инесса не было бы варианта Inesssa. И работала на не знакомых словах которых нет в файле со статистикой.

## Решение

Вариант со скрытой марковской моделью получился не очень, поскольку разбиение на слоги не учитывает различные варианты разбиений, но в первую очередь из-за применения модели первого порядка.
 
Пример использования содержится в классе [HmmTranslitTest](src/test/java/antivoland/amahir/translit/hmm/HmmTranslitTest.java), его вывод подтверждает сказанное выше:

```
avundiy -> авундии
plakilla -> плякилля
usfazan -> юзфазан
pheognia -> феожня
epiktet -> епиктет
inessa -> инса
petrov -> петров
petroff -> петров
jurij -> юриж

авундий -> avyndi
плакилла -> plakilla
усфазан -> usfasan
феогния -> feogniya
эпиктет -> epictet
инесса -> injessssa
петров -> petrov
юрий -> uri
```
