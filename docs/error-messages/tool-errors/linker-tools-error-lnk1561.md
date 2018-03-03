---
title: "Erreur LNK1561 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1561
dev_langs:
- C++
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cbd0ca9e932bdb2845ada2f47b569391e943cb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1561"></a>Erreur des outils Éditeur de liens LNK1561
point d’entrée doit être défini.  
  
L’éditeur de liens n’a pas trouvé un *point d’entrée*, la fonction initiale à appeler dans votre fichier exécutable. Par défaut, l’éditeur de liens recherche un `main` ou `wmain` fonction d’une application console, un `WinMain` ou `wWinMain` fonction pour une application Windows, ou `DllMain` pour une DLL qui nécessite l’initialisation. Vous pouvez spécifier une autre fonction en utilisant le [/ENTRY](../../build/reference/entry-entry-point-symbol.md) option de l’éditeur de liens.  
  
Cette erreur peut avoir plusieurs causes :  
-   Vous n’avez ne peut-être pas inclus le fichier qui définit votre point d’entrée dans la liste des fichiers à lier. Vérifiez que le fichier qui contient la fonction de point d’entrée est lié à votre application.  
-   Avoir défini le point d’entrée à l’aide de la signature de fonction incorrect ; par exemple, vous pouvez ont mal orthographié ou utilisé la casse correcte pour le nom de fonction ou spécifié de manière incorrecte le type de retour ou les types de paramètre.  
-   Vous n’avez ne peut-être pas spécifié le [/DLL](../../build/reference/dll-build-a-dll.md) option lors de la création d’une DLL.  
-   Vous avez peut-être spécifié le nom de la fonction de point d’entrée incorrecte lorsque vous avez utilisé le [/ENTRY](../../build/reference/entry-entry-point-symbol.md) option de l’éditeur de liens.  
-   Si vous utilisez la [LIB](../../build/reference/lib-reference.md) outil pour générer une DLL, vous avez peut-être spécifié un fichier .def. Dans ce cas, supprimez le fichier .def de la génération.    
  
Lorsque vous créez une application, l’éditeur de liens recherche pour une fonction de point d’entrée à appeler pour démarrer votre code. Il s’agit de la fonction est appelée après que l’application est chargée et l’exécution est initialisé. Vous devez fournir une fonction de point d’entrée pour une application ou votre application ne peut pas s’exécuter. Un point d’entrée est facultatif pour une DLL. Par défaut, l’éditeur de liens recherche pour une fonction de point d’entrée qui a l’une des différents des noms spécifiques et les signatures, tel que `int main(int, char**)`. Vous pouvez spécifier un autre nom de la fonction en tant que l’entrée de point à l’aide de l’option de l’éditeur de liens /ENTRY.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur LNK1561 :  
  
```cpp  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```