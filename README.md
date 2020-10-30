# Тестовое задание для Boston Gene
 
Нужно написать небольшое веб-приложение для обработки “тяжелых” задач в
фоновом режиме.
Пользователь отправляет в GET-запросе число Х, приложение должно
вычислить 2*Х и вернуть пользователю. Но сделать это нужно в фоновом режиме, смоделировав таким образом ситуацию “тяжелых” вычислений. Приложение принимает запрос на вычисление, возвращает пользователю 201 и id вычисления, по которому позже с помощью второго запроса пользователь сможет узнать результат вычисления. При этом “тяжелое” вычисление не должно мешать приложению принимать другие запросы от пользователей.

Эндпоинты:​

● /calculate. GET-запрос с параметром Х (float). В ответ отправляется стату
201 и id запроса на вычисление

● /result. GET-запрос, параметр - id запроса на вычисление, который мы
получили с предыдущего эндпоинта. Если вычисление уже закончено - возвращает статус 200 и число 2 * Х. Если еще не закончено - статус 201 с пустым ответом.

Прим. Вычислить в фоновом режиме значит в другом процессе. Процесс, в котором работает веб-приложение, не должен заниматься вычислениями. Он должен только слушать запросы, давать ответы и инициировать вычисления в других потоках.

## запуск
`docker-compose build`

`docker-compose up`

после этого список методов будет доступен на 0.0.0.0:8000/docs



