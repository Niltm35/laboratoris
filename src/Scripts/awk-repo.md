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

### Avançats
