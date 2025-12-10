# Chef du projet : BELAID ZINEB (BMC) | Lien GitHub : https://github.com/belaidzineb09-dot/belaid-zineb-BMC-
# AYACHI RANA
# BEZZAOUYA INES FATINE
# benhammo ibtihel
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

# *** Affichage avec une bibliothèque de visualisation (matplotlib) ***
import matplotlib.pyplot as plt

# Affichage du tableau de données sous forme de graphique
plt.figure(figsize=(10, 4))
plt.plot(df["Séquence"], df["Pourcentage GC"], marker="o")
plt.xlabel("Séquence")
plt.ylabel("Pourcentage GC")
plt.title("Pourcentage de GC par séquence")
plt.show()
