Если не вдаваться глубоко в описание файловых систем:

[Ссылка на краткую статью на сайте Microsoft] (http://windows.microsoft.com/ru-ru/windows-vista/comparing-ntfs-and-fat-file-systems)

#### Сравнение файловых систем NTFS и FAT в контексте Windows Vista
Применимо к Windows Vista
Файловая система — это основная структура, используемая компьютером для упорядочения информации на жестком диске. При установке нового жесткого диска его необходимо разбить на разделы и отформатировать под определенную файловую систему, после чего на нем можно хранить данные и программы. В Windows существует три возможных варианта файловой системы: NTFS, FAT32 и редко используемая устаревшая система FAT (также известная как FAT16).

#### NTFS

NTFS является предпочтительной файловой системой для этой версии Windows. Она имеет множество преимуществ перед более ранней системой FAT32; ниже перечислены некоторые из них.

Способность автоматически восстанавливаться после некоторых ошибок диска (FAT32 не обладает такой способностью).

Улучшенная поддержка больших жестких дисков.

Более высокая степень безопасности. Возможно использование разрешений и шифрования для запрета пользовательского доступа к определенным файлам.

#### FAT32

Файловая система FAT32 и редко применяемая система FAT использовались в предыдущих версиях Windows, в том числе в Windows 95, Windows 98 и Windows Millenium Edition. Файловая система FAT32 не обеспечивает уровня безопасности, предоставляемого NTFS, поэтому если на компьютере имеется раздел или том, отформатированный под FAT32, файлы на этом разделе видны любому пользователю, имеющему доступ к компьютеру. Файловая система FAT32 также имеет ограничения по размеру файлов. В этой версии Windows невозможно создать раздел FAT32 размером более 32Гб. Кроме того, раздел FAT32 не может содержать файл размером более 4Гб.

---

#### EXT4

Стандартная файловая система для многих Linux дистрибутивов

[Ссылка на Wikipedia] (https://ru.wikipedia.org/wiki/Ext4)

##### Основные изменения по сравнению с ext3:

* увеличение максимального объёма одного раздела диска до 1 эксбибайта (260 байт) при размере блока 4 кибибайт;
* увеличение размера одного файла до 16 тебибайт (240 байт);
* введение механизма пространственной (extent) записи файлов, уменьшающего фрагментацию и повышающего производительность. Суть механизма заключается в том, что новая информация добавляется в конец области диска, выделенной заранее по соседству с областью, занятой содержимым файла.