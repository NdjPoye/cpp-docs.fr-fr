---
title: CRowset::SetData | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CRowset<TAccessor>.SetData
- SetData
- ATL::CRowset::SetData
- CRowset<TAccessor>.SetData
- CRowset::SetData
- ATL.CRowset.SetData
- CRowset.SetData
- CRowset<TAccessor>::SetData
- ATL::CRowset<TAccessor>::SetData
dev_langs:
- C++
helpviewer_keywords:
- SetData method
ms.assetid: 68125142-8510-4132-9393-e39efd39c784
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2d9f42397ffaa186bfd96db454251c687b634d69
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetsetdata"></a>CRowset::SetData
Définit les valeurs de données dans une ou plusieurs colonnes d’une ligne.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetData() const throw();   


HRESULT SetData(int nAccessor) const throw();  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nAccessor`  
 [in] Le numéro de l’accesseur à utiliser pour accéder aux données.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Pour le `SetData` formulaire qui accepte aucun argument, tous les utilisateurs connectés sont utilisés pour mettre à jour. En général, vous appelez **SetData** pour définir les valeurs de données dans des colonnes dans une ligne, puis appelez [mise à jour](../../data/oledb/crowset-update.md) pour transmettre ces modifications.  
  
 Cette méthode requiert l’interface facultative `IRowsetChange`, qui ne peut pas être pris en charge sur tous les fournisseurs ; si c’est le cas, la méthode retourne **E_NOINTERFACE**. Vous devez également définir **DBPROP_IRowsetChange** à `VARIANT_TRUE` avant d’appeler **ouvrir** sur la table ou d’une commande qui contient l’ensemble de lignes.  
  
 L’opération de paramétrage peut échouer si une ou plusieurs colonnes n’est pas accessible en écriture. Modifier le mappage de votre curseur pour corriger ce problème.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowset (classe)](../../data/oledb/crowset-class.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)