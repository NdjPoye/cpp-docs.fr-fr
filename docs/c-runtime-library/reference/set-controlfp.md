---
title: "_set_controlfp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_controlfp"
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
  - "set_controlfp"
  - "_set_controlfp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_controlfp (fonction)"
  - "fonctions en virgule flottante, définir un mot de commande"
  - "set_controlfp (fonction)"
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _set_controlfp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit le mot de commande des virgules.  
  
## Syntaxe  
  
```  
void __cdecl _set_controlfp(  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### Paramètres  
 `newControl`  
 Nouvelles valeurs des bits du mot de contrôle.  
  
 `mask`  
 Masque pour de nouveaux bits du mot de contrôle à définir.  
  
## Valeur de retour  
 Aucun.  
  
## Notes  
 `_set_controlfp` est similaire à `_control87`, mais affecte uniquement le mot de commande des virgule flottante à `newControl`.  Les bits dans les valeurs indiquent l'état du contrôle à virgule flottante.  L'état du contrôle à virgule flottante permet au programme de modifier la précision, l'arrondi, et les modes d'infini dans le package math des virgules flottantes.  Vous pouvez également masquer ou démasquer des exceptions de virgules flottantes en utilisant `_set_controlfp`.  Pour plus d'informations, consultez [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md).  
  
 Cette fonction est ignorée lorsque vous utilisez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md) ou `/clr:pure` pour compiler car le Common Langage Runtime \(CLR\) ne prend en charge que la précision de virgule flottante par défaut.  
  
## Configuration requise  
  
|Routine|En\-tête requis|Compatibilité|  
|-------------|---------------------|-------------------|  
|`_set_controlfp`|\<float.h\>|processeurs x86 uniquement|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_clear87, \_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)