# Day 1 Lab — Working with Filesystem and nano

Practical tasks for basic Linux commands and file management.  
Задачи для практики базовых команд Linux и управления файлами.

---

## 1. Creating directory structure / Создание структуры каталогов

Create a folder `projects` with three subfolders: `scripts`, `configs`, `logs`.  
Создай папку `projects` с тремя подпапками: `scripts`, `configs`, `logs`.

```bash
mkdir -p ~/projects/{scripts,configs,logs}
cd projects
ls -ls
```

**Explanation / Пояснение:**  
- `mkdir` — create directory / создать директорию.  
- `-p` — create parent directories as needed / создать недостающие родительские папки.  
- `~` — home directory / домашняя директория.  
- `{scripts,configs,logs}` — brace expansion in bash / расширение фигурных скобок в bash.

---

## 2. Working with files / Работа с файлами

Create two empty files in `configs` and add text to `startup.log`.  
Создай два пустых файла в `configs` и добавь текст в `startup.log`.

```bash
touch ~/projects/configs/{nginx.conf,ssh_config}
echo "Hello DevOps" > ~/projects/logs/startup.log
cat ~/projects/logs/startup.log
```

**Explanation / Пояснение:**  
- `touch` — create empty file or update timestamp / создать пустой файл или обновить дату изменения.  
- `echo` — print text / вывести текст.  
- `>` — redirect output (overwrite) / перенаправление вывода (перезапись).  
- `cat` — print file content / вывести содержимое файла.

---

## 3. Copying and backups / Копирование и резервное копирование

Make a copy of `startup.log`.  
Сделай копию `startup.log`.

```bash
cp ~/projects/logs/startup.log ~/projects/logs/startup.log.bak
```

**Explanation / Пояснение:**  
- `cp` — copy file or directory / копировать файл или каталог.  
- First argument — source file / исходный файл.  
- Second argument — destination / место назначения.

---

## 4. Searching files / Поиск файлов

Find all `.conf` files in `projects`.  
Найди все `.conf` файлы в `projects`.

```bash
find ~/projects -name "*.conf"
```

**Explanation / Пояснение:**  
- `find` — search for files/directories / искать файлы и каталоги.  
- `-name "*.conf"` — match files ending with `.conf` / искать файлы с расширением `.conf`.

---

## 5. Permissions / Права доступа

Give the file owner read/write permissions only for `ssh_config`.  
Дай владельцу файла права на чтение и запись для `ssh_config`.

```bash
chmod 600 ~/projects/configs/ssh_config
ls -l ~/projects/configs/ssh_config
```

**Explanation / Пояснение:**  
- `chmod` — change permissions / изменить права доступа.  
- `600` — rw------- (read/write for owner only) / rw------- (чтение и запись только для владельца).  
