---
title: "fesetenv | Microsoft Docs"
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
  - "fesetenv"
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
  - "fesetenv"
  - "fenv/fesetenv"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fesetenv (fonction)"
ms.assetid: ffc64fff-8ea7-4d59-9e04-ff96ef8cd012
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fesetenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit l’environnement à virgule flottante.  
  
## Syntaxe  
  
```  
int fesetenv(  
   const fenv_t *penv  
);  
  
```  
  
#### Paramètres  
 `penv`  
 Pointeur vers un `fenv_t` un objet contenant un environnement à virgule flottante en tant que jeu par un appel à [fegetenv](../Topic/fegetenv2.md) ou [feholdexcept](../Topic/feholdexcept1.md). Vous pouvez également spécifier l’environnement à virgule flottante de démarrage par défaut à l’aide de la macro FE\_DFL\_ENV.  
  
## Valeur de retour  
 Retourne 0 si l’environnement a été correctement définie. Sinon, retourne une valeur différente de zéro.  
  
## Notes  
 Le `fesetenv` fonction affecte l’environnement actuel et à virgule flottante à partir de la valeur stockée dans le `fenv_t` objet pointé par `penv`. Flottante de l’environnement est le jeu d’indicateurs d’état et les modes de contrôle qui affectent les calculs à virgule flottante. Cela inclut le mode d’arrondi et les indicateurs d’état pour les exceptions de virgule flottante. Si `penv` n’est pas FE\_DFL\_ENV ou ne pointe pas vers un `fenv_t` de l’objet, le comportement suivant n’est pas défini.  
  
 Un appel à cette fonction définit l’exception des indicateurs d’état qui se trouvent dans le `penv` objet, mais il ne déclenche pas ces exceptions.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la `#pragma fenv_access(on)` directive avant l’appel. Pour plus d'informations, consultez [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`fesetenv`|\<fenv.h\>|\<cfenv\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)