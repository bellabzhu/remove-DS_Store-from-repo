# Если надо удалить .DS_Store (или др.мусорные файлы) из репозитория:
1. Удаляем существующие .DS_Store файлы в репозитории: 
```
find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch
```

2. Создаем файл .gitignore в корневой папке, содержимое файла см. ниже. 

3. Делаем коммит:
```
git commit -m '.DS_Store banished!'
```
# Чтобы настроить раз и навсегда
### Глобальное игнорирование заданных файлов из всех репозиций git в вашей системе:
1. Создаем глобальный файл .gitignore, например:
```
vi ~/.gitignore_global
```
2. Добавляем этот файл в свой глобальный git config:
```
git config --global core.excludesfile ~/.gitignore_global
```

# Содержимое файла .gitignore (правила игнорирования):
```
# OS generated files #
######################
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db
.DS_Store
.AppleDouble
.LSOverride
.DocumentRevisions-V100
.fseventsd
.Spotlight-V100
.TemporaryItems
.Trashes
.VolumeIcon.icns
.com.apple.timemachine.donotpresent

# Misc
.vscode
Icon

# Node
dist
node_modules

# Directories potentially created on remote AFP share
.AppleDB
.AppleDesktop
Network Trash Folder
Temporary Items
.apdisk

### macOS Patch ###
# iCloud generated files
*.icloud

# Compiled source #
###################
*.com
*.class
*.dll
*.exe
*.o
*.so

# Packages #
############
# it better to unpack these files and commit the raw source
# git has its own built in compression methods
*.7z
*.dmg
*.gz
*.iso
*.jar
*.rar
*.tar
*.zip

# Logs and databases #
######################
*.log
*.sql
*.sqlite
```
На основе ветки на [StackOverFlow](https://stackoverflow.com/questions/107701/how-can-i-remove-ds-store-files-from-a-git-repository)
