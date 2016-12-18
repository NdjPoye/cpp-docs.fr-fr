---
title: "feupdateenv | Microsoft Docs"
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
  - "feupdateenv"
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
  - "feupdateenv"
  - "fenv/feupdateenv"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "feupdateenv (fonction)"
ms.assetid: 3d170042-dfd5-4e4f-a55f-038cf2296cc9
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# feupdateenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Enregistre les exceptions en virgule flottante en relief, restaure l’état de l’environnement à virgule flottante spécifié, puis lève les exceptions de virgule flottante enregistrées.  
  
## Syntaxe  
  
```  
int feupdateenv(  
   const fenv_t* penv  
);  
```  
  
#### Paramètres  
 `penv`  
 Pointeur vers un `fenv_t` un objet contenant un environnement à virgule flottante en tant que jeu par un appel à [fegetenv](../Topic/fegetenv2.md) ou [feholdexcept](../Topic/feholdexcept1.md). Vous pouvez également spécifier l’environnement à virgule flottante de démarrage par défaut à l’aide de la macro FE\_DFL\_ENV.  
  
## Valeur de retour  
 Retourne 0 si toutes les actions terminées avec succès. Sinon, retourne une valeur différente de zéro.  
  
## Notes  
 Le `feupdateenv` fonction effectue plusieurs actions. Tout d’abord, il stocke les indicateurs d’état déclenché exception à virgule flottante en cours de stockage automatique. Ensuite, il définit l’environnement actuel et à virgule flottante à partir de la valeur stockée dans le `fenv_t` objet pointé par `penv`. Si `penv` n’est pas FE\_DFL\_ENV ou ne pointe pas vers un `fenv_t` de l’objet, le comportement suivant n’est pas défini. Enfin, `feupdateenv` déclenche les exceptions de virgule flottante stockées localement.  
  
 Pour utiliser cette fonction, vous devez désactiver les optimisations à virgule flottante qui peuvent empêcher l’accès à l’aide de la `#pragma fenv_access(on)` directive avant l’appel. Pour plus d'informations, consultez [fenv\_access](../../preprocessor/fenv-access.md).  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`feupdateenv`|\<fenv.h\>|\<cfenv\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [fegetenv](../../c-runtime-library/reference/fegetenv1.md)   
 [feclearexcept](../../c-runtime-library/reference/feclearexcept1.md)   
 [feholdexcept](../../c-runtime-library/reference/feholdexcept2.md)   
 [fesetexceptflag](../../c-runtime-library/reference/fesetexceptflag2.md)