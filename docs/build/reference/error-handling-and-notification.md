---
title: "Gestion et notification des erreurs | Microsoft Docs"
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
  - "gestion des erreurs, et la notification"
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Gestion et notification des erreurs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour plus d'informations sur la gestion et la notification des erreurs, consultez [Présentation de la fonction d'assistance](http://msdn.microsoft.com/fr-fr/6279c12c-d908-4967-b0b3-cabfc3e91d3d).  
  
 Pour plus d'informations sur les fonctions de raccordement, consultez [Définitions des structures et constantes](../../build/reference/structure-and-constant-definitions.md).  
  
 Si votre programme utilise les DLL à chargement différé, il doit assurer une gestion très stricte des erreurs dans la mesure où les défaillances qui interviennent au moment de l'exécution du programme provoquent des exceptions non gérées.  La gestion des défaillances se déroule en deux phases :  
  
 Récupération à l'aide d'un raccordement.  
 Si votre code doit récupérer ou fournir une autre bibliothèque et\/ou routine à l'occasion d'une défaillance, un raccordement peut être fourni à la fonction d'assistance pour revenir à une situation normale.  La routine de raccordement doit retourner soit une valeur appropriée permettant la poursuite du traitement de continuer \(HINSTANCE ou FARPROC\), soit 0 pour indiquer qu'une exception doit être générée.  Elle peut également générer sa propre exception ou **longjmp**  à partir du raccordement.  Il existe des raccordements de notification et des raccordements de défaillance.  
  
 Notification via une exception.  
 S'il suffit d'annuler la procédure pour gérer l'erreur, aucun raccordement n'est nécessaire tant que le code utilisateur peut gérer l'exception.  
  
 Les rubriques suivantes traitent de la gestion et de la notification des erreurs :  
  
-   [Raccordements de notification](../../build/reference/notification-hooks.md)  
  
-   [Raccordements de défaillance](../../build/reference/failure-hooks.md)  
  
-   [Exceptions](../../build/reference/exceptions-c-cpp.md)  
  
## Voir aussi  
 [Prise en charge de l'éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)