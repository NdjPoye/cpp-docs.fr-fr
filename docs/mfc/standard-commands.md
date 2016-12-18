---
title: "Commandes standard | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ID de commande, commandes standard"
  - "commandes (C++), standard"
  - "Menu Edition (commandes standard)"
  - "menu Fichier"
  - "Aide, menus"
  - "identificateurs (C++), ID de commande"
  - "commandes OLE"
  - "ID définis par le programmeur (C++)"
  - "ID de commandes standard"
  - "commandes standard"
  - "commandes du menu Affichage"
  - "commandes du menu Fenêtre"
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Commandes standard
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit l'infrastructure de nombreux messages standards de commande.  Les ID pour les commandes prennent généralement la forme suivante :  
  
 **ID\_** *Source*\_*élément*  
  
 où la *Cource* est généralement un nom de menu et un *élément* est un élément de menu.  Par exemple, l'ID de commande pour la nouvelle commande du menu Fichier est `ID_FILE_NEW`.  Les identificateurs standard de commande sont indiqués en gras dans la documentation.  Les ID définis par le programmeur sont affichés dans une police qui diffère du texte environnant.  
  
 Voici une liste des commandes prises en charge les plus importantes :  
  
 *Commandes du Menu Fichier*  
 Nouveau, Ouvrir, Fermer, Sauvegarder, Sauvegarder sous, Mise en page, Configuration de l'impression, Impression, Aperçu avant impression, Sortie, et fichiers récemment utilisés.  
  
 *Commandes du menu édition*  
 Effacer, Tout effacer, Copier, Couper, Rechercher, Coller, Répéter, Remplacer, Sélectionnez tout, Annuler, Refaire.  
  
 *Commandes du menu Affichage*  
 Barre d'outils et barre d'état.  
  
 *Commandes du menu Fenêtre*  
 Nouveau, Arranger, Empiler, Mosaïque horizontale, Mosaïque verticale, et Séparer.  
  
 *Commandes du menu ? \(Aide\)*  
 Index, à l'aide, et A propos de.  
  
 *Commandes OLE du menu édition*  
 Insérer un nouvel objet, Editer un lien, Copier un lien, Collage spécial, et objet *typename* \(commandes verbales\).  
  
 L'infrastructure fournit différents niveaux de prise en charge de ces commandes.  Certaines commandes sont prises en charge uniquement comme ID définis de commande, tandis que d'autres sont prises en charge avec des implémentations complètes.  Par exemple, l'infrastructure implémente la commande ouverte dans le menu Fichier lorsque vous créez un objet document, en affichant une boîte de dialogue ouverte, et en ouvrant et lors de la lecture du fichier.  En revanche, vous devez implémenter des commandes du menu Edition vous\-même, les commandes comme **ID\_EDIT\_COPY** dépendent de la nature des données copiée.  
  
 Pour plus d'informations sur les commandes prises en charge et le niveau de l'implémentation fourni, consultez la [Note technique 22](../mfc/tn022-standard-commands-implementation.md).  Les commandes standards sont définies dans le fichier AFXRES.H.  
  
## Voir aussi  
 [Objets d'interface utilisateur et ID de commande](../mfc/user-interface-objects-and-command-ids.md)