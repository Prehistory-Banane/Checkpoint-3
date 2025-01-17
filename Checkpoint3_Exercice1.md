# Partie 1 : Gestion des utilisateurs

### Q.1.1.1
1. Première étape, trouver Kelly Rhameur  
![1](https://github.com/user-attachments/assets/7299710a-18a7-45d4-8627-6eba31aa2778)
![2](https://github.com/user-attachments/assets/59d8c6e3-b23d-40db-9e24-3d25df650bd0)

2. Deuxième étape, créer Lionel Lemarchand avec les mêmes attirbuts que Kelly Rhammeur  
![3](https://github.com/user-attachments/assets/15c1d295-a45b-44ea-982c-b9e941e6085e)
![5](https://github.com/user-attachments/assets/e44451bd-198c-441b-bb9d-190e4fec7233)


### Q.1.1.2
1. Création de la nouvelle OU  
![6](https://github.com/user-attachments/assets/63e7af30-e0f6-4233-b497-d0399dd9e5bc)
![7](https://github.com/user-attachments/assets/87a60a92-37d9-4a28-a66f-e9117ff41910)

2. Déplacement de Kelly dans cette nouvelle OU  
![8](https://github.com/user-attachments/assets/0ab2dcb7-4270-4db7-af24-6d1941620163)

3. Vérification que cela a fonctionné  
![9](https://github.com/user-attachments/assets/eda38bbd-f2fc-43ab-9fdb-c191f1599ce1)


### Q.1.1.3
Suppression de Kelly du groupe de l'OU  
![10](https://github.com/user-attachments/assets/aa519a5d-5f92-487f-b492-0f65af7333bb)


### Q.1.1.4
Création du dossier individuel du nouvel utilisateur et archivage celui de Kelly Rhameur en le suffixant par -ARCHIVE  
![11](https://github.com/user-attachments/assets/64e474ed-13ef-4284-ab7c-84e925a1c4f1)



# Partie 2 : Restrictions utilisateurs

### Q.1.2.1
Restriction des heures de connection pour l'utilisateur Gabriel Ghul  
![12](https://github.com/user-attachments/assets/57808364-cd7d-4c96-9bca-1eef629a97df)


### Q.1.2.2
Permettre la connection de Gabriel uniquement du l'ordinateur CLIENT01  
![13](https://github.com/user-attachments/assets/cdd980f0-4960-4522-b34b-666fab7d5393)


### Q.1.2.3
Création d'une GPO pour l'OU **LabUsers**  
![14](https://github.com/user-attachments/assets/37774757-33fd-401e-ab70-e174f1e43f98)

On lui donne un nom clair pour s'y retrouver facilement dans la gestion des GPO  
![15](https://github.com/user-attachments/assets/4eaeda01-a16b-418a-9cf9-c77ec9d9d67e)

On édite la GPO  
![16](https://github.com/user-attachments/assets/b9539481-2aba-4a0c-abda-c8afbc27cb2b)

- Pour gérer la `stratégie de mots de passe` dans le Group Policy Management Editor :
  - Dérouler `Computer Configuration`
  - Dérouler `Policies`
  - Dérouler `Windows Settings`
  - Dérouler `Security Settings`
  - Dérouler `Account Policy`
  - Cliquer sur `Password Policy`
![17](https://github.com/user-attachments/assets/7ef42a4a-8f5e-4b08-99c8-9cfd034f7243)

  - Afin de durcir les comptes utilisateurs de l'OU **LabUsers**, je fais les choix suivants
![18](https://github.com/user-attachments/assets/e9628b93-c9b9-49c8-89cb-165afc45bb90)



# Partie 3 : Lecteurs réseaux

### Q.1.3.1
- Préparations en amont de la création de la GPO
  - Ouvrir le `File Explorer`
  - Faire un clic droit sur `DossiersCommuns (E:)`
  - Cliquer sur `Properties`
  - Cliquer sur `Sharing`
  - Cliquer sur `Advanced Sharing`
  - Cliquer sur `Share this folder`
  - Cliquer sur OK
  - Bien mettre de côté le chemin de partage `\\Srvwin01\e`
  - Cliquer sur `Close`
![21](https://github.com/user-attachments/assets/057844d9-59c2-460f-b77f-91d2bd60b686)

  - Renouveler la procédure avec `DossiersPersonnels (F:)`

- Création de la nouvelle GPO **Drive_Mount**  
![19](https://github.com/user-attachments/assets/d90896ed-66b1-4c55-9717-81fc231666a3)

- Pour gérer la stratégie `Drive-Mount` dans le Group Policy Management Editor :
  - Dérouler `User Configuration`
  - Dérouler `Preference`
  - Dérouler `Drive Maps`
  - Dans la zone à droit, faire un clic droit
  - Cliquer sur `New` puis sur `Mapped Drive`  
![20](https://github.com/user-attachments/assets/22243253-ab2c-4a68-b7f4-6a918017bbf6)

- Remplir les champs comme suit pour le mappage de `DossiersCommuns (E:)`
![22](https://github.com/user-attachments/assets/06974273-70ee-452d-a33a-cdf586051417)

- Répéter l'action pour le mappage de `DossiersPersonnels (F:)`
![23](https://github.com/user-attachments/assets/a5c3899a-6970-4c7c-8aa6-2686f3786556)
