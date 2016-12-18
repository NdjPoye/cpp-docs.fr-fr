---
title: "D&#233;finitions et d&#233;clarations (C++) | Microsoft Docs"
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
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finitions et d&#233;clarations (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 L'interface DLL fait référence à tous les éléments \(fonctions et données\) qui sont connus pour être exportés par un programme du système, c'est\-à\-dire tous les éléments déclarés comme **dllimport** ou `dllexport`.  Toutes les déclarations incluses dans l'interface DLL doivent spécifier l'attribut **dllimport** ou `dllexport`.  Toutefois, la définition doit spécifier uniquement l'attribut `dllexport`.  Par exemple, la définition de fonction suivante génère une erreur de compilation :  
  
```  
__declspec( dllimport ) int func() {   // Error; dllimport  
                                    // prohibited on definition.  
   return 1;  
}  
```  
  
 Le code suivant génère aussi une erreur :  
  
```  
#define DllImport   __declspec( dllimport )  
  
__declspec( dllimport ) int i = 10;  // Error; this is a  
                                     // definition.  
```  
  
 Mais voici la syntaxe correcte :  
  
```  
__declspec( dllexport ) int i = 10;     // Okay--export definition  
```  
  
 L'utilisation de `dllexport` implique une définition tandis que **dllimport** implique une déclaration.  Vous devez utiliser le mot clé `extern` avec `dllexport` pour forcer une déclaration. Sinon, une définition est impliquée.  Les exemples suivants sont donc corrects :  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
extern DllImport int k; // These are both correct and imply a  
DllImport int j;        // declaration.  
```  
  
 Les exemples suivants clarifient l'exemple précédent :  
  
```  
static __declspec( dllimport ) int l; // Error; not declared extern.  
  
void func() {  
    static __declspec( dllimport ) int s;  // Error; not declared  
                                           // extern.  
    __declspec( dllimport ) int m;         // Okay; this is a   
                                           // declaration.  
    __declspec( dllexport ) int n;         // Error; implies external  
                                           // definition in local scope.  
    extern __declspec( dllimport ) int i;  // Okay; this is a  
                                           // declaration.  
    extern __declspec( dllexport ) int k;  // Okay; extern implies  
                                           // declaration.  
    __declspec( dllexport ) int x = 5;     // Error; implies external  
                                           // definition in local scope.  
}  
```  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)