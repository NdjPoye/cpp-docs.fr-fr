---
title: Liaison dynamique des colonnes dans votre fournisseur | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- columns [C++], dynamic column binding
- dynamic column binding
- providers [C++], dynamic column binding
ms.assetid: 45e811e3-f5a7-4627-98cc-bf817c4e556e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f95dde27d6958bd9f1ad40bc411c7c434634879b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="dynamically-binding-columns-in-your-provider"></a>Liaison dynamique des colonnes dans votre fournisseur
Assurez-vous que vous avez vraiment besoin de liaison dynamique des colonnes. Vous en aurez besoin, car :  
  
-   Les colonnes de l’ensemble de lignes ne sont pas définies au moment de la compilation.  
  
-   Vous prenez en charge un élément tel que les signets qui ajoute des colonnes.  
  
### <a name="to-implement-dynamic-column-binding"></a>Pour implémenter la liaison de colonne dynamique  
  
1.  Supprimer les **PROVIDER_COLUMN_MAP**s à partir de votre code.  
  
2.  Dans l’enregistrement utilisateur (votre structure), ajoutez la déclaration suivante :  
  
    ```  
    static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
    ```  
  
3.  Implémentez la `GetColumnInfo` (fonction). Cette fonction indique comment les informations sont stockées. Vous devrez peut-être obtenir des propriétés ou autres informations pour cette fonction. Vous souhaiterez peut-être créer une macro, similaire à la [COLUMN_ENTRY](../../data/oledb/column-entry.md) macro, pour ajouter vos propres informations.  
  
     L’exemple suivant montre un `GetColumnInfo` (fonction).  
  
    ```  
    // Check the property flag for bookmarks, if it is set, set the zero  
    // ordinal entry in the column map with the bookmark information.  
    CAgentRowset* pRowset = (CAgentRowset*) pThis;  
    CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
    CDBPropIDSet set(DBPROPSET_ROWSET);  
    set.AddPropertyID(DBPROP_BOOKMARKS);  
    DBPROPSET* pPropSet = NULL;  
    ULONG ulPropSet = 0;  
    HRESULT hr;  
  
    if (spRowsetProps)  
       hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
    if (pPropSet)  
    {  
       CComVariant var = pPropSet->rgProperties[0].vValue;  
       CoTaskMemFree(pPropSet->rgProperties);  
       CoTaskMemFree(pPropSet);  
  
       if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
       {  
          ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD), DBTYPE_BYTES,   
             0, 0, GUID_NULL, CAgentMan, dwBookmark, DBCOLUMNFLAGS_ISBOOKMARK)  
          ulCols++;  
       }  
    }  
  
    // Next, set up the other columns.  
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,   
       GUID_NULL, CAgentMan, szCommand)  
    ulCols++;  
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,   
       GUID_NULL, CAgentMan, szText)  
    ulCols++;  
  
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,   
       GUID_NULL, CAgentMan, szCommand2)  
    ulCols++;  
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,   
       GUID_NULL, CAgentMan, szText2)  
    ulCols++;  
  
    if (pcCols != NULL)  
       *pcCols = ulCols;  
  
    return _rgColumns;  
    }  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des modèles du fournisseur OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)