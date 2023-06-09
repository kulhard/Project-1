# Online-Store - Страница корзины товаров

---

[ПРИМЕР](https://online-store-rs.netlify.app/cart)

## Критерии оценки сross-check

**Максимальный балл `60`**

1. Реализован блок отображения добавленных продуктов +5
   - продукты выводятся списком, у каждого продукта присутствуют полные данные (имя, категория, цена и т.д.) и блок для управления кол-вом данного товара `+5`
2. Реализовано увеличение кол-ва конкретного товара и его удаление +10
   - у каждого товара есть кнопка увеличения его кол-ва в корзине. При увеличении кол-ва, также изменяется состояние кол-ва и общей цены в Header-e и на странице корзины товаров. А также увеличивается общая сумма этого товара у него в списке. При этом, нельзя добавить товара больше, чем есть на складе. Информация о наличии на складе также должна выводится `+5`
   - у каждого товара есть кнопка уменьшения его кол-ва в корзине. Если при уменьшении кол-ва товара его значения становится менее 1, то товар автоматический удаляется из корзины и текущей страницы. Также изменяется состояние кол-ва и общей цены в Header-e и на странице корзины товаров `+5`
3. Реализована пагинация +15
   - добавлена пагинация с выбором кол-ва товара на одной странице. При изменении кол-ва товаров на странице, автоматически пересчитывается кол-во страниц для переключения. Нельзя переключиться на несуществующую страницу. Также, при удалении товара, пагинация также должна пересчитываться в случае, если после удаления страниц стало меньше, чем та, на которой находился пользователь. Например, выбран лимит 3 товара на странице, всего в корзине 4 товара, соответственно имеем 2 страницы и если пользователь, находясь на второй странице(где есть 1 товар) удаляет его, то автоматический должна переключаться страница на 1 назад. Данные также добавляются в query-параметры, а состояние текущей выбранной страницы и лимита товаров на ней восстанавливается при перезагрузке страницы `+8`
   - если товаров в корзине нет, то все блоки страницы скрываются и вместо них выводится соответствующее сообщение `+5`
   - товар на каждой странице имеет порядковый номер с учетом того, сколько товаров есть до него на предыдущих страницах `+2`
4. Хранение данных в localStorage +10
   - данные о добавленных продуктах хранятся в localStorage и при перезагрузке страницы восстанавливаются `+5`
   - добавление и сохранение данных в localStorage происходит также и с других страниц приложения `+5`
5. Реализован промокод блок +10
   - реализовано поле ввода промокодов. При этом, если промокод найден во время ввода, то должна быть возможность добавления промокода в список примененных. При добавлении каждого промокода, зачеркивается старая итоговая цена на странице корзины(итоговая цена к оплате за все товары) и отображается новая(например под ней), с учетом скидки промокода. Если промокодов более одного, то суммируется их общая скидка и применяется к итоговой цене. Например, было применено 2 промокода, каждый из которых даёт 10% скидки. Суммируем и получаем скидку в размере 20%, затем применяем её к цене, которая образовалась до применения всех промокодов. Кол-во примененных промокодов не ограничено. Кроме того, должна быть возможность удаления промокода из списка примененных. Итоговая цена при этом также пересчитывается `+5`
   - реализован блок примененных промокодов, где указаны все примененные промокоды и размер скидки, которые они дают, при этом цена до применения всех промокодов должна быть перечеркнута, и добавлена новая цена, с учетом скидок всех промокодов `+5`
6. Реализована кнопка открытия [модального окна оформления покупки](purchase-modal.md) + 5
   - при клике на кнопку открывается модальное окно для оформления заказа `+5`
7. Реализован блок с общей суммой и кол-вом всех выбранных товаров +5
   - блок отображает сумму и кол-во всех товаров и реагирует на применение промокодов (дополнительно указывается новая цена после применения промокодов) `+5`
