---
title: "feclearexcept | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "feclearexcept"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "feclearexcept"
  - "fenv/feclearexcept"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "feclearexcept (fonction)"
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# feclearexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Tente d’effacer les indicateurs d’exception à virgule flottante spécifiées par l’argument.  
  
## Syntaxe  
  
```  
int feclearexcept(  
   int excepts  
);  
```  
  
#### Paramètres  
 `excepts`  
 Pour effacer les indicateurs d’état exception.  
  
## Valeur de retour  
 Retourne zéro si `excepts` est égal à zéro, ou si toutes les exceptions spécifiées ont été effacées avec succès. Sinon, retourne une valeur différente de zéro.  
  
## Notes  
 Le `feclearexcept` fonction tente d’effacer flottante point indicateurs d’état exception spécifiées par `excepts`. La fonction prend en charge ces macros d’exceptions, définies dans fenv.h :  
  
|Macros d’exception|Description|  
|------------------------|-----------------|  
|FE\_DIVBYZERO|Une erreur de singularité ou pôle s’est produite dans une opération en virgule flottante précédemment ; une valeur infinie a été créée.|  
|FE\_INEXACT|La fonction a été forcée d’arrondir le résultat d’une opération en virgule flottante précédemment stocké.|  
|FE\_INVALID|Une erreur de domaine s’est produite lors d’une opération en virgule flottante plus tôt.|  
|FE\_OVERFLOW|Une erreur de plage s’est produite ; un résultat d’opération en virgule flottante précédent était trop grand pour être représenté.|  
|FE\_UNDERFLOW|Un résultat d’opération en virgule flottante précédent était trop petit pour être représentée en précision ; une valeur denormal a été créée.|  
|FE\_ALLEXCEPT|L’opération de bits OR de tous les prises en charge les exceptions de virgule flottante.|  
  
 Le `excepts` argument peut être zéro ou l’opérateur de bits OR d’un ou plusieurs des macros d’exception prises en charge. Le résultat de toute autre valeur d’argument est indéfini.  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`feclearexcept`|\<fenv.h\>|\<cfenv\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)