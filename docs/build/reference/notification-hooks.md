---
title: "Raccordements de notification | Microsoft Docs"
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
  - "chargement différé de DLL, raccordements de notification"
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Raccordements de notification
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les raccordements de notification sont appelés juste avant que les mesures ci\-dessous ne soient prises dans la routine d'assistance :  
  
-   Le handle stocké vers la bibliothèque fait l'objet d'un contrôle visant à vérifier s'il a déjà été chargé.  
  
-   **LoadLibrary** est appelé pour tenter le chargement de la DLL.  
  
-   **GetProcAddress** est appelé pour tenter d'obtenir l'adresse de la procédure.  
  
-   Retour au thunk de chargement différé des importations.  
  
 Le raccordement de notification est activé :  
  
-   grâce à une nouvelle définition du pointeur **\_\_pfnDliNotifyHook2** initialisé pour pointer vers votre propre fonction qui reçoit les notifications ;  
  
     ou  
  
-   via une affectation du pointeur **\_\_pfnDliNotifyHook2** à la fonction de raccordement avant que ne soit adressé tout appel à la DLL que le programme charge en différé.  
  
 Si la notification est **dliStartProcessing**, la fonction de raccordement peut retourner :  
  
 NULL  
 L'assistance par défaut gère le chargement de la DLL.  Cela permet d'effectuer un appel visant uniquement à obtenir des informations.  
  
 pointeur fonction  
 Ignorez la gestion du chargement différé par défaut.  Cela vous permet de fournir votre propre gestionnaire de chargement.  
  
 Si la notification est **dliNotePreLoadLibrary**, la fonction de raccordement peut retourner :  
  
-   0, s'il s'agit uniquement d'obtenir des notifications d'information.  
  
-   le HMODULE pour la DLL chargée, s'il a chargé la DLL elle\-même.  
  
 Si la notification est **dliNotePreGetProcAddress**, la fonction de raccordement peut retourner :  
  
-   0, s'il s'agit uniquement d'obtenir des notifications d'information.  
  
-   l'adresse de la fonction importée, si la fonction de raccordement obtient l'adresse elle\-même.  
  
 Si la notification est **dliNoteEndProcessing**, la valeur de retour de la fonction de raccordement est ignorée.  
  
 Si ce pointeur est initialisé \(différent de zéro\), l'assistance de chargement différé appelle la fonction à certains stades de notification au cours de son exécution.  Le pointeur fonction a la définition suivante :  
  
```  
// The "notify hook" gets called for every call to the  
// delay load helper.  This allows a user to hook every call and  
// skip the delay load helper entirely.  
//  
// dliNotify == {  
//  dliStartProcessing |  
//  dliNotePreLoadLibrary  |  
//  dliNotePreGetProc |  
//  dliNoteEndProcessing}  
//  on this call.  
//  
ExternC  
PfnDliHook   __pfnDliNotifyHook2;  
  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 Les notifications passent dans une structure **DelayLoadInfo** et sont passées à la fonction de raccordement avec la valeur de notification.  Ces données sont identiques à celles qui sont utilisées par la routine d'assistance de chargement différé.  La valeur de notification est l'une des valeurs définies dans [Définitions des structures et constantes](../../build/reference/structure-and-constant-definitions.md).  
  
## Voir aussi  
 [Gestion et notification des erreurs](../../build/reference/error-handling-and-notification.md)