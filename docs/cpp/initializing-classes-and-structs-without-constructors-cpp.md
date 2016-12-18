---
title: "Initialisation des classes et structs sans constructeurs (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
caps.latest.revision: 3
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Initialisation des classes et structs sans constructeurs (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il n'est pas toujours nécessaire de définir un constructeur pour une classe, en particulier celles qui sont relativement simples.  Les utilisateurs peuvent initialiser des objets d'une classe ou d'un struct à l'aide de l'initialisation uniforme, comme illustré dans l'exemple suivant :  
  
```  
struct TempData  
{  
    int StationId;  
    time_t time;  
    double current;  
    double max;  
    double min;  
};  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    // Member initialization:  
    TempData td { 45978, GetCurrentTime(), 28.9, 37.0, 16.7 };  
  
    // Default initialization = {0,0,0,0,0}  
    TempData td_default {};  
  
    //Error C4700 uninitialized local variable  
    TempData td_noInit;   
    return 0;  
}  
```  
  
## Voir aussi  
 [Classes et structs](../cpp/classes-and-structs-cpp.md)   
 [Constructeurs](../cpp/constructors-cpp.md)