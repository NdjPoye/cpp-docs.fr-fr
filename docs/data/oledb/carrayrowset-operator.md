---
title: CArrayRowset::operator | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CArrayRowset::operator[]
- CArrayRowset.operator[]
dev_langs: C++
helpviewer_keywords:
- operator [], arrays
- '[] operator'
- operator[], arrays
ms.assetid: 3bb8c310-cc1e-46e8-9711-9b565488acaa
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 61929df340fb12afc5c2abdc6bd9f4e8bd899108
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="carrayrowsetoperator"></a>CArrayRowset::operator
Fournit la syntaxe de type tableau pour l’accès à une ligne dans l’ensemble de lignes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      TAccessor  
      & operator[](int nrow);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `TAccessor`  
 Un paramètre basé sur un modèle qui spécifie le type d’accesseur stockée dans l’ensemble de lignes.  
  
 `nRow`  
 [in] Numéro de la ligne (élément de tableau) que vous souhaitez accéder.  
  
## <a name="return-value"></a>Valeur de retour  
 Le contenu de la ligne demandée.  
  
## <a name="remarks"></a>Notes  
 Si `nRow` dépasse le nombre de lignes dans l’ensemble de lignes, une exception est levée.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CArrayRowset, classe](../../data/oledb/carrayrowset-class.md)