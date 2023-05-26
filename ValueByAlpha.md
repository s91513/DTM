## Value By Alpha Maps in QGIS

# Datenquelle (Wahlgeometrie & Wahlergebnisse)
[Bundestagswahl 2021](https://www.bundeswahlleiterin.de/bundestagswahlen/2021/ergebnisse.html)

Tabelle mit Wahlergebnissen bereinigen:
![grafik](https://github.com/s91513/DTM/assets/134683756/9650c4aa-0a07-40e5-83b9-4d54f0a73aef)

## QGIS

1.) Vergleich SPD vs. CDU Stimmenstärkere Partei regelbasiert darstellen
Regel "Olaf"
```
"SPD" > "CDU" 
```
 Regel "Armin"
```
 "SPD" < "CDU"
```

2.) Ebene "Alpha" ergänzen und auf Symbolebene 1 setzen
![grafik](https://github.com/s91513/DTM/assets/134683756/04b26bdb-5eee-4c6a-87db-bd4c09ba0b41)

4.) Regel für "Alpha": über Symbol einfache Füllung unter "Füllfarbe" -> Datendefinierte Übersteuerung bearbeiten
![grafik](https://github.com/s91513/DTM/assets/134683756/039760e2-0b59-4869-98e6-1aa2af789509)
```
set_color_part(
"black",
"alpha",
126)
```

statt eines festen Alpha-Werts, wird dieser wertebasiert aus einem Attribut für jede Bezugseinheit berechnet.
```
set_color_part(
'black',
'alpha',
 scale_linear("G",
 100000, 200000,
 230,0)
 )
 ```
