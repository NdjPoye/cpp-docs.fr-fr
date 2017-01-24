---
title: "D&#233;termination de mani&#232;re dynamique des colonnes retourn&#233;es au consommateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "signets (C++), déterminer les colonnes de manière dynamique"
  - "déterminer les colonnes de manière dynamique (C++)"
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;termination de mani&#232;re dynamique des colonnes retourn&#233;es au consommateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les macros PROVIDER\_COLUMN\_ENTRY gèrent normalement l'appel **IColumnsInfo::GetColumnsInfo**.  Toutefois, parce qu'un consommateur peut choisir d'utiliser des signets, le fournisseur doit être capable de modifier les colonnes retournées si le consommateur demande un signet.  
  
 Pour gérer l'appel **IColumnsInfo::GetColumnsInfo**, supprimez la macro PROVIDER\_COLUMN\_MAP, qui définit une fonction `GetColumnInfo`, de l'enregistrement utilisateur `CAgentMan` dans MyProviderRS.h et remplacez\-la par la définition de votre propre fonction `GetColumnInfo` :  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
class CAgentMan  
{  
public:  
   DWORD dwBookmark;  
   TCHAR szCommand[256];  
   TCHAR szText[256];  
   TCHAR szCommand2[256];  
   TCHAR szText2[256];  
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
   bool operator==(const CAgentMan& am)  
   {  
      return (lstrcmpi(szCommand, am.szCommand) == 0);  
   }  
  
};  
```  
  
 Ensuite, implémentez la fonction `GetColumnInfo` dans MyProviderRS.cpp, comme le montre le code suivant.  
  
 `GetColumnInfo` vérifie d'abord si la propriété OLE DB **DBPROP\_BOOKMARKS** est définie.  Pour obtenir la propriété, `GetColumnInfo` utilise un pointeur \(`pRowset`\) désignant l'objet rowset.  Le pointeur `pThis` représente la classe qui a créé l'ensemble de lignes qui est la classe contenant le mappage de propriété.  `GetColumnInfo` convertit le type du pointeur `pThis` en un pointeur `RMyProviderRowset`.  
  
 Pour vérifier la présence de la propriété **DBPROP\_BOOKMARKS**, `GetColumnInfo` utilise l'interface `IRowsetInfo`, que vous pouvez obtenir en appelant `QueryInterface` sur l'interface `pRowset`.  Comme solution de rechange, vous pouvez utiliser une méthode ATL [CComQIPtr](../../atl/reference/ccomqiptr-class.md).  
  
```  
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(void* pThis, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   // Check the property flag for bookmarks; if it is set, set the zero   
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
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),   
         DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
         DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
   }  
  
   // Next, set the other columns up.  
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
  
 Cet exemple loge les informations sur les colonnes dans un tableau statique.  Si le consommateur ne souhaite pas la colonne signets, une entrée du tableau reste inutilisée.  Pour gérer les informations, vous créez deux macros de tableau : ADD\_COLUMN\_ENTRY et ADD\_COLUMN\_ENTRY\_EX.  ADD\_COLUMN\_ENTRY\_EX prend un paramètre supplémentaire, `flags`, qui est nécessaire si vous désignez une colonne signets.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision,   
scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type,   
precision, scale, guid, dataClass, member, flags) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = flags; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member); \  
   memset(&(_rgColumns[ulCols].columnid), 0, sizeof(DBID)); \  
   _rgColumns[ulCols].columnid.uName.pwszName = (LPOLESTR)name;  
```  
  
 Dans la fonction `GetColumnInfo`, la macro de signets est utilisée de la façon suivante :  
  
```  
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),  
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
   DBCOLUMNFLAGS_ISBOOKMARK)  
```  
  
 Vous pouvez à présent compiler et exécuter le fournisseur amélioré.  Pour tester le fournisseur, modifiez le consommateur de test comme décrit dans [Implémentation d'un consommateur simple](../../data/oledb/implementing-a-simple-consumer.md).  Exécutez le consommateur de test avec le fournisseur.  Vérifiez que le consommateur de test récupère les chaînes appropriées à partir du fournisseur lorsque vous cliquez sur le bouton **Exécuter** dans la boîte de dialogue **Consommateur de test**.  
  
## Voir aussi  
 [Amélioration du fournisseur simple accessible en lecture seule](../../data/oledb/enhancing-the-simple-read-only-provider.md)