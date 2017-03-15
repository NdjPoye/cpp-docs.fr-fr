---
title: "ML Error Messages | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.errors.ml"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MASM (Microsoft Macro Assembler), ML error messages"
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Error Messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les messages d'erreur générés par les composants de MASM appartiennent à trois catégories :  
  
-   **erreurs irrécupérables.** Cela indique un problème grave qui empêché l'utilitaire de compléter son processus normal.  
  
-   **erreurs récupérables.** L'utilitaire peut effectuer son processus.  Si tel est le cas, son résultat n'est pas être celui que vous souhaitez.  
  
-   **avertissements.** ces messages indiquent les conditions qui peuvent vous empêcher d'obtenir les résultats que vous souhaitez.  
  
 Tous les messages d'erreur prennent la forme suivante :  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 où :  
  
 `Utility`  
 le programme qui a envoyé le message d'erreur.  
  
 *nom de fichier*  
 le fichier qui contient la condition erreur\-générante.  
  
 *Line*  
 la ligne approximative où la condition d'erreur existe.  
  
 *Error\_type*  
 Erreur irrécupérable, erreur, avertissement ou.  
  
 *Code*  
 L'unique 5 ou code d'erreur de 6 chiffres.  
  
 `Message_text`  
 une description courte et générale de la condition d'erreur.  
  
## Voir aussi  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)