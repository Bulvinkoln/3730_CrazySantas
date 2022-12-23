## Santa Show @ GIT
тобы сделать это, мы используем команду git remote add command, который добавляет новый remote к репозиторию:

git remote add origin https://github.com/microsindotnet/gitnew
Но эта команда вернула ошибку:

fatal: remote origin already exists.
Этим сообщением git говорит нам, что remote origin уже существует.

Способ решения проблемы. Мы не можем добавить новый remote, используя имя, которое уже используется, даже если мы указываем для remote новый URL. В этом случае мы попытались создать новый remote с именем "origin", когда remote с таким именем уже существует. Чтобы исправить эту ошибку, мы должны удалить существующий remote, который называется "origin", и добавить новый, либо должны поменять URL существующего remote.

Чтобы удалить существующий remote и добавить новый, мы можем установить новый URL для нашего remote:

git remote set-url origin https://github.com/microsindotnet/gitnew
Это предпочтительный метод, потому что мы можем в одной команде поменять URL, связанный с нашим remote. Не понадобится уделить старый origin и создавать новый, потому что существует команда set-url.

Альтернативно мы можем удалить наш remote "origin", и после этого создать новый, с новым URL:

git remote rm origin
git remote add origin https://github.com/microsindotnet/gitnew