---
title: "_CrtSetReportHook | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetReportHook"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_CrtSetReportHook"
  - "CrtSetReportHook"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtSetReportHook (fonction)"
  - "_CrtSetReportHook (fonction)"
ms.assetid: 1ae7c64f-8c84-4797-9574-b59f00f7a509
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtSetReportHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Installe une fonction de rapport définie par le client en l'accrochant dans le processus de création de débogage du runtime C \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
_CRT_REPORT_HOOK _CrtSetReportHook(   
   _CRT_REPORT_HOOK reportHook   
);  
```  
  
#### Paramètres  
 `reportHook`  
 Nouvelle fonction de rapport définie par le client à connecter dans le processus de création de débogage du runtime C.  
  
## Valeur de retour  
 Renvoie la fonction de rapport définie par le client précédent.  
  
## Notes  
 `_CrtSetReportHook` permet à une application d'utiliser sa propre fonction de rapport dans le processus de création de bibliothèque de débogage du runtime C.  Par conséquent, lorsque [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) est appelé pour générer un rapport de débogage, la fonction de rapport de l'application est d'abord appelée.  Cette fonctionnalité permet à une application d'exécuter des opérations telles que le filtrage des rapports de débogage elle peut se concentrer sur des types spécifiques d'allocation ou envoyer un rapport aux destinations qui ne sont pas disponibles à l'aide de `_CrtDbgReport`.  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, Les appels de `_CrtSetReportHook` sont supprimés pendant le prétraitement.  
  
 Pour une version plus fiable de `_CrtSetReportHook`, consultez [\_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md).  
  
 La fonction `_CrtSetReportHook` installe la nouvelle fonction de rapport définie par le client spécifiée dans `reportHook` et renvoie le raccordement défini par le client précédent.  L'exemple suivant montre comment un raccordement défini par le client de rapport doit être prototypé:  
  
```  
int YourReportHook( int reportType, char *message, int *returnValue );  
```  
  
 alors que `reportType` est le type de rapport de débogage \(`_CRT_WARN`, `_CRT_ERROR`, ou `_CRT_ASSERT`\), `message` est le message utilisateur entièrement assemblé de débogage à inclure dans le rapport, et `returnValue` est la valeur définie par la fonction de rapport définie par le client qui doit être retournée par `_CrtDbgReport`.  Pour une description complète des types disponibles du rapport, consultez la fonction [\_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md).  
  
 Si la fonction de rapport définie par le client traite complètement le message de débogage tels qu'aucun rapport supplémentaire n'est requis, la fonction doit renvoyer `TRUE`.  Lorsque la fonction renvoie `FALSE`, `_CrtDbgReport` est appelé pour créer le rapport de débogage avec les paramètres actuels du type, le mode, et le fichier de rapport.  En outre, en spécifiant la valeur de retour de `_CrtDbgReport` dans `returnValue`, l'application peut également contrôler si un saut de débogage s'est produit.  Pour une description complète sur comment le rapport de débogage est configuré et généré, consultez `_CrtSetReportMode`, [\_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md), et `_CrtDbgReport`.  
  
 Pour plus d'informations sur l'utilisation d'autres fonctions runtime raccordement\- capables et écrire vos propres fonctions de raccordement définies par le client, consultez [Écriture de fonctions de raccordement de débogage](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
> [!NOTE]
>  Si votre application est compilée avec `/clr` et la fonction de rapport est appelée après que l'application ai arrêté Main, le CLR lève une exception si les fonction de rapport appellent n'importe quelle fonction CRT.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_CrtSetReportHook`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_CrtGetReportHook](../../c-runtime-library/reference/crtgetreporthook.md)