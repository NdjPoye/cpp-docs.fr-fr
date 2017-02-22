---
title: "__based, grammaire | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adressage basé sur"
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# __based, grammaire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 L'adressage est utile lorsque vous avez besoin d'exercer un contrôle précis sur le segment dans lequel les objets sont alloués \(données statiques et dynamiques\).  
  
 Le seul type d'adressage acceptable dans les compilations 32 et 64 bits est l'adressage « basé sur un pointeur » qui définit un type contenant un déplacement 32 ou 64 bits vers une base 32 ou 64 bits ou basé sur `void`.  
  
## Grammaire  
 *based\-range\-modifier* :  
 **\_\_based\(**  *base\-expression*  **\)**  
  
 *base\-expression* :  
 *based\-variablebased\-abstract\-declaratorsegment\-namesegment\-cast*  
  
 *based\-variable* :  
 *identifier*  
  
 *based\-abstract\-declarator* :  
 *abstract\-declarator*  
  
 *base\-type* :  
 *type\-name*  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Pointeurs basés sur](../cpp/based-pointers-cpp.md)