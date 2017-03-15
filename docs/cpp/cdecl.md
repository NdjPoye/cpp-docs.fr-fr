---
title: "__cdecl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__cdecl"
  - "__cdecl_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__cdecl (mot clé) (C++)"
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# __cdecl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 `__cdecl` est la convention d'appel par défaut pour les programmes C et C\+\+.  Comme la pile est nettoyée par l'appelant, il peut exécuter des fonctions **vararg**.  La convention d'appel `__cdecl` crée des exécutables plus grands que [\_\_stdcall](../cpp/stdcall.md), car elle exige que chaque appel de fonction inclue un code de nettoyage de la pile.  La liste suivante illustre l'implémentation de cette convention d'appel.  
  
|Élément|Implémentation|  
|-------------|--------------------|  
|Ordre de transmission des arguments|De droite à gauche|  
|Responsabilité de la maintenance de la pile|La fonction appelante enlève les arguments de la pile.|  
|Convention de décoration de nom|Le trait de soulignement \(\_\) est préfixé aux noms, sauf lorsque des fonctions \_\_cdecl qui utilisent une liaison C sont exportées.|  
|Convention de conversion de casse|Aucune conversion de casse n'est effectuée.|  
  
> [!NOTE]
>  Pour plus d'informations, consultez [Noms décorés](../build/reference/decorated-names.md).  
  
 Placez le modificateur `__cdecl` avant un nom de variable ou de fonction.  Comme les conventions d'affectation de noms et d'appel C sont définies par défaut, la seule fois où vous devez utiliser `__cdecl` dans un code x86 est lorsque vous avez spécifié l'option **\/Gv** \(vectorcall\), **\/Gz** \(stdcall\) ou **\/Gr** \(fastcall\) du compilateur.  L'option [\/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md) du compilateur impose la convention d'appel `__cdecl`.  
  
 Sur les processeurs ARM et x64, `__cdecl` est accepté mais en général ignoré par le compilateur.  Par convention sur ARM et x64, les arguments sont passés dans les registres le cas échéant, et les arguments suivants sont passés sur la pile.  Dans le code x64, utilisez `__cdecl` pour remplacer l'option du compilateur **\/Gv** et utiliser la convention d'appel par défaut x64.  
  
 Pour les fonctions de classe non statiques, si la fonction est définie hors ligne, il n'est pas nécessaire de spécifier le modificateur de convention d'appel dans la définition hors ligne.  En d'autres termes, pour les méthodes membres non statiques de classe, la convention d'appel spécifiée dans le cadre de la déclaration est utilisée par défaut au stade de la définition.  Compte tenu de la définition de classe suivante :  
  
```cpp  
struct CMyClass {  
   void __cdecl mymethod();  
};  
```  
  
 le code suivant :  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 équivaut au code :  
  
```cpp  
void __cdecl CMyClass::mymethod() { return; }  
```  
  
## Exemple  
 Dans l'exemple suivant, le compilateur est chargé d'utiliser les conventions de nommage et d'appel du langage C pour la fonction `system`.  
  
```cpp  
// Example of the __cdecl keyword on function  
int __cdecl system(const char *);  
// Example of the __cdecl keyword on function pointer  
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## Voir aussi  
 [Passage des arguments et conventions de dénomination](../cpp/argument-passing-and-naming-conventions.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)