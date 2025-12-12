# Chef du projet : BELAID ZINEB (BMC) | Lien GitHub : https://github.com/belaidzineb09-dot/belaid-zineb-BMC-
# AYACHI RANA
# BEZZAOUYA INES FATINE
# benhammou ibtihel
# Hadjiedj  rania
import pandas as pd

# 1) Données : Séquences ADN, Longueur, Pourcentage de GC
data = {
    "Séquence": ["ATGCGTACGTA", "GCTAGCTAGGCC", "GCTAGCTAGGCC", "TACGATCGTA","ATGAAAGGCTT","CGTACGTAGC","TTAACCGGAT"],
    "Longueur": [12, 12, 12, 10,11,10,10],
    "Pourcentage GC": [50, 66.67, 58.33, 40,45.45,60,50]
}
# Création du DataFrame (tableau pandas)
df = pd.DataFrame(data)

# Affichage du tableau
print("Tableau Longueur :")
print(df)

# Opérations sur les tableaux:
print("************** Operations ***************")

# 2) Sélectionner la colonne "Longueur"
longueur = df["Longueur"]
print(longueur)

# Affichage avec une bibliothèque de visualisation (matplotlib)
#import matplotlib.pyplot as plt
# Données
#sequences = ["ATGCGTACGTA", "GCTAGCTAGGCC", "GCTAGCTAGGCC", "TACGATCGTA","ATGAAAGGCTT","CGTACGTAGC","TTAACCGGAT"]
#longueur = [12, 12, 12, 10,11,10,10]
#gc_content = [50, 66.67, 58.33, 40,45.45,60,50]
# Création d'un DataFrame
#data = {"Séquence": sequences, "Longueur": longueur, "Pourcentage GC": gc_content}
#df = pd.DataFrame(data)

# Affichage du tableau de données sous forme de graphique
#plt.figure(figsize=(10, 6))
#plt.bar(df["Séquence"], df["Pourcentage GC"], color='skyblue')
#plt.xlabel("Séquences")
#plt.ylabel("Pourcentage GC")
#plt.title("Pourcentage de GC par séquence")
#plt.show()

# 3)Filtrer les séquences avec la Longueur > 10
print("************* Filtrage : longueur supérieure à 10************")
# Filtrer les séquences avec la Longueur est supérieur à 10
filtered_df = df[df["Longueur"] > 10]
print(filtered_df)

# 4)Calculer la moyenne du pourcentage de GC avec 3 chiffre après la virgule 
print("************* Calcul de la moyenne ***************")
# Calculer la moyenne du pourcentage de GC avec 3 chiffre aprè la virgule 
average_gc = df["Pourcentage GC"].mean()
print(f"Pourcentage moyen de GC : {average_gc:.3f}%")

# 5) Ajouter une nouvelle colonne "Catégorie GC"
print("************* Ajout d'une nouvelle colonne catégorie GC *************")
# Ajouter une nouvelle colonne "catégorie GC"
df["Catégorie GC"] = df["Pourcentage GC"].apply(lambda x: "Riche" if x > 55 else ("Moyen" if 45 <= x <= 55 else "Faible")
)
print(df)

# 6) Ajouter colonne du nombre de 'G'
df["Nb_G"] = df["Séquence"].apply(lambda seq: seq.count("G"))
print(df)

# 7) Calculer l’écart-type du %GC et de la longueur des sequences
ecart_gc = df["Pourcentage GC"].std()
ecart_longueur = df["Longueur"].std()
print("\nÉcart-type %GC :", ecart_gc)
print("Écart-type Longueur :", ecart_longueur)

# 8) Sauvegarder le tableau final dans un fichier CSV
#Sauvegarder le tableau final dans un fichier CSV
df.to_csv("tableau_sequences.csv", index=False)
print("Fichier CSV sauvegardé avec succès ")
