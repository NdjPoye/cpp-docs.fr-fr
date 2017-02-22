---
title: "Appel de fonctions de la DLL &#224; partir d&#39;applications Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__stdcall (mot clé C++)"
  - "appel de fonctions DLL à partir d'applications Visual Basic (C++)"
  - "fonctions DLL (C++)"
  - "fonctions DLL (C++), appeler"
  - "DLL (C++), appeler"
  - "appels de fonction (C++), DLL (fonctions)"
  - "fonctions (C++), appeler des fonctions DLL à partir de Visual Basic"
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Appel de fonctions de la DLL &#224; partir d&#39;applications Visual Basic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour que des applications Visual Basic \(ou des applications écrites dans d'autres langages tels que Pascal ou Fortran\) appellent des fonctions dans une DLL C\/C\+\+, les fonctions doivent être exportées à l'aide de la convention d'appel correcte sans la décoration de noms effectuée par le compilateur.  
  
 `__stdcall` crée la convention d'appel correcte pour la fonction \(la fonction appelée nettoie le pile et les paramètres sont passés de droite à gauche\) mais décore le nom de la fonction différemment.  Donc, quand le mot clé **\_\_declspec\(dllexport\)** est appliqué à une fonction exportée d'une DLL, le nom décoré est exporté également.  
  
 La décoration de nom `__stdcall` fait précéder le nom du symbole d'un trait de soulignement \(\_\) et annexe au symbole arobase \(@\) suivi du nombre d'octets dans la liste d'arguments \(l'espace de pile requis\).  Lorsqu'elle est déclarée en tant que :  
  
```  
int __stdcall func (int a, double b)  
```  
  
 la fonction est alors décorée de la manière suivante :  
  
```  
_func@12  
```  
  
 La convention d'appel C \(`__cdecl`\) décore le nom en tant que `_func`.  
  
 Pour obtenir le nom décoré, utilisez [\/MAP](../build/reference/map-generate-mapfile.md).  L'utilisation du mot clé **\_\_declspec\(dllexport\)** produit l'effet suivant :  
  
-   Si la fonction est exportée à l'aide de la convention d'appel C \(**\_cdecl**\), elle supprime le trait de soulignement de début \(\_\) quand le nom est exporté.  
  
-   Si la fonction exportée n'utilise pas la convention d'appel C \(par exemple, `__stdcall`\), elle exporte le nom décoré.  
  
 Comme il n'existe aucun moyen de substituer les cas où le nettoyage de pile se produit, vous devez utiliser `__stdcall`.  Pour supprimer la décoration des noms au moyen de `__stdcall`, vous devez spécifier les noms à l'aide d'alias dans la section EXPORTS du fichier .def.  Cette approche est illustrée ci\-dessous pour la déclaration de fonction suivante :  
  
```  
int  __stdcall MyFunc (int a, double b);  
void __stdcall InitCode (void);  
```  
  
 Dans le fichier .DEF :  
  
```  
EXPORTS  
   MYFUNC=_MyFunc@12  
   INITCODE=_InitCode@0  
```  
  
 Pour que les DLL puissent être appelées par des programmes écrits en Visual Basic, la technique des alias décrite dans cette rubrique est nécessaire dans le fichier .def.  Si l'alias est utilisé dans le programme Visual Basic, l'utilisation des alias dans le fichier .def n'est pas nécessaire.  Elle peut être intégrée dans le programme Visual Basic par l'ajout d'une clause d'alias à l'instruction [Declare](../Topic/Declare%20Statement.md).  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Exportation à partir d'une DLL](../build/exporting-from-a-dll.md)  
  
-   [Exportation à partir d'une DLL à l'aide de fichiers .DEF](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportation à partir d'une DLL à l'aide de \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportation de fonctions C\+\+ à utiliser dans des exécutables en langage C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Méthode d'exportation à utiliser](../build/determining-which-exporting-method-to-use.md)  
  
-   [Noms décorés](../build/reference/decorated-names.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)