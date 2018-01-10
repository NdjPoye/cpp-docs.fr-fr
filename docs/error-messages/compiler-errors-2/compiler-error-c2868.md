---
title: Erreur du compilateur C2868 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2868
dev_langs: C++
helpviewer_keywords: C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7255aa3e73e23109535ae0e83d6e9bd907cdbcd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2868"></a>Erreur du compilateur C2868  
  
> '*identificateur*' : syntaxe de déclaration using non conforme ; nom qualifié attendu  
  
A [à l’aide de la déclaration](../../cpp/using-declaration.md) nécessite un *nom qualifié*, un opérateur de portée (`::`) séparées par la séquence de noms d’espace de noms, classe ou d’énumération qui se termine par le nom d’identificateur. Un opérateur de résolution de portée unique peut être utilisé pour introduire un nom à partir de l’espace de noms global.  
  
## <a name="example"></a>Exemple  
  
L’exemple suivant génère l’erreur C2868 et montre également l’utilisation correcte :  
  
```cpp  
// C2868.cpp  
class X {  
public:  
   int i;  
};  
  
class Y : X {  
public:  
   using X::i;   // OK  
};  
  
int main() {  
   using X;   // C2868  
}  
```