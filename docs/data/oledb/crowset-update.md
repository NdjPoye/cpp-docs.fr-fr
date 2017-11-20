---
title: CRowset::Update | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset.Update
- ATL.CRowset.Update
- ATL.CRowset<TAccessor>.Update
- ATL::CRowset<TAccessor>::Update
- CRowset<TAccessor>::Update
- CRowset::Update
- CRowset<TAccessor>.Update
- ATL::CRowset::Update
dev_langs: C++
helpviewer_keywords: Update method
ms.assetid: cd5fedc8-2b85-4cb8-8c40-c79576316903
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 17541ea324fa7d6c314501f1e09519881a1fff7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetupdate"></a>CRowset::Update
Transmet toutes les modifications apportées à la ligne en cours depuis la dernière extraction ou **mise à jour** appeler sur celle-ci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT Update(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pcRows`  
 [out] Un pointeur vers l’emplacement où **mettre à jour** retourne le nombre de lignes qu’il a tenté de mettre à jour, si nécessaire.  
  
 `phRow`  
 [out] Un pointeur vers l’emplacement où **mettre à jour** retourne le handle de la ligne, il avait tenté de mettre à jour. Aucun handle n’est retournée si `phRow` a la valeur null.  
  
 `pStatus`  
 [out] Un pointeur vers l’emplacement où **mise à jour** retourne la valeur d’état de ligne. Aucun état n’est retournée si `pStatus` a la valeur null.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Remarques  
 Transmet les modifications apportées à la ligne actuelle dans la mesure où cette ligne dernière extraction ou mis à jour en attente (à l’aide de **mise à jour** ou [UpdateAll](../../data/oledb/crowset-updateall.md)). En général, vous appelez [SetData](../../data/oledb/crowset-setdata.md) pour définir des valeurs de données dans des colonnes dans une ligne, puis appelez **mise à jour** pour transmettre ces modifications.  
  
 Cette méthode requiert l’interface facultative `IRowsetUpdate`, qui ne peut pas être pris en charge sur tous les fournisseurs ; si c’est le cas, la méthode retourne **E_NOINTERFACE**. Vous devez également définir **DBPROP_IRowsetUpdate** à `VARIANT_TRUE` avant d’appeler **ouvrir** sur la table ou d’une commande qui contient l’ensemble de lignes.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowset (classe)](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)