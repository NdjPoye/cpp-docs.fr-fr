---
title: "Avertissement du compilateur (niveau 1) C4747 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4747"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4747"
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Avertissement du compilateur (niveau 1) C4747
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appel de 'PointEntrée' managé : impossible d'exécuter du code managé lors du verrouillage du chargeur, y compris le point d'entrée de DLL et les appels accessibles à partir du point d'entrée de DLL  
  
 Le compilateur a détecté un point d'entrée de DLL \(probable\) compilé en code MSIL.  En raison de problèmes potentiels liés au chargement d'une DLL dont le point d'entrée a été compilé en code MSIL, il est fortement déconseillé de compiler une fonction de point d'entrée de DLL en code MSIL.  
  
 Pour plus d’informations, consultez [Initialisation d'assemblys mixtes](../../dotnet/initialization-of-mixed-assemblies.md) et [Erreur des outils Éditeur de liens LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).  
  
### Pour corriger cette erreur  
  
1.  Ne compilez pas le module avec **\/clr**.  
  
2.  Marquez la fonction de point d'entrée avec `#pragma unmanaged`.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4747 :  
  
```  
// C4747.cpp  
// compile with: /clr /c /W1  
// C4747 expected  
#include <windows.h>  
  
// Uncomment the following line to resolve.  
// #pragma unmanaged  
  
BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {  
   return TRUE;  
};  
```