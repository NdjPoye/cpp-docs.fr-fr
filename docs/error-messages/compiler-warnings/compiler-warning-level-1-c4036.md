---
title: Compilateur avertissement (niveau 1) C4036 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4036
dev_langs:
- C++
helpviewer_keywords:
- C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6392ba12c14ca3ef89f992e358bf019d1d92e5db
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4036"></a>Avertissement du compilateur (niveau 1) C4036
'type' sans nom comme paramètre réel  
  
 Une structure, union, énumération ou classe utilisée comme paramètre réel n’a pas reçu de nom de type. Si vous utilisez [/Zg](../../build/reference/zg-generate-function-prototypes.md) pour générer des prototypes de fonction, le compilateur émet cet avertissement et met en commentaire le paramètre formel dans le prototype généré.  
  
 Spécifiez un nom de type pour remédier à cet avertissement.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’avertissement C4036.  
  
```  
// C4036.c  
// compile with: /Zg /W1  
// D9035 expected  
typedef struct { int i; } T;  
void f(T* t) {}   // C4036  
  
// OK  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```
