---
title: Compilateur avertissement (niveau 1) C4964 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4964
dev_langs:
- C++
helpviewer_keywords:
- C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1c7483b82c363898bc16ed5fc7d48f9cf0b35c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4964"></a>Avertissement du compilateur (niveau 1) C4964
Aucune option d’optimisation ont été spécifiées ; les informations de profil ne seront pas collectées.  
  
 [/GL](../../build/reference/gl-whole-program-optimization.md) et [LTCG](../../build/reference/ltcg-link-time-code-generation.md) ont été spécifiées, mais aucune optimisation n’a été demandé, donc aucun fichier .pgc ne sera généré et, par conséquent, aucune optimisation guidée par profil n’est plus possible.  
  
 Si vous souhaitez que les fichiers .pgc à générer lorsque vous exécutez votre application, spécifiez l’une de la [/O](../../build/reference/o-options-optimize-code.md) options du compilateur.  
  
 L’exemple suivant génère l’erreur C4964 :  
  
```  
// C4964.cpp  
// compile with: /W1 /GL /link /ltcg:pgi  
// C4964 expected  
// Add /O2, for example, to the command line to resolve this warning.  
int main() {  
   int i;  
}  
```