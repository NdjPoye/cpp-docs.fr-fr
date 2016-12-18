---
title: "Champs de bits C++ | Microsoft Docs"
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
  - "champs de bits"
  - "champs de bits"
  - "champs (C++), de bits"
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Champs de bits C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes et les structures peuvent contenir des membres qui occupent moins d'espace de stockage qu'un type intégral.  Ces membres sont spécifiés en tant que champs de bits.  La syntaxe de la spécification *member\-declarator* de champ de bits est la suivante :  
  
## Syntaxe  
  
```  
  
declarator  : constant-expression  
```  
  
## Notes  
 L'élément `declarator` \(facultatif\) est le nom par lequel le membre est accessible dans le programme.  Il doit s'agir d'un type intégral \(y compris les types énumérés\).  *constant\-expression* spécifie le nombre de bits que le membre occupe dans la structure.  Les champs de bits anonymes, autrement dit les membres de champ de bits sans identificateur, peuvent être utilisés pour le remplissage.  
  
> [!NOTE]
>  Un champ de bits sans nom de largeur 0 force l'alignement du champ de bits suivant sur la prochaine limite de `type`, où `type` est le type du membre.  
  
 L'exemple suivant déclare une structure qui contient des champs de bits :  
  
```  
// bit_fields1.cpp  
// compile with: /LD  
struct Date {  
   unsigned short nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned short nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned short nMonth    : 5;    // 0..12  (5 bits)  
   unsigned short nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 La disposition de mémoire conceptuelle d'un objet de type `Date` est illustrée dans la figure suivante.  
  
 ![Graphique Disposition en mémoire d'un objet date](../cpp/media/vc38uq1.png "vc38UQ1")  
Disposition de la mémoire d'un objet Date  
  
 Notez que `nYear` a une longueur de 8 bits et provoquerait un dépassement de la limite de mot du type déclaré, **unsigned short**.  Par conséquent, il est lancé au début d'un nouveau **unsigned short**.  Il n'est pas nécessaire que tous les champs de bits tiennent dans un objet du type sous\-jacent ; de nouvelles unités de stockage sont allouées en fonction du nombre de bits demandé dans la déclaration.  
  
 **Section spécifique à Microsoft**  
  
 Le classement des données déclarées comme champs de bits s'étend du bit faible au bit de poids fort, comme illustré dans la figure ci\-dessus.  
  
 **FIN de la section spécifique à Microsoft**  
  
 Si la déclaration d'une structure inclut un champ sans nom de longueur 0, comme indiqué dans l'exemple suivant,  
  
```  
// bit_fields2.cpp  
// compile with: /LD  
struct Date {  
   unsigned nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned           : 0;    // Force alignment to next boundary.  
   unsigned nMonth    : 5;    // 0..12  (5 bits)  
   unsigned nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 la disposition de la mémoire se présente comme dans la figure suivante.  
  
 ![Disposition d'un objet date avec un champ de bits de longueur 0](../cpp/media/vc38uq2.png "vc38UQ2")  
Disposition d'un objet Date avec un champ de bits de longueur 0  
  
 Le type sous\-jacent d'un champ de bits doit être un type intégral, comme décrit dans [Types fondamentaux](../cpp/fundamental-types-cpp.md).  
  
## Restrictions sur les champs de bits  
 La liste suivante détaille les opérations erronées sur les champs de bits :  
  
1.  Prise de l'adresse d'un champ de bits.  
  
2.  Initialisation d'une référence avec un champ de bits.  
  
## Voir aussi  
 [Classes et structs](../cpp/classes-and-structs-cpp.md)