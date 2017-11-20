---
title: CDynamicAccessor::GetColumnInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetColumnInfo
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
dev_langs: C++
helpviewer_keywords: GetColumnInfo method
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c3d3b24ffce579d3a74706ca9a238059ed8eb08f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicaccessorgetcolumninfo"></a>CDynamicAccessor::GetColumnInfo
Retourne les métadonnées de colonne requises par la plupart des consommateurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT GetColumnInfo(   
   IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pRowset`  
 [in] Un pointeur vers le [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) interface.  
  
 *pColumns*  
 [out] Pointeur vers la mémoire dans lequel retourner le nombre de colonnes dans l’ensemble de lignes ; Ce nombre inclut la colonne des signets, si elle existe.  
  
 *ppColumnInfo*  
 [out] Pointeur vers la mémoire dans lequel retourner un tableau de **DBCOLUMNINFO** structures. Consultez la section « Structures DBCOLUMNINFO » dans [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) dans les *de référence du programmeur OLE DB*.  
  
 `ppStringsBuffer`  
 [out] Pointeur vers la mémoire dans lequel retourner un pointeur vers le stockage pour toutes les valeurs de chaîne (noms utilisés au sein de *columnid* ou *pwszName*) dans un bloc d’allocation unique.  
  
## <a name="return-value"></a>Valeur de retour  
 Un de la norme `HRESULT` valeurs.  
  
## <a name="remarks"></a>Remarques  
 Consultez [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) dans les *de référence du programmeur OLE DB* pour plus d’informations sur les types de données **DBORDINAL**, **DBCOLUMNINFO**, et **OLECHAR**.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)