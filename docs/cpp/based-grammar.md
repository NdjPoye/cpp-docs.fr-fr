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
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 427906751c57b8b5f0c46479e8481394fa20f56c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="based-grammar"></a>Syntaxe __based
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 L'adressage est utile lorsque vous avez besoin d'exercer un contrôle précis sur le segment dans lequel les objets sont alloués (données statiques et dynamiques).  
  
 Le seul type d'adressage acceptable dans les compilations 32 et 64 bits est l'adressage « basé sur un pointeur » qui définit un type contenant un déplacement 32 ou 64 bits vers une base 32 ou 64 bits ou basé sur `void`.  
  
## <a name="grammar"></a>Grammaire  
 *en fonction de modificateur de plage*:  
 **__based (***base-expression***)    **  
  
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
