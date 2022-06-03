# gitignore-settings
1. Удаляем существующие .DS_Store файлы в репозитории: 
```
find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch
```

2. Создаем файл .gitignore в корневой папке, содержимое файла копируем [отсюда](https://github.com/bellabzhu/gitignore-settings/blob/main/.gitignore) 

3. Делаем коммит:
```
git commit -m '.DS_Store banished!'
```
