---
title: "Conflits avec le compilateur&#160;x86 | Microsoft Docs"
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
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Conflits avec le compilateur&#160;x86
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les types de données qui sont plus grands que 4 octets ne sont pas alignés automatiquement sur la pile lorsque vous utilisez le compilateur x86 pour compiler une application.  Parce que l'architecture pour le compilateur x86 est une pile alignée de 4 octets, toute valeur supérieure à 4 octets \(par exemple, un entier 64 bits\) ne peut pas être alignée automatiquement à une adresse de 8 octets.  
  
 L'utilisation de données non alignées a deux conséquences.  
  
-   L'accès aux emplacements non alignés peut prendre plus de temps qu'il n'en faut pour accéder aux emplacements alignés.  
  
-   Les emplacements non alignés ne peuvent pas être utilisés dans les opérations verrouillées.  
  
 Si vous avez besoin d'un alignement plus strict, utilisez `__declspec(align(N)) on your variable declarations`.  Le compilateur aligne alors dynamiquement la pile, selon vos spécifications.  Toutefois, l'ajustement dynamique de la pile au moment de l'exécution peut provoquer une exécution plus lente de votre application.  
  
## Voir aussi  
 [Types et stockage](../build/types-and-storage.md)   
 [align](../cpp/align-cpp.md)