Оптимальные параметры виртуальной машины Java подбираются автоматически при установке и настройке кластера, в зависимости от типа виртуальной машины. Если вы получаете ошибки «Out of memory», то рекомендуем пересоздать кластер с конфигурацией большего размера, либо изменить параметры в интерфейсе Ambari.

Для изменения параметров войдите в интерфейс Ambari,

1.  Откройте интересующий сервис (например, HDFS) и выберите вкладку «Configs».

    ![](./assets/1533046004276-2b810b16a9e5a8fa00384ee98514fecf-png)

2.  На вкладке Configs прокрутите в самый низ страницы до настроек Java-машины:

    ![](./assets/1533046017375-83e3494aca4c45ba7fa7ae05a859645c-png)

3.  После изменения настроек Ambari предложит перезапустить сервисы.
