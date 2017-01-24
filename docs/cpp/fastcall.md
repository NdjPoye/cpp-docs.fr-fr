---
title: "__fastcall | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__fastcall"
  - "__fastcall_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__fastcall (mot clé) (C++)"
ms.assetid: bb5b9c8a-dfad-450c-9119-0ac2bc59544f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __fastcall
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 La convention d'appel `__fastcall` spécifie que les arguments des fonctions doivent être passés dans les registres, lorsque cela est possible.  Cette convention d'appel s'applique uniquement à l'architecture x86.  La liste suivante illustre l'implémentation de cette convention d'appel.  
  
|Élément|Implémentation|  
|-------------|--------------------|  
|Ordre de transmission des arguments|Les deux premiers DWORD ou arguments plus petits qui figurent dans la liste d'arguments de gauche à droite sont transmis dans les registres ECX et EDX ; tous les autres arguments sont transmis sur la pile de droite à gauche.|  
|Responsabilité de la maintenance de la pile|La fonction appelée enlève les arguments de la pile.|  
|Convention de décoration de nom|L'arobase \(@\) est préfixé aux noms ; un arobase suivi du nombre d'octets \(au format décimal\) dans la liste de paramètres est suffixé aux noms.|  
|Convention de conversion de casse|Aucune conversion de casse n'est effectuée.|  
  
> [!NOTE]
>  Les futures versions du compilateur peuvent utiliser des registres pour stocker les paramètres.  
  
 L'utilisation de l'option du compilateur [\/Gr](../build/reference/gd-gr-gv-gz-calling-convention.md) provoque la compilation de chaque fonction du module en tant que `__fastcall` sauf si la fonction est déclarée avec un attribut en conflit, ou le nom de la fonction est `main`.  
  
 Le mot clé `__fastcall` est accepté et ignoré par les compilateurs qui ciblent les architectures ARM et x64 ; sur un processeur x64, par convention, les quatre premiers arguments sont transmis dans les registres si possible, et les arguments supplémentaires sont transmis sur la pile.  Pour plus d'informations, consultez [Vue d'ensemble des conventions d'appel x64](../build/overview-of-x64-calling-conventions.md).  Sur un processeur ARM, jusqu'à quatre arguments entiers et huit arguments à virgule flottante peuvent être transmis dans les registres, et des arguments supplémentaires sont transmis sur la pile.  
  
 Pour les fonctions de classe non statiques, si la fonction est définie hors ligne, il n'est pas nécessaire de spécifier le modificateur de convention d'appel dans la définition hors ligne.  En d'autres termes, pour les méthodes membres non statiques de classe, la convention d'appel spécifiée dans le cadre de la déclaration est utilisée par défaut au stade de la définition.  Compte tenu de la définition de classe suivante :  
  
```cpp  
struct CMyClass {  
   void __fastcall mymethod();  
};  
```  
  
 le code suivant :  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 équivaut au code :  
  
```cpp  
void __fastcall CMyClass::mymethod() { return; }  
```  
  
## Exemple  
 Dans l'exemple suivant, la fonction `DeleteAggrWrapper` correspond aux arguments transmis dans les registres :  
  
```c  
// Example of the __fastcall keyword  
#define FASTCALL    __fastcall  
  
void FASTCALL DeleteAggrWrapper(void* pWrapper);  
// Example of the __ fastcall keyword on function pointer  
typedef BOOL (__fastcall *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Passage des arguments et conventions de dénomination](../cpp/argument-passing-and-naming-conventions.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)