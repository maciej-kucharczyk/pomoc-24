# Pomoc Drogowa 24/7 – Strona Internetowa (GitHub Pages)

Nowoczesna, lekka strona internetowa dla firmy pomocy drogowej, działająca bezpośrednio na **GitHub Pages** (bez serwerów, baz danych i skomplikowanego budowania).

---

## 📁 Struktura Projektu

```text
├── index.html            # Główny plik strony (HTML + Tailwind CSS + Marked.js)
├── config.md             # Główne dane firmy (telefon, adres, email itp.)
├── pages/                # Treści 4 podstron w formacie Markdown (.md)
│   ├── home.md           # Strona główna
│   ├── galeria.md        # Galeria realizacji (opis + lista zdjęć)
│   ├── laweta-wroclaw.md # Podstrona „Laweta Wrocław | Cennik”
│   └── kontakt.md        # Podstrona „Kontakt”
├── images/
│   ├── logo.png          # Główne logo
│   ├── favicon.svg       # Mała ikonka w zakładce przeglądarki
│   ├── pages/            # Obrazki używane w treściach podstron
│   └── gallery/          # Zdjęcia wyświetlane w galerii
└── README.md             # Niniejsza instrukcja
```

---

## 🛠️ Instrukcja Obsługi Dla Osoby Nietechnicznej

Wszystkie treści możesz edytować bezpośrednio na GitHubie (klikając ikonę ołówka ✏️ przy pliku) lub w dowolnym edytorze tekstu (np. Notatnik, VS Code).

### 1. Zmiana Numeru Telefonu, Adresu i Danych Firmy
Otwórz plik `config.md`. Znajdziesz w nim proste linijki w formacie `klucz: wartość`:

```markdown
nazwa_firmy: Pomoc Drogowa 24/7 Wrocław
telefon: 577 408 770
email: kontakt@pomocdrogowa24.wroclaw.pl
adres: ul. Krakowska 100, 50-427 Wrocław
```

* Wpisujesz numer dokładnie tak, jak ma być widoczny dla człowieka (np. `577 408 770`).
* System **sam automatycznie generuje techniczny link do dzwonienia** (`href="tel:+48577408770"`) usuwając spacje i dodając prefiks `+48`. Nie musisz podawać żadnych dodatkowych pól!

---

### 2. Edycja Tekstów na Podstronach
Wejdź do folderu `pages/` i wybierz odpowiedni plik (np. `home.md` lub `kontakt.md`):

* **Nagłówki:** wpisz `# Duży Nagłówek` lub `## Średni Nagłówek`.
* **Pogrubienie:** zaznacz tekst dwiema gwiazdkami: `**ważny tekst**`.
* **Punkty / Lista:** każdą linijkę zacznij od myślnika: `- punkt pierwszy`.
* **Wstawienie zmiennej z konfiguracji:** wpisz np. `{{telefon}}` lub `{{adres}}`.

---

### 3. Zarządzanie Galerią Zdjęć
Kolejność i zawartość galerii ustawiasz w pliku `pages/galeria.md`.

Znajdziesz tam sekcję:
```markdown
[galeria]
1-laweta.svg | Nowoczesna autolaweta z platformą hydrauliczną
2-holowanie.svg | Bezpieczne holowanie samochodu po kolizji
moje-nowe-auto.jpg | Zdjęcie z wczorajszej akcji
[/galeria]
```

* **Dodanie nowego zdjęcia:**
  1. Wgraj plik ze zdjęciem (np. `moje-nowe-auto.jpg`) do folderu `images/gallery/`.
  2. W pliku `pages/galeria.md` dopisz nową linijkę wewnątrz bloku `[galeria]`:
     `moje-nowe-auto.jpg | Mój własny podpis zdjęcia`
* **Zmiana kolejności:** po prostu zamień kolejność linijek miejscami. Pierwsza linijka to pierwsze zdjęcie na stronie!
* **Usunięcie zdjęcia:** skasuj linijkę z pliku `pages/galeria.md`.

---

### 4. Dodawanie Obrazków do Treści Podstron
1. Wgraj plik ze zdjęciem do folderu `images/pages/` (np. `nowa-laweta.jpg`).
2. W pliku danej podstrony (np. `pages/laweta-wroclaw.md`) wstaw kod:
   `![Opis zdjęcia dla niewidomych](nowa-laweta.jpg)`
   *(Nie musisz dopisywać ścieżki do folderu – strona automatycznie wie, że zdjęcie pochodzi z `images/pages/`)*.

---

## 🚀 Jak Opublikować Stronę na GitHub Pages?

1. Zaloguj się na GitHub i przejdź do swojego repozytorium.
2. Wejdź w zakładkę **Settings** (Ustawienia) ➔ z lewego menu wybierz **Pages**.
3. W sekcji **Build and deployment**:
   * **Source:** wybierz `Deploy from a branch`
   * **Branch:** wybierz gałąź `main` (lub `master`) oraz katalog `/ (root)`
   * Kliknij **Save**.
4. Po około 1 minucie Twoja strona będzie dostępna pod adresem:  
   `https://twoj-login.github.io/nazwa-repozytorium/`

---

## 💻 Testowanie Lokalne na Komputerze

Przeglądarki internetowe ze względów bezpieczeństwa blokują wczytywanie plików przez `fetch()` przy otwieraniu pliku bezpośrednio z dysku (`file:///`).

Aby uruchomić szybki serwer developerski:

### Metoda 1: Za pomocą npm (rekomendowana)
1. W folderze projektu uruchom:
   ```bash
   npm start
   ```
2. Otwórz w przeglądarce adres: **`http://localhost:3000`**

*(Możesz też użyć polecenia `npm run dev`).*

### Metoda 2: Za pomocą Pythona (bez instalacji npm)
```bash
python3 -m http.server 8000
```
Następnie wejdź pod adres: `http://localhost:8000`
