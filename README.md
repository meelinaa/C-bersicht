# C# Befehle 
---

## Wichtige C#-Befehle in Tabellenform

| Befehl / Feature        | Beschreibung                                               | Beispiel                          |
|-------------------------|------------------------------------------------------------|-----------------------------------|
| `var`                   | Variablendeklaration mit automatischem Typ                | `var name = "Anna";`              |
| `int`, `string`, etc.   | Statische Typisierung                                     | `int zahl = 5;`                   |
| `if / else`             | Bedingte Ausführung                                       | `if (x > 0) { ... } else { ... }` |
| `switch`                | Mehrere Bedingungen                                       | `switch (x) { case 1: ... }`      |
| `for`, `while`, `foreach` | Schleifen                                                | `foreach (var item in list) {}`  |
| `class`                 | Klassen deklarieren                                       | `class Person { ... }`           |
| `object`                | Instanz einer Klasse                                      | `var p = new Person();`          |
| `List<T>`               | Generische Liste                                          | `List<int> zahlen = new();`      |
| `Dictionary<K,V>`       | Schlüssel-Wert-Speicher                                   | `var dict = new Dictionary<>();` |
| `using`                 | Ressourcen automatisch freigeben                          | `using (var con = ...) {}`       |
| `try / catch / finally` | Fehlerbehandlung                                          | `try { ... } catch { ... }`      |
| `return`                | Wert aus Methode zurückgeben                              | `return summe;`                  |
| `async / await`         | Asynchrone Programmierung                                 | `await SomeMethodAsync();`       |
| `Task`                  | Repräsentiert eine laufende oder geplante Aufgabe         | `Task<int>`                       |
| `static`                | Gehört zur Klasse, nicht zur Instanz                      | `static int Count = 0;`          |
| `public / private`      | Zugriffsmodifizierer                                      | `public class Auto {}`           |
| `get / set`             | Eigenschaften einer Klasse                                | `public string Name { get; set; }` |
| `namespace`             | Gruppiert Klassen logisch                                 | `namespace MeineApp.Models {}`   |
| `interface`             | Definiert Verträge für Klassen                            | `interface IDruckbar { void Drucke(); }` |
| `enum`                  | Aufzählung möglicher Werte                                | `enum Status { Aktiv, Inaktiv }` |
| `?` (nullable)          | Nullable Types                                            | `int? alter = null;`             |
| `??` (null-coalescing)  | Fallback bei `null`                                       | `string name = eingabe ?? "Gast";` |
| `? :` (ternary operator)| Kurzform von `if / else`                                  | `var result = x > 0 ? "ja" : "nein";` |
| `nameof()`              | Gibt den Namen einer Variable oder Property als String zurück | `nameof(Person.Name)`       |
| `params`                | Beliebig viele Parameter                                  | `void Drucke(params string[] zeilen)` |
| `extension method`      | Methoden zu bestehenden Typen hinzufügen                  | `public static bool IstLeer(this string text)` |
| `lambda =>`             | Kurzform für Methoden oder Funktionen                     | `list.Where(x => x > 5)`         |
| `delegate / Func / Action` | Methoden als Parameter oder Rückgabewert                | `Func<int, int> quadriere = x => x * x;` |
| `event`                 | Reaktion auf Ereignisse                                   | `public event EventHandler Geklickt;` |
| `DateTime`              | Zeit & Datum                                              | `DateTime.Now`                   |
| `Guid.NewGuid()`        | Neue eindeutige ID erzeugen                               | `var id = Guid.NewGuid();`       |
| `File / Directory / Path` | Dateien & Ordner verwalten                              | `File.WriteAllText("text.txt", "Hi");` |
| `Regex`                 | Textmuster finden & prüfen                                | `Regex.IsMatch(text, "^[a-z]+$")` |

---

## Codebeispiele mit Kommentaren

```csharp
// var: automatische Typzuweisung
var name = "Anna"; // C# erkennt automatisch, dass dies ein string ist

// int, string, etc.
int zahl = 5; // explizit typisiert
string begruessung = "Hallo";

// if / else
if (zahl > 0)
{
    Console.WriteLine("Zahl ist positiv");
}
else
{
    Console.WriteLine("Zahl ist negativ oder null");
}

// switch
switch (zahl)
{
    case 1:
        Console.WriteLine("Eins");
        break;
    case 2:
        Console.WriteLine("Zwei");
        break;
    default:
        Console.WriteLine("Etwas anderes");
        break;
}

// for / while / foreach
for (int i = 0; i < 3; i++) Console.WriteLine(i);

int j = 0;
while (j < 3)
{
    Console.WriteLine(j);
    j++;
}

var namen = new List<string> { "Anna", "Ben" };
foreach (var n in namen)
{
    Console.WriteLine(n);
}

// class & object
class Person
{
    public string Name;
    public void SagHallo() => Console.WriteLine($"Hallo, ich bin {Name}");
}

var person = new Person { Name = "Anna" };
person.SagHallo();

// List<T> & Dictionary<K,V>
List<int> zahlen = new() { 1, 2, 3 };
Dictionary<string, int> alter = new() { { "Anna", 25 } };

// using (z.B. für DB-Verbindungen)
using (var reader = new StreamReader("datei.txt"))
{
    string text = reader.ReadToEnd();
}

// try / catch / finally
try
{
    int x = int.Parse("abc");
}
catch (FormatException)
{
    Console.WriteLine("Ungültige Eingabe");
}
finally
{
    Console.WriteLine("Fertig");
}

// return
int Summe(int a, int b) => a + b;

// async / await
async Task LadeDatenAsync()
{
    await Task.Delay(1000);
    Console.WriteLine("Fertig geladen");
}

// static
static class Mathe
{
    public static int Quadriere(int x) => x * x;
}

// public / private
public class Auto
{
    private string marke;
    public void SetMarke(string m) => marke = m;
}

// get / set
class Produkt
{
    public string Name { get; set; }
}

// namespace
namespace MeinProjekt.Models
{
    class Kunde { }
}

// interface
interface IDruckbar { void Drucke(); }
class Bericht : IDruckbar
{
    public void Drucke() => Console.WriteLine("Drucke Bericht");
}

// enum
enum Status { Aktiv, Inaktiv }
Status s = Status.Aktiv;

// ? nullable
int? optional = null;

// ?? null-coalescing
string eingabe = null;
string nameFinal = eingabe ?? "Gast";

// ? : ternary operator
int z = 5;
string result = z > 0 ? "Positiv" : "Nicht positiv";

// nameof
Console.WriteLine(nameof(Person.Name)); // Ausgabe: "Name"

// params
void Drucke(params string[] texte)
{
    foreach (var t in texte) Console.WriteLine(t);
}
Drucke("A", "B", "C");

// extension method
public static class StringErweiterung
{
    public static bool IstLeer(this string s) => string.IsNullOrWhiteSpace(s);
}

// lambda => und LINQ
var liste = new List<int> { 1, 2, 3, 4 };
var gefiltert = liste.Where(x => x > 2);

// delegate, Func, Action
Func<int, int> verdoppeln = x => x * 2;
Console.WriteLine(verdoppeln(4));

// event
public class Button
{
    public event EventHandler Geklickt;
    public void Klick() => Geklickt?.Invoke(this, EventArgs.Empty);
}

// DateTime
DateTime jetzt = DateTime.Now;

// Guid
Guid id = Guid.NewGuid();

// File, Directory, Path
File.WriteAllText("test.txt", "Hallo Welt");
string pfad = Path.Combine("C:", "Ordner", "datei.txt");

// Regex
bool istGueltig = Regex.IsMatch("abc123", "^[a-z0-9]+$");
```
