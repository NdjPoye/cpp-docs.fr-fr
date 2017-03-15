---
title: "CDataSource::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataSource::Open"
  - "ATL.CDataSource.Open"
  - "CDataSource::Open"
  - "CDataSource.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open (méthode)"
ms.assetid: a6d28bd1-799a-48ed-8993-5f82d1705b77
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CDataSource::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ouvre une connexion à une source de données en utilisant un moniker **CLSID**, **ProgID** ou `CEnumerator` ou présente une invite à l'utilisateur sous forme de boîte de dialogue de recherche.  
  
## Syntaxe  
  
```  
  
        HRESULT Open(  
   const CLSID& clsid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CLSID& clsid,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   HWND hWnd = GetActiveWindow( ),  
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET   
) throw( );  
HRESULT Open(   
   LPCWSTR szProgID,   
   DBPROPSET* pPropSet = NULL,   
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(   
   LPCSTR szProgID,   
   LPCTSTR pName,   
   LPCTSTR pUserName = NULL,   
   LPCTSTR pPassword = NULL,   
   long nInitMode = 0   
) throw( );  
```  
  
#### Paramètres  
 `clsid`  
 \[in\] **CLSID** du fournisseur de données.  
  
 *pPropSet*  
 \[in\] Pointeur désignant un tableau de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) contenant les propriétés et les valeurs à définir.  Consultez [Jeux de propriétés et groupes de propriétés](https://msdn.microsoft.com/en-us/library/ms713696.aspx) dans le *Guide de référence du programmeur OLE DB* dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *nPropertySets*  
 \[in\] Nombre de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) passées dans l'argument *pPropSet*.  
  
 *pName*  
 \[in\] Nom de la base de données à laquelle se connecter.  
  
 *pUserName*  
 \[in\] Nom de l'utilisateur.  
  
 *pPassword*  
 \[in\] Mot de passe de l'utilisateur.  
  
 `nInitMode`  
 \[in\] Mode d'initialisation de la base de données.  Pour obtenir la liste des modes d'initialisation valides, consultez [Propriétés d'initialisation](https://msdn.microsoft.com/en-us/library/ms723127.aspx)dans le *Guide de référence du programmeur OLE DB* dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Si `nInitMode` est égal à zéro, aucun mode d'initialisation n'est inclus dans le jeu de propriétés utilisé pour ouvrir la connexion.  
  
 `szProgID`  
 \[in\] Identificateur de programme.  
  
 `enumerator`  
 \[in\] Objet [CEnumerator](../../data/oledb/cenumerator-class.md) utilisé pour obtenir un moniker pour ouvrir la connexion quand l'appelant ne spécifie pas de **CLSID**.  
  
 `hWnd`  
 \[in\] Handle de fenêtre devant être le parent de la boîte de dialogue.  L'utilisation de la surcharge de fonction avec le paramètre `hWnd` a pour effet d'appeler automatiquement les composants de service ; consultez les Notes pour plus d'informations.  
  
 `dwPromptOptions`  
 \[in\] Détermine le style de la boîte de dialogue de recherche à afficher.  Consultez Msdasc.h pour connaître les valeurs possibles.  
  
## Valeur de retour  
 `HRESULT` standard.  
  
## Notes  
 La surcharge de méthode qui utilise le paramètre `hWnd` ouvre un objet source de données à l'aide des composants de service d'oledb32.dll ; cette DLL contient l'implémentation des fonctionnalités Composants de service telles que la mise en pool de ressources, l'inscription de transaction automatique, etc.  Pour plus d'informations, consultez « Services OLE DB » dans le Guide de référence du programmeur OLE DB à l'adresse [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
 Les surcharges de méthode qui n'utilisent pas le paramètre `hWnd` ouvrent un objet source de données sans utiliser les composants de service dans oledb32.dll.  Un objet [CDataSource](../../data/oledb/cdatasource-class.md) ouvert avec ces surcharges de fonction ne peut utiliser aucune fonctionnalité des composants de service.  
  
## Exemple  
 Le code suivant montre comment ouvrir une source de données Jet 4.0 avec les modèles OLE DB.  Même si vous traitez la source de données Jet comme une source de données OLE DB,  votre appel à **Open** a besoin de deux jeux de propriétés : un pour **DBPROPSET\_DBINIT** et un autre pour **DBPROPSET\_JETOLEDB\_DBINIT**, ce qui vous permet de définir **DBPROP\_JETOLEDB\_DATABASEPASSWORD**.  
  
 [!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/CPP/cdatasource-open_1.cpp)]  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataSource, classe](../../data/oledb/cdatasource-class.md)