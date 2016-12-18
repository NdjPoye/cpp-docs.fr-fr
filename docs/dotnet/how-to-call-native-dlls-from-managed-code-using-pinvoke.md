---
title: "Comment&#160;: appeler des DLL natives &#224; partir du code manag&#233; &#224; l&#39;aide de PInvoke | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshaling de données (C++), appel de DLL natives"
  - "Interop (C++), appel de DLL natives"
  - "marshaling (C++), appel de DLL natives"
  - "appel de code non managé (C++), appel de DLL natives"
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: appeler des DLL natives &#224; partir du code manag&#233; &#224; l&#39;aide de PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions implémentées dans des DLL non managées peuvent être appelées à partir du code managé à l'aide de la fonctionnalité d'appel de code non managé \(P\/Invoke\).  Si le code source de la DLL n'est pas disponible, P\/Invoke est la seule possibilité d'interaction.  Toutefois, contrairement aux autres langages .NET, Visual C\+\+ offre une alternative à P\/Invoke.  Pour plus d'informations, consultez [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## Exemple  
 L'exemple de code suivant utilise la fonction Win32 [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) pour récupérer la résolution actuelle de l'écran en pixels.  
  
 Pour les fonctions qui utilisent uniquement des types intrinsèques comme arguments et qui retournent des valeurs, aucun travail supplémentaire n'est requis.  D'autres types de données, tels que les pointeurs fonction, les tableaux et les structures, exigent des attributs supplémentaires pour garantir un marshaling correct des données.  
  
 Même si cela n'est pas obligatoire, il est conseillé de créer des membres statiques de déclarations P\/Invoke d'une valeur afin qu'ils n'existent pas dans l'espace de noms global, comme illustré dans cet exemple.  
  
```  
// pinvoke_basic.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value class Win32 {  
public:  
   [DllImport("User32.dll")]  
   static int GetSystemMetrics(int);  
  
   enum class SystemMetricIndex {  
      // Same values as those defined in winuser.h.  
      SM_CXSCREEN = 0,  
      SM_CYSCREEN = 1  
   };  
};  
  
int main() {  
   int hRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CXSCREEN) );  
   int vRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CYSCREEN) );  
   Console::WriteLine("screen resolution: {0},{1}", hRes, vRes);  
}  
```  
  
## Voir aussi  
 [Utilisation d'un PInvoke explicite en C\+\+ \(attribut DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)