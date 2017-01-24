---
title: "Simplification de l&#39;acc&#232;s aux donn&#233;es &#224; l&#39;aide d&#39;attributs de base de donn&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-attr.db_param"
  - "vc-attr.db_column"
  - "vc-attr.db_accessor"
  - "vc-attr.db_command"
  - "vc-attr.db_table"
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributs (C++), accès aux données"
  - "attributs (C++), base de données"
  - "attributs (C++), consommateur OLE DB"
  - "données (C++), simplifier l'accès"
  - "accès aux données (C++), attributs de bases de données"
  - "attributs de bases de données (C++)"
  - "bases de données (C++), attributs"
  - "OLE DB (consommateurs) (C++), attributs de bases de données"
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Simplification de l&#39;acc&#232;s aux donn&#233;es &#224; l&#39;aide d&#39;attributs de base de donn&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette procédure pas à pas illustre l'utilisation des attributs de base de données pour simplifier les opérations liées aux bases de données.  
  
 La méthode fondamentale d'accès aux informations à partir d'une base de données consiste à créer une classe de commande \(ou de table\) et une classe d'enregistrement d'utilisateur pour une table particulière dans la base de données.  Les attributs de base de données simplifient certaines des déclarations de modèles que vous deviez effectuer précédemment.  
  
 Pour illustrer l'utilisation des attributs de base de données, les sections qui suivent montrent deux déclarations équivalentes de classes de table et d'enregistrement utilisateur : la première utilise des attributs et la seconde utilise des modèles OLE DB.  Un tel code de déclaration est généralement placé dans un fichier d'en\-tête nommé pour l'objet table ou commande ; par exemple, Authors.h.  
  
 En comparant les deux fichiers, vous pouvez constater combien il est beaucoup plus simple d'utiliser les attributs.  Parmi les différences, il y a les suivantes :  
  
-   Avec les attributs, la déclaration se limite à une seule classe : `CAuthors`, alors qu'avec les modèles vous devez en déclarer deux : `CAuthorsNoAttrAccessor` et `CAuthorsNoAttr`.  
  
-   L'appel de `db_source` dans la version avec attributs est équivalent à l'appel `OpenDataSource()` dans la déclaration de modèle.  
  
-   L'appel de **db\_table** dans la version avec attributs est équivalent à la déclaration de modèle suivante :  
  
    ```  
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor> >  
    ```  
  
-   Les appels de **db\_column** dans la version avec attributs sont équivalents au mappage de colonnes \(consultez `BEGIN_COLUMN_MAP ... END_COLUMN_MAP`\) dans la déclaration de modèle.  
  
 Les attributs injectent une déclaration de classe d'enregistrement utilisateur à votre place.  La classe d'enregistrement utilisateur est équivalente à `CAuthorsNoAttrAccessor` dans la déclaration de modèle.  Si votre classe de table est `CAuthors`, la classe d'enregistrement utilisateur injectée sera nommée `CAuthorsAccessor`, et vous pouvez seulement afficher sa déclaration dans le code injecté.  Pour plus d'informations, consultez « Classes d'enregistrement utilisateur injectées par des attributs » dans [Enregistrements utilisateur](../../data/oledb/user-records.md).  
  
 Notez qu'aussi bien dans le code avec attributs que dans le code avec modèles, vous devez définir les propriétés du jeu de lignes à l'aide de `CDBPropSet::AddProperty`.  
  
 Pour plus d'informations sur les attributs présentés dans cette rubrique, consultez [Attributs du consommateur OLE DB](../../windows/ole-db-consumer-attributes.md).  
  
## Déclaration de tables et d'accesseurs à l'aide d'attributs  
 Le code suivant appelle `db_source` et **db\_table** sur la classe de table.  `db_source` spécifie la source de données et la connexion à utiliser.  **db\_table** injecte le code du modèle approprié pour déclarer une classe de table.  **db\_column** spécifie le mappage de colonnes et injecte la déclaration d'accesseur.  Vous pouvez utiliser des attributs du consommateur OLE DB dans tout projet qui prend en charge ATL.  
  
 Déclaration de table et d'accesseur à l'aide d'attributs :  
  
```  
//////////////////////////////////////////////////////////////////////  
// Table and accessor declaration using attributes  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// Table class declaration  
// (Note that you must provide your own connection string for db_source.)  
[  
   db_source(L"your connection string"),  
   db_table("Authors")  
]  
class CAuthors  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
};  
```  
  
## Déclaration de tables et d'accesseurs à l'aide de modèles  
 Voici la déclaration de tables et d'accesseurs effectuée à l'aide de modèles.  
  
```  
//////////////////////////////////////////////////////////////////////  
// Table and user record class declaration using templates  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// User record class declaration  
class CAuthorsNoAttrAccessor  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   LONG m_AuID;  
   TCHAR m_Author[51];  
   SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
   HRESULT OpenDataSource()  
   {  
      CDataSource _db;  
      HRESULT hr;  
      hr = _db.OpenFromInitializationString(L"your connection string");  
      if (FAILED(hr))  
      {  
#ifdef _DEBUG  
         AtlTraceErrorRecords(hr);  
#endif  
         return hr;  
      }  
      return m_session.Open(_db);  
   }  
   void CloseDataSource()  
   {  
      m_session.Close();  
   }  
   operator const CSession&()  
   {  
      return m_session;  
   }  
   CSession m_session;  
   BEGIN_COLUMN_MAP(CAuthorsNoAttrAccessor)  
      COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, m_dwAuIDLength, m_dwAuIDStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, m_dwAuthorLength, m_dwAuthorStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, m_dwYearBornLength, m_dwYearBornStatus)  
   END_COLUMN_MAP()  
};  
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor> >  
{  
public:  
   HRESULT OpenAll()  
   {  
      HRESULT hr;  
      hr = OpenDataSource();  
      if (FAILED(hr))  
         return hr;  
      __if_exists(GetRowsetProperties)  
      {  
         CDBPropSet propset(DBPROPSET_ROWSET);  
         __if_exists(HasBookmark)  
         {  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
         }  
         GetRowsetProperties(&propset);  
         return OpenRowset(&propset);  
      }  
      __if_not_exists(GetRowsetProperties)  
      {  
         __if_exists(HasBookmark)  
         {  
            CDBPropSet propset(DBPROPSET_ROWSET);  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
            return OpenRowset(&propset);  
         }  
      }  
      return OpenRowset();  
   }  
   HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)  
   {  
      HRESULT hr = Open(m_session, "Authors", pPropSet);  
#ifdef _DEBUG  
      if(FAILED(hr))  
         AtlTraceErrorRecords(hr);  
#endif  
      return hr;  
   }  
   void CloseAll()  
   {  
      Close();  
      CloseDataSource();  
   }  
};  
```  
  
## Voir aussi  
 [OLE DB Consumer Attributes](../../windows/ole-db-consumer-attributes.md)   
 [Attributes Walkthroughs](http://msdn.microsoft.com/fr-fr/73df1d5d-261a-4521-98fb-06dcbf5ec0d0)