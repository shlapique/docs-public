Вы можете управлять плавающими IP-адресами: просматривать, добавлять в проект и убирать их из проекта, а также привязывать и отвязывать эти IP-адреса.

## Просмотр списка плавающих IP-адресов

<tabs>
<tablist>
<tab>Личный кабинет</tab>
<tab>OpenStack CLI</tab>
</tablist>
<tabpanel>

1. Перейдите в [личный кабинет](https://mcs.mail.ru/app/) VK Cloud.
1. Выберите проект и регион, где находится нужный IP-адрес.
1. Перейдите в раздел **Виртуальные сети** → **Плавающие IP**.

   Будет отображен список плавающих IP-адресов (колонка **Внешний IP**).

</tabpanel>
<tabpanel>

1. Убедитесь, что клиент OpenStack [установлен](/ru/manage/tools-for-using-services/openstack-cli#1--ustanovite-klient-openstack), и [пройдите аутентификацию](/ru/manage/tools-for-using-services/openstack-cli#3--proydite-autentifikaciyu) в проекте.

1. Выполните команду:

   ```bash
   openstack floating ip list
   ```

</tabpanel>
</tabs>

## Добавление плавающего IP-адреса в проект

<tabs>
<tablist>
<tab>Личный кабинет</tab>
<tab>OpenStack CLI</tab>
</tablist>
<tabpanel>

1. Перейдите в [личный кабинет](https://mcs.mail.ru/app/) VK Cloud.
1. Выберите проект и регион, где находится нужный IP-адрес.
1. Перейдите в раздел **Виртуальные сети** → **Плавающие IP**.
1. Нажмите кнопку **Добавить IP в проект**.
1. (Опционально) Добавьте описание.
1. Нажмите кнопку **Добавить IP**.

</tabpanel>
<tabpanel>

1. Убедитесь, что клиент OpenStack [установлен](/ru/manage/tools-for-using-services/openstack-cli#1--ustanovite-klient-openstack), и [пройдите аутентификацию](/ru/manage/tools-for-using-services/openstack-cli#3--proydite-autentifikaciyu) в проекте.

1. Выполните команду:

   ```bash
   openstack floating ip create ext-net
   ```

</tabpanel>
</tabs>

## Редактирование описания плавающего IP-адреса

<tabs>
<tablist>
<tab>Личный кабинет</tab>
<tab>OpenStack CLI</tab>
</tablist>
<tabpanel>

1. Перейдите в [личный кабинет](https://mcs.mail.ru/app/) VK Cloud.
1. Выберите проект и регион, где находится нужный IP-адрес.
1. Перейдите в раздел **Виртуальные сети** → **Плавающие IP**.
1. Раскройте меню нужного плавающего IP-адреса и выберите пункт **Редактировать описание**.
1. Задайте описание.
1. Нажмите кнопку **Сохранить**.

</tabpanel>
<tabpanel>

1. Убедитесь, что клиент OpenStack [установлен](/ru/manage/tools-for-using-services/openstack-cli#1--ustanovite-klient-openstack), и [пройдите аутентификацию](/ru/manage/tools-for-using-services/openstack-cli#3--proydite-autentifikaciyu) в проекте.

1. [Получите список плавающих IP-адресов](#prosmotr-spiska-plavayushchih-ip-adresov). Найдите в списке идентификатор плавающего IP-адреса, для которого нужно отредактировать описание.

1. Выполните команду:

   ```bash
   openstack floating ip set <идентификатор плавающего IP-адреса> --description "<описание>"
   ```

</tabpanel>
</tabs>

## Привязка плавающего IP-адреса

<tabs>
<tablist>
<tab>Личный кабинет</tab>
<tab>OpenStack CLI</tab>
</tablist>
<tabpanel>

1. Перейдите в [личный кабинет](https://mcs.mail.ru/app/) VK Cloud.
1. Выберите проект и регион, где находится нужный IP-адрес.
1. Перейдите в раздел **Виртуальные сети** → **Плавающие IP**.
1. Раскройте меню плавающего IP-адреса, для которого в столбце **Внутренний IP** указано `Не привязан`, и выберите пункт **Привязать IP**.

   <info>Непривязанные IP-адреса также содержат ссылку на привязку в соседнем столбце.
Чтобы привязать плавающий IP к другому внутреннему IP, сначала [отвяжите](#otvyazka-plavayushchego-ip-adresa) его от текущего.</info>

1. Из выпадающего списка выберите порт OpenStack с внутренним IP-адресом, к которому выполняется привязка.
1. Нажмите кнопку **Подтвердить**.

</tabpanel>
<tabpanel>

1. Убедитесь, что клиент OpenStack [установлен](/ru/manage/tools-for-using-services/openstack-cli#1--ustanovite-klient-openstack), и [пройдите аутентификацию](/ru/manage/tools-for-using-services/openstack-cli#3--proydite-autentifikaciyu) в проекте.

1. [Получите список плавающих IP-адресов](#prosmotr-spiska-plavayushchih-ip-adresov). Найдите в списке идентификатор плавающего IP-адреса, который нужно привязать к порту.
1. Получите список портов. Найдите в списке идентификатор порта, к которому нужно привязать плавающий IP-адрес.
1. Выполните команду:

   ```bash
   openstack floating ip set <идентификатор плавающего IP-адреса> --port <идентификатор порта>
   ```

</tabpanel>
</tabs>

## Отвязка плавающего IP-адреса

<tabs>
<tablist>
<tab>Личный кабинет</tab>
<tab>OpenStack CLI</tab>
</tablist>
<tabpanel>

1. Перейдите в [личный кабинет](https://mcs.mail.ru/app/) VK Cloud.
1. Выберите проект и регион, где находится нужный IP-адрес.
1. Перейдите в раздел **Виртуальные сети** → **Плавающие IP**.
1. Раскройте меню плавающего IP-адреса, который привязан к внутреннему IP, и выберите пункт **Отвязать IP**.
1. Нажмите кнопку **Подтвердить**.

</tabpanel>
<tabpanel>

1. Убедитесь, что клиент OpenStack [установлен](/ru/manage/tools-for-using-services/openstack-cli#1--ustanovite-klient-openstack), и [пройдите аутентификацию](/ru/manage/tools-for-using-services/openstack-cli#3--proydite-autentifikaciyu) в проекте.

1. [Получите список плавающих IP-адресов](#prosmotr-spiska-plavayushchih-ip-adresov). Найдите в списке идентификатор плавающего IP-адреса, который нужно отвязать от порта.

1. Выполните команду:

   ```bash
   openstack floating ip unset <идентификатор плавающего IP-адреса> --port
   ```

</tabpanel>
</tabs>

## Удаление плавающего IP-адреса из проекта

<tabs>
<tablist>
<tab>Личный кабинет</tab>
<tab>OpenStack CLI</tab>
</tablist>
<tabpanel>

1. Перейдите в [личный кабинет](https://mcs.mail.ru/app/) VK Cloud.
1. Выберите проект и регион, где находится нужный IP-адрес.
1. Перейдите в раздел **Виртуальные сети** → **Плавающие IP**.
1. Раскройте меню нужного плавающего IP-адреса и выберите пункт **Убрать IP из проекта**. Чтобы отвязать сразу несколько IP, выберите их с помощью флажков и нажмите кнопку **Убрать IP из проекта**.
1. Нажмите кнопку **Подтвердить**.

</tabpanel>
<tabpanel>

1. Убедитесь, что клиент OpenStack [установлен](/ru/manage/tools-for-using-services/openstack-cli#1--ustanovite-klient-openstack), и [пройдите аутентификацию](/ru/manage/tools-for-using-services/openstack-cli#3--proydite-autentifikaciyu) в проекте.

1. [Получите список плавающих IP-адресов](#prosmotr-spiska-plavayushchih-ip-adresov). Найдите в списке идентификатор плавающего IP-адреса, который нужно удалить из проекта.

1. Выполните команду:

   ```bash
   openstack floating ip delete <идентификатор плавающего IP-адреса>
   ```

</tabpanel>
</tabs>
