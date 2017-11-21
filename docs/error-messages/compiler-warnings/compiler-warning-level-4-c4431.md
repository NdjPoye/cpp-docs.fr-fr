---
title: Compilateur avertissement (niveau 4) C4431 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4431
dev_langs: C++
helpviewer_keywords: C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2f9f18e625059003eb20c289fd6bbd37a6df45ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4431"></a>Avertissement du compilateur (niveau 4) C4431
spécificateur de type manquant - int est pris en compte par défaut. Remarque : C ne prend plus en charge int par défaut  
  
 Cette erreur peut être due à la mise en conformité du compilateur pour Visual C++ 2005 : Visual C++ ne crée plus identificateurs non typés en tant qu’int par défaut. Le type d’un identificateur doit être spécifié explicitement.  
  
 Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4431.  
  
```  
// C4431.c  
// compile with: /c /W4  
#pragma warning(default:4431)  
i;   // C4431  
int i;   // OK  
```