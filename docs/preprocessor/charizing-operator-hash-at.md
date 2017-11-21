---
title: "Opérateur charizing (#@) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#@'
dev_langs: C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1920d8183607140ebe38aaf56a447bc9cd3010f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
  
 en  
  
```  
a = 'b';  
```  
  
 Le guillemet simple ne peut pas être utilisé avec l'opérateur charizing.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs de préprocesseur](../preprocessor/preprocessor-operators.md)