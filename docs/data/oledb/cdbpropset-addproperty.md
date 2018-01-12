---
title: CDBPropSet::AddProperty | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
dev_langs: C++
helpviewer_keywords: AddProperty method
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fa9c2d979bc98ebac543f0b17c7afdce2ab5f59b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropsetaddproperty"></a>CDBPropSet::AddProperty
Ajoute une propriété au jeu de propriétés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      bool AddProperty(   
   DWORD dwPropertyID,   
   const VARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCSTR szValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCWSTR szValue,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   bool bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   BYTE bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   short nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   long nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   float fltValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   double dblValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   CY cyValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 *dwPropertyID*  
 [in] L’ID de la propriété à ajouter. Utilisé pour initialiser le **dwPropertyID** de la `DBPROP` structure ajouté au jeu de propriétés.  
  
 `var`  
 [in] Variant utilisé pour initialiser la valeur de propriété pour la `DBPROP` structure ajouté au jeu de propriétés.  
  
 `szValue`  
 [in] Chaîne utilisée pour initialiser la valeur de propriété pour la `DBPROP` structure ajouté au jeu de propriétés.  
  
 `bValue`  
 [in] A **octets** ou une valeur booléenne utilisée pour initialiser la valeur de propriété pour la `DBPROP` structure ajouté au jeu de propriétés.  
  
 `nValue`  
 [in] Une valeur entière utilisée pour initialiser la valeur de propriété pour la `DBPROP` structure ajouté au jeu de propriétés.  
  
 *fltValue*  
 [in] Valeur à virgule flottante utilisée pour initialiser la valeur de propriété pour la `DBPROP` structure ajouté au jeu de propriétés.  
  
 `dblValue`  
 [in] Une valeur à virgule flottante double précision utilisée pour initialiser la valeur de propriété pour la `DBPROP` structure ajouté au jeu de propriétés.  
  
 `cyValue`  
 [in] Une valeur de devise CY utilisée pour initialiser la valeur de propriété pour la `DBPROP` structure ajouté au jeu de propriétés.  
  
## <a name="return-value"></a>Valeur de retour  
 **true** si la propriété a été ajoutée avec succès. dans le cas contraire, **false**.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDBPropSet (classe)](../../data/oledb/cdbpropset-class.md)   
 [Structure DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx)