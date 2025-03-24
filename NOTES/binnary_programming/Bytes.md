Note:
## 1. Co to są bajty (`bytes`) w Pythonie?

Bajty to sekwencja liczb całkowitych od 0 do 255. W Pythonie reprezentują dane binarne. Często używane są do pracy z plikami, siecią i niskopoziomową manipulacją danymi.

```python
b = bytes([65, 66, 67])
print(b)  # b'ABC'
```

## 2. Różnica między `bytes` i `bytearray`

| Typ        | Mutowalność | Przykład              |
|------------|-------------|------------------------|
| `bytes`    | Nie         | `b = bytes([1, 2, 3])` |
| `bytearray`| Tak         | `b = bytearray([1,2])` |

## 3. Operatory bitowe (bitwise operators)

W Pythonie operatory bitowe działają na poziomie bitów (0 i 1) i są używane głównie do operacji niskopoziomowych.

| Operator | Nazwa        | Opis                                                           | Przykład (`a=0b1010`, `b=0b1100`) |
|----------|--------------|----------------------------------------------------------------|----------------------------------|
| `&`      | AND          | Bity ustawione w obu operandach                                | `a & b` → `0b1000`               |
| `|`      | OR           | Bity ustawione w przynajmniej jednym operancie                 | `a | b` → `0b1110`               |
| `^`      | XOR          | Bity ustawione tylko w jednym z operandów                      | `a ^ b` → `0b0110`               |
| `~`      | NOT          | Neguje każdy bit (jedynki na zera i odwrotnie)                 | `~a` → `0b...0101`               |
| `<<`     | przesunięcie w lewo | Przesuwa bity w lewo o podaną liczbę miejsc         | `a << 1` → `0b10100`             |
| `>>`     | przesunięcie w prawo| Przesuwa bity w prawo o podaną liczbę miejsc        | `a >> 1` → `0b0101`              |

## 4. Przykład użycia operatorów bitowych

```python
a = 0b1010  # 10
b = 0b1100  # 12

print(bin(a & b))  # 0b1000
print(bin(a | b))  # 0b1110
print(bin(a ^ b))  # 0b110
print(bin(~a))     # -0b1011 (komplement bitowy)
print(bin(a << 2)) # 0b101000
print(bin(b >> 2)) # 0b11
```

## 5. Do czego można ich używać?

- Operacje na flagach (np. system uprawnień)
- Kompresja danych
- Kryptografia
- Szybkie operacje matematyczne

## 6. Podsumowanie

Bajty i operatory bitowe są podstawowymi narzędziami do pracy z niskopoziomową reprezentacją danych. Zrozumienie ich działania jest kluczowe przy pisaniu efektywnego kodu operującego na surowych danych.

---

Metadata:

Status: #pending  
Tags: #python #bytes #bitwise #binary
