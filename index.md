<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>HTML Elements Reference</title>
        <meta name="description" content="Century Calculator v1.1">
        <meta name="author" content="CheryX">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
    </head>
</html>

# Century Calculator
Century Calculator is a simple program that helps you with calculating century, half of century or millenium

## How to download it?
If you rather to download old, English version, you can use [Old verison](https://github.com/CheryX/centurycalc), but if you want to get newer verison, you can use [Current Version](https://github.com/CheryX/centurycalc-pl/releases/tag/v1.1)

### Code
```py
while True:
    print ("Wpisz rok tutaj:")
    year = int(input("> "))
    print ("Wybierz erę: (0 = p.n.e, 1 = n.e)")
    era = int(input("> "))
    if (year > 999):
        year2 = int(str(year)[:2])
        half = int(str(year)[2:])
        last3 = int(str(year)[1:])
        mil = int(str(year)[0])
    elif (99 < year < 1000):
        year2 = int(str(year)[0])
        half = int(str(year)[1:])
        last3 = year
        mil = 0
    elif (year < 100):
        year2 = 0
        half = year
        last3 = year
        mil = 0
    if (year != 0):
        if (era == 1):
            if (half == 00):
                century = year2
            else:
                century = year2 + 1
            if (half > 50) or (half == 0):
                halffc = 2
            else:
                halffc = 1
            if (last3 == 000):
                mil2 = mil
            else:
                mil2 = mil + 1
            if (last3 > 500) or (last3 == 000):
                hmil = 2
            else:
                hmil = 1
            print ("## Informacje:")
            print ("Rok:", year)
            print (" ")
            print ("Wiek:", century)
            print ("Połowa wieku:", halffc)
            print ("Tysiąclecie:", mil2)
            print ("Połowa tysiąclecia:", hmil)
        else:
            if (half == 00):
                century = year2
            else:
                century = year2 + 1
            if (half > 50) or (half == 0):
                halffc = 1
            else:
                halffc = 2
            if (last3 == 000):
                mil2 = mil
            else:
                mil2 = mil + 1
            if (last3 > 500) or (last3 == 000):
                hmil = 1
            else:
                hmil = 2
            print ("##Informacje:")
            print ("Rok: ", year, "p.n.e")
            print (" ")
            print ("Wiek: ", century, "p.n.e")
            print ("Połowa wieku: ", halffc, "p.n.e")
            print ("Tysiąclecie: ", mil2, "p.n.e")
            print ("Połowa tysiąclecia: ", hmil, "p.n.e")
            print ("""
## Daty graniczne:""")
        if (era == 1):
            rok2 = century * 100
            rok1 = rok2 - 99
            print (rok1, "-", rok2, sep='')
        else:
            rok1 = century * 100
            rok2 = rok1 - 99
            print (rok1, "p.n.e", " - ", rok2, "p.n.e", sep='')
        if (era == 1):
            minelo = 2020 - year
            print ("""
## Od tego momentu minelo:""", minelo, """lat
            """)
        else:
            minelo = 2020 + year - 1
            print ("""
## Od tego momentu minelo:""", minelo, """lat
            """)
    else:
        print ("NIE MA ROKU ZEROWEGO!")
    continue
```
