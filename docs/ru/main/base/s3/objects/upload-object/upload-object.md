В бакет S3 можно загружать файлы любого типа — изображения, резервные копии, данные, фильмы и так далее. Максимальный размер обычного файла, который можно загрузить в бакет составляет 32 ГБ. Для файлов, которые превышают этот размер, необходимо использовать метод мультипартовой загрузки и хранения. Для комфортной загрузки файла объемом свыше 1 ГБ рекомендуется использовать AWS S3 CLI или AWS S3 REST API.

<warn>

При загрузке объекта ему назначается ключевое имя: комбинация имени объекта и имен папок, в которых находится объект (при наличии). Если загружается новый объект с ключевым именем, которое уже существует в бакете, S3 заменяет существующий объект новым.

</warn>

## Загрузка из личного кабинета VK Cloud

1. Перейдите в [личный кабинет](https://mcs.mail.ru/app/) VK Cloud.
1. Перейдите в раздел **Объектное хранилище → Бакеты**.
1. Нажмите на имя нужного бакета.
1. Нажмите кнопку **Добавить файл**.
1. Выберите необходимые настройки ACL для загружаемых объектов.
1. Чтобы загрузить один или несколько файлов, выполните одно из следующих действий:

   - Перетащите файлы в окно загрузки (только для браузеров Firefox и Chrome).
   - Нажмите кнопку **Выбрать файлы** и выберите файлы.

1. Чтобы загрузить папку с файлами, перетащите папку в окно загрузки (только для браузеров Firefox и Chrome).

## Загрузка из S3 CLI

В S3 CLI доступны несколько вариантов загрузки объектов:

Следующая команда копирует файл в указанный бакет и задает ключ:

```bash
aws s3 cp test.txt s3://mybucket/test2.txt --endpoint-url https://hb.bizmrg.com
```

Для удобства загрузки файлов из локального каталога можно применить синхронизацию объектов, ключи которых будут автоматически созданы после завершения загрузки объектов в указанный бакет.

В случае, если в бакете уже существуют объекты, то синхронизации подлежат файлы:

- Размер которых отличается от размера объекта S3.
- Время последнего изменения локального файла новее, чем время последнего изменения объекта S3.
- Локальный файл не существует в указанном бакете.

```bash
aws s3 sync <локальный_путь> s3://<имя_бакета> --endpoint-url https://hb.bizmrg.com
```

Полное описание операций копирования и перемещения объектов и файлов доступно в [официальной документации S3 CLI](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/s3/index.html#synopsis).
