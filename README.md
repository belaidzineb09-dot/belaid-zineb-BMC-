# Chef du projet : BELAID ZINEB (BMC) | Lien GitHub : https://github.com/belaidzineb09-dot/belaid-zineb-BMC-
# AYACHI RANA
# BEZZAOUYA INES FATINE
# benhammou ibtihel
# Hadjiedj  rania
import pandas as pd

# Données : Séquences ADN, Longueur, Pourcentage de GC
data = {
    "Séquence": ["ATGCGTACGTA", "GCTAGCTAGGCC", "GCTAGCTAGGCC", "TACGATCGTA","ATGAAAGGCTT","CGTACGTAGC","TTAACCGGAT"],
    "Longueur": [12, 12, 12, 10,11,10,10],
    "Pourcentage GC": [50, 66.67, 58.33, 40,45.45,60,50]
}
# Création du DataFrame (tableau pandas)
df = pd.DataFrame(data)

# *** Première partie : Création et affichage ***
print("Analyse des séquences ADN")
print(df)
print("\n")

# *** Deuxième partie : Opérations ***
print("******* Opérations *******")

# 1) Sélectionner la colonne "Séquence"
sequences = df["Séquence"]
print(sequences)
print("\n")


#2) Sélectionner et afficher uniquement la colonne "Longueur"
print("************* Affichage de la colonne Longueur ***************\n")

col_longueur = df["Longueur"]
print(col_longueur)

#3)Filtrer les séquences avec la Longueur est supérieurr à 10%
print("************* Filtrage avec pourcentage % *************")
# Filtrer les séquences avec la Longueur est supérieur à 10
filtered_df = df[df["Longueur"] > 10]
print(filtered_df)

#4)Calculer la moyenne du pourcentage de GC après la virgule 
print("************* Calcul de la moyenne *************")
# Calculer la moyenne du pourcentage de GC avec 3 chiffre aprè la virgule 
average_gc = df["Pourcentage GC"].mean()
print(f"Pourcentage moyen de GC : {average_gc:.3f}%")

5)Ajouter une nouvelle colonne avec des calculs
print("************* Ajout d'une nouvelle colonne *************")
# Ajouter une nouvelle colonne "Longueur catégorisée"
df["Catégorie GC"] = df["Catégorie"].apply(lambda x: "riche" if %GC> 55 else "moyen"if 45<%GC<55 else “faible”%GC<45)
print(df)
