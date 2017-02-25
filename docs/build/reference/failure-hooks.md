---
title: "Raccordements de d&#233;faillance | Microsoft Docs"
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
  - "chargement différé de DLL, raccordements de défaillance"
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Raccordements de d&#233;faillance
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le raccordement de défaillance est activé de la même façon que le [raccordement de notification](../../build/reference/notification-hooks.md).  La routine de raccordement doit retourner soit une valeur appropriée permettant la poursuite du traitement \(HINSTANCE ou FARPROC\), soit 0 pour indiquer qu'une exception doit être générée.  
  
 La variable pointeur qui fait référence à la fonction définie par l'utilisateur est :  
  
```  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 La structure **DelayLoadInfo** contient toutes les données pertinentes nécessaires pour une notification exacte de l'erreur, y compris la valeur issue de `GetLastError`.  
  
 Si la notification est **dliFailLoadLib**, la fonction de raccordement peut retourner :  
  
-   0 en cas d'impossibilité de gérer la défaillance.  
  
-   Un HMODULE, si le raccordement de défaillance a résolu le problème et chargé lui\-même la bibliothèque.  
  
 Si la notification est **dliFailGetProc**, la fonction de raccordement peut retourner :  
  
-   0 en cas d'impossibilité de gérer la défaillance.  
  
-   Une adresse de procédure valide \(adresse de fonction d'importation\), si le raccordement de défaillance a réussi à obtenir l'adresse elle\-même.  
  
## Voir aussi  
 [Gestion et notification des erreurs](../../build/reference/error-handling-and-notification.md)