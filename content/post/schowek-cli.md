---
title: "schowek() – prosty schowek do kopiowania z terminala"
date: 2026-01-05
draft: false
author: "Ulvhedin"
tags:
  - linux
  - bash
  - alias
  - cli
  - produktywność
categories:
  - tools
---

Praca w terminalu bardzo często kończy się potrzebą skopiowania wyniku polecenia do schowka systemowego.  
Ręczne zaznaczanie tekstu myszką nie zawsze jest wygodne, szczególnie podczas pracy na serwerach lub w tiling window managerach.

Poniżej pokażę **prosty i bardzo użyteczny skrót**, który pozwala kopiować dane do schowka bezpośrednio z terminala.

---

## Funkcja `schowek()`

```bash
schowek() {
  xclip -sel clip
}
```
Ta funkcja:

- czyta dane ze standardowego wejścia (STDIN)
- zapisuje je bezpośrednio do schowka systemowego (clipboard)

Dzięki temu możesz kopiować wynik dowolnego polecenia jednym pipe’em.

## Wymagania

Funkcja korzysta z narzędzia `xclip`, które musi być zainstalowane w systemie.

### Instalacja `xclip`

**Debian / Ubuntu**
```bash
sudo apt install xclip
```

**Archlinux**
```
sudo pacman -S xclip
```
### Jak używać?
- Kopiowanie wyniku polecenia
  ```bash
    ls -la | schowek
  ```
- Kopiowanie zawartości pliku
  ```bash
  cat /etc/hosts | schowek
  ```
{{< author >}}

