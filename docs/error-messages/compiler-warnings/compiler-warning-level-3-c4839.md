---
title: "Du compilateur (niveau 3) d’avertissement C4839 | Documents Microsoft"
ms.date: 10/25/2017
ms.technology:
- cpp-tools
ms.topic: error-reference
f1_keywords:
- C4839
dev_langs:
- C++
helpviewer_keywords:
- C4839
ms.assetid: f4f99066-9258-4330-81a8-f4a75a1d95ee
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aee1e564ffd72b9b08d883c94311c2bca72b5aef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4839"></a>Du compilateur (niveau 4) d’avertissement C4839

> utilisation non standard de la classe*type*' en tant qu’argument à une fonction variadique

Dans Visual Studio 2017, classes ou structs qui sont passés à un variadic fonctionnent comme `printf` doit être plus simplement être copiés. Quand de tels objets sont passés, le compilateur effectue simplement une copie au niveau du bit et n’appelle pas le constructeur ou le destructeur.

## <a name="example"></a>Exemple

L’exemple suivant génère C4839 :

```cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called; 
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

Pour corriger cette erreur, vous pouvez appeler une fonction membre qui retourne un type copiable de manière triviale,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

ou effectuer un cast statique pour convertir l’objet avant de le transmettre :

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

Pour les chaînes créées et gérées à l’aide de `CStringW`, fourni `operator LPCWSTR()` doit être utilisé pour convertir un `CStringW` objet avec le pointeur de C attendu par la chaîne de format.

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```