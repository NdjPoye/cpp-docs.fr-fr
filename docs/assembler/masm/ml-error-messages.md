---
title: "Messages d’erreur ML | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09478bd3cff63e890014c6c14b11335feb8dfb3f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="ml-error-messages"></a>Messages d'erreur ML
Les messages d’erreur générés par les composants MASM se répartissent en trois catégories :  
  
-   **Erreurs irrécupérables.** Celles-ci indiquent un problème grave qui empêche l’utilitaire à partir de la fin de son processus normal.  
  
-   **Erreurs récupérables.** L’utilitaire peut terminer son processus. Dans ce cas, son résultat n’est pas susceptible d’être celle qui que vous intéresse.  
  
-   **Avertissements.** Ces messages indiquent les conditions qui peuvent vous empêcher d’obtenir les résultats souhaités.  
  
 Tous les messages d’erreur prennent la forme suivante :  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 où :  
  
 `Utility`  
 Le programme qui a envoyé le message d’erreur.  
  
 *Filename*  
 Le fichier qui contient la condition de la génération d’erreur.  
  
 *Line*  
 La ligne approximative où se trouve la condition d’erreur.  
  
 *Error_type*  
 Irrécupérable erreur, erreur ou avertissement.  
  
 *Code*  
 Le code d’erreur unique 5 ou 6 chiffres.  
  
 `Message_text`  
 Description courte et générale de la condition d’erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur Microsoft Macro Assembler](../../assembler/masm/microsoft-macro-assembler-reference.md)