---
title: "Champs de bits C | Microsoft Docs"
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
  - "champs de bits"
  - "champs de bits"
ms.assetid: 9faf74c4-7fd5-4b44-ad18-04485193d06e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Champs de bits C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En plus des déclarateurs des membres d'une structure ou d'une union, un déclarateur de structures peut également être un nombre de bits spécifié, appelé « champ de bits ». Sa longueur est séparé du déclarateur dans le nom de champ par un deux\-points.  Un champ de bits est interprète comme un type entier.  
  
## Syntaxe  
 *struct\-declarator*:  
 *déclarateur*  
  
 *type\-specifier declarator*  opt **:** *constant\-expression*  
  
 *L'expression constante* spécifie la largeur du champ de bits.  Le *spécificateur de type* du `declarator` doit être un `unsigned int`, un **signed int**, ou un `int`, et *l'expression constante* doit être une valeur entière non négative.  Si la valeur est nulle, la déclaration n'a aucun `declarator`.  Vous ne pouvez pas utiliser de tableau de champs de bits, de pointeur aux champs de bits, ou de fonction retournant les champs de bits.  Le `declarator` facultatif nomme le champ de bits.  Les champs de bits peuvent uniquement être déclarés dans le cadre d'une structure.  L'opérateur d'adresse \(**&**\) ne peut pas être appliqué aux composants de champ de bits.  
  
 Les champs de bits sans nom ne peuvent pas être référencés, et leur contenu au moment de l'exécution est imprévisible.  Ils peuvent être utilisés en tant que champs « fictifs », pour l'alignement.  Un champ de bits sans nom dont la largeur est spécifiée à 0 garantit que le stockage du membre qui le suit dans la *liste de déclaration des structures* commence à la limite d'un `int`.  
  
 Les champs de bits doivent également être assez longs pour contenir le modèle de bit.  Par exemple, ces deux instructions ne sont pas autorisées :  
  
```  
short a:17;        /* Illegal! */  
int long y:33;     /* Illegal! */  
```  
  
 Cet exemple définit un tableau à deux dimensions de structures nommé `screen`.  
  
```  
struct   
{  
    unsigned short icon : 8;  
    unsigned short color : 4;  
    unsigned short underline : 1;  
    unsigned short blink : 1;  
} screen[25][80];  
```  
  
 Le tableau contient 2000 éléments.  Chaque élément est une structure individuelle contenant quatre membres de champ de bits : `icon`, `color`, `underline`, et `blink`.  La taille de chaque structure est de deux octets.  
  
 Les champs de bits ont la même sémantique que le type entier.  Cela signifie qu'un champ de bits est utilisé dans des expressions de la même façon qu'une variable de même type de base est utilisée, indépendamment du nombre de bits présent dans le champ de bits.  
  
 **Spécifique à Microsoft**  
  
 Les champs de bits définis comme des `int` sont traités comme signés.  Une extension Microsoft à la norme C ANSI permet d'inclure des types `char`, **long** \( **signed** et `unsigned`\) dans des champs de bits.  Les champs de bits sans nom avec type de base **long**, **short** ou `char` \(**signed** ou `unsigned`\) forcent l'alignement à une limite appropriée pour type de base.  
  
 Les champs de bits sont alloués dans un entier du bit de poids faible au bits de poids fort.  Dans le code ci\-dessous.  
  
```  
struct mybitfields  
{  
    unsigned short a : 4;  
    unsigned short b : 5;  
    unsigned short c : 7;  
} test;  
  
int main( void );  
{  
    test.a = 2;  
    test.b = 31;  
    test.c = 0;  
}  
```  
  
 les bits seraient disposés ainsi :  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 Puisque la famille processeurs 8086 enregistre le bas octet de valeurs entières avant l'octet élevé, l'entier `0x01F2` ci\-dessus est stocké en mémoire physique comme `0xF2` suivi de `0x01`.  
  
 **END Spécifique à Microsoft**  
  
## Voir aussi  
 [Déclarations de structure](../c-language/structure-declarations.md)