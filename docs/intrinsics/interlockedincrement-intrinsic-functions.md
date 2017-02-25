---
title: "_InterlockedIncrement, fonctions intrins&#232;ques | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedIncrement_acq"
  - "_InterlockedIncrement16_rel_cpp"
  - "_InterlockedIncrement16_cpp"
  - "_InterlockedIncrement64_rel"
  - "_InterlockedIncrement_rel"
  - "_InterlockedIncrement64_nf"
  - "_InterlockedIncrement16_acq_cpp"
  - "_InterlockedIncrement_rel_cpp"
  - "_InterlockedIncrement64"
  - "_InterlockedIncrement64_rel_cpp"
  - "_InterlockedIncrement16_nf"
  - "_InterlockedIncrement16_rel"
  - "_InterlockedIncrement16_acq"
  - "_InterlockedIncrement_nf"
  - "_InterlockedIncrement_acq_cpp"
  - "_InterlockedIncrement64_cpp"
  - "_InterlockedIncrement64_acq_cpp"
  - "_InterlockedIncrement"
  - "_InterlockedIncrement_cpp"
  - "_InterlockedIncrement64_acq"
  - "_InterlockedIncrement16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedIncrement, intrinsèque"
  - "_InterlockedIncrement_acq, intrinsèque"
  - "_InterlockedIncrement_nf, intrinsèque"
  - "_InterlockedIncrement_rel, intrinsèque"
  - "_InterlockedIncrement16, intrinsèque"
  - "_InterlockedIncrement16_acq, intrinsèque"
  - "_InterlockedIncrement16_nf, intrinsèque"
  - "_InterlockedIncrement16_rel, intrinsèque"
  - "_InterlockedIncrement64, intrinsèque"
  - "_InterlockedIncrement64_acq, intrinsèque"
  - "_InterlockedIncrement64_nf, intrinsèque"
  - "_InterlockedIncrement64_rel, intrinsèque"
  - "InterlockedIncrement, intrinsèque"
  - "InterlockedIncrement_acq, intrinsèque"
  - "InterlockedIncrement_rel, intrinsèque"
  - "InterlockedIncrement16, intrinsèque"
  - "InterlockedIncrement64, intrinsèque"
  - "InterlockedIncrement64_acq, intrinsèque"
  - "InterlockedIncrement64_rel, intrinsèque"
ms.assetid: 37700615-f372-438b-bcef-d76e11839482
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _InterlockedIncrement, fonctions intrins&#232;ques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Fournit une prise en charge des intrinsèques du compilateur pour la fonction Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [InterlockedIncrement](http://msdn.microsoft.com/library/ms683614.aspx).  
  
## Syntaxe  
  
```  
long _InterlockedIncrement(  
   long * lpAddend  
);  
long _InterlockedIncrement_acq(  
   long * lpAddend  
);  
long _InterlockedIncrement_rel(  
   long * lpAddend  
);  
long _InterlockedIncrement_nf(  
   long * lpAddend  
);  
short _InterlockedIncrement16(  
   short * lpAddend  
);  
short _InterlockedIncrement16_acq(  
   short * lpAddend  
);  
short _InterlockedIncrement16_rel(  
   short * lpAddend  
);  
short _InterlockedIncrement16_nf (  
   short * lpAddend  
);  
__int64 _InterlockedIncrement64(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_acq(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_rel(  
   __int64 * lpAddend  
);   
__int64 _InterlockedIncrement64_nf(  
   __int64 * lpAddend  
);  
```  
  
#### Paramètres  
 \[in, out\] `lpAddend`  
 Pointeur vers la variable à incrémenter.  
  
## Valeur de retour  
 La valeur de retour est la valeur incrémentée résultante.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|En\-tête|  
|-----------------|------------------|--------------|  
|`_InterlockedIncrement`, `_InterlockedIncrement16`, `_InterlockedIncrement64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedIncrement_acq`, `_InterlockedIncrement_rel`, `_InterlockedIncrement_nf`, `_InterlockedIncrement16_acq`, `_InterlockedIncrement16_rel`, `_InterlockedIncrement16_nf`, `_InterlockedIncrement64_acq`, `_InterlockedIncrement64_rel`, `_InterlockedIncrement64_nf`|ARM|\<intrin.h\>|  
  
## Notes  
 Il existe plusieurs variantes de `_InterlockedIncrement` qui varient selon les types de données qu'elles impliquent et l'utilisation d'une sémantique acquire ou release spécifique au processeur.  
  
 La fonction `_InterlockedIncrement` opère sur des valeurs entières de 32 bits, `_InterlockedIncrement16` sur des valeurs entières de 16 bits et `_InterlockedIncrement64` sur des valeurs entières de 64 bits.  
  
 Sur les plateformes ARM, utilisez les fonctions intrinsèques avec des suffixes `_acq` et `_rel` si vous devez acquérir et libérer des éléments de la sémantique, comme le début et la fin d'une section critique.  La fonction intrinsèque avec un suffixe `_nf` \(pour « no fence », « pas de délimitation »\) n'agit pas comme une barrière mémoire.  
  
 La variable vers laquelle pointe le paramètre `lpAddend` doit être alignée sur une limite de 32 bits. Dans le cas contraire, cette fonction échoue sur les systèmes x86 multiprocesseurs et les systèmes autres que x86.  Pour plus d'informations, consultez [align](../cpp/align-cpp.md).  
  
 La fonction Win32 est déclarée dans `Wdm.h` ou `Ntddk.h`.  
  
 Ces routines sont disponibles seulement comme fonctions intrinsèques.  
  
## Exemple  
 Pour obtenir un exemple de l'utilisation de `_InterlockedIncrement`, consultez [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)