---
title: Compilateur avertissement (niveau 4) C4289 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4289
dev_langs:
- C++
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 98acda62a984f2625ddc742e309aca7628d9c9f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4289"></a>Avertissement du compilateur (niveau 4) C4289
extension non standard utilisée : ’var’ : variable de contrôle de boucle déclarée dans la boucle for utilisée à l’extérieur de la portée de la boucle  
  
 Lors de la compilation avec [/Ze](../../build/reference/za-ze-disable-language-extensions.md) et **/Zc:forScope-**, une variable déclarée dans une [pour](../../cpp/for-statement-cpp.md) boucle a été utilisée après la **pour**-portée de la boucle.  
  
 Consultez [/Zc : forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) pour plus d’informations sur la façon de spécifier un comportement standard dans **pour** boucles avec **/Ze**.  
  
 Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.  
  
 L’exemple suivant génère l’erreur C4289 :  
  
```  
// C4289.cpp  
// compile with: /W4 /Zc:forScope-  
#pragma warning(default:4289)  
int main() {  
   for (int i = 0 ; ; )   // C4289  
      break;  
   i++;  
}  
```