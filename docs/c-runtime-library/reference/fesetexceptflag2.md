---
title: "fesetexceptflag2 | Microsoft Docs"
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
  - "fesetexceptflag"
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
  - "fesetexceptflag"
  - "fenv/fesetexceptflag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fesetexceptflag (fonction)"
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# fesetexceptflag
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit les indicateurs d’état à virgule flottante spécifié dans l’environnement actuel à virgule flottante.  
  
## Syntaxe  
  
```  
int fesetexceptflag(  
     const fexcept_t *pstatus,  
     int excepts  
);  
  
```  
  
#### Paramètres  
 `pstatus`  
 Pointeur vers un  `fexcept_t` objet contenant les valeurs pour définir des indicateurs d’état de l’exception. L’objet peut être défini par un appel précédent à [fegetexceptflag](../Topic/fegetexceptflag1.md).  
  
 `excepts`  
 Pour définir les indicateurs d’état exception à virgule flottante.  
  
## Valeur de retour  
 Si tous les indicateurs d’état d’exception spécifiée sont définies correctement, retourne 0. Sinon, retourne une valeur différente de zéro.  
  
## Remarques  
 Le `fesetexceptflag` fonction définit l’état des indicateurs d’état de l’exception de virgule flottante spécifié par `excepts` aux valeurs correspondantes définies le `fexcept_t` objet pointé par `pstatus`.  Elle ne déclenche pas d’exceptions. Le `pstatus` pointeur doit pointer vers un valide `fexcept_t` objet, ou le comportement suivant n’est pas défini. Le `fesetexceptflag` fonction prend en charge ces valeurs de macros d’exception dans `excepts`, défini dans \< fenv.h \> :  
  
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
|`fesetexceptflag`|\<fenv.h\>|\<cfenv\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetexceptflag](../../c-runtime-library/reference/fegetexceptflag2.md)