---
title: Erreur du compilateur C2026 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: c429f81c64b7710b7edc2b8540d98e8c790e4062
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2026"></a>Erreur du compilateur C2026
chaîne trop grande, caractères de fin tronqués  
  
 La chaîne était plus longue que la limite de 16380 caractères codés sur un.  
  
 Avant la concaténation des chaînes adjacentes, une chaîne ne peut pas dépasser 16380 caractères sur un octet.  
  
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
  
 Vous pouvez vouloir stocker des littéraux de chaîne de taille exceptionnelle (32 Ko ou plus) dans une ressource personnalisée ou d’un fichier externe. Consultez la page [création d’une ressource personnalisée ou la ressource de données](../../windows/creating-a-new-custom-or-data-resource.md) pour plus d’informations.
