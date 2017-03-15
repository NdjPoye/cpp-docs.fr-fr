---
title: "__stdcall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__stdcall_cpp"
  - "__stdcall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__stdcall (mot clé C++)"
ms.assetid: e212594b-1827-4d07-9527-7d412b300df8
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# __stdcall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 La convention d'appel `__stdcall` sert à appeler des fonctions API Win32.  L'appelé nettoie la pile, afin que le compilateur rende les fonctions **varag** `__cdecl`.  Les fonctions qui utilisent cette convention d'appel requièrent un prototype de fonction.  
  
## Syntaxe  
  
```  
  
return-type __stdcall function-name[(argument-list)]  
```  
  
## Notes  
 La liste suivante illustre l'implémentation de cette convention d'appel.  
  
|Élément|Implémentation|  
|-------------|--------------------|  
|Ordre de transmission des arguments|De droite à gauche|  
|Convention de passage d'argument|Par valeur, à moins qu'un type pointeur ou référence soit passé.|  
|Responsabilité de la maintenance de la pile|La fonction appelée enlève ses propres arguments de la pile.|  
|Convention de décoration de nom|Un trait de soulignement \(\_\) est ajouté en préfixe au nom.  Le nom est suivi de l'arobase \(@\), suivi du nombre d'octets \(au format décimal\) dans la liste d'arguments.  Par conséquent, la fonction déclarée comme `int func( int a, double b )` est décorée comme suit : `_func@12`|  
|Convention de conversion de casse|Aucun|  
  
 L'option du compilateur [\/Gz](../build/reference/gd-gr-gv-gz-calling-convention.md) spécifie `__stdcall` pour toutes les fonctions qui ne sont pas déclarées explicitement avec une autre convention d'appel.  
  
 Les fonctions déclarées à l'aide du modificateur `__stdcall` retournent des valeurs de la même façon que les fonctions déclarées à l'aide de [\_\_cdecl](../cpp/cdecl.md).  
  
 Pour les processeurs ARM et x64, `__stdcall` est accepté et ignoré par le compilateur ; pour les architectures ARM et x64, par convention, les quatre premiers arguments sont passés dans les registres dans la mesure du possible et les arguments suivants sont passés sur la pile.  
  
 Pour les fonctions de classe non statiques, si la fonction est définie hors ligne, il n'est pas nécessaire de spécifier le modificateur de convention d'appel dans la définition hors ligne.  En d'autres termes, pour les méthodes membres non statiques de classe, la convention d'appel spécifiée dans le cadre de la déclaration est utilisée par défaut au stade de la définition.  Étant donné cette définition de classe,  
  
```cpp  
struct CMyClass {  
   void __stdcall mymethod();  
};  
```  
  
 ceci  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 équivaut à ceci  
  
```cpp  
void __stdcall CMyClass::mymethod() { return; }  
```  
  
## Exemple  
 Dans l'exemple suivant, l'utilisation de \_\_**stdcall** entraîne le traitement de tous les types de fonction `WINAPI` comme un appel standard :  
  
```c  
// Example of the __stdcall keyword  
#define WINAPI __stdcall  
// Example of the __stdcall keyword on function pointer  
typedef BOOL (__stdcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## Voir aussi  
 [Passage des arguments et conventions de dénomination](../cpp/argument-passing-and-naming-conventions.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)