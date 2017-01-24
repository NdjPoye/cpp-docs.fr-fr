---
title: "_ReadWriteBarrier | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ReadWriteBarrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReadWriteBarrier (intrinsèque)"
  - "ReadWriteBarrier (intrinsèque)"
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ReadWriteBarrier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Limite les optimisations du compilateur qui peuvent réordonnancer les accès à la mémoire sur le point de l'appel.  
  
> [!CAUTION]
>  Les intrinsèques `_ReadBarrier`, `_WriteBarrier` et `_ReadWriteBarrier` du compilateur et la macro `MemoryBarrier` sont tous déconseillés et ne doivent pas être utilisés.  Pour la communication entre threads, utilisez des mécanismes tels que [atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md) et [std::atomic\<T\>](../standard-library/atomic.md), qui sont définis dans la [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md).  Pour l'accès au matériel, utilisez l'option [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) du compilateur avec le mot clé [volatile](../cpp/volatile-cpp.md).  
  
## Syntaxe  
  
```  
void _ReadWriteBarrier(void);  
```  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_ReadWriteBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 L'intrinsèque `_ReadWriteBarrier` limite les optimisations du compilateur qui peuvent supprimer ou réordonnancer les accès à la mémoire sur le point de l'appel.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [\_ReadBarrier](../intrinsics/readbarrier.md)   
 [\_WriteBarrier](../intrinsics/writebarrier.md)   
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)