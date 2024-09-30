# Repositori d'exercicis

Aquesta secció conté els exercicis realitzats pels estudiants de l'assignatura d'Administració i Manteniment de Sistemes i Aplicacions (AMSA).

## Exercicis

### Bàsics
Filtra el document pokemon.csv i mostra nomes els que siguin de tipus 'Flying' i 'Fairy'
```awk
awk -F, '/Flying/ && /Fairy/ {print $2,$3,$4}' pokemon.csv
```
Filtra per tot de la segona columna comenci amb H
```awk
awk -F, '$2 ~ /^H/ {print $2}' pokemon.csv
```
### Intermedis
Compara i mostra el pokemon més debil i el més fort
```awk
awk -F, 'BEGIN { fort=0; debil=100 } /Fire/ && $12 == 1 { if ($7 > fort) { fort=$7; pfort=$2 } if ($7 < debil) { debil=$7; pdebil=$2 } } END { print "---\nEl més debil:", pdebil, "\nEl més fort:", pfort }' pokemon.csv
```
Mostra quants pokemons tenen més de 90 a cada un dels atributs
```awk
awk -F, '{ if (NR > 1 && ($6 > 90 && $7 > 90  && $8 > 90  && $9 > 90  && $10 > 90  && $11 > 90)) count++ } END { print "Hi ha", count, "pokemons amb més de 90 de cada atribut." }' pokemon.csv
```
### Avançats
Conta quants pokemons hi ha de cada generació i ho mostra
```awk
awk -F, 'BEGIN { print "\nNombre de Pokemons per generació\n"} NR > 1 { generacio[$12]++ } END { for (gen in generacio) {  print " La generació", gen, "te", generacio[gen], "Pokemons\n" } }' pokemon.csv
```
