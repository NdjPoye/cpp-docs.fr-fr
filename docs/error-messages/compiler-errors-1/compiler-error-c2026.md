---
title: Erreur du compilateur C2026 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 97937579c12730fecfa89c69d9e7cf51229b5c6c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2026"></a>Erreur du compilateur C2026
chaîne trop grande, caractères de fin tronqués  
  
 La chaîne était supérieure à la limite de 16380 caractères codés sur un octet.  
  
 Avant la concaténation des chaînes adjacentes, une chaîne ne peut pas dépasser 16380 caractères codés sur un octet.  
  
 Une chaîne Unicode d’environ la moitié de cette longueur générerait également cette erreur.  
  
 Si vous avez une chaîne définie comme suit, il génère C2026 :  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 Vous pourriez la fractionner comme suit :  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 Vous pouvez vouloir stocker des littéraux de chaîne de taille exceptionnelle (32 Ko ou plus) dans une ressource personnalisée ou d’un fichier externe. Consultez [création d’une ressource personnalisée ou ressource de données](../../windows/creating-a-new-custom-or-data-resource.md) pour plus d’informations.
