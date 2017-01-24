---
title: "Initialisation du CRT | Microsoft Docs"
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
  - "initialisation du CTR (C++)"
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Initialisation du CRT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment le CRT initialise les états globaux en code natif.  
  
 Par défaut, l'éditeur de liens inclut la bibliothèque CRT, qui fournit son propre code de démarrage.  Ce code de démarrage initialise la bibliothèque CRT, appelle les initialiseurs globaux, puis appelle la fonction `main`fournie à l'utilisateur pour les applications console.  
  
## Initialisation d'un objet global  
 Examinons le code ci\-dessous.  
  
```  
int func(void)  
{  
    return 3;  
}  
  
int gi = func();  
  
int main()  
{  
    return gi;  
}  
```  
  
 Selon la norme C\/C\+\+, `func()` doit être appelé avant que `main()` soit exécuté.  Mais qui l'appelle ?  
  
 Une méthode pour déterminer cela consiste à définir un point d'arrêt dans `func()`, de déboguer l'application, et d'examiner la pile.  Cela est possible parce que le code source CRT est inclus dans Visual Studio.  
  
 Lorsque vous parcourez les fonctions dans la pile, vous constaterez que le CRT effectue une boucle en parcourant la liste des pointeurs et appelant celles ci lorsqu'il les recontre.  Ces fonctions sont soit similaires à `func()` ou à des constructeurs pour les instances de la classe.  
  
 Le CRT obtient la liste des pointeurs par le compilateur Visual C\+\+.  Lorsque le compilateur voit un initialiseur global, il génère un initialiseur dynamique dans la section de `.CRT$XCU` \(où `CRT` est le nom de la section et `XCU` le nom du groupe\).  Pour obtenir une liste de ces initialiseurs dynamiques exécutez la commande **dumpbin \/all main.obj**, puis recherchez la section de`.CRT$XCU` \(lorsque main.cpp est compilé comme un fichier C\+\+ et non un fichier C\).  Il est semblable à ceux\-ci :  
  
```  
SECTION HEADER #6  
.CRT$XCU name  
       0 physical address  
       0 virtual address  
       4 size of raw data  
     1F2 file pointer to raw data (000001F2 to 000001F5)  
     1F6 file pointer to relocation table  
       0 file pointer to line numbers  
       1 number of relocations  
       0 number of line numbers  
40300040 flags  
         Initialized Data  
         4 byte align  
         Read Only  
  
RAW DATA #6  
  00000000: 00 00 00 00                                      ....  
  
RELOCATIONS #6  
                                                Symbol    Symbol  
 Offset    Type              Applied To         Index     Name  
 --------  ----------------  -----------------  --------  ------  
 00000000  DIR32                      00000000         C  ??__Egi@@YAXXZ (void __cdecl `dynamic initializer for 'gi''(void))  
```  
  
 Le CRT définit deux pointeurs :  
  
-   `__xc_a` dans `.CRT$XCA`  
  
-   `__xc_z` dans `.CRT$XCZ`  
  
 Les deux groupes n'ont aucun autre symbole défini sauf`__xc_a` et `__xc_z`.  
  
 Désormais, lorsque l'éditeur de liens lis des groupes variés `.CRT`, il les combine dans une section et les classe par ordre alphabétique.  Cela signifie que les initialiseurs globaux défini par l'utilisateur \(que le compilateur Visual C\+\+ met dans `.CRT$XCU`\) viendront toujours après `.CRT$XCA` et avant `.CRT$XCZ`.  
  
 La section ressemblera à ce qui suit :  
  
```  
.CRT$XCA  
            __xc_a  
.CRT$XCU  
            Pointer to Global Initializer 1  
            Pointer to Global Initializer 2  
.CRT$XCZ  
            __xc_z  
```  
  
 Par conséquent, la bibliothèque CRT utilise `__xc_a` et `__xc_z` pour déterminer le début et la fin de la liste des initialiseurs globaux en raison de la manière avec laquelle ils sont rangés dans la mémoire après que l'image soit chargée.  
  
## Voir aussi  
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)