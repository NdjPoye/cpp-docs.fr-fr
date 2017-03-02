---
title: ABC (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: c8b49cd8a94c5ff580393814be08b1819a1eca52
ms.lasthandoff: 02/24/2017

---
# <a name="abc-structure"></a>ABC, structure
Le **ABC** structure contient la largeur d’un caractère dans une police TrueType.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct _ABC { /* abc */  
    int abcA;  
    UINT abcB;  
    int abcC;  
} ABC;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *abcA*  
 Spécifie l’espacement entre un caractère. L’espacement A est la distance à ajouter à la position actuelle avant de dessiner le glyphe de caractères.  
  
 *abcB*  
 Spécifie l’espacement B du caractère. L’espacement de B est la largeur de la partie du glyphe caractère dessinée.  
  
 *abcC*  
 Spécifie l’espacement C du caractère. L’espacement C est la distance à ajouter à la position actuelle pour fournir des espaces à droite du glyphe de caractères.  
  
## <a name="remarks"></a>Remarques  
 La largeur totale d’un caractère est la somme des espaces A, B et C. L’une ou l’espace C peut être négatif pour indiquer underhangs ou déborder.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** wingdi.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)



