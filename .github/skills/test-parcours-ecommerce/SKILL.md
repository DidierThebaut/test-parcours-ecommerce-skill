---
name: test-parcours-ecommerce
description: "Analyser et tester le parcours utilisateur d'un site e-commerce, de la découverte d'un produit à la commande : tests exploratoires, fonctionnels et end-to-end, panier, checkout, paiement, responsive et accessibilité. Utiliser pour vérifier un tunnel d'achat, préparer des cas de test ou diagnostiquer un blocage de conversion."
argument-hint: "Indique l’URL du site, le parcours à tester et si un environnement de test est disponible"
user-invocable: true
---

# Tester un parcours utilisateur e-commerce

Vérifie le parcours d'achat du point de vue d'un client, repère les blocages et restitue des résultats reproductibles. Commence par tester le site existant ; ne modifie pas le code sauf si l'utilisateur demande une correction.

## Procédure

1. **Cadrer le test.** Repère l'URL ou l'application et le résultat attendu. Si le site ou le parcours n'est pas identifiable, demande l'URL et précise si un environnement de test, des données de test ou un compte dédié sont disponibles. Clarifie uniquement les points qui empêchent de tester sans risque.
2. **Inspecter avant d'agir.** Examine les pages, les commandes disponibles, la configuration et les tests existants. Identifie les étapes réellement présentes (par exemple catalogue, recherche, fiche produit, panier, livraison, paiement et confirmation) ; n'impose pas une étape absente du site. Réutilise les outils de navigateur ou le framework de test déjà présent dans le projet.
3. **Définir un scénario concret.** Énonce le profil et l'objectif du client, les prérequis, les données de test nécessaires et le résultat attendu à chaque étape. Couvre, selon le périmètre et les fonctions existantes :
   - trouver un produit via la navigation, la recherche ou les filtres ;
   - consulter la fiche et choisir une variante ou une quantité ;
   - ajouter au panier, vérifier son contenu, modifier une quantité et retirer un article ;
   - poursuivre en invité ou se connecter, compléter les coordonnées et choisir la livraison ;
   - saisir un code promotionnel si cette fonction existe ;
   - vérifier les validations, erreurs, récapitulatif, taxes et frais affichés ;
   - tester le paiement et la confirmation uniquement dans un environnement de test ;
   - vérifier les états vides, indisponibilités, erreurs et la reprise après une interruption pertinente.
4. **Exécuter sans risque.** Utilise des données fictives et des comptes dédiés. Sur un site public ou de production, limite-toi à la navigation et aux actions réversibles qui ne créent pas d'effets externes. Ne passe pas de commande réelle, ne déclenche pas de paiement, d'email, de réservation, de changement de stock ou d'autre action irréversible sans autorisation explicite et environnement approprié. N'invente pas de moyens de paiement ; n'utilise que les données de test documentées par le projet ou le fournisseur.
5. **Tester les conditions d'usage.** Vérifie au moins le format d'écran pertinent et, si demandé ou utile, le mobile, le clavier, les libellés accessibles, les messages d'erreur, les chargements, la navigation et la persistance du panier. Distingue un problème observé d'un risque qui n'a pas pu être vérifié.
6. **Automatiser si utile.** Si le dépôt contient un framework de tests, ajoute ou adapte un test de bout en bout ciblé en suivant ses conventions. Préfère des sélecteurs accessibles et stables, des assertions sur le résultat visible et des données isolées. Évite les temporisations fixes et les tests dépendants d'un service de paiement réel. Lance le test ciblé et rapporte précisément le résultat ; n'affirme pas qu'un test a réussi s'il n'a pas été exécuté.
7. **Diagnostiquer et corriger sur demande.** Pour chaque échec, fournis les étapes de reproduction, le résultat attendu et observé, les éléments de preuve disponibles et l'impact utilisateur. Si une correction est demandée, limite-la au défaut constaté, puis rejoue le scénario ou le test concerné.

## Restitution

Commence par le périmètre et l'environnement testés. Présente ensuite les étapes sous forme de tableau :

| Étape | Résultat attendu | Résultat observé | Statut |
|---|---|---|---|

Utilise les statuts **Réussi**, **Échec**, **Bloqué** ou **Non testé**. Pour chaque échec ou blocage, indique la reproduction, l'impact et une preuve utile (URL, capture ou sortie de test si disponible). Termine par les limites et les tests qui restent à faire. Ne confonds pas l'absence de défaut constaté avec une couverture exhaustive.
