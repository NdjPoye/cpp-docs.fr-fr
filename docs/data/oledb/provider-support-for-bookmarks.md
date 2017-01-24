---
title: "Prise en charge des signets par le fournisseur | Microsoft Docs"
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
  - "signets, OLE DB"
  - "IRowsetLocate (classe)"
  - "IRowsetLocate (classe), prise en charge des signets par le fournisseur"
  - "modèles du fournisseur OLE DB, signets"
  - "fournisseurs OLE DB, prise en charge des signets"
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge des signets par le fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'exemple de cette rubrique ajoute l'interface `IRowsetLocate` à la classe `CMyProviderRowset`.  Dans la plupart des cas, vous commencez par ajouter une interface à un objet COM existant.  Vous pouvez alors le tester en ajoutant des appels supplémentaires à partir des modèles du consommateur.  L'exemple illustre comment :  
  
-   ajouter une interface à un fournisseur ;  
  
-   déterminer dynamiquement les colonnes retournées au consommateur ;  
  
-   ajouter la prise en charge de signets .  
  
 L'interface `IRowsetLocate` hérite de l'interface `IRowset`.  Pour ajouter l'interface `IRowsetLocate`, héritez `CMyProviderRowset` de [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md).  
  
 L'ajout de l'interface `IRowsetLocate` est quelque peu différent de celui de la plupart des interfaces.  Pour aligner les VTABLE, les modèles du fournisseur OLE DB disposent d'un paramètre de modèle pour gérer l'interface dérivée.  Le code suivant montre la nouvelle liste d'héritage :  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
// CMyProviderRowset  
class CMyProviderRowset : public CRowsetImpl< CMyProviderRowset,   
      CTextData, CMyProviderCommand, CAtlArray<CTextData>,   
      CSimpleRow,   
          IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> >  
```  
  
 Les sixième, cinquième et quatrième paramètres sont tous ajoutés.  Cet exemple utilise les valeurs par défaut pour les quatrième et cinquième paramètres mais spécifie `IRowsetLocateImpl` comme sixième paramètre.  `IRowsetLocateImpl` est une classe de modèle OLE DB qui prend deux paramètres de modèle : ils raccordent l'interface `IRowsetLocate` à la classe `CMyProviderRowset`.  Pour ajouter la plupart des interfaces, vous pouvez sauter cette étape et passer directement à la suivante.  Seules les interfaces `IRowsetLocate` et `IRowsetScroll` doivent être gérées de cette façon.  
  
 Vous devez alors indiquer à `CMyProviderRowset` d'appeler `QueryInterface` pour l'interface `IRowsetLocate`.  Ajoutez la ligne `COM_INTERFACE_ENTRY(IRowsetLocate)` à la table.  Le mappage d'interface pour `CMyProviderRowset` doit apparaître comme indiqué dans le code ci\-dessous :  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
typedef CRowsetImpl< CMyProviderRowset, CTextData, CMyProviderCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> > _RowsetBaseClass;  
  
BEGIN_COM_MAP(CMyProviderRowset)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 Vous devez également raccorder votre table à la classe `CRowsetImpl`.  Ajoutez la macro COM\_INTERFACE\_ENTRY\_CHAIN pour raccorder la table `CRowsetImpl`.  Créez aussi un typedef appelé `RowsetBaseClass` qui contient les informations d'héritage.  Ce typedef est arbitraire et peut être ignoré.  
  
 Enfin, gérez l'appel **IColumnsInfo::GetColumnsInfo**.  Pour effectuer cette opération, vous devez normalement utiliser les macros PROVIDER\_COLUMN\_ENTRY.  Toutefois, un consommateur peut souhaiter utiliser des signets.  Vous devez pouvoir modifier les colonnes que le fournisseur retourne selon que le consommateur demande ou non un signet.  
  
 Pour gérer l'appel **IColumnsInfo::GetColumnsInfo**, supprimez la table **PROVIDER\_COLUMN** dans la classe `CTextData`.  La macro PROVIDER\_COLUMN\_MAP définit une fonction `GetColumnInfo`.  Vous devez définir votre propre fonction `GetColumnInfo`.  La déclaration de la fonction doit ressembler à ceci :  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CTextData  
{  
   ...  
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderRowset* pThis,   
        ULONG* pcCols);  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderCommand* pThis,   
        ULONG* pcCols);  
...  
};  
```  
  
 Ensuite, implémentez la fonction `GetColumnInfo` dans le fichier MyProviderRS.cpp, de la façon suivante :  
  
```  
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
  
template <class TInterface>  
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   CComQIPtr<TInterface> spProps = pPropsUnk;  
  
   CDBPropIDSet set(DBPROPSET_ROWSET);  
   set.AddPropertyID(DBPROP_BOOKMARKS);  
   DBPROPSET* pPropSet = NULL;  
   ULONG ulPropSet = 0;  
   HRESULT hr;  
  
   if (spProps)  
      hr = spProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
   // Check the property flag for bookmarks, if it is set, set the   
// zero ordinal entry in the column map with the bookmark   
// information.  
  
   if (pPropSet)  
   {  
      CComVariant var = pPropSet->rgProperties[0].vValue;  
      CoTaskMemFree(pPropSet->rgProperties);  
      CoTaskMemFree(pPropSet);  
  
      if ((SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE)))  
      {  
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,   
                     sizeof(DWORD), DBTYPE_BYTES,  
            0, 0, GUID_NULL, CAgentMan, dwBookmark,         
                        DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
  
   }  
  
   // Next set the other columns up.  
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field1"), 1, 16, DBTYPE_STR,   
          0xFF, 0xFF, GUID_NULL, CTextData, szField1)  
   ulCols++;  
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field2"), 2, 16, DBTYPE_STR,  
       0xFF, 0xFF, GUID_NULL, CTextData, szField2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
  
ATLCOLUMNINFO* CTextData::GetColumnInfo(CMyProviderCommand* pThis,   
     ULONG* pcCols)  
{  
   return CommonGetColInfo<ICommandProperties>(pThis->GetUnknown(),  
        pcCols);  
}  
  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(RUpdateRowset* pThis, ULONG* pcCols)  
{  
   return CommonGetColInfo<IRowsetInfo>(pThis->GetUnknown(), pcCols);  
}  
```  
  
 `GetColumnInfo` vérifie d'abord si une propriété appelée **DBPROP\_IRowsetLocate** est définie.  OLE DB possède des propriétés pour chacune des interfaces facultatives liées à l'objet rowset.  Si le consommateur souhaite utiliser l'une de ces interfaces facultatives, il affecte à une propriété la valeur true.  Le fournisseur peut ainsi vérifier cette propriété et prendre des mesures spéciales.  
  
 Dans votre implémentation, vous obtenez la propriété en utilisant le pointeur désignant l'objet command.  Le pointeur `pThis` représente la classe rowset ou command.  Dans la mesure où vous utilisez des modèles ici, vous devez passer ceci en tant que pointeur `void`, sinon le code n'est pas compilé.  
  
 Spécifiez un tableau statique pour contenir les informations se rapportant aux colonnes.  Si le consommateur ne souhaite pas la colonne des signets, une entrée est perdue dans le tableau.  Vous pouvez affecter ce tableau de manière dynamique, mais vous devez alors veiller à l'éliminer correctement.  Cet exemple définit et utilise les macros ADD\_COLUMN\_ENTRY et ADD\_COLUMN\_ENTRY\_EX pour insérer les informations dans le tableau.  Vous pouvez ajouter les macros au fichier MyProviderRS.H, comme le montre le code suivant :  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member, flags) \  
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
  
 Pour tester le code dans le consommateur, vous devez apporter quelques modifications au gestionnaire `OnRun`.  La première modification à effectuer concerne le code que vous ajoutez pour ajouter une propriété au jeu de propriétés.  Le code affecte la valeur true à la propriété **DBPROP\_IRowsetLocate**, indiquant ainsi au fournisseur que vous voulez la colonne des signets.  Le code du gestionnaire `OnRun` doit apparaître de la façon suivante :  
  
```  
//////////////////////////////////////////////////////////////////////  
// TestProv Consumer Application in TestProvDlg.cpp  
  
void CTestProvDlg::OnRun()   
{  
   CCommand<CAccessor<CProvider> > table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL, NULL, NULL,   
          NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   CDBPropSet propset(DBPROPSET_ROWSET);  
   propset.AddProperty(DBPROP_IRowsetLocate, true);  
   if (table.Open(session, _T("c:\\public\\testprf2\\myData.txt"),   
          &propset) != S_OK)  
      return;  
  
   CBookmark<4> tempBookmark;  
   ULONG ulCount=0;  
   while (table.MoveNext() == S_OK)  
   {  
  
      DBCOMPARE compare;  
      if (ulCount == 2)  
         tempBookmark = table.bookmark;  
      HRESULT hr = table.Compare(table.dwBookmark, table.dwBookmark,  
                 &compare);  
      if (FAILED(hr))  
         ATLTRACE(_T("Compare failed: 0x%X\n"), hr);  
      else  
         _ASSERTE(compare == DBCOMPARE_EQ);  
  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
      ulCount++;  
   }  
  
   table.MoveToBookmark(tempBookmark);  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 La boucle while contient le code pour appeler la méthode `Compare` dans l'interface `IRowsetLocate`.  Le code que vous possédez doit toujours passer dans la mesure où vous comparez exactement les mêmes signets.  Stockez aussi un signet dans une variable temporaire de façon que vous puissiez l'utiliser une fois que la boucle while a fini d'appeler la fonction `MoveToBookmark` dans les modèles du consommateur.  La fonction `MoveToBookmark` appelle la méthode `GetRowsAt` dans `IRowsetLocate`.  
  
 Vous devez également mettre à jour l'enregistrement utilisateur dans le consommateur.  Ajoutez une entrée dans la classe pour gérer un signet et une entrée dans **COLUMN\_MAP** :  
  
```  
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
class CProvider  
{  
// Attributes  
public:  
   CBookmark<4>    bookmark;  // Add this line  
   char   szCommand[16];  
   char   szText[256];  
  
   // Binding Maps  
BEGIN_ACCESSOR_MAP(CProvider, 1)  
   BEGIN_ACCESSOR(0, true)   // auto accessor  
      BOOKMARK_ENTRY(bookmark)  // Add this line  
      COLUMN_ENTRY(1, szField1)  
      COLUMN_ENTRY(2, szField2)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
 Une fois que vous avez mis le code à jour, vous devez pouvoir générer et exécuter le fournisseur avec l'interface `IRowsetLocate`.  
  
## Voir aussi  
 [Techniques avancées du fournisseur](../../data/oledb/advanced-provider-techniques.md)