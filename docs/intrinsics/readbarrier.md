---
title: "_ReadBarrier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ReadBarrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReadBarrier (intrinsèque)"
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _ReadBarrier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Limite les optimisations du compilateur qui peuvent réordonnancer les opérations d'accès à la mémoire sur le point de l'appel.  
  
> [!CAUTION]
>  Les intrinsèques `_ReadBarrier`, `_WriteBarrier` et `_ReadWriteBarrier` du compilateur et la macro `MemoryBarrier` sont tous déconseillés et ne doivent pas être utilisés.  Pour la communication entre threads, utilisez des mécanismes tels que [atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md) et [std::atomic\<T\>](../standard-library/atomic.md), qui sont définis dans la [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md).  Pour l'accès au matériel, utilisez l'option [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) du compilateur avec le mot clé [volatile](../cpp/volatile-cpp.md).  
  
## Syntaxe  
  
```  
void _ReadBarrier(void);  
```  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_ReadBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 L'intrinsèque `_ReadBarrier` limite les optimisations du compilateur qui peuvent supprimer ou réordonnancer les opérations d'accès à la mémoire sur le point de l'appel.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)