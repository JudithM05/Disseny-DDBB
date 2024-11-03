# Disseny-DDBB

Per aquesta pràctica hem tingut que dissenyar una base de dades amb el model entitat-relació sobre l'enunciat de la pràctica.

Així és com ens ha quedat el resultat final:
![alt text](image.png)

A partir de l'enunciat, hem trobat les següents entitats (on cadascuna té els seus atributs):

1) RECINTES
     (nom, m2_escenari, m2_zona_espectadors, disponibilitat_de_lavabos, escenari_cobert_o_no)
   
2) CONCERTS
     (data, hora_inici, hora_fi, preu_contractació)
   
3) GRUPS
     (nom, país, nº_components)
   
4) PARCEL·LES
     (id_parcela, numero, preu, m2)
   
5) CARRERS
     (codi, nom_grup)
   
6) PERSONES (amb dos subentitats: PÚBLIC i RESPONSABLES)
     (usuari, mail, contrassenya, DNI, dades_personals)
      
7) ACCÉS
     (data, hora, tipus)

Aspectes a destacar
-------------------

- RECINTES té com a clau primària el nom, ja que el recinte és identificat pel seu nom.
- RECINTES té una relació 1 - N amb CONCERTS, ja que en un recinte es poden fer diversos concerts.
- GRUPS té una relació 1 - N amb CONCERTS, ja que un grup pot realitzar diversos concerts.
- A dintre de GRUPS, hi ha una relació recíproca N - N, perquè un grup pot substituïr a un altre grup.
- A PARCEL·LES, id_parcela és un atribut que hem afegit com a clau primària per identificar la parcel·la.
- PARCEL·LES té una relació N - 1 amb CARRERS, ja que diferents parcel·les poden estar ubicades en un mateix carrer.
- PARCEL·LES té una relació 1 - 1 amb RESPONSABLES (subentitat de PERSONES), ja que un responsable lloga una parcel·la.
- CARRERS té com a clau primària el codi, ja que un carrer és identificat pel seu codi.
- PERSONES té com a clau primària usuari, perquè és l'usuari qui identifica a la persona.
- PERSONES té una relació especial amb el seu atribut dades_personals ja que està associat a les persones registrades.
- PERSONES té dos subentitats: PÚBLIC i RESPONSABLES, on públic és els espectadors que hi van al concert i responsables qui lloguen la parcel·la. I és disjunta i parcial, disjunta perquè només poden tenir una especialització, i parcial perquè no hi són tots els tipus de persones que hi poden haver.
- ACCÉS té una relació N - 1 amb RECINTES, perquè hi poden haver molts registres en un recinte.
