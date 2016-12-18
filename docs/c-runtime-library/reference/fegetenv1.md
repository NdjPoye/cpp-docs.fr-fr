---
title: "fegetenv | Microsoft Docs"
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
  - "fetegenv"
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
  - "fegetenv"
  - "fenv/fegetenv"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fetegenv (fonction)"
ms.assetid: 68962421-6978-4b27-8e4c-ad1577830cf6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fegetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stocke l’environnement à virgule flottante en cours dans l’objet spécifié.  
  
## Syntaxe  
  
```  
int fegetenv(  
   fenv_t *penv  
);  
  
```  
  
#### Paramètres  
 `penv`  
 Pointeur vers un `fenv_t` objet pour contenir les valeurs à virgule flottante environnement actuel.  
  
## Valeur de retour  
 Retourne 0 si l’environnement à virgule flottante a été stockée dans `penv`. Sinon, retourne une valeur différente de zéro.  
  
## Notes  
 Le `fegetenv` fonction stocke l’environnement à virgule flottante dans l’objet désigné par `penv`. Flottante de l’environnement est le jeu d’indicateurs d’état et les modes de contrôle qui affectent les calculs à virgule flottante. Cela inclut le mode d’arrondi sens et les indicateurs d’état pour les exceptions de virgule flottante. Si `penv` ne pointe pas vers un `fenv_t` de l’objet, le comportement suivant n’est pas défini.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la `#pragma fenv_access(on)` directive avant l’appel. Pour plus d'informations, consultez [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`fegetenv`|\<fenv.h\>|\<cfenv\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fesetenv](../../c-runtime-library/reference/fesetenv1.md)