# M319 Zusammenfassung


# Schleifen

## While-Schleife

Die while-Schleife führt einen Codeblock aus, solange eine Bedingung wahr ist.
```cs
int i = 0;
while (i < 5)
{
    Console.WriteLine(i);
    i++;
}

```

## Do-While-Schleife
Die do-while-Schleife ist ähnlich wie die while-Schleife, mit dem Unterschied, dass der Codeblock mindestens einmal ausgeführt wird, bevor die Bedingung überprüft wird.

```cs
int i = 0;
do
{
    Console.WriteLine(i);
    i++;
} while (i < 5);
```

## For-Schleife

Die for-Schleife wird verwendet, wenn Sie wissen, wie oft der Codeblock ausgeführt werden soll.
```cs
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```

## Break
Das Break Statement wird verwendet, um Schleifen frühzeitig zu beenden.

```cs
for (int i = 0; i < 10; i++)
{
    if (i == 4)
    {
        break;
    }
    Console.WriteLine(i);
}
```


# Unterprogramme
Unterprogramme in C# können Methoden oder Funktionen sein. Sie können Parameter akzeptieren und Werte zurückgeben.

## Methode ohne Rückgabewert
```cs
void MyMethod(string name)
{
    Console.WriteLine("Hello " + name);
}
```

## Methode mit Rückgabewert
```cs
int Multiply(int a, int b)
{
    return a * b;
}
```

## Call by Value
In C# werden alle Parameter standardmäßig “by value” übergeben. Das bedeutet, dass eine Kopie des Arguments an die Methode übergeben wird.

```cs
void ChangeValue(int x)
{
    x = 200;
}

int a = 100;
ChangeValue(a);
Console.WriteLine(a);  // Gibt 100 aus, nicht 200
```

## Rückgabewerte

```cs
using System;

class Program
{
    static void Main()
    {
        int result = Add(5, 7);
        Console.WriteLine("Das Ergebnis der Addition ist: " + result);
    }

    static int Add(int num1, int num2)
    {
        int sum = num1 + num2;
        return sum;
    }
}

```

# Operatoren

## Modulo

Der Modulo Operator (%) übernimmt eine ganz spezielle Funktion. Er übergibt, anders als der Divisionsoperator, den Restwert einer Division und nicht das Ergebnis aus der Rechnung. Würden wir 10 / 3 rechnen, kämen wir auf das Ergebnis 3.33. Rechnen wir jedoch 10 % 3, so erhalten wir den Restwert aus der Division 10 / 3, nämlich 1. Bei einer Division wie z.B. 10 / 2, erhalten wir keinen Restwert, weil die Division sauber aufgeht.

```cs
int a = 10 % 3; //Restwert ist 1
int b = 10 % 2: //Restwert ist 0
```

## Zusammengesetzte Zuweisungen

Mit der zusammengesetzten Zuweisung könne wir Werte nicht nur zuweisen, sondern gleichzeitig auch noch eine mathematische Operation starten. Im unteren Beispiel addieren, subtrahieren, multiplizieren und dividieren wir jeweils zur Zuweisung noch die Zahl 5.

```cs
int a = 5;
a += 5; // Der Variable a wird 5 addiert und sie wird gespeichert
a -= 5; // Der Variable a wird 5 subtrahiert und sie wird gespeichert
a *= 5; // Die Variable a wird mit 5 multipliziert und wird gespeichert
a /= 5; // Die Variable a wird mit 5 dividiert und wird gespeichert
```

# Beispielskripte

Schaltjahrprogramm

```cs

using System;

class Program
{
    static void Main(string[] args)
    {
        int startYear = InputYear("start year");
        int endYear = InputYear("end year");
        PrintAllLeapYears(startYear, endYear);
        Console.ReadLine();
    }

    static int InputYear(string yearType)
    {
        int year;
        while (true)
        {
            Console.Write($"Enter {yearType}: ");
            if (int.TryParse(Console.ReadLine(), out year) && year >= 0 && year <= 5000)
            {
                return year;
            }
            else
            {
                Console.WriteLine("Invalid input. Please enter a valid year between 0 and 5000.");
            }
        }
    }

    static void PrintAllLeapYears(int startYear, int endYear)
    {
        Console.WriteLine($"Leap years between {startYear} and {endYear}:");
        for (int year = startYear; year <= endYear; year++)
        {
            if (IsLeapYear(year))
            {
                Console.WriteLine(year);
            }
        }
    }

    static bool IsLeapYear(int year)
    {
        return (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
    }
}
```
