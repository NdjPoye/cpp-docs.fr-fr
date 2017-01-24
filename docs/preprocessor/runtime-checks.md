---
title: "runtime_checks | Microsoft Docs"
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
  - "vc-pragma.runtime_checks"
  - "runtime_checks_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "runtime_checks (pragma)"
  - "pragmas (runtime_checks)"
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# runtime_checks
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Désactive ou restaure les paramètres [\/RTC](../build/reference/rtc-run-time-error-checks.md).  
  
## Syntaxe  
  
```  
  
#pragma runtime_checks(  
"[runtime_checks]", {restore | off} )  
```  
  
## Notes  
 Vous ne pouvez pas activer un contrôle à l'exécution qui n'a pas été activé via une option du compilateur. Par exemple, si vous ne spécifiez aucun paramètre \/RTC, la spécification de `#pragma runtime_checks( "s", restore)` n'active pas la vérification du frame de pile.  
  
 Le pragma **runtime\_checks** doit apparaître à l'extérieur d'une fonction et prend effet à la première fonction définie après sa détection. Les arguments **restore** et **off** activent ou désactivent les options spécifiées dans *runtime\_checks*.  
  
 Le pragma *runtime\_checks* peut être égal à zéro ou plusieurs des paramètres indiqués dans le tableau suivant.  
  
### Paramètres du pragma runtime\_checks  
  
|Paramètre\(s\)|Type de contrôle à l'exécution|  
|--------------------|------------------------------------|  
|**s**|Active la vérification de pile \(frame\).|  
|**c**|Signale quand une valeur est assignée à un type de données plus petit qui se traduit par une perte de données.|  
|**u**|Signale quand une variable est utilisée avant d'être définie.|  
  
 Ce sont les mêmes lettres que celles utilisées avec l'option du compilateur \/RTC. Exemple :  
  
```  
#pragma runtime_checks( "sc", restore )  
```  
  
 L'utilisation du pragma **runtime\_checks** avec la chaîne vide \(**""**\) est une forme particulière de la directive :  
  
-   Lorsque vous utilisez le paramètre **off**, il désactive les contrôles d'erreurs à l'exécution, répertoriés dans le tableau ci\-dessus.  
  
-   Lorsque vous utilisez le paramètre **restore**, il réinitialise les contrôles d'erreurs à l'exécution à ceux que vous avez spécifiés avec l'option du compilateur \/RTC.  
  
```  
#pragma runtime_checks( "", off )  
.  
.  
.  
#pragma runtime_checks( "", restore )   
```  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [RTC sample](http://msdn.microsoft.com/fr-fr/b3415b09-f6fd-43dc-8c02-9a910bc2574e)