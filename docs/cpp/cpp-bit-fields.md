---
title: Champs de bits C++ | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- bitfields [C++]
- fields [C++], bit
- bit fields
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff6b2a37c511313bd129705da38e66380e89edae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="c-bit-fields"></a>Champs de bits C++
Les classes et les structures peuvent contenir des membres qui occupent moins d'espace de stockage qu'un type intégral. Ces membres sont spécifiés en tant que champs de bits. La syntaxe de champ de bits *déclarateur de membre* spécification suivante :  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
declarator  : constant-expression  
```  
  
## <a name="remarks"></a>Notes  
 L'élément `declarator` (facultatif) est le nom par lequel le membre est accessible dans le programme. Il doit s'agir d'un type intégral (y compris les types énumérés). Le *expression constante* Spécifie le nombre de bits, le membre occupe dans la structure. Les champs de bits anonymes, autrement dit les membres de champ de bits sans identificateur, peuvent être utilisés pour le remplissage.  
  
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
  
 ![Disposition de mémoire d’un objet date](../cpp/media/vc38uq1.png "vc38UQ1")  
Disposition de la mémoire d'un objet Date  
  
 Notez que `nYear` est de 8 bits et provoquerait un dépassement de la limite de mot du type déclaré, **court non signé**. Par conséquent, il est lancé au début d’une nouvelle **court non signé**. Il n'est pas nécessaire que tous les champs de bits tiennent dans un objet du type sous-jacent ; de nouvelles unités de stockage sont allouées en fonction du nombre de bits demandé dans la déclaration.  
  
 **Section spécifique à Microsoft**  
  
 Le classement des données déclarées comme champs de bits s'étend du bit faible au bit de poids fort, comme illustré dans la figure ci-dessus.  
  
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
  
 ![Disposition d’un objet Date avec zéro &#45; le champ de bits de longueur](../cpp/media/vc38uq2.png "vc38UQ2")  
Disposition d'un objet Date avec un champ de bits de longueur 0  
  
 Le type sous-jacent d’un champ de bits doit être un type intégral, comme décrit dans [Types fondamentaux](../cpp/fundamental-types-cpp.md).  
  
## <a name="restrictions-on-bit-fields"></a>Restrictions sur les champs de bits  
 La liste suivante détaille les opérations erronées sur les champs de bits :  
  
1.  Prise de l'adresse d'un champ de bits.  
  
2.  Initialisation d'une référence avec un champ de bits.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes et structs](../cpp/classes-and-structs-cpp.md)