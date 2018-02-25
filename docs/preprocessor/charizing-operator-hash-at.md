---
title: "Opérateur charizing (#@) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#@'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6521322e7a71d8e76b657fb8580157c036e881b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="charizing-operator-"></a>Opérateur charizing (#@)
**Section spécifique à Microsoft**  
  
 L’opérateur charizing peut être utilisé uniquement avec des arguments de macros. Si  **#@**  précède un paramètre formel dans la définition de la macro, l’argument réel est placé entre guillemets simples et traité comme un caractère lorsque la macro est développée. Exemple :  
  
```  
#define makechar(x)  #@x  
```  
  
 provoque le développement de l'instruction  
  
```  
a = makechar(b);  
```  
  
 à développer en  
  
```  
a = 'b';  
```  
  
 Le guillemet simple ne peut pas être utilisé avec l'opérateur charizing.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs de préprocesseur](../preprocessor/preprocessor-operators.md)