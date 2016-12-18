---
title: "fetestexcept | Microsoft Docs"
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
  - "fetestexcept"
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
  - "fetestexcept"
  - "fenv/fetestexcept"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fetestexept (fonction)"
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fetestexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine les indicateurs d’état de l’exception à virgule flottante spécifiée sont actuellement définis.  
  
## Syntaxe  
  
```  
int fetestexcept(  
   int excepts  
);  
  
```  
  
#### Paramètres  
 `excepts`  
 Une opération de bits OR des indicateurs d’état à virgule flottante à tester.  
  
## Valeur de retour  
 En cas de réussite, retourne un masque de bits qui contient une opération OR au niveau du bit des macros d’exception à virgule flottante qui correspondent aux indicateurs d’état de l’exception actuellement définies. Retourne 0 si aucune des exceptions est définies.  
  
## Notes  
 La fonction fetestexcept permet de déterminer les exceptions levées par flottante pointez l’opération. Utilisez le `excepts` pour spécifier les indicateurs d’état exception à tester. Le `fetestexcept` fonction utilise ces macros d’exception définies dans \< fenv.h \> de `excepts` et la valeur de retour :  
  
|Macros d’exception|Description|  
|------------------------|-----------------|  
|FE\_DIVBYZERO|Une erreur de singularité ou pôle s’est produite dans une opération en virgule flottante précédemment ; une valeur infinie a été créée.|  
|FE\_INEXACT|La fonction a été forcée d’arrondir le résultat d’une opération en virgule flottante précédemment stocké.|  
|FE\_INVALID|Une erreur de domaine s’est produite lors d’une opération en virgule flottante plus tôt.|  
|FE\_OVERFLOW|Une erreur de plage s’est produite ; un résultat d’opération en virgule flottante précédent était trop grand pour être représenté.|  
|FE\_UNDERFLOW|Un résultat d’opération en virgule flottante précédent était trop petit pour être représentée en précision ; une valeur denormal a été créée.|  
|FE\_ALLEXCEPT|L’opération de bits OR de tous les prises en charge les exceptions de virgule flottante.|  
  
 Spécifié `excepts` argument peut être 0, un de l’exception de virgule flottante prises en charge des macros ou l’opérateur de bits ou de deux ou plusieurs des macros. L’effet de n’importe quel autre `excepts` valeur d’argument n’est pas défini.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la `#pragma fenv_access(on)` directive avant l’appel. Pour plus d'informations, consultez [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`fetestexcept`|\<fenv.h\>|\<cfenv\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feraiseexcept](../../c-runtime-library/reference/feraiseexcept.md)