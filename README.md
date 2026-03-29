# pierre-feuille-ciseaux

import random

manches = int(input("Combien de manches voulez-vous faire ? "))

insultes = [
    "idiot", "merde", "va te faire", "enculé",
    "enfant du viol", "fdp", "fils de pute",
    "salope", "conasse","pute"
]

score_joueur = 0
score_ordi = 0

options = ["pierre", "feuille", "ciseaux", "puits"]

while score_joueur < manches and score_ordi < manches:
    choix_joueur = input(
        "Que choisissez-vous ? [pierre], [feuille], [ciseaux]: "
    ).strip().lower()

    while choix_joueur not in options:
        if choix_joueur in insultes:
            print("C'est celui qui le dit qui l'est.")
        else:
            print("Ton choix n'est pas dans les options,tu sais pas jouer ?idiot:")

        choix_joueur = input(
            "Choisis parmi [pierre], [feuille], [ciseaux]: "
        ).strip().lower()

    choix_ordi = random.choice(options)

    print(f"\n{choix_joueur.capitalize()} contre {choix_ordi.capitalize()} !")

    if choix_joueur == choix_ordi:
        print("Égalité !")

    elif (
        (choix_joueur == "pierre" and choix_ordi == "ciseaux") or
        (choix_joueur == "feuille" and choix_ordi == "pierre") or
        (choix_joueur == "ciseaux" and choix_ordi == "feuille") or
        (choix_joueur == "puits")
    ):
        score_joueur += 1
        print("Gagné ! Mais que cette manche...")

    else:
        score_ordi += 1
        print("J'ai gagné cette manche, signé l'ordinateur.")

    print(f"Score : [ {score_joueur} - {score_ordi} ]\n")

if score_joueur == manches:
    print("GG bg, tu as gagné !")
else:
    print("L'ordinateur vous a vaincu...(t'est nul) Réessaie !")
