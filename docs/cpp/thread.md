---
title: thread | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- thread_cpp
dev_langs:
- C++
helpviewer_keywords:
- thread local storage (TLS)
- thread __declspec keyword
- TLS (thread local storage), compiler implementation
- __declspec keyword [C++], thread
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: f460497071445cff87308fa9bf6e0d43c6f13a3e
ms.openlocfilehash: 7261dc1d6d76eeac8a6b2959bc9bb6fc3c98a66e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="thread"></a>thread

**Section spécifique à Microsoft**  
Le **thread** modificateur de classe de stockage étendu est utilisé pour déclarer une variable locale de thread. Pour l’ordinateur portable équivalente dans C ++ 11 et versions ultérieure, utilisez la [thread_local](../cpp/storage-classes-cpp.md#thread_local) spécificateur de classe de stockage.

## <a name="syntax"></a>Syntaxe

```
__declspec( thread ) declarator
```

## <a name="remarks"></a>Remarques

Le stockage local des threads (TLS) est le mécanisme par lequel chaque thread d’un processus multithread alloue de l’espace de stockage pour les données spécifiques aux threads. Dans les programmes multithread standard, les données sont partagées entre tous les threads d’un processus donné, alors que le stockage local des threads est le mécanisme d’allocation des données par thread. Pour obtenir une description complète des threads, consultez [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Les déclarations de variables locales de thread doivent utiliser [étendu de la syntaxe d’attribut](../cpp/declspec.md) et `__declspec` mot clé avec la **thread** (mot clé). Par exemple, le code suivant déclare une variable locale de thread entière et lui affecte une valeur initiale :

```cpp
__declspec( thread ) int tls_i = 1;  
```

Vous devez respecter ces indications lorsque vous déclarez des variables et des objets locaux de thread :

- Vous pouvez appliquer la **thread** attribut uniquement à la classe et les déclarations de données et les définitions ; **thread** ne peut pas être utilisé sur des définitions ou déclarations de fonction.

- L’utilisation de la **thread** attribut peut interférer avec [chargement différé](../build/reference/linker-support-for-delay-loaded-dlls.md) des importations de DLL.

- Sur les systèmes XP, **thread** peut ne pas fonctionner correctement si une DLL utilise des données de __declspec (thread) et elle est chargée dynamiquement via LoadLibrary.

- Vous pouvez spécifier le **thread** attribut uniquement sur les éléments de données avec une durée de stockage statique. Cela inclut les objets de données globaux (à la fois **statique** et **extern**), les objets statiques locaux et les membres de données statiques des classes. Vous ne pouvez pas déclarer des objets de données automatiques avec le **thread** attribut.

- Vous devez utiliser le **thread** d’attribut pour la déclaration et la définition d’un objet local de thread, que la déclaration et la définition se produisent dans le même fichier ou dans des fichiers distincts.

- Vous ne pouvez pas utiliser le **thread** attribut sous la forme d’un modificateur de type.

- Étant donné que la déclaration d’objets qui utilisent le **thread** attribut est autorisé, ces deux exemples sont sémantiquement équivalentes :

    ```cpp
    // declspec_thread_2.cpp
    // compile with: /LD
    __declspec( thread ) class B {
    public:
       int data;
    } BObject;   // BObject declared thread local.

    class B2 {
    public:
       int data;
    };
    __declspec( thread ) B2 BObject2;   // BObject2 declared thread local.
    ```

- Le langage C standard permet l'initialisation d'un objet ou d'une variable à l'aide d'une expression impliquant une auto-référence, mais uniquement pour les objets d'étendue non statique. Même si C++ admet normalement l'initialisation dynamique d'un objet à l'aide d'une référence impliquant une auto-référence, ce type d'initialisation n'est pas permis avec les objets locaux de thread. Exemple :

    ```cpp
    // declspec_thread_3.cpp
    // compile with: /LD
    #define Thread __declspec( thread )
    int j = j;   // Okay in C++; C error
    Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
    ```

     Notez qu’un **sizeof** expression qui inclut l’objet initialisé ne constitue pas une référence à lui-même et est autorisée en C et C++.

**FIN de la section spécifique à Microsoft**

## <a name="see-also"></a>Voir aussi

[__declspec](../cpp/declspec.md)  
[Mots clés](../cpp/keywords-cpp.md)  
[Stockage local des threads (TLS)](../parallel/thread-local-storage-tls.md)

