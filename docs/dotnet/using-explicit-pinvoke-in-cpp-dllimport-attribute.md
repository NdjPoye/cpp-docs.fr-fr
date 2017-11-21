---
title: "À l’aide de PInvoke explicite en C++ (attribut DllImport) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b3b2c69e022de6420223786f0f3b3f266c4f816
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>Utilisation d'un PInvoke explicite en C++ (attribut DllImport)
Le .NET Framework fournit des fonctionnalités de code non managé (ou PInvoke) explicites avec le `Dllimport` attribut pour autoriser les applications managées à appeler des fonctions non managées empaquetées dans des DLL. PInvoke explicite est requis pour les situations où les API non managées sont empaquetés en tant que DLL et le code source n’est pas disponible. Appel de fonctions Win32, par exemple, requiert PInvoke. Sinon, utilisez P implicite {Invoke ; consultez [à l’aide du interopérabilité C++ (PInvoke implicite)](../dotnet/using-cpp-interop-implicit-pinvoke.md) pour plus d’informations.  
  
 PInvoke fonctionne à l’aide de <xref:System.Runtime.InteropServices.DllImportAttribute>. Cet attribut, qui prend le nom de la DLL comme premier argument, est placé avant une déclaration de fonction pour chaque point d’entrée DLL qui sera utilisé. La signature de la fonction doit correspondre au nom d’une fonction exportée par la DLL (mais une conversion de type peut être exécutée implicitement en définissant le `DllImport` déclarations en termes de types managés.)  
  
 Le résultat est un point d’entrée managé pour chaque fonction DLL native qui contient le code de transition nécessaire (ou thunk) et les conversions de données simple. Les fonctions managées peuvent ensuite appeler la DLL via ces points d’entrée. Inséré le code dans un module comme résultat de PInvoke est intégralement géré et PInvoke explicite est pris en charge pour **/CLR**, **/CLR : pure**, et **/CLR : safe** compilations. Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015. Pour plus d’informations, consultez [Code pur et vérifiable (C + c++ / CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## <a name="in-this-section"></a>Dans cette section  
  
-   [Appel à des fonctions natives à partir de code managé](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [Guide pratique pour appeler des DLL natives à partir du code managé à l’aide de PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [Guide pratique pour marshaler des chaînes à l’aide de PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [Guide pratique pour marshaler des structures à l’aide de PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [Guide pratique pour marshaler des tableaux à l’aide de PInvoke](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [Guide pratique pour marshaler des pointeurs fonction à l’aide de PInvoke](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [Guide pratique pour marshaler des pointeurs incorporés à l’aide de PInvoke](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Appel à des fonctions natives à partir de code managé](../dotnet/calling-native-functions-from-managed-code.md)