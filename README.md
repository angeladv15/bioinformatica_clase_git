# bioinformatica_clase_git
# Parcial
```ssh -i bio.pt.pem -p 37022 bio.pt@172.25.255.10``` para eentrar al clusteer.
```cd data´´´para entrar a la carpeta del curso 
```cd Parcial1´´´
```mkdir parcial1_angeladelgado´´
## Punto 1
en atom pongo buscar **(>\w+)(\.1)(\s)(\w+)(\s)(\w+)(\s)(\w+)(\s)(\w+-\w+) (\w*\s\w*\s\w*\s\w*\s\w*)([()]\w*[()]\s\w*,\s\w+\s\w+;\s\w+)** y remplazar por **$1_$2_$3_$4_$6_$10**
se sube el arcivo al cluster utilizando ```scp -i bio.pt.pem -P 37022 :/Users/angeladelgado/desktop/parcial/sequence.fasta bio.pt@172.25.255.10:/home/bio.pt/data/Parcial1/parcial1_angeladelgado/punto_1´´
se corre ```salloc´´´antes de correr el blast
para crear nuestra base de datos usamos el siguiente codigo:
```makeblastdb -in sequence.fasta -dbtype nucl -parse_seqids -out trans_sequence -title "Spodoptera_exigua"´´´
despues hacemos nuestro blast nuestro BLAST con el codigo:
```blastn -query query_parcial -task megablast -db trans_sequence -outfmt 7 -word_size 7 -out blast_hsp90 -num_threads 1´´´
## Punto 2
Concatenamos las secuencias del Popset y la query en un solo archivo fasta con el siguiente codigo.
```cat query_parcial.fasta sequence.fasta > seq_concat.fasta´´´
### Alineamiento
Realizamos un alineamiento múltiple utilizando MUSCLE 
primero lo cargamos: ```module load muscle/3.8.31´´´
Corremos un alineamiento :
```muscle -in seq_concat.fasta -out seq_concat_muscle.fasta´´´

###árbol de máxima verosimilitud 
 cp copiamos el script FASconCAT-G_v1.05.1.pl que está en la carpeta data y creamos una carpeta nueva (arbor_mvero) donde sólo tengamos nuestro alineamiento fasta y el script de FASconCAT, cuando tengamos la carpeta corremos el codico ``` ./FASconCAT-G_v1.05.1.pl´´´ y , seleccionamos formato Nexus por bloques y Phylip Relaxed y oprimimos s para ejecutar.
 
En la carpeta donde tenemos la matriz corremos:

```module load iqtree´´´

```iqtree -s FcC_supermatrix.phy -m TEST -bb 1000 -pre salticidae_clustal´´´








### Head 3
*italic*
_italica_
**negrilla**
_letras **mixtas** se hace así_
~tachado~
```codigo```
* Lista1
* Lista2
  * Lista 2.1
  * Lista 2.2
* Lista3
1. uno
2. dos
  2. 1 dos.1
3. tres
[Google scholar](https://scholar.google.com/citations?user=Oqq-sgcAAAAJ&hl=es)
![Caos](https://i.pinimg.com/originals/e0/19/17/e0191785c29396e42bccc19c6c3db098.jpg)
Nombre | Nota_final
-------|-----------
Fabian_Salgado | 5.0
Pepito perez | 5.5
