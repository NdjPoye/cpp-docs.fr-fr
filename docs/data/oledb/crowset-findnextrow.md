---
title: CRowset::FindNextRow | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset.FindNextRow
- CRowset<TAccessor>.FindNextRow
- ATL::CRowset::FindNextRow
- CRowset::FindNextRow
- CRowset<TAccessor>::FindNextRow
- CRowset.FindNextRow
- ATL.CRowset<TAccessor>.FindNextRow
- ATL::CRowset<TAccessor>::FindNextRow
- FindNextRow
dev_langs: C++
helpviewer_keywords: FindNextRow method
ms.assetid: 36484df9-3625-4f15-bf69-db73a8d91c55
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9a7b3e68ef75344b6ee0e612fb104c9a21ea1bde
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetfindnextrow"></a>CRowset::FindNextRow
Recherche la ligne correspondante suivante après le signet spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT FindNextRow(   
   DBCOMPAREOP op,   
   BYTE* pData,   
   DBTYPE wType,   
   DBLENGTH nLength,   
   BYTE bPrecision,   
   BYTE bScale,   
   BOOL bSkipCurrent = TRUE,   
   CBookmarkBase* pBookmark = NULL    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `op`  
 [in] L’opération à utiliser pour comparer les valeurs de ligne. Pour les valeurs, consultez [IRowsetFind::FindNextRow](https://msdn.microsoft.com/en-us/library/ms723091.aspx).  
  
 `pData`  
 [in] Pointeur vers la valeur à mettre en correspondance.  
  
 `wType`  
 [in] Indique le type de données de la partie de la valeur de la mémoire tampon. Pour plus d’informations sur les indicateurs de type, consultez [des Types de données](https://msdn.microsoft.com/en-us/library/ms723969.aspx) dans les *de référence du programmeur OLE DB* dans le Kit de développement logiciel Windows.  
  
 `nLength`  
 [in] La longueur, en octets, de la structure de données de consommateur allouée pour la valeur de données. Pour plus d’informations, consultez la description de **cbMaxLen** dans [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) dans le *de référence du programmeur OLE DB.*  
  
 `bPrecision`  
 [in] La précision maximale utilisée lors de l’obtention des données. Utilisé uniquement si `wType` est `DBTYPE_NUMERIC`. Pour plus d’informations, consultez [Conversions impliquant des DBTYPE_DECIMAL ou DBTYPE_NUMERIC](https://msdn.microsoft.com/en-us/library/ms719714.aspx) dans les *de référence du programmeur OLE DB*.  
  
 `bScale`  
 [in] L’échelle utilisée lors de l’obtention des données. Utilisé uniquement si `wType` est `DBTYPE_NUMERIC` ou **DBTYPE_DECIMAL**. Pour plus d’informations, consultez [Conversions impliquant des DBTYPE_DECIMAL ou DBTYPE_NUMERIC](https://msdn.microsoft.com/en-us/library/ms719714.aspx) dans les *de référence du programmeur OLE DB*.  
  
 *bSkipCurrent*  
 [in] Le nombre de lignes à partir du signet à partir duquel commencer la recherche.  
  
 `pBookmark`  
 [in] Le signet de position à laquelle lancer une recherche.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Remarques  
 Cette méthode requiert l’interface facultative **IRowsetFind**, qui ne peut pas être pris en charge sur tous les fournisseurs ; si c’est le cas, la méthode retourne **E_NOINTERFACE**. Vous devez également définir **DBPROP_IRowsetFind** à `VARIANT_TRUE` avant d’appeler **ouvrir** sur la table ou d’une commande qui contient l’ensemble de lignes.  
  
 Pour plus d’informations sur l’utilisation de signets dans des consommateurs, consultez [à l’aide de signets](../../data/oledb/using-bookmarks.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowset (classe)](../../data/oledb/crowset-class.md)   
 [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)