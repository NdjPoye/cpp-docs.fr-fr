---
title: "Alignement avec malloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Alignement avec malloc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[malloc](../c-runtime-library/reference/malloc.md) est garanti pour retourner une mémoire qui est correctement alignée pour stocker un objet qui a un alignement simple et qui peut contenir la quantité de mémoire allouée.  Un *alignement simple* est un alignement qui est inférieur ou égal au plus grand alignement pris en charge par l'implémentation sans spécification d'alignement. \(Dans Visual C\+\+, il s'agit de l'alignement qui est requis pour un `double`, ou 8 octets.  Dans le code qui cible les plateformes 64 bits, il correspond à 16 octets.\) Par exemple, une allocation de quatre octets serait alignée sur une limite qui prend en charge un objet de quatre octets ou plus petit.  
  
 Visual C\+\+ permet les types qui ont un *alignement étendu*, également appelés types *sur\-alignés*.  Par exemple, les types SSE [\_\_m128](../cpp/m128.md) et `__m256`, et les types déclarés à l'aide de `__declspec(align(``n``))` où `n` est supérieur à 8, ont un alignement étendu.  L'alignement de la mémoire sur une limite adaptée à un objet qui requiert l'alignement étendu n'est pas garanti par `malloc`.  Pour allouer de la mémoire pour les types sur\-alignés, utilisez [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) et les fonctions liées.  
  
## Voir aussi  
 [Utilisation de la pile](../build/stack-usage.md)   
 [align](../cpp/align-cpp.md)   
 [\_\_declspec](../cpp/declspec.md)