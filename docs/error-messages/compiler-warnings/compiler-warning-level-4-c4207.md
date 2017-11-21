---
title: Compilateur avertissement (niveau 4) C4207 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4207
dev_langs: C++
helpviewer_keywords: C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6a6755549aa7d529de1726d2d1cedd8d9b733067
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4207"></a>Avertissement du compilateur (niveau 4) C4207
extension non standard utilisée : étendus forme de l’initialiseur  
  
 Avec les extensions Microsoft (/Ze), vous pouvez initialiser un tableau non dimensionné de `char` à l’aide d’une chaîne entre accolades.  
  
## <a name="example"></a>Exemple  
  
```  
// C4207.c  
// compile with: /W4  
char c[] = { 'a', 'b', "cdefg" }; // C4207  
  
int main()  
{  
}  
```  
  
 De telles initialisations sont non valides sous compatibilité ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).