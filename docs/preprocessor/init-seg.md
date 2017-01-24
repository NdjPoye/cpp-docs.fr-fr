---
title: "init_seg | Microsoft Docs"
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
  - "vc-pragma.init_seg"
  - "init_seg_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "initialisation de segments de données (C++)"
  - "init_seg (pragma)"
  - "pragmas, init_seg"
ms.assetid: 40a5898a-5c85-4aa9-8d73-3d967eb13610
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# init_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Spécifie un mot clé ou une section de code qui affecte l'ordre dans lequel le code de démarrage est exécuté.  
  
## Syntaxe  
  
```  
  
#pragma init_seg({ compiler | lib | user | "section-name" [, func-name]} )  
```  
  
## Notes  
 Les termes *segment* et *section* sont interchangeables dans cette rubrique.  
  
 Étant donné que l'initialisation d'objets statiques globaux peut impliquer l'exécution de code, vous devez spécifier un mot clé qui définit le moment où les objets doivent être construits.  Il est particulièrement important d'utiliser le pragma **init\_seg** dans les bibliothèques de liens dynamiques \(DLL\) ou les bibliothèques nécessitant l'initialisation.  
  
 Les options pour le pragma **init\_seg** sont :  
  
 **compiler**  
 Réservé pour l'initialisation de la bibliothèque Runtime C Microsoft.  Les objets de ce groupe sont construits en premier.  
  
 **lib**  
 Disponible pour les initialisations des fournisseurs de bibliothèques de classes tierces.  Les objets de ce groupe sont construits après ceux marqués **compilateur** mais avant les autres.  
  
 **utilisateur**  
 Disponible pour tout utilisateur.  Les objets de ce groupe sont construits en dernier.  
  
 *section\-name*  
 Autorise la spécification explicite de la section d'initialisation.  Les objets d'un *section\-name* spécifié par l'utilisateur ne sont pas implicitement construits. Toutefois, leurs adresses sont placées dans la section nommée par *section\-name*.  
  
 Le nom de section que vous donnez contiendra les pointeurs vers des fonctions d'assistance qui construiront les objets globaux déclarés dans ce module après le pragma.  
  
 Pour obtenir la liste des noms à ne pas utiliser lorsque vous créez une section, consultez [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 *func\-name*  
 Spécifie une fonction à appeler au lieu de `atexit` lorsque le programme se ferme.  Cette fonction d'assistance appelle également [atexit](../c-runtime-library/reference/atexit.md) avec un pointeur vers le destructeur de l'objet global.  Si vous spécifiez un identificateur de fonction dans le pragma du formulaire,  
  
```  
int __cdecl myexit (void (__cdecl *pf)(void))  
```  
  
 votre fonctionnalité est appelée à la place de l'`atexit`de la bibliothèque Runtime C.  Cela vous permet de générer une liste des destructeurs qui devront être appelés lorsque vous êtes prêt à détruire les objets.  
  
 Si vous devez différer l'initialisation \(par exemple, dans une DLL\) vous pouvez choisir de spécifier le nom de section explicitement.  Vous devez ensuite appeler les constructeurs pour chaque objet statique.  
  
 Il ne reste aucun guillemet autour de l'identificateur du remplacement d'`atexit`.  
  
 Vos objets seront toujours placés dans les sections définies par les autres pragmas XXX\_seg.  
  
 Les objets déclarés dans le module ne seront pas automatiquement initialisés par le runtime C.  Vous devez effectuer cela vous\-même.  
  
 Par défaut, les sections `init_seg` sont en lecture seule.  Si le nom de section est .CRT, le compilateur passe silencieusement l'attribut en mode de lecture seule même s'il est marqué comme étant en lecture et en écriture.  
  
 Vous ne pouvez pas spécifier **init\_seg** plusieurs fois dans une unité de traduction.  
  
 Même si votre objet n'a pas de constructeur défini par l'utilisateur, un constructeur non défini explicitement dans le code, le compilateur peut en générer un \(par exemple pour lier des pointeurs v\- table\).  Par conséquent, votre code doit appeler le constructeur généré par le compilateur.  
  
## Exemple  
  
```  
// pragma_directive_init_seg.cpp  
#include <stdio.h>  
#pragma warning(disable : 4075)  
  
typedef void (__cdecl *PF)(void);  
int cxpf = 0;   // number of destructors we need to call  
PF pfx[200];    // pointers to destructors.  
  
int myexit (PF pf) {  
   pfx[cxpf++] = pf;  
   return 0;  
}  
  
struct A {  
   A() { puts("A()"); }  
   ~A() { puts("~A()"); }  
};  
  
// ctor & dtor called by CRT startup code   
// because this is before the pragma init_seg  
A aaaa;   
  
// The order here is important.  
// Section names must be 8 characters or less.  
// The sections with the same name before the $  
// are merged into one section. The order that  
// they are merged is determined by sorting  
// the characters after the $.  
// InitSegStart and InitSegEnd are used to set  
// boundaries so we can find the real functions  
// that we need to call for initialization.  
  
#pragma section(".mine$a", read)  
__declspec(allocate(".mine$a")) const PF InitSegStart = (PF)1;  
  
#pragma section(".mine$z",read)  
__declspec(allocate(".mine$z")) const PF InitSegEnd = (PF)1;  
  
// The comparison for 0 is important.  
// For now, each section is 256 bytes. When they  
// are merged, they are padded with zeros. You  
// can't depend on the section being 256 bytes, but  
// you can depend on it being padded with zeros.  
  
void InitializeObjects () {  
   const PF *x = &InitSegStart;  
   for (++x ; x < &InitSegEnd ; ++x)  
      if (*x) (*x)();  
}  
  
void DestroyObjects () {  
   while (cxpf>0) {  
      --cxpf;  
      (pfx[cxpf])();  
   }  
}  
  
// by default, goes into a read only section  
#pragma init_seg(".mine$m", myexit)  
  
A bbbb;   
A cccc;  
  
int main () {  
   InitializeObjects();  
   DestroyObjects();  
}  
```  
  
  **A\(\)**  
**A\(\)**  
**A\(\)**  
**~A\(\)**  
**~A\(\)**  
**~A\(\)**   
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)