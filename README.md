# IPython, Jupyter notebook, NumPy

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
## NumPy
NumPy (Numerical Python) to biblioteka Pythona umożliwiająca pracę z tablicami wielowymiarowymi i wykonywanie zaawansowanych operacji matematycznych. Szybka i wydajna, dzięki implementacji w C.
Tablice NumPy są podobne do list Pythona, główną ich zaletą jest to, że są szybsze i wydajniejsze w operacjach matematycznych i logicznych. Pierwszą i najistotniejszą kwestią jest zaimportowanie NumPy za pomocą następującego kodu. 
```python 
import numpy as np
```

### Tablica w NumPy
#### Podstawowa tablica
Tablica `ndarray` jest główną strukturą danych w pakiecie NumPy, której dokładna nazwa to n-wymiarowa tablica. Wszystkie jej elementy muszą być tego samego typu, indeksowane przez typ `tuple` lub nieujemne liczby całkowite. Każdy element takiej tablicy nosi nazwę `dtype`.
```python
arr = np.array([1, 2, 3]) # tworzy 1-wymiarowa tablice
print(type(arr)) # drukuje <class 'numpy.ndarray'>
print(arr.shape) # drukuje (3,) - zwraca wymiary tablicy
print(arr.size) # drukuje 3 - zwraca ilość elementów tablicy
arr2 = np.array([[1, 2, 3],
[4, 5, 6],
[7, 8, 9]]) # tworzy 2-wymiarowa tablice 3x3
print(type(arr2)) # drukuje <class 'numpy.ndarray'>
print(arr2.shape) # drukuje (3, 3)
print(arr2.size) # drukuje 9
```
Częsty błąd polega na wywoływaniu tablicy z wieloma argumentami, zamiast podawania pojedynczego ciągu jako argumentu.
```python
a = np.array(1, 2, 3, 4) # ŹLE
Traceback (most recent call last):
...
TypeError: array() takes from 1 to 2 positional arguments but 4 were given
a = np.array([1, 2, 3, 4]) # POPRAWNIE
```
#### Tablice specjalne
W pracy z wektorami lub macierzami przydadzą się nam funkcje, które pozwalają na wstępną inicjalizację tablicy zerami, jedynkami i innymi liczbami. Kilka przykładów metod pozwalających na takie operacje:
```python
shape = (3, 3)
a = np.zeros(shape) # tworzy tablice składającą się z samych zer
a = np.ones(shape) # tworzy tablice składającą się z samych jedynek
a = np.eye(shape[0]) # tworzy tablice w postaci macierzy jednostkowej
# należy podać tylko jedna liczbę jako parametr
a = np.empty(shape) # tworzy tablice składająca się z losowych wartości
# zależnie od pamięci komputera (szybsza od np.zeros())
a = np.random.random(shape) # tworzy tablice wartości losowych na przedziale [0, 1]
# należy podać tylko jedna liczbę jako parametr
const_value = 10
a = np.full(shape, const_value) # tworzy tablice o stałej zadanej wartości
# nalezy podac tylko jedna liczbe jako parametr
```
#### Tablice z wartościami w zadanym przedziale
Warto znać dwie metody: `np.arange` oraz `np.linspace`, które są często wykorzystywane podczas generowania zmiennych w zadanym przedziale.
```python
# tworzy tablice równomiernie rozmieszczonych wartości w przedziale
# z krokiem równym step
a = np.arange(start=0, stop=100, step=11)
print(a) # drukuje [0 11 22 33 44 55 66 77 88 99]
# tworzy tablice równomiernie rozmieszczonych num elementów w przedziale
a = np.linspace(start=0, stop=100, num=11)
print(a) # drukuje [0. 10. 20. 30. 40. 50. 60. 70. 80. 90. 100.]
```
#### Indeksowanie i wycinanie tablic
Generalnie NumPy pozwala na bardzo dużo sposobów indeksowania i wycinania elementów w tablicach.
```python
a = np.array([[1, 2, 3],
[4, 5, 6],
[7, 8, 9]])
b = a[0, 2] # [numer wiersza, numer kolumny]
print(b) # drukuje 3
# [od początku do wiersza 2, od kolumny 1 do końca]
c = a[:2, 1:] # [wiersze 0 i 1, kolumny 1 i 2]
print(c) # drukuje [[2 3]
# [5 6]] drukuje 123
b = 123
print(a[0, 2]) # drukuje 3
c[0, 1] = 123
print(a[0, 2]) # drukuje 123
# weź wszystko z kolumny pierwszej
print(a[:, 1]) # drukuje [2 5 8]
# weź wszystko z wiersza pierwszego
print(a[1, :]) # drukuje [4 5 6]
```
> Żeby zrozumieć, dlaczego `a[0, 2]` wyświetla `123` należy wiedzieć, że wycinanie to operacja „wglądu” do oryginalnej tablicy. Jak w C++ mamy referencję, tak tutaj mamy wgląd do oryginału i modyfikujemy zawartość głównej tablicy.

Kolejną ciekawą możliwością jest indeksowanie przy pomocy innych tablic.
```python
a = np.array([[1, 2, 3],
[4, 5, 6],
[7, 8, 9]])
b = [0, 0, 1]
c = np.arange(3) # tablica [0, 1, 2]
# na wierszach tablicy operuje b, na kolumnach c
# pierwszy element b to 0, pierwszy element c to 0, wiec jest a[0, 0] to 1
# drugi element b to 0, drugi element c to 1, wiec a[0, 1] to 2
# trzeci element b to 1, trzeci element c to 2, wiec a[1, 2] to 6
print(a[b, c]) # drukuje [1 2 6]
# spróbuj opanować skąd bierze się taki wyniki
print(a[c, b]) # drukuje [1 4 8]
```
> Należy pamiętać, że nowej zmiennej tablicowej na podstawie już istniejącej tablicy nie odbywa się przez operator `=` lecz za pomocą metody `copy()`
```python
a = np.array([[ 0, 1, 2, 3],
[ 4, 5, 6, 7],
[ 8, 9, 10, 11]])
b = a # nowy obiekt nie jest tworzony mamy tutaj tylko przypisanie do
nazwy b
# referencji do pamięci, gdzie znajduje się tablica
print(b is a) # a i b to dwie nazwy dla tego samego obiektu ndarray
d = a.copy() # zostanie utworzony nowy obiekt tablicowy z nowymi danymi
print(d is a)
```
Można też korzystać z zapisów warunkowych, żeby sprawdzić, gdzie jest spełniony dany warunek w tablicy.
```python
a = np.array([[1, 2, 3],
[4, 5, 6],
[7, 8, 9]])
# zwróci wartość True dla każdego elementu tablicy a większego od 5
b = (a > 5)
print(b) # drukuje [[False False False]
# [False False True]
# [True True True]]
print(a[b]) # drukuje [6 7 8 9]
print(a[a > 5]) # drukuje [6 7 8 9]
```
Gdy chcemy więcej niż jeden warunek przydatna będzie funkcja, która pozwala na takie operacje – `np.logical_and()`:
```python
a = np.array([[1, 2, 3],
[4, 5, 6],
[7, 8, 9]])
b = (a > 5)
c = (a <= 8)
print(a[np.logical_and(b, c)])
```
Gdy pracujemy w uczeniu maszynowym może się przydać dodanie kolumny bądź wiersza jedynek:
```python
a = np.array([[1, 2, 3],
[4, 5, 6],
[7, 8, 9]])
b = np.ones(3)
b = b[np.newaxis, :]
print(b, '\n')
new_row = np.concatenate((a, b), axis=0) # dodanie b jako wiersz
new_column = np.concatenate((a, b.T), axis=1) # dodanie b jako kolumna
print(new_row, '\n') # [[1. 2. 3.]
# [4. 5. 6.]
# [7. 8. 9.]
# [1. 1. 1.]]
print(new_column, '\n') # [[1. 2. 3. 1.]
# [4. 5. 6. 1.]
# [7. 8. 9. 1.]]
```
Początkowo dodajemy nowy wymiar do wektora jedynek, jest to operacja wymagana. Następnie wykonujemy konkatenację dwóch tablic, czyli ich dodanie. W pierwszym przypadku dodajemy tablice jedynek jako nowy wiersz, w kolejnym przypadku jako kolumnę. Należy pamiętać o transpozycji. Możemy to zrobić na 2 sposoby: `<nazwa tablicy>.T` lub `np.transpose(<nazwa tablicy>)`.
#### Typy danych w NumPy
Typów danych jest dużo. Poniżej pokazane zostały dwa podstawowe, z nimi będziemy pracować zdecydowanie najczęściej.
```python
x = np.array([1, 2])
print(x.dtype) # wyświetla "int32"
x = np.array([1.0, 2.0])
print(x.dtype) # wyświetla "float64"
x = np.array([1, 2], dtype=np.int64) # przekonwertuj do danego typu
print(x.dtype) # wyświetla "int64"
```
#### Operacje arytmetyczne
Mamy dostęp do wszystkich operacji arytmetycznych. 
```python
x = np.array([[1, 2], [3, 4]], dtype=np.float64)
y = np.array([[5, 6], [7, 8]], dtype=np.float64)
# Dodawanie elementów każdego z osobna
# [[ 6.0 8.0]
# [10.0 12.0]]
print(x + y)
print(np.add(x, y))
# Odejmowanie elementów każdego z osobna
# [[-4.0 -4.0]
# [-4.0 -4.0]]
print(x - y)
print(np.subtract(x, y))
# Mnożenie elementów każdego z osobna
# [[ 5.0 12.0]
# [21.0 32.0]]
print(x * y)
print(np.multiply(x, y))
# Dzielenie elementów każdego z osobna
# [[ 0.2 0.33333333]
# [ 0.42857143 0.5 ]]
print(x / y)
print(np.divide(x, y))
# Pierwiastek każdego z elementów
# [[ 1. 1.41421356]
# [ 1.73205081 2. ]]
print(np.sqrt(x))
```
`*` to iloczyn każdego elementu z osobna, na obliczenie iloczynu macierzy lub iloczynu skalarnego pozwala funkcja `np.dot()`, którą możemy wykorzystywać jako funkcję biblioteki jak i funkcję instancji obiektu:
```python
x = np.array([[1, 2],[3, 4]])
y = np.array([[5, 6],[7, 8]])
v = np.array([9, 10])
u = np.array([11, 12])
# Iloczyn skalarny wektorów, 219 jest wynikiem
print(v.dot(u))
print(np.dot(v, u))
# Mnożenie macierzy, wynikiem jest [[19 22]
# [43 50]]
print(x.dot(y))
print(np.dot(x, y))
```
#### Rozmiary tablic
Ważnym zagadnieniem są długość, szerokość czy ilość wymiarów tablic w NumPy. Przy zaawansowanych obliczeniach musimy pamiętać, że tablice w Pythonie iterują się od 0.
```python
arr = np.array([[1, 2, 3],
[4, 5, 6],
[7, 8, 9]])
print('arr.ndim:', arr.ndim) # 2 - ilość wymiarow
print('arr.size:', arr.size) # 9 - ilość elementow
print('arr.shape:', arr.shape) # (3, 3) - (ilość wierszy, ilość kolumn)
```

## Zadania do wykonania
1. Wypróbuj kod z listingów znajdujących się w instrukcji i sprawdź ich działanie.
2. Stwórz macierz jednowymiarową wypełnią dowolnymi wartościami i naj jej podstawie wypisz macierz transponowaną.
3. Utwórz macierz np. [[1, 2, 3]
                      [4, 5, 6]
                      [7, 8, 9]
                      [1, 1, 10]]
i wybierz z niej wartości, które są większe od 8 i mniejsze od 2.
4. Dla (dowolnego rozmiaru większego niż 1) tablicy kwadratowej `A` stworzyć tablicę jednowymiarową, której `k`-ty element to suma elementów `k`-tej kolumny tablicy `A` leżących poniżej głównej przekątnej.
5. Napisz funkcję `zastap_zera(A, x)`, która zwraca tablicę utworzoną z tablicy `A` (o dowolnym kształcie) poprzez zastąpienie wszystkich elementów równych zero liczbą `x`. Sama tablica `A` powinna pozostać niezmieniona.

> Zadania od 2-5 umieść na repozytorium
