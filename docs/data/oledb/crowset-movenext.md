---
title: CRowset::MoveNext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CRowset<TAccessor>.MoveNext
- ATL.CRowset.MoveNext
- ATL::CRowset<TAccessor>::MoveNext
- CRowset<TAccessor>.MoveNext
- CRowset.MoveNext
- CRowset<TAccessor>::MoveNext
- CRowset::MoveNext
- ATL::CRowset::MoveNext
dev_langs:
- C++
helpviewer_keywords:
- MoveNext method
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 493a9c44a582dc51831f72f54b936c3af1307783
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetmovenext"></a>CRowset::MoveNext
Déplace le curseur à l’enregistrement suivant.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT MoveNext() throw();HRESULT MoveNext(LONG lSkip,   
   bool bForward= true) throw();  
```  
  
#### <a name="parameters"></a>Paramètres  
 `lSkip`  
 [in] Le nombre de lignes à ignorer avant l’extraction.  
  
 `bForward`  
 [in] Passer **true** d’avancer jusqu'à l’enregistrement suivant, **false** à déplacer vers le haut.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard. Lorsque la fin de l’ensemble de lignes a été atteinte, retourne **DB_S_ENDOFROWSET**.  
  
## <a name="remarks"></a>Notes  
 Extrait la ligne suivante séquentielle à partir de la `CRowset` objet, sans oublier la position précédente. Si vous le souhaitez, vous pouvez choisir d’ignorer `lSkip` lignes ou en arrière.  
  
 Cette méthode requiert que vous définissez les propriétés suivantes avant d’appeler **ouvrir** sur la table ou d’une commande qui contient l’ensemble de lignes :  
  
-   **DBPROP_CANSCROLLBACKWARDS** doit être `VARIANT_TRUE` si `lSkip` < 0  
  
-   **DBPROP_CANFETCHBACKWARDS** doit être `VARIANT_TRUE` si `bForward` = false  
  
 Dans le cas contraire (si `lSkip` > = 0 et `bForward` = true), vous n’avez pas besoin de définir des propriétés supplémentaires.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowset (classe)](../../data/oledb/crowset-class.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)