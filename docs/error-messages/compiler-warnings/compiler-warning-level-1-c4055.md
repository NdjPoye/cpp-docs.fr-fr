---
title: Compilateur avertissement (niveau 1) C4052 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4055
dev_langs:
- C++
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47d7d8891b589dc8205b0d799f88466c1e7d8a59
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4055"></a>Avertissement du compilateur (niveau 1) C4055

> '*conversion*' : du pointeur donnée '*type1*'vers le pointeur de fonction'*type2*'

## <a name="remarks"></a>Notes

**Obsolète :** cet avertissement n’est pas généré par Visual Studio 2017 et versions ultérieures.

Un pointeur donnée est converti (peut-être de façon incorrecte) en un pointeur fonction. Il s’agit d’un avertissement de niveau 1 sous /Za et d’un avertissement de niveau 4 sous /Ze.

## <a name="example"></a>Exemple

L’exemple suivant génère l’avertissement C4055 :

```C
// C4055.c
// compile with: /Za /W1 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
   return (PFUNC)pi;   // C4055
}
```

Sous /Ze, il s’agit d’un avertissement de niveau 4.

```C
// C4055b.c
// compile with: /W4 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
return (PFUNC)pi;   // C4055
}
```
