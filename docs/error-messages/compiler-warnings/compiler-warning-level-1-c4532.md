---
title: Compilateur avertissement (niveau 1) C4532 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4532
dev_langs:
- C++
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44aae61190b20bf1ef93b586c02e88837d487324
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4532"></a>Avertissement du compilateur (niveau 1) C4532
'continue' : saut hors du bloc __finally/finally a un comportement indéfini lors de la gestion de l’arrêt  
  
 Le compilateur a rencontré un des mots clés suivants :  
  
-   [continue](../../cpp/continue-statement-cpp.md)  
  
-   [break](../../cpp/break-statement-cpp.md)  
  
-   [goto](../../cpp/goto-statement-cpp.md)  
  
 à l’origine d’un saut en dehors d’un [__finally](../../cpp/try-finally-statement.md) ou [enfin](../../dotnet/finally.md) bloc pendant un arrêt anormal.  
  
 Si une exception se produit, et pendant que la pile n’est pas vidée lors de l’exécution des gestionnaires de terminaisons (les `__finally` ou blocs finally), et votre code saute hors d’un `__finally` bloc avant le `__finally` fin de ce bloc, le comportement n’est pas défini. Contrôle ne peut pas retourner le code de déroulement, afin de l’exception ne peut pas être gérée correctement.  
  
 Si vous devez sauter hors d’un **__finally** bloquer, vérifiez tout d’abord pour un arrêt anormal.  
  
 L’exemple suivant génère C4532 ; simplement commentez les instructions de saut pour résoudre les avertissements.  
  
```  
// C4532.cpp  
// compile with: /W1  
// C4532 expected  
int main() {  
   int i;  
   for (i = 0; i < 10; i++) {  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         continue;  
      }  
  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         break;  
      }  
   }  
}  
```