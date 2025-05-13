# IPython, Jupyter notebook, Numpy

## Czym jest IPython?
IPython (Interactive Python) to interaktywne środowisko pracy dla języka Python. Umożliwia szybkie testowanie kodu, obsługę komend systemowych i zaawansowaną pracę z Pythonem. Popularny wśród naukowców i programistów dzięki swojej elastyczności i funkcjom interaktywnego testowania.

## Czym jest Jupyter Notebook?
Jupyter Notebook to aplikacja webowa, która umożliwia tworzenie interaktywnych dokumentów. Dokumenty mogą zawierać kod źródłowy (Python), tekst, wykresy, obrazy i inne multimedia. Początkowo część projektu IPython, ale rozwinięty jako osobny projekt wspierający wiele języków programowania (Julia, R, Python).

### Instalacja i uruchamianie

#### Instalacja
Upewnij się, że masz zainstalowanego Pythona (https://www.python.org/). 
Otwórz terminal i wykonaj polecenie:
```bash
pip install ipython jupyter notebook numpy
```
#### Uruchamianie Jupyter Notebook
W terminalu wykonaj polecenie:
```bash
jupyter notebook
```
Automatycznie otworzy się przeglądarka internetowa z interfejsem Jupyter Notebook.

### Interfejs Jupyter Notebook
#### Główne elementy:
| Elementy       | Opis          |
| ------------- |:-------------|
|![obraz](https://github.com/user-attachments/assets/fca5cd2d-eda0-4d0e-9ab1-5bde5c5d84e4)   <br> ![obraz](https://github.com/user-attachments/assets/e81535a5-3377-43cf-9530-32d3a0097492)|1. Pasek menu: Na górze strony, zawiera opcje do zarządzania notebookiem (Plik, Edytuj, Widok).<br> 2. Pasek narzędzi: Szybki dostęp do najczęściej używanych funkcji (uruchamianie komórek, dodawanie komórek, zapisywanie).<br> 3. Komórki: Miejsce, w którym piszesz kod lub tekst.<br> 4. Tryby pracy:<br>   a) Tryb poleceń: (niebieska ramka) - pozwala na zarządzanie komórkami.<br>   b) Tryb edycji: (zielopomarańczowa ramka) - pozwala pisać kod lub tekst w komórce. |

### Przykładowe operacje w Jupyter Notebook

1. Pasek menu: Na górze strony, zawiera opcje do zarządzania notebookiem (Plik, Edytuj, Widok).
2. Pasek narzędzi: Szybki dostęp do najczęściej używanych funkcji (uruchamianie komórek, dodawanie komórek, zapisywanie).
3. Komórki: Miejsce, w którym piszesz kod lub tekst.
4. Tryby pracy:
  a) Tryb poleceń: (niebieska ramka) - pozwala na zarządzanie komórkami.
  b) Tryb edycji: (zielopomarańczowa ramka) - pozwala pisać kod lub tekst w komórce.

#### Prosty kod Python:
```python
print("Witaj w Jupyter Notebook!")
```
#### Obliczenia matematyczne:
```python
x = 10
y = 5
suma = x + y
print("Suma:", suma)
```
#### Używanie Markdown (komórka tekstowa):
```markdown
# Nagłówek H1
## Nagłówek H2
### Nagłówek H3

**Pogrubiony tekst**

*Pochylony tekst*

- Punkt listy
- Drugi punkt listy

[Link do Google](https://www.google.com)
```
