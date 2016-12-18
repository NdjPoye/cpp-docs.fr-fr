---
title: "manag&#233;, non manag&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.unmanaged"
  - "managed_CPP"
  - "unmanaged_CPP"
  - "vc-pragma.managed"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "pragma managé"
  - "pragmas, managé"
  - "pragmas, non managés"
  - "pragma non managé"
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# manag&#233;, non manag&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Activez le contrôle au niveau de la fonction pour compiler les fonctions comme managées ou non managées.  
  
## Syntaxe  
  
```  
  
        #pragma managed  
#pragma unmanaged  
#pragma managed([push,] on | off)  
#pragma managed(pop)  
```  
  
## Notes  
 L'option du compilateur [\/clr](../build/reference/clr-common-language-runtime-compilation.md) fournit un contrôle au niveau du module pour compiler les fonctions comme managées ou non managées.  
  
 Une fonction non managée est compilée pour la plateforme native et l'exécution de cette partie du programme est passée à la plateforme native par le Common Langage Runtime.  
  
 Les fonctions sont compilées comme managées par défaut lorsque l'option **\/clr** est utilisée.  
  
 Quand vous appliquez ces pragmas :  
  
-   Ajoutez le pragma devant une fonction, et non dans un corps de fonction.  
  
-   Ajoutez le pragma après les instructions `#include`.  N'utilisez pas ces pragmas avant les instructions `#include`.  
  
 Le compilateur ignore les pragmas `managed` et `unmanaged` si l'option **\/clr** n'est pas utilisée dans la compilation.  
  
 Lorsqu'une fonction modèle est instanciée, l'état du pragma au moment de la définition du modèle détermine si elle est managée ou non managée.  
  
 Pour plus d'informations, consultez [Initialisation d'assemblys mixtes](../dotnet/initialization-of-mixed-assemblies.md).  
  
## Exemple  
  
```  
// pragma_directives_managed_unmanaged.cpp  
// compile with: /clr  
#include <stdio.h>  
  
// func1 is managed  
void func1() {  
   System::Console::WriteLine("In managed function.");  
}  
  
// #pragma unmanaged  
// push managed state on to stack and set unmanaged state  
#pragma managed(push, off)  
  
// func2 is unmanaged  
void func2() {  
   printf("In unmanaged function.\n");  
}  
  
// #pragma managed  
#pragma managed(pop)  
  
// main is managed  
int main() {  
   func1();  
   func2();  
}  
```  
  
  **In managed function.  In unmanaged function.**    
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)