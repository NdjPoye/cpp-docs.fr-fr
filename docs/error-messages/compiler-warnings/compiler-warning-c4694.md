---
title: Avertissement du compilateur C4694 | Documents Microsoft
ms.date: 10/25/2017
ms.technology: cpp-tools
ms.topic: article
f1_keywords: C4694
dev_langs: C++
helpviewer_keywords: C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3f635aad0039812b50bd48a36f307ab5f60cba10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4694"></a>Avertissement du compilateur C4694

> '*classe*' : une classe abstraite sealed ne peut pas avoir une classe de base*base_class*'

Une classe abstraite et sealed ne peut pas hériter d’un type référence ; elle ne peut pas non plus implémenter de fonctions de classe de base ou se laisser utiliser comme classe de base.

Pour plus d’informations, consultez [abstraite](../../windows/abstract-cpp-component-extensions.md), [sealed](../../windows/sealed-cpp-component-extensions.md), et [les Classes et Structs](../../windows/classes-and-structs-cpp-component-extensions.md).

Cet avertissement est automatiquement promu en une erreur. Si vous souhaitez modifier ce comportement, utilisez [#pragma warning](../../preprocessor/warning.md).

## <a name="example"></a>Exemple

L’exemple suivant génère l’avertissement C4694.

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```