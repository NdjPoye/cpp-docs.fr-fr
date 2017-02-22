---
title: "Modificateurs de commandes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modificateurs de commandes"
  - "programme NMAKE, modificateurs de commandes"
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Modificateurs de commandes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez spécifier un ou plusieurs modificateurs de commandes devant une commande, séparés facultativement par des espaces ou des tabulations.  Comme avec les commandes, les modificateurs doivent être mis en retrait.  
  
|Modificateur|Objectif|  
|------------------|--------------|  
|@*commande*|Empêche l'affichage de la commande.  L'affichage par les commandes n'est pas supprimé.  Par défaut, NMAKE répercute toutes les commandes exécutées.  Utilisez l'option \/S pour supprimer l'affichage du makefile entier ; utilisez **.SILENT** pour supprimer l'affichage d'une partie seulement du makefile.|  
|**–**\[`number` \]*commande*|Désactive la vérification des erreurs pour *commande*.  Par défaut, NMAKE s'arrête quand une commande retourne un code de sortie différent de zéro.  Si le modificateur –`number` est utilisé, NMAKE s'arrête si le code de sortie dépasse `number`.  Les espaces et les tabulations sont interdits entre le tiret et le *nombre.* Il faut au minimum un espace ou une tabulation entre `number` et *commande*.  Utilisez l'option \/I pour désactiver la vérification des erreurs pour le makefile entier et **.IGNORE** pour une partie seulement du makefile.|  
|**\!** *commande*|Exécute *commande* pour chaque fichier dépendant si *commande* utilise **$\*\*** \(tous les fichiers dépendants dans la dépendance\) ou **$?** \(tous les fichiers dépendants dans la dépendance avec un horodatage postérieur à celui de la cible\).|  
  
## Voir aussi  
 [Commandes dans un makefile](../build/commands-in-a-makefile.md)