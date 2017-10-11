---
title: "Erreur irrécupérable 1311 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9aeb63e041ddfe26a8fc47afc838f2f5c3ce35d6
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1311"></a>Erreur irrécupérable 1311
Le format COFF ne peut pas initialiser de manière statique 'var' avec un nombre octet (s) d’une adresse  
  
 Une adresse dont la valeur n’est pas connue au moment de la compilation ne peut pas être affectée de manière statique à une variable dont le type possède un stockage inférieur à quatre octets.  
  
 Cette erreur peut se produire sur du code qui est sinon C++ valide.  
  
 L’exemple suivant montre une condition susceptibles de provoquer 1311.  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```
