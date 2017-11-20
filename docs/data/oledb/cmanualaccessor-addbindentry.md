---
title: CManualAccessor::AddBindEntry | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- AddBindEntry
- CManualAccessor.AddBindEntry
dev_langs: C++
helpviewer_keywords: AddBindEntry method
ms.assetid: 8556dda9-dda1-4f67-96bc-6031e6c6a271
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 15fe497839265bbe76f49bcbe915d91c493c22dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cmanualaccessoraddbindentry"></a>CManualAccessor::AddBindEntry
Ajoute une entrée de liaison pour les colonnes de sortie.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      void AddBindEntry(  
   DBORDINAL nOrdinal,  
   DBTYPE wType,  
   DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL   
) throw ( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) dans les *de référence du programmeur OLE DB*.  
  
 `nOrdinal`  
 [in] Numéro de colonne.  
  
 `wType`  
 [in] Type de données.  
  
 `nColumnSize`  
 [in] Taille de la colonne en octets.  
  
 `pData`  
 [in] Pointeur vers les données de colonne stockées dans la mémoire tampon.  
  
 `pLength`  
 [in] Pointeur vers la longueur de champ, si nécessaire.  
  
 `pStatus`  
 [in] Pointeur vers la variable à lier à l’état de la colonne, si nécessaire.  
  
## <a name="remarks"></a>Remarques  
 Pour utiliser cette fonction, vous devez d’abord appeler [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md). Vous ne pouvez pas ajouter plus d’entrées que le nombre de colonnes spécifié dans `CreateAccessor`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CManualAccessor (classe)](../../data/oledb/cmanualaccessor-class.md)   
 [Exemple DBVIEWER](../../visual-cpp-samples.md)