# PARCIAL 1
## Punto 1

Se realizó el primer punto del parcial colocando las carpetas desde el computador hasta el home y luego se concatenaron y editaron usando lo siguiente:

```cat *.fasta > concatsecs.fasta```

```sed -E 's/^(>[^ ]+) ([^ ]+) ([^ ]+).*/\1_\2_\3/' concatsecs.fasta > concatnombres.fasta```

En donde cat nos ayudó a concatenar las diferentes secuencias y colocarlas en "> concatsecs.fasta" nos ayudó a guardar el concatenado realizado.

Luego se realizó sed para editar y -E para usar las expresiones regulares (Que fueron 's/^(>[^ ]+) ([^ ]+) ([^ ]+).*/\1_\2_\3/') y nuevamente "> concatnombres.fasta" para guardar el archivo ya editado.

Para realizar la base de datos tipo blast y visualizar el BLAST se uso el siguiente código:

```makeblastdb -in concatnombres.fasta -dbtype nucl -parse_seqids -out ballens_blastt -title "Ballenasblasttt"```

```blastn -query query.fasta -task megablast -db ballens_blastt -outfmt 7 -word_size 7 -out blast_hsp90 -num_threads```

Y a partir de los resultados obtenidos y la comparación de factores como %de identidad, alignment length, evalue, bit score, entre otros, se cree que la especie query es Balaenoptera_borealis.


## PUNTO 2
Para realizar el alineamiento se usó el siguiente código:

```salloc```

```module load muscle/3.8.31```

```muscle -in todojunto.fasta -out todojunto_muscle.fasta```

Y luego se esperó a que corrieran los archivos...

...

...

...

Finalmente con "FASconCAT-G_v1.05.1.pl" se corrieron los códigos:

```./FASconCAT-G_v1.05.1.pl -n -p -s```

```module load iqtree/1.6.12```

```iqtree -s FcC_supermatrix.phy -m TEST -bb 1000 -pre todo_ballenas```

![Caos](https://photos.app.goo.gl/Dt8HT9toApNW8NTcA)

Según el árbol podemos concluir que hay alta similitus entre las secuencias, en donde seq 1, que fue la query, es la más distinta, al estar tan definidas las ramas es posible decir que son especies bastante cercanas entre sí, con un pronto ancestro en común.


## PUNTO 3
