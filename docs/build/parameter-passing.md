---
title: "Passage de param&#232;tres | Microsoft Docs"
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
ms.assetid: e838ee5f-c2fe-40b0-9a23-8023c949c820
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Passage de param&#232;tres
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les quatre premiers arguments entiers sont passés dans les registres.  Les valeurs entières sont passées \(de gauche à droite\) dans RCX, RDX, R8, et R9.  Les cinq arguments et supérieur sont passés dans la pile.  Tous les arguments sont justifiés à droite dans les registres.  De cette manière, l'appelé peut éventuellement ignorer les bits supérieurs du registre et accéder uniquement à la partie du registre nécessaire.  
  
 Les arguments à virgule flottante et en double précision sont passés dans XMM0 \- XMM3 \(4 maximum\) avec l'emplacement de l'entier \(RCX, RDX, R8 et R9\) qui serait normalement utilisé pour cet emplacement de cardinal ignoré \(voir l'exemple\), et inversement.  
  
 les types , les tableaux et les chaînes de[\_\_m128](../cpp/m128.md) ne sont jamais passés par valeur immédiate mais plutôt un pointeur est passé à la mémoire allouée par l'appelant.  Les structs\/union de \_\_m64 de la taille 8, un de 16, 32, ou 64 bits et sont passés comme s'ils étaient des entiers de la même taille.  Les structs\/union autres que les tailles sont passés en tant que pointeur vers la mémoire allouée par l'appelant.  Pour ces types d'agrégats passés en tant que pointeur \(notamment \_\_m128\), la mémoire temporaire allouée par l'appelant est alignée sur 16 octets.  
  
 Les fonctions intrinsèques qui n'allouent pas d'espace de pile et n'appellent pas d'autres fonctions peuvent utiliser d'autres registres volatils pour passer des arguments de registre supplémentaires, car il existe une liaison étroite entre le compilateur et l'implémentation de la fonction intrinsèque.  Il s'agit là d'une autre possibilité d'améliorer les performances.  
  
 L'appelé est chargé de vider les paramètres de registre le cas échéant dans leur espace d'ombrage.  
  
 Le tableau suivant résume la manière dont les paramètres sont passés :  
  
|Type de paramètre|Mode de passage|  
|-----------------------|---------------------|  
|Virgule flottante|4 premiers paramètres \(XMM0 à XMM3\).  Les autres sont passés sur la pile.|  
|Entier|4 premiers paramètres \(RCX, RDX, R8, R9\).  Les autres sont passés sur la pile.|  
|Agrégats \(8, 16, 32 ou 64 bits\) et \_\_m64|4 premiers paramètres \(RCX, RDX, R8, R9\).  Les autres sont passés sur la pile.|  
|Agrégats \(autres\)|Par pointeur.  Les 4 premiers paramètres sont passés comme pointeurs dans RCX, RDX, R8 et R9|  
|\_\_m128|Par pointeur.  Les 4 premiers paramètres sont passés comme pointeurs dans RCX, RDX, R8 et R9|  
  
## Exemple d'argument qui passe 1 \(tous les entiers\)  
  
```  
func1(int a, int b, int c, int d, int e);    
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack  
```  
  
## Exemple d'argument qui passe 2 \(toutes les valeurs float\)  
  
```  
func2(float a, double b, float c, double d, float e);    
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack  
```  
  
## Exemple d'argument qui passe 3 \(à la fois les valeurs int et les valeurs float\)  
  
```  
func3(int a, double b, int c, float d);    
// a in RCX, b in XMM1, c in R8, d in XMM3  
```  
  
## Exemple d'argument qui passe 4 \(\_\_m64, \_\_m128 et agrégats\)  
  
```  
func4(__m64 a, _m128 b, struct c, float d);  
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3  
```  
  
## Voir aussi  
 [Convention d'appel](../build/calling-convention.md)