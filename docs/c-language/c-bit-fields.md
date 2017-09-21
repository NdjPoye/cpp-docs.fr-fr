---
title: Champs de bits C | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- bitfields
- bit fields
ms.assetid: 9faf74c4-7fd5-4b44-ad18-04485193d06e
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e0370ea8d0d519ca10f3035c7a84748d0888e8d7
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="c-bit-fields"></a>Champs de bits C
En plus des déclarateurs pour les membres d’une structure ou une union, un déclarateur de structure peut également être un nombre de bits spécifié, appelé « champ de bits ». Sa longueur est définie à partir du déclarateur pour le nom de champ par un signe deux-points. Un champ de bits est interprété comme un type intégral.  
  
## <a name="syntax"></a>Syntaxe  
 *struct-declarator* :  
 *declarator*  
  
 *type-specifier declarator* opt**:** *constant-expression*  
  
 *expression constante* spécifie la largeur du champ en bits. *type-specifier* pour le `declarator` doit être `unsigned int`, **signed int**, ou `int`, et *constant-expression* doit être une valeur d’entier non négatif. Si la valeur est zéro, la déclaration n’a aucun `declarator`. Les tableaux de champs de bits, pointeurs vers des champs de bits et fonctions qui retournent des champs de bits ne sont pas autorisés. Le `declarator` facultatif désigne le champ de bits. Les champs de bits peuvent uniquement être déclarés comme faisant partie d’une structure. L’opérateur address-of (**&**) ne peut pas être appliqué aux composants de champ de bits.  
  
 Les champs de bits sans nom ne peuvent pas être référencés et leur contenu lors de l’exécution est imprévisible. Ils peuvent être utilisés comme des champs « factices », à des fins d’alignement. Un champ de bits sans nom dont la largeur est spécifiée comme 0 garantit que le stockage pour le membre suivant dans *struct-declaration-list* démarre sur une limite `int`.  
  
 Les champs de bits doivent également être suffisamment longs pour contenir le modèle binaire. Par exemple, les deux instructions suivantes ne sont pas autorisées :  
  
```  
short a:17;        /* Illegal! */  
int long y:33;     /* Illegal! */  
```  
  
 Cet exemple définit un tableau de structures à deux dimensions nommé `screen`.  
  
```  
struct   
{  
    unsigned short icon : 8;  
    unsigned short color : 4;  
    unsigned short underline : 1;  
    unsigned short blink : 1;  
} screen[25][80];  
```  
  
 Le tableau contient 2 000 éléments. Chaque élément est une structure individuelle qui contient quatre membres de champ de bits : `icon`, `color`, `underline` et `blink`. La taille de chaque structure est de deux octets.  
  
 Les champs de bits ont la même sémantique que le type entier. Cela signifie qu'un champ de bits est utilisé dans les expressions exactement de la même façon qu’une variable du même type de base serait utilisée, quel que soit le nombre de bits dans le champ de bits.  
  
 **Section spécifique à Microsoft**  
  
 Les champs de bits définis comme `int` sont considérés comme signés. Une extension Microsoft de la norme ANSI C autorise les types `char` et **long** (**signed** et `unsigned`) pour les champs de bits. Sans champs de bits avec le type de base **long**, **short** ou `char` (**signed** ou `unsigned`) forcent l’alignement sur une limite appropriée pour le type de base.  
  
 Les champs de bits sont alloués dans un entier du bit de poids le plus faible au bit de poids le plus fort. Dans le code suivant  
  
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
  
 les bits sont disposés comme suit :  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 Les processeurs de la gamme 8086 stockent l'octet faible des valeurs entières avant l'octet fort. L'entier `0x01F2` ci-dessus serait stocké en mémoire physique comme `0xF2` suivi de `0x01`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Déclarations de structure](../c-language/structure-declarations.md)