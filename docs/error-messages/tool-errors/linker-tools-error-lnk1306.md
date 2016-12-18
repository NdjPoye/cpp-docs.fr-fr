---
title: "Erreur des outils &#201;diteur de liens LNK1306 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1306"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1306"
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1306
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' de point d'entrée de la DLL ne peut pas être managé ; compilez en natif  
  
 DllMain ne peut pas être compilé en MSIL ; il doit être compilé en natif.  
  
 Pour y remédier :  
  
-   Compilez le fichier qui contient le point d'entrée sans **\/clr**.  
  
-   Placez le point d'entrée dans une section `#pragma unmanaged`.  
  
-   Pour plus d'informations, consultez  
  
-   [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [managé, non managé](../../preprocessor/managed-unmanaged.md)  
  
-   [Initialisation d'assemblys mixtes](../../dotnet/initialization-of-mixed-assemblies.md)  
  
-   [Comportement de la bibliothèque runtime](../../build/run-time-library-behavior.md)  
  
## Exemple  
 L'exemple suivant génère l'erreur LNK1306.  
  
```  
// LNK1306.cpp  
// compile with: /clr /link /dll /entry:NewDllMain  
// LNK1306 error expected  
#include <windows.h>  
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {  
   return 1;  
}  
```