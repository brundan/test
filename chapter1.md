---
title: Template Chapter 1
description: This is a template chapter.
---
## Wiederholung wesentlicher Inhalte

```yaml
type: NormalExercise
lang: r
xp: 100
skills: 1
key: 641f650cf3
```

In dieser Aufgabe werden wir kurz den Zugriff auf Objekte unterschiedlicher Typen, das Einlesen von Datensätzen und einfache Berechnungen wiederholen. 

Alle Themen werden in den folgenden Aufgaben nochmals intensiv trainiert.

`@instructions`
- speichern Sie den zweiten und fünften Eintrag des Vektors `kurse_vec` in `daten_auswahl1`
- speichern Sie nur die Kurse des Vektors `kurse_vec`, die über 18 liegen, in `daten_auswahl2`
- speichern Sie die Kurse der zweiten Spalte und Zeile 30 bis 40 aus `kurse_mat` in `daten_auswahl3`
- speichern Sie die Kurse der Facebookaktie aus `kurse_dataframe` in `daten_auswahl4`
- berechnen Sie mit den Daten aus `kurse_dataframe` die absolute Kursspanne für alle Handelstage und speichern Sie das Ergebnis in `daten_auswahl5`

`@hint`


`@pre_exercise_code`
```{r}
library(dplyr)

deutschebank <- read.csv("https://www.uni-duesseldorf.de/redaktion/fileadmin/redaktion/Fakultaeten/Wirtschaftswissenschaftliche_Fakultaet/Statistik/Kurse/BW_09/db_aktie_Feiertage2NA.csv",stringsAsFactors = F)
facebook <- read.csv("https://www.uni-duesseldorf.de/redaktion/fileadmin/redaktion/Fakultaeten/Wirtschaftswissenschaftliche_Fakultaet/Statistik/Kurse/BW_09/fb_aktie2NA.csv", stringsAsFactors = F)

aktienjoin <- full_join(facebook, deutschebank, by = "Date")
aktien <- select(aktienjoin, Date, fb = Open.x, db = Open.y )
remove(aktienjoin)
remove(facebook)
remove(deutschebank)
aktien <- aktien[order(aktien$Date),]

kurse_vec <- c(aktien$db)
kurse_mat <- cbind(aktien$db,aktien$fb)
kurse_dataframe <- aktien
```

`@sample_code`
```{r}
# alle benötigten Objekte sind bereits eingelesen
daten_auswahl1 <- ___

daten_auswahl2 <- ___

daten_auswahl3 <- ___

daten_auswahl4 <- ___

daten_auswahl5 <- ___
```
`@solution`
```{r}
daten_auswahl1 <- kurse_vec[c(2,5)]

daten_auswahl2 <- kurse_vec[kurse_vec > 18]

daten_auswahl3 <- kurse_mat[ 30:40 , 2 ]

daten_auswahl4 <- kurse_dataframe$fb

daten_auswahl5 <- abs(kurse_dataframe$fb- kurse_dataframe$db)
```
`@sct`
```{r}
test_object("daten_auswahl1") 
test_object("daten_auswahl2")
test_object("daten_auswahl3")
test_object("daten_auswahl4")
test_object("daten_auswahl5")
test_error()
success_msg("Sehr gut!")
```
