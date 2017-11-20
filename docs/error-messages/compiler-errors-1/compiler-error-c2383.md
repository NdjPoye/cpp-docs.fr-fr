---
title: Erreur du compilateur C2383 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2383
dev_langs: C++
helpviewer_keywords: C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20f6fa7626541f5fcd06bc2c2c513f52ec443ba4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2383"></a>Erreur du compilateur C2383
'*symbole*' : les arguments par défaut ne sont pas autorisés sur ce symbole  
  
 Le compilateur C++ n’autorise pas les arguments par défaut sur les pointeurs vers des fonctions.  
  
 Ce code a été accepté par le compilateur Visual C++ dans les versions antérieures de Visual Studio 2005, mais génère maintenant une erreur. Pour le code qui fonctionne dans toutes les versions de Visual C++, n’assignez pas de valeur par défaut à un argument de pointeur de fonction.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2383 et illustre une solution possible :  
  
```cpp  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```