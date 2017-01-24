---
title: "Exportation de fonctions&#160;C &#224; utiliser dans des ex&#233;cutables en langage&#160;C ou&#160;C++ | Microsoft Docs"
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
  - "__cplusplus (macro)"
  - "exporter des DLL (C++), fonctions C dans les exécutables C++"
  - "exporter des fonctions (C++), fonctions C dans les exécutables C++"
  - "fonctions (C), exécutables C ou C++ et"
  - "fonctions (C), exporter"
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Exportation de fonctions&#160;C &#224; utiliser dans des ex&#233;cutables en langage&#160;C ou&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si, dans une DLL écrite en C, vous avez des fonctions auxquelles vous souhaitez accéder à partir d'un module rédigé en langage C ou C\+\+, vous devez utiliser la macro de préprocesseur **\_\_cplusplus** pour déterminer le langage compilé, puis déclarer ces fonctions à l'aide d'une liaison C en cas d'utilisation à partir d'un module en C\+\+.  Si vous utilisez cette technique et fournissez des fichiers d'en\-tête pour votre DLL, ces fonctions peuvent être utilisées par des utilisateurs C et C\+\+ sans modification.  
  
 Le code suivant montre un fichier d'en\-tête qui peut être utilisé par des applications clientes en C et C\+\+ :  
  
```  
// MyCFuncs.h  
#ifdef __cplusplus  
extern "C" {  // only need to export C interface if  
              // used by C++ source code  
#endif  
  
__declspec( dllimport ) void MyCFunc();  
__declspec( dllimport ) void AnotherCFunc();  
  
#ifdef __cplusplus  
}  
#endif  
```  
  
 Si vous devez lier des fonctions C à votre exécutable C\+\+ et que les fichiers d'en\-tête de déclaration de fonctions n'ont pas utilisé la technique ci\-dessus, accédez au fichier source en C\+\+ puis procédez de la façon suivante pour empêcher le compilateur de décorer les noms de fonctions du C :  
  
```  
extern "C" {  
#include "MyCHeader.h"  
}  
```  
  
## Que voulez\-vous faire ?  
  
-   [Exporter à partir d'une DLL à l'aide de fichiers .def](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exporter à partir d'une DLL à l'aide de \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exporter et importer à l'aide de AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Déterminer la méthode d'exportation à utiliser](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importer dans une application à l'aide de \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialiser une DLL](../build/initializing-a-dll.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Noms décorés](../build/reference/decorated-names.md)  
  
-   [Spécifications de liaison](http://msdn.microsoft.com/fr-fr/d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)  
  
## Voir aussi  
 [Exportation à partir d'une DLL](../build/exporting-from-a-dll.md)