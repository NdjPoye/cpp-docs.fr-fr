---
title: Erreur du compilateur C2512 | Documents Microsoft
ms.custom: 
ms.date: 02/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2512
dev_langs:
- C++
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57dbb542eee7e893253e6c3bdd3410c605a8d2db
ms.sourcegitcommit: 8ae12a602244a5853e941e5e8806e3545d876844
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2018
---
# <a name="compiler-error-c2512"></a>Erreur du compilateur C2512

> '*identificateur*' : aucun constructeur par défaut approprié disponible  

A *constructeur par défaut*, un constructeur qui ne requiert aucun argument, n’est pas disponible pour la classe spécifiée, structure ou union. Le compilateur fournit un constructeur par défaut uniquement si aucun constructeur défini par l’utilisateur n’est fournis.

Si vous fournissez un constructeur qui accepte un paramètre non void, et vous souhaitez autoriser votre classe d’être créés sans paramètres (par exemple, les éléments d’un tableau), vous devez également fournir un constructeur par défaut. Le constructeur par défaut peut être un constructeur avec des valeurs par défaut pour tous les paramètres.

## <a name="example"></a>Exemple

Une cause courante de l’erreur C2512 est lorsque vous définissez un constructeur de classe ou un struct qui accepte des arguments, et vous tentez de déclarer une instance de votre classe ou un struct sans arguments. Par exemple, `struct B` ci-dessous déclare un constructeur qui nécessite un `char *` argument, mais pas un qui n’accepte aucun argument. Dans `main`, une instance de B est déclarée, mais aucun argument n’est fourni. Le compilateur génère l’erreur C2512 car il ne peut pas trouver un constructeur par défaut pour B.

```cpp
// C2512.cpp
// Compile with: cl /W4 c2512.cpp
// C2512 expected
struct B {
   B (char *) {}
   // Uncomment the following line to fix.
   // B() {}
};

int main() {
   B b;   // C2512 - This requires a default constructor
}
```

Vous pouvez résoudre ce problème en définissant un constructeur par défaut pour votre structure ou une classe, tels que `B() {}`, ou un constructeur dans lequel tous les arguments ont des valeurs par défaut, telles que `B (char * = nullptr) {}`.
