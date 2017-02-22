---
title: "fegetexceptflag2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fegetexceptflag"
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
  - "fegetexceptflag"
  - "fenv/fegetexceptflag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fegetexceptflag (fonction)"
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# fegetexceptflag
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stocke l’état actuel des indicateurs d’exception à virgule flottante spécifiée.  
  
## Syntaxe  
  
```  
int fegetexceptflag(   
   fexcept_t* pstatus,   
   int excepts   
);  
  
```  
  
#### Paramètres  
 `pstatus`  
 Un pointeur vers un `fexcept_t` objet pour contenir les valeurs actuelles des indicateurs d’exception spécifiés par `excepts`.  
  
 `excepts`  
 Les indicateurs d’exception de virgule flottante à stocker dans `pstatus`.  
  
## Valeur de retour  
 En cas de réussite, retourne 0. Sinon, retourne une valeur différente de zéro.  
  
## Notes  
 Le `fegetexceptflag` fonction stocke l’état actuel des indicateurs d’état de l’exception de virgule flottante spécifié par `excepts` dans le `fexcept_t` objet pointé par `pstatus`.`pstatus` doit pointer vers un valide `fexcept_t` objet, ou le comportement suivant n’est pas défini. Le `fegetexceptflag` fonction prend en charge ces macros d’exceptions, définies dans \< fenv.h \> :  
  
|Macros d’exception|Description|  
|------------------------|-----------------|  
|FE\_DIVBYZERO|Une erreur de singularité ou pôle s’est produite dans une opération en virgule flottante précédemment ; une valeur infinie a été créée.|  
|FE\_INEXACT|La fonction a été forcée d’arrondir le résultat d’une opération en virgule flottante précédemment stocké.|  
|FE\_INVALID|Une erreur de domaine s’est produite lors d’une opération en virgule flottante plus tôt.|  
|FE\_OVERFLOW|Une erreur de plage s’est produite ; un résultat d’opération en virgule flottante précédent était trop grand pour être représenté.|  
|FE\_UNDERFLOW|Un résultat d’opération en virgule flottante précédent était trop petit pour être représentée en précision ; une valeur denormal a été créée.|  
|FE\_ALLEXCEPT|L’opération de bits OR de tous les prises en charge les exceptions de virgule flottante.|  
  
 Le `excepts` argument peut être égal à zéro, un de l’exception de virgule flottante prises en charge des macros ou l’opérateur de bits ou de deux ou plusieurs des macros. L’effet de toute autre valeur d’argument n’est pas défini.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la `#pragma fenv_access(on)` directive avant l’appel. Pour plus d'informations, consultez [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`fegetexceptflag`|\<fenv.h\>|\<cfenv\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)