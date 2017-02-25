---
title: "feraiseexcept | Microsoft Docs"
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
  - "feraiseexcept"
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
apitype: "HeaderDef"
f1_keywords: 
  - "feraiseexcept"
  - "fenv/feraiseexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "feraiseexcept (fonction)"
ms.assetid: 87e89151-83c2-4563-9a9a-45666245d437
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# feraiseexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déclenche les exceptions de virgule flottante spécifiées.  
  
## Syntaxe  
  
```  
int feraiseexcept(  
   int excepts  
);  
```  
  
#### Paramètres  
 `excepts`  
 Les exceptions de virgule flottante à déclencher.  
  
## Valeur de retour  
 Si toutes les exceptions spécifiées sont déclenchées avec succès, retourne 0.  
  
## Notes  
 Le `feraiseexcept` fonction tente de lever les exceptions de virgule flottante spécifiées par `excepts`.   Le `feraiseexcept` fonction prend en charge ces macros d’exceptions, définies dans \< fenv.h \> :  
  
|Macros d’exception|Description|  
|------------------------|-----------------|  
|FE\_DIVBYZERO|Une erreur de singularité ou pôle s’est produite dans une opération en virgule flottante précédemment ; une valeur infinie a été créée.|  
|FE\_INEXACT|La fonction a été forcée d’arrondir le résultat d’une opération en virgule flottante précédemment stocké.|  
|FE\_INVALID|Une erreur de domaine s’est produite lors d’une opération en virgule flottante plus tôt.|  
|FE\_OVERFLOW|Une erreur de plage s’est produite ; un résultat d’opération en virgule flottante précédent était trop grand pour être représenté.|  
|FE\_UNDERFLOW|Un résultat d’opération en virgule flottante précédent était trop petit pour être représentée en précision ; une valeur denormal a été créée.|  
|FE\_ALLEXCEPT|L’opération de bits OR de tous les prises en charge les exceptions de virgule flottante.|  
  
 Le `excepts` argument peut être égal à zéro, une des valeurs macro exception, ou l’opérateur de bits ou de deux ou plusieurs des macros d’exception prises en charge. Si une des macros d’exception spécifiée est FE\_OVERFLOW ou FE\_UNDERFLOW, l’exception FE\_INEXACT peut être émise en tant qu’effet secondaire.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la `#pragma fenv_access(on)` directive avant l’appel. Pour plus d'informations, consultez [fenv\_access](../../preprocessor/fenv-access.md).  
  
 **Microsoft Specific :** exceptions spécifiées dans `excepts` sont déclenchés dans l’ordre FE\_INVALID, FE\_DIVBYZERO, FE\_OVERFLOW, FE\_UNDERFLOW, FE\_INEXACT. Toutefois, FE\_INEXACT peut être déclenché lorsque FE\_OVERFLOW ou FE\_UNDERFLOW est déclenchée, même si non spécifié dans `excepts`.**Fin de la section spécifique à Microsoft**  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`feraiseexcept`|\<fenv.h\>|\<cfenv\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fetestexcept](../../c-runtime-library/reference/fetestexcept1.md)   
 [feupdateenv](../../c-runtime-library/reference/feupdateenv.md)