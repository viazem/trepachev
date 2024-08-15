### SSH

```
git@github.com:viazem/trepachev.git
```

create a new repository on the command line

```
echo "# trepachev" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:viazem/trepachev.git
git push -u origin main
```

push an existing repository from the command line

```
git remote add origin git@github.com:viazem/trepachev.git
git branch -M main
git push -u origin main
```


### HTTPS

```
https://github.com/viazem/trepachev.git
```

create a new repository on the command line

```
echo "# trepachev" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/viazem/trepachev.git
git push -u origin main
```

push an existing repository from the command line

```
git remote add origin https://github.com/viazem/trepachev.git
git branch -M main
git push -u origin main
```

### Настройка локального репозитория

```
git config user.name ...

git config user.email ...
```

### Создание ключей

<https://habr.com/ru/companies/yandex_praktikum/articles/700708/>

```
ssh-keygen

cat ~/.ssh/id_rsa.pub

ssh-rsa AAA...KPs= user@email
```

Скопируйте ключ от символов ssh-rsa и до конца файла и вставьте его в ваш аккаунт на GitHub.

Profilr - Settings - SSH and GPG keys