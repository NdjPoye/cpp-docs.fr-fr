---
title: "Liaison des noms avec portée de bloc | Documents Microsoft"
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
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- block scope [C++]
- external linkage, scope linkage rules
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: de093c90e0da4a906d8aefebfb7048733c1a1f1d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="linkage-in-names-with-block-scope"></a>Liaison des noms avec la portée de bloc
Les règles de liaison suivantes s’appliquent aux noms avec une portée de bloc (noms locaux) :  
  
-   Noms déclarés en tant que `extern` ont une liaison externe, sauf si elles ont été précédemment déclarés comme **statique**.  
  
-   Tous les autres noms avec portée de bloc ne possèdent pas de liaison.  
  
## <a name="see-also"></a>Voir aussi  
 [Programme et liaison](../cpp/program-and-linkage-cpp.md)
