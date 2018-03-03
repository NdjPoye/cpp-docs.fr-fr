---
title: Erreur du compilateur C2061 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2061
dev_langs:
- C++
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e18810742efa94cdd130c1e11a2cdda0656c9921
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2061"></a>Erreur du compilateur C2061
Erreur de syntaxe : identificateur 'identificateur'  
  
 Le compilateur a détecté un identificateur là où il n’était pas attendu. Assurez-vous que `identifier` est déclaré avant de l’utiliser.  
  
 Un initialiseur peut être mis entre parenthèses. Pour éviter ce problème, incluez le déclarateur entre parenthèses ou rendre un `typedef`.  
  
 Cette erreur peut également être provoquée lorsque le compilateur détecte une expression comme argument de modèle de classe ; Utilisez [typename](../../cpp/typename.md) pour indiquer au compilateur qu’il s’agit d’un type.  
  
 L’exemple suivant génère l’erreur C2061 :  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 L’erreur C2061 peut se produire si vous passez un nom de l’instance [typeid](../../windows/typeid-cpp-component-extensions.md):  
  
```  
// C2061b.cpp  
// compile with: /clr  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   System::Type ^ pType = typeid<pG>;   // C2061  
   System::Type ^ pType2 = typeid<G>;   // OK  
}  
```