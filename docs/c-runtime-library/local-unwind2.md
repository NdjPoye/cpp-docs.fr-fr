---
title: "_local_unwind2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_local_unwind2"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_local_unwind2"
  - "local_unwind2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_local_unwind2 (fonction)"
  - "local_unwind2 (fonction)"
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _local_unwind2
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fonction CRT interne.  Exécute tous les gestionnaires de terminaisons répertoriés dans la table d'étendue.  
  
## Syntaxe  
  
```  
void _local_unwind2(    PEXCEPTION_REGISTRATION xr,    int stop );  
```  
  
#### Paramètres  
 \[in\] `xr`  
 Enregistrement d'inscription associé à une table d'étendue.  
  
 \[in\] `stop`  
 Niveau lexical qui indique là où `_local_unwind2` doit s'arrêter.  
  
## Notes  
 Cette méthode est employé uniquement par l'environnement d'exécution.  N'appelez pas la méthode dans votre code.  
  
 Quand cette méthode exécute des gestionnaires de terminaisons, elle part du niveau lexical actuel et parcourt les autres situés au\-dessus jusqu'à atteindre celui indiqué par `stop`.  Elle n'exécute pas les gestionnaires de terminaisons au niveau indiqué par `stop`.  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)