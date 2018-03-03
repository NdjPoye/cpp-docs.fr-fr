---
title: "Erreur LNK1306 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1306
dev_langs:
- C++
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32b6589fa5e4d7dc02ccb9a6c3157c109725b895
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1306"></a>Erreur des outils Éditeur de liens LNK1306  
  
> Fonction de point d’entrée DLL ne peut pas être managée ; compilez en natif  
  
`DllMain`ne peut pas être compilé en langage MSIL ; Il doit être compilé en mode natif.  
  
Pour résoudre ce problème,  
  
-   Compilez le fichier qui contient le point d’entrée sans **/CLR**.  
  
-   Placez le point d’entrée dans un `#pragma unmanaged` section.  
  
Pour plus d'informations, voir :  
  
-   [/CLR (Compilation pour le common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [managed, unmanaged](../../preprocessor/managed-unmanaged.md)  
  
-   [Initialisation d’assemblys mixtes](../../dotnet/initialization-of-mixed-assemblies.md)  
  
-   [DLL et comportement de la bibliothèque runtime Visual C++](../../build/run-time-library-behavior.md)  
  
## <a name="example"></a>Exemple  
  
L’exemple suivant génère l’erreur LNK1306.  
  
```cpp  
// LNK1306.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
// LNK1306 error expected  
#include <windows.h>  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
```  
  
Pour résoudre ce problème, n’utilisez pas l’option/CLR pour compiler ce fichier, ou utilisez un `#pragma` directive à placer la définition de point d’entrée dans une section non managée, comme indiqué dans cet exemple :  
  
```cpp  
// LNK1306fix.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
#include <windows.h>  
#pragma managed(push, off)  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
#pragma managed(pop)  
```  
