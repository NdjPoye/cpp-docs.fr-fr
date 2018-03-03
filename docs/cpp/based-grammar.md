---
title: syntaxe __based | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a2cb2929fa595ad13746ea929217f41272a8189
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="based-grammar"></a>Syntaxe __based
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 L'adressage est utile lorsque vous avez besoin d'exercer un contrôle précis sur le segment dans lequel les objets sont alloués (données statiques et dynamiques).  
  
 Le seul type d'adressage acceptable dans les compilations 32 et 64 bits est l'adressage « basé sur un pointeur » qui définit un type contenant un déplacement 32 ou 64 bits vers une base 32 ou 64 bits ou basé sur `void`.  
  
## <a name="grammar"></a>Grammaire  
 *en fonction de modificateur de plage*:  
 **__based (***base-expression***)**   
  
 *expression de la base de*:  
 *based-variablebased-abstract-declaratorsegment-namesegment-cast*  
  
 *variable en fonction*:  
 *identifier*  
  
 *base-abstract-declarator*:  
 *abstract-declarator*  
  
 *type de base*:  
 *nom de type*  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Pointeurs based](../cpp/based-pointers-cpp.md)