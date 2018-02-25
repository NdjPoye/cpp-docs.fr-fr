---
title: CXMLAccessor::GetXMLRowData | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CXMLAccessor::GetXMLRowData
- ATL.CXMLAccessor.GetXMLRowData
- CXMLAccessor::GetXMLRowData
- CXMLAccessor.GetXMLRowData
- GetXMLRowData
dev_langs:
- C++
helpviewer_keywords:
- GetXMLRowData method
ms.assetid: 156b66e3-42fd-491c-8943-38cf5e36f687
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2e356be7a5ab7c125dc92a822384a3e6b02b8f8e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cxmlaccessorgetxmlrowdata"></a>CXMLAccessor::GetXMLRowData
Récupère le contenu entier d’une table en tant que données de chaîne au format XML, par ligne.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetXMLRowData(CSimpleStringW& strOutput,   
   bool bAppend = false) throw();  
```  
  
#### <a name="parameters"></a>Paramètres  
 `strOutput`  
 [out] Une référence à une mémoire tampon contenant les données de table doit être récupéré. Les données sont formatées sous forme de données de chaîne avec des noms de balise XML qui correspondent aux noms de colonne du magasin de données.  
  
 *bAppend*  
 [in] Valeur booléenne spécifiant s’il faut ajouter une chaîne à la fin des données de sortie.  
  
## <a name="return-value"></a>Valeur de retour  
 Un de la norme `HRESULT` valeurs.  
  
## <a name="remarks"></a>Notes  
 L’exemple suivant montre comment les données de ligne sont au format XML. `DATA` ci-dessous représente les données de ligne. Utilisez les méthodes pour passer à la ligne souhaitée de déplacement.  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CXMLAccessor, classe](../../data/oledb/cxmlaccessor-class.md)