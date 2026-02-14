# web_codingForche

School Notebook fuer JavaScript, JSON, Python (Indent-Subset) und Python Schueler (Brace-Subset).

## Schnellstart

1. `index.html` im Browser oeffnen.
2. Zellen anlegen, Sprache waehlen, Code schreiben.
3. `Run` pro Zelle oder `Run All` ausfuehren.
4. Notebook als JSON speichern/laden.

## Sprachen und Modus

- `JavaScript`: laeuft direkt im Browser.
- `JSON (Daten)`: wird nicht ausgefuehrt, nur gespeichert/geladen.
- `Python (Indent, Subset)`: Python-Subset mit Einrueckung.
- `Python Schueler ({ } statt Indent, Subset)`: Python-Subset mit geschweiften Klammern.

## Wichtige Laufzeitfunktionen

- `print(...)` (Python): Ausgabe in die rechte Konsole.
- `input("...")` (Python): wartet auf Eingabe im Konsolen-Input.
- `consolePrint(...)` (JavaScript): Ausgabe mit Zeilenumbruch.
- `consoleInput("...")` (JavaScript): async Eingabe (Promise).

## Print-Verhalten (wichtig)

In dieser Version macht `print()` **keinen automatischen Zeilenumbruch**.

### Beispiele

```py
print("A")
print("B")
# Ausgabe: AB
```

```py
print("A", end="\n")
print("B", end="\n")
# Ausgabe:
# A
# B
```

```py
print("x", "y", sep=" | ", end="\n")
# Ausgabe: x | y
```

## Python Subset: Unterstuetzte Faelle

### 1) Variablen und Bedingungen

```py
name = await input("Name? ")
if name == "Ada":
  print("Hallo Ada", end="\n")
elif name == "Bob":
  print("Hallo Bob", end="\n")
else:
  print("Hallo ", name, end="\n")
```

### 2) Schleifen

```py
for i in range(3):
  print(i, end=" ")
print("", end="\n")

n = 3
while n > 0:
  print(n, end=" ")
  n = n - 1
print("", end="\n")
```

### 3) Funktionen

```py
def add(a, b):
  return a + b

summe = add(2, 5)
print("summe=", summe, end="\n")
```

### 4) OOP (Python-aehnlich)

- `class` wird unterstuetzt.
- `def __init__(self, ...)` wird als Konstruktor behandelt.
- `self.x` wird auf Objektattribute gemappt.
- Instanziierung `Person("Ada")` wird intern zu `new Person("Ada")`.

```py
class Person:
  def __init__(self, name):
    self.name = name

  def hi(self):
    print("Hi ", self.name, end="\n")

p = Person("Ada")
p.hi()
```

### 5) Datentyp-Casts

Unterstuetzt: `int(...)`, `float(...)`, `str(...)`, `bool(...)`, `list(...)`, `len(...)`.

```py
age = int(await input("Age? "))
pi = float("3.14")
text = str(age)
flag = bool(1)
chars = list("abc")
laenge = len(chars)

print(age, pi, text, flag, laenge, end="\n")
```

### 6) Listen

- `append(...)` funktioniert.
- Negativer Index `[-1]` wird unterstuetzt (letztes Element).

```py
nums = [10, 20, 30]
nums.append(40)
print(nums[-1], end="\n")  # 40
```

## Python Schueler Subset ({ })

Gleiche Subset-Logik wie oben, aber mit Klammern statt Einrueckung.

```py
name = await input("Name? ")
if name == "Ada" {
  print("Hallo Ada", end="\n")
} else {
  print("Hallo", name, end="\n")
}
```

## Neues Feature: Python Schueler -> Python konvertieren

Pro `python_student`-Zelle gibt es den Button `To Python`.

Was passiert:

- Sprache der Zelle wird auf `python` gestellt.
- Klammerbloecke `{ ... }` werden in Einrueckungsbloecke umgewandelt.
- Blockkoepfe (`if/elif/else/while/for/def/class`) bekommen bei Bedarf `:`.

### Beispiel

Vorher (`python_student`):

```py
class Person {
  def __init__(self, name) {
    self.name = name
  }
}
```

Nachher (`python`):

```py
class Person:
  def __init__(self, name):
    self.name = name
```

## JavaScript Beispiele

```js
consolePrint("Hallo aus JS");
const name = await consoleInput("Name? ");
consolePrint("Hi", name);
```

## JSON Datenzelle Beispiel

```json
{
  "topic": "demo",
  "values": [1, 2, 3]
}
```

Hinweis: JSON-Zellen werden nicht ausgefuehrt.

## Speichern/Laden

- `Download JSON` speichert alle Zellen.
- `Laden` importiert eine Notebook-JSON-Datei.

## Grenzen des Subsets

- Kein vollstaendiger Python-Interpreter.
- Fokus auf schulnahe Kernsyntax.
- Komplexe Python-Features (z. B. vollstaendige Imports, Generatoren, Decorators) sind nicht Ziel dieses Editors.

## Referenz

- https://datenflix007.github.io/