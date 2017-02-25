---
title: "Prise en charge de l&#39;&#233;diteur de liens pour les DLL &#224; chargement diff&#233;r&#233; | Microsoft Docs"
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
  - "chargement différé de DLL, prise en charge de l'éditeur de liens"
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Prise en charge de l&#39;&#233;diteur de liens pour les DLL &#224; chargement diff&#233;r&#233;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'éditeur de liens Visual C\+\+ prend désormais en charge le chargement différé des DLL.  Cela vous évite d'utiliser les fonctions **LoadLibrary** et **GetProcAddress** de [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] pour implémenter le chargement différé des DLL.  
  
 Avant Visual C\+\+ 6.0, la seule façon de charger une DLL au moment de l'exécution consistait à utiliser **LoadLibrary** et **GetProcAddress** ; le système d'exploitation chargeait la DLL lors du chargement de l'exécutable ou de la DLL qui l'utilisait.  
  
 À partir de Visual C\+\+ 6.0, lors de l'édition statique de liens avec une DLL, l'éditeur de liens fournit les options permettant de différer le chargement de la DLL jusqu'au moment où le programme appelle une fonction de cette DLL.  
  
 Une application peut différer le chargement d'une DLL à l'aide de l'option [\/DELAYLOAD \(Différer le chargement de l'importation\)](../../build/reference/delayload-delay-load-import.md) de l'éditeur de liens avec une fonction d'assistance \(implémentation par défaut assurée par Visual C\+\+\).  La fonction d'assistance charge la DLL au moment de l'exécution en appelant **LoadLibrary** et **GetProcAddress** à votre place.  
  
 Vous devez envisager le chargement différé d'une DLL dans les cas suivants :  
  
-   Votre programme n'appelle pas une fonction dans la DLL.  
  
-   Une fonction de la DLL n'est appelée que tardivement au cours de l'exécution de votre programme.  
  
 Le chargement différé d'une DLL peut être spécifié pendant la génération d'un projet .EXE ou .DLL.  Un projet .DLL qui diffère le chargement d'une ou de plusieurs DLL ne doit pas lui\-même appeler un point d'entrée au chargement différé dans Dllmain.  
  
 Les rubriques suivantes décrivent le chargement différé des DLL :  
  
-   [Spécification de DLL dont le chargement doit être différé](../../build/reference/specifying-dlls-to-delay-load.md)  
  
-   [Déchargement explicite d'une DLL à chargement différé](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
-   [Chargement de toutes les importations pour une DLL à chargement différé](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)  
  
-   [Liaison d'importations](../../build/reference/binding-imports.md)  
  
-   [Gestion et notification des erreurs](../../build/reference/error-handling-and-notification.md)  
  
-   [Dump des importations à chargement différé](../../build/reference/dumping-delay-loaded-imports.md)  
  
-   [Contraintes relatives aux DLL à chargement différé](../../build/reference/constraints-of-delay-loading-dlls.md)  
  
-   [Fonctionnement de la fonction d'assistance](http://msdn.microsoft.com/fr-fr/6279c12c-d908-4967-b0b3-cabfc3e91d3d)  
  
-   [Développement de votre propre fonction d'assistance](../../build/reference/developing-your-own-helper-function.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../../build/dlls-in-visual-cpp.md)   
 [Liaison](../../build/reference/linking.md)