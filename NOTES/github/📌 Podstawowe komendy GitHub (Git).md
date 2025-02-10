Created: 2025-02-10 16:02

--- 
Note: 
## 🔹 **Podstawowa praca z plikami**
```shell
# Sprawdzenie statusu repozytorium
git status
# Dodanie pliku do śledzenia
git add nazwa_pliku
# Dodanie wszystkich plików do śledzenia
git add .
# Zapisanie zmian w repozytorium
git commit -m "Opis zmian"
```

## 🔹 **Praca z gałęziami (branching)**
```shell
# Wyświetlenie listy gałęzi
git branch
# Tworzenie nowej gałęzi
git branch nowa-galaz
# Przełączanie się na inną gałąź
git checkout nowa-galaz
# Tworzenie i przełączanie się na nową gałąź
git checkout -b nowa-galaz
```

## 🔹 **Praca z GitHubem (Remote Repositories)**
```shell
# Powiązanie repozytorium lokalnego z GitHub
git remote add origin https://github.com/user/repository.git
# Wysłanie zmian do GitHuba
git push -u origin main
# Pobranie zmian z GitHuba
git pull origin main
```

## 🔹 **Przydatne operacje**
```shell
# Wyświetlenie historii commitów
git log --oneline --graph --decorate --all
# Resetowanie zmian w pliku
git checkout -- nazwa_pliku
# Cofnięcie ostatniego commita (z zachowaniem zmian w plikach)
git reset --soft HEAD~1
# Usunięcie zmian w lokalnym repozytorium
git reset --hard HEAD
```

## 🔹 **Usuwanie i czyszczenie**
```shell
# Usunięcie pliku z repozytorium
git rm nazwa_pliku
# Usunięcie gałęzi lokalnie
git branch -d nazwa-galezi
# Usunięcie gałęzi zdalnie
git push origin --delete nazwa-galezi
```
--- 
Metadata: 

Status: #pending 
Tags: #git #github #commands 