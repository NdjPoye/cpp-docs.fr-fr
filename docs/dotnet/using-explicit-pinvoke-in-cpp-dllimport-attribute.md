---
title: "Utilisation d&#39;un PInvoke explicite en C++ (attribut DllImport) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interopérabilité C++, appel de code non managé"
  - "marshaling de données (C++), appel de code non managé"
  - "Interop (C++), appel de code non managé"
  - "marshaling (C++), appel de code non managé"
  - "appel de code non managé (C++), marshaling en C++"
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation d&#39;un PInvoke explicite en C++ (attribut DllImport)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le .NET Framework fournit des fonctionnalités d'appel de code non managé \(ou PInvoke\) explicites avec l'attribut `Dllimport` pour autoriser les applications managées à appeler des fonctions non managées emballées à l'intérieur de DLL.  Un PInvoke explicite est requis pour les situations où les API non managées sont emballées en tant que DLL et où le code source n'est pas disponible.  Par exemple, l'appel de fonctions Win32 requiert PInvoke.  Sinon, utilisez un PInvoke implicite ; consultez [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md) pour plus d'informations.  
  
 PInvoke fonctionne à l'aide de <xref:System.Runtime.InteropServices.DllImportAttribute>.  Cet attribut, qui prend le nom de la DLL comme premier argument, est placé avant une déclaration de fonction pour chaque point d'entrée de DLL devant être utilisé.  La signature de la fonction doit correspondre au nom d'une fonction exportée par la DLL \(mais une conversion d'un certain type peut être exécutée implicitement en définissant les déclarations `DllImport` en termes de types managés\).  
  
 Le résultat est un point d'entrée managé pour chaque fonction DLL native qui contient le code de transition nécessaire \(ou thunk\) et des conversions de données simples.  Les fonctions managées peuvent ensuite effectuer un appel dans la DLL par l'intermédiaire de ces points d'entrée.  Le code inséré dans un module en tant que résultat de PInvoke est intégralement géré et le PInvoke explicite est pris en charge pour les compilations **\/clr**, **\/clr:pure** et **\/clr:safe**.  Pour plus d'informations, consultez [Code pur et vérifiable](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## Dans cette section  
  
-   [Appel à des fonctions natives à partir de code managé](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [Comment : appeler des DLL natives à partir du code managé à l'aide de PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [Comment : marshaler des chaînes à l'aide de PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [Comment : marshaler des structures à l'aide de PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [Comment : marshaler des tableaux à l'aide de PInvoke](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [Comment : marshaler des pointeurs fonction à l'aide de PInvoke](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [Comment : marshaler des pointeurs incorporés à l'aide de PInvoke](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## Voir aussi  
 [Appel à des fonctions natives à partir de code managé](../dotnet/calling-native-functions-from-managed-code.md)