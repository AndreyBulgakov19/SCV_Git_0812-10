# Работа с удаленным репозиторием
1. Создать аккаунт на GitHub
2. Создать локальный репозиторий
3. Связать локальный и удаленный репозиторий
Adding your SSH key to the ssh-agent
1. Ensure the ssh-agent is running. 
# start the ssh-agent in the background
$ eval "$(ssh-agent -s)" сама команда
> Agent pid 59566
2. Add your SSH private key to the ssh-agent. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_ed25519 in the command with the name of your private key file.
3. Add the SSH key to your account on GitHub. For more information, see "Adding a new SSH key to your GitHub account."


## Generating a new SSH key for a hardware security key  Наш случай
If you are using macOS or Linux, you may need to update your SSH client or install a new SSH client prior to generating a new SSH key. For more information, see "Error: Unknown key type."

Insert your hardware security key into your computer.

Open Git Bash.

Paste the text below, substituting in the email address for your account on GitHub.

1. `ssh-keygen -t ed25519-sk -C "YOUR_EMAIL"` создаём новый ssh key
Note: If the command fails and you receive the error invalid format or feature not supported, you may be using a hardware security key that does not support the Ed25519 algorithm. Enter the following command instead.

 `ssh-keygen -t ecdsa-sk -C "your_email@example.com"`
When you are prompted, touch the button on your hardware security key.

When you are prompted to "Enter a file in which to save the key," press Enter to accept the default file location.

2. > Enter a file in which to save the key (/c/Users/YOU/.ssh/id_ed25519_sk):[Press enter]
When you are prompted to type a passphrase, press Enter. ЭТО ПАПКА ПО УМОЧАНИЮ НА ВИНДЕ

> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
Add the SSH key to your account on GitHub. For more information, see "Adding a new SSH key to your GitHub account."
Copy the SSH public key to your clipboard.

If your SSH public key file has a different name than the example code, modify the filename to match your current setup. When copying your key, don't add any newlines or whitespace.

Copy the SSH public key to your clipboard.

If your SSH public key file has a different name than the example code, modify the filename to match your current setup. When copying your key, don't add any newlines or whitespace.
3. $ clip < ~/.ssh/id_ed25519.pub
  # Copies the contents of the id_ed25519.pub file to your clipboard
Tip: If clip isn't working, you can locate the hidden .ssh folder, open the file in your favorite text editor, and copy it to your clipboard.

4. копирум ключ на гитхабе

## Добавить удаленный репозиторий к проекту:    
git remote add <repository name> <url -addreess of repository> repository name - обычно origin
Пример: git remote add origin git@github.com:texnoman1/remote.git
git branch -M main переключаемся на ветку main, тк эта ветка по умолчанию на github
git push -u origin main собственно заливаем на гитхаб.


Доступ по логину - паролю отменили на гитхабе с 2021 года, если он выдает эту ошибку и не входит -делаем следующее:
https://www.youtube.com/watch?v=Bxxh8Jne-QM - Git с нуля.7: GitHub авторизация по ключу

git remote -v смотрим  origin 
если авторизация идет через http:s// (http:s//git@github.com:texnoman1/remote.gitgit)
удаляем на origin командой: 
git remote remove origin  или git remote rm origin
добавляем новый:
git remote add origin ******

## Скопировать удаленный репозиторий на локальный комп
git pull  если репозиторий наш 
git clone <URL- репозитория>, если чужой

## Скопировать локальный репозиторий на GitHub
branch -M main
git push  origin main

## ВИЛКА
1. переходим в чужой репозиторий: https://github.com/AndreyBulgakov19/SCV_Git_0812-10.git.
2. в правом верхнем жмем Fork
3. Жмем зеленую кнопку Create fork. Это создает в нашем аккаунте новый репозиторий SCV_Git_0812-10
4. Жмем зелёную кнопку Code  и копируем ссылку git@github.com:texnoman1/SCV_Git_0812-10.git в буфер обмена (при копировании ссылки выбирам SSH !!!!!!!!!!!!!!)
5. создаем новую папку, создаем в ней репозиторий git init, и копируем в нее репозиторий с ГитХаба `git pull https://github.com/AndreyBulgakov19/SCV_Git_0812-10.git`










