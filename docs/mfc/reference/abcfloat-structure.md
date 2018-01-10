---
title: Abcfloat, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ABCFLOAT
dev_langs: C++
helpviewer_keywords: ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b58871df5a526455297dd6d092f98e9facd901ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="abcfloat-structure"></a>ABCFLOAT, structure
Le `ABCFLOAT` structure contient les largeurs de A, B et C d’un caractère de la police.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct _ABCFLOAT { /* abcf */  
    FLOAT abcfA;  
    FLOAT abcfB;  
    FLOAT abcfC;  
} ABCFLOAT;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *abcfA*  
 Spécifie l’espacement A du caractère. L’espacement A est la distance à ajouter à la position actuelle avant de dessiner le glyphe de caractère.  
  
 *abcfB*  
 Spécifie l’espacement B du caractère. L’espacement B est la largeur de la partie dessinée du glyphe de caractère.  
  
 *abcfC*  
 Spécifie l’espacement C du caractère. L’espacement C est la distance à ajouter à la position actuelle pour fournir des espaces blancs à droite du glyphe de caractère.  
  
## <a name="remarks"></a>Notes  
 Les largeurs de A, B et C sont mesurées le long de la ligne de base de la police. L’incrément de caractère (largeur totale) d’un caractère est la somme des espaces A, B et C. L’un ou l’espace de C peut être négatif pour indiquer underhangs ou dépassements.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** wingdi.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

