Источник: http://www.rhd.ru/docs/manuals/enterprise/RHEL-AS-2.1-Manual/getting-started-guide/s1-zip-tar.html

### GZIP

Архивация

```
gzip filename.ext
```

Разархивация (оригинальный архив удаляется)

```
gunzip archive.gz
```

### ZIP

Архивация

```
zip -r filename.zip file1 file2 somedir
```

Разархивация

```
unzip filename.zip
```


### TAR

Архивирование в один файл, без сжатия

```
tar -cvf somearchive.tar somedir
```

Просмотр

```
tar -tvf foo.tar
```

Разархивирование

```
tar -xvf somearchive.tar
```

Архивирование TAR+GUNZIP со сжатием

```
tar -czvf somearchive.tar.gz somedir
```