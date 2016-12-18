---
title: "/Gh (Activer la fonction de raccordement _penter) | Microsoft Docs"
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
  - "_penter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gh (option du compilateur C++)"
  - "_penter (fonction)"
  - "Gh (option du compilateur C++)"
  - "-Gh (option du compilateur C++)"
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Gh (Activer la fonction de raccordement _penter)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déclenche un appel à la fonction `_penter` au début de chaque méthode ou fonction.  
  
## Syntaxe  
  
```  
/Gh  
```  
  
## Notes  
 La fonction `_penter` ne fait partie d'aucune bibliothèque et c'est à vous de fournir une définition pour `_penter`.  
  
 Sauf si vous envisagez d'appeler explicitement `_penter`, vous n'avez pas besoin de fournir un prototype.  La fonction doit apparaître comme si elle avait le prototype suivant, et elle doit exécuter un push sur le contenu de tous les registres à l'entrée et un pop sur le contenu non modifié à la sortie :  
  
```  
void __declspec(naked) _cdecl _penter( void );  
```  
  
 Cette déclaration n'est pas disponible pour les projets 64 bits.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Exemple  
 Le code suivant, une fois compilé avec **\/Gh**, montre comment `_penter` est appelée deux fois ; la première fois en entrant la fonction `main` et la deuxième fois en entrant la fonction `x`.  
  
```  
// Gh_compiler_option.cpp  
// compile with: /Gh  
// processor: x86  
#include <stdio.h>  
void x() {}  
  
int main() {  
   x();  
}  
  
extern "C" void __declspec(naked) _cdecl _penter( void ) {  
   _asm {  
      push eax  
      push ebx  
      push ecx  
      push edx  
      push ebp  
      push edi  
      push esi  
    }  
  
   printf_s("\nIn a function!");  
  
   _asm {  
      pop esi  
      pop edi  
      pop ebp  
      pop edx  
      pop ecx  
      pop ebx  
      pop eax  
      ret  
    }  
}  
```  
  
  **Dans une fonction \!**  
**Dans une fonction \!**   
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)