---
title: Modificateurs de commandes | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 610725bf52522cd5041d2f6dcadb422bf942458a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="command-modifiers"></a>Modificateurs de commandes
Vous pouvez spécifier un ou plusieurs modificateurs de commandes devant une commande, éventuellement séparée par des espaces ou des tabulations. Comme avec les commandes, modificateurs doivent être mis en retrait.  
  
|Modificateur|Objectif|  
|--------------|-------------|  
|@*commande*|Empêche l’affichage de la commande. Affichage par les commandes n’est pas supprimé. Par défaut, NMAKE répercute toutes les commandes exécutées. /S permet de supprimer l’affichage du makefile entier ; Utilisez **. En mode silencieux** pour supprimer l’affichage d’une partie du makefile.|  
|**-**[`number` ]*commande*|Désactive la vérification des erreurs pour *commande*. Par défaut, NMAKE s’arrête quand une commande retourne un code de sortie différent de zéro. If -`number` est utilisé, NMAKE s’arrête si le code de sortie dépasse `number`. Des espaces ou des onglets ne peut pas apparaître entre le tiret et *nombre.* Au moins un espace ou tabulation doit apparaître entre `number` et *commande*. Utilisez l’option /I pour désactiver la vérification des erreurs pour le makefile entier ; Utilisez **. Ignorer** pour désactiver la vérification des erreurs pour la partie du makefile.|  
|**!** *command*|Exécute *commande* pour chaque fichier dépendant si *commande* utilise  **$ \* \***  (tous les fichiers dépendants dans la dépendance) ou **$?** (tous les fichiers dépendants dans la dépendance avec un horodatage postérieur à la cible).|  
  
## <a name="see-also"></a>Voir aussi  
 [Commandes dans un makefile](../build/commands-in-a-makefile.md)