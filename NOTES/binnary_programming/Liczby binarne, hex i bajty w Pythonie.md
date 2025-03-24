Created: 2025-03-24 23:15

--- 
Note: 
## 🔢 Systemy liczbowe: binarny i szesnastkowy (hex)

### 🔹 System binarny (dwójkowy)

System binarny używa tylko dwóch cyfr: `0` i `1`. Każda kolejna cyfra (bit) reprezentuje potęgę liczby 2.

|Bit|Wartość dziesiętna|
|---|---|
|2⁷|128|
|2⁶|64|
|2⁵|32|
|2⁴|16|
|2³|8|
|2²|4|
|2¹|2|
|2⁰|1|

👉 Liczba `213` w systemie binarnym:

```
213 -> 11010101
     -> 128 + 64 + 16 + 4 + 1 = 213
```

### 🔹 System szesnastkowy (heksadecymalny)

System hex używa 16 cyfr:

```
0 1 2 3 4 5 6 7 8 9 A B C D E F
```

Gdzie `A = 10`, `B = 11`, ..., `F = 15`

👉 Jak przeliczyć liczbę dziesiętną na hex?

1. Dziel przez 16 i zapisz resztę.
    
2. Powtarzaj aż licznik będzie 0.
    
3. Zapisz reszty od końca.
    

### Przykład: 213 na hex

```
213 ÷ 16 = 13 reszta 5
13 = D
→ D5
```

👉 Przykład: 3454 na hex

```
3454 ÷ 16 = 215 reszta 14 (E)
215 ÷ 16 = 13 reszta 7
13 = D
→ D7E
```

---

## 🧠 Bajty i bity

- **1 bajt = 8 bitów**
    
- **1 hex = 4 bity**
    
- Hex `D5` = binarnie `1101 0101` = 213
    

### Sposób odczytu hex jako bajtów:

- `0xA9` → `10101001`
    
- `0xD7` → `11010111`
    
- `0xFF` → `11111111`
    

Każda cyfra hex odpowiada 4 bitom:

|   |   |
|---|---|
|Hex|Bin|
|0|0000|
|1|0001|
|2|0010|
|3|0011|
|4|0100|
|5|0101|
|6|0110|
|7|0111|
|8|1000|
|9|1001|
|A|1010|
|B|1011|
|C|1100|
|D|1101|
|E|1110|
|F|1111|

---

## ✍️ Przeliczanie liczb na bity

Aby przeliczyć liczbę na bity:

1. Dziel przez 2.
    
2. Zapisuj reszty.
    
3. Czytaj reszty od końca.
    

**Przykład: 13 → bin**

```
13 ÷ 2 = 6 reszta 1
6 ÷ 2 = 3 reszta 0
3 ÷ 2 = 1 reszta 1
1 ÷ 2 = 0 reszta 1
→ 1101
```

**Przykład: 175 → bin**

```
175 ÷ 2 = 87 reszta 1
87 ÷ 2 = 43 reszta 1
43 ÷ 2 = 21 reszta 1
21 ÷ 2 = 10 reszta 1
10 ÷ 2 = 5 reszta 0
5 ÷ 2 = 2 reszta 1
2 ÷ 2 = 1 reszta 0
1 ÷ 2 = 0 reszta 1
→ 10101111
```

---

## ✅ Podsumowanie

- System binarny = 0 i 1, każda cyfra = potęga 2.
    
- Hex = system szesnastkowy, 1 hex = 4 bity.
    
- 1 bajt = 8 bitów = 2 cyfry hex.
    
- Python: `hex(x)` i `bin(x)` przelicza liczbę na odpowiedni zapis.
    

Przydatne funkcje:

```
hex(213)  # '0xd5'
bin(213)  # '0b11010101'
int('d5', 16)  # 213
int('11010101', 2)  # 213
```
--- 
Metadata: 

Status: #pending 
Tags: #python, #bity, #hex, #binarny, #bajty