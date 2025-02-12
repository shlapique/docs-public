Регион это географическая область, объединяющая [зоны доступности](/ru/additionals/start/it-security/platform-security#zony-dostupnosti). В каждой зоне доступности находится один или несколько центров обработки данных (ЦОДов), где физически размещены объекты облачной инфраструктуры.

Регион назначается каждому [проекту](../projects) автоматически и зависит от URL сайта, на котором владелец проекта [зарегистрировал](/ru/additionals/start/get-started/account-registration) свой аккаунт.

Создавать объекты (например, виртуальные машины) можно только в зоне доступности региона, в котором был создан проект.

<warn>

Все регионы имеют единую базу пользователей. Невозможно зарегистрировать учетные записи с одной и той же почтой в разных регионах.

</warn>

Доступны следующие регионы:

|            | Москва             | Казахстан              |
|-------------------------------|--------------------|------------------------|
| URL сайта | https://mcs.mail.ru | https://vkcloud.kz, https://kz.mcs.mail.ru |
| Зоны доступности              | MS1 (KO1), GZ1 | QAZ |
| Валюта проектов                | Рубли               | Тенге |

У проектов, созданных в разных регионах, различаются:

- набор доступных сервисов;
- набор [квот](../../concepts/quotasandlimits);
- адреса [эндпоинтов VK Cloud API](/ru/manage/tools-for-using-services/rest-api);
- имя региона в файлах конфигурации [openrc](/ru/manage/tools-for-using-services/openstack-cli#3--proydite-autentifikaciyu) и [Terraform](/ru/manage/tools-for-using-services/terraform/quick-start).

<warn>

Объединить виртуальные сети проектов из разных регионов стандартными способами невозможно. Сетевую связность между такими проектами можно настроить при помощи [VPN-туннеля](/ru/networks/vnet/use-cases/vpn-tunnel).

</warn>
