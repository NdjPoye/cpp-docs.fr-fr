---
title: "offsetof, macro | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
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
apitype: "DLLExport"
f1_keywords: 
  - "offsetof"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "offsetof (macro)"
  - "membres de structures, offset"
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# offsetof, macro
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère le décalage d'un membre au début de sa structure parent.  
  
## Syntaxe  
  
```  
  
        size_t offsetof(  
   structName,  
   memberName   
);  
```  
  
#### Paramètres  
 *structName*  
 Nom de la structure de données parent.  
  
 `memberName`  
 Nom du membre dans la structure de données parent pour lequel le décalage doit être déterminé.  
  
## Valeur de retour  
 `offsetof` retourne le décalage en octets du membre spécifié au début de sa structure de données parent.  Il n'est pas défini pour les champs de bits.  
  
## Notes  
 La macro `offsetof` retourne le décalage en octets de `memberName` à partir du début de la structure spécifiée par *structName* sous de valeur de type `size_t`.  Vous pouvez spécifier les types avec le mot clé `struct`.  
  
> [!NOTE]
>  `offsetof` n'est pas une fonction et ne peut pas être décrite à l'aide d'un prototype C.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`offsetof`|\<stddef.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)