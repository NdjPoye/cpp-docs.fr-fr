---
title: "M&#233;thodes de consommateur g&#233;n&#233;r&#233;es par l&#39;Assistant | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes et méthodes injectées par les attributs"
  - "CloseAll (méthode)"
  - "CloseDataSource (méthode)"
  - "classes et méthodes générées par l'Assistant Consommateur"
  - "GetRowsetProperties (méthode)"
  - "méthodes (C++), générées par l'Assistant Consommateur OLE DB"
  - "consommateurs OLE DB, méthodes et classes générées par l'Assistant"
  - "OpenAll (méthode)"
  - "OpenDataSource (méthode)"
  - "OpenRowset (méthode)"
  - "méthodes et classes générées par l'Assistant"
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# M&#233;thodes de consommateur g&#233;n&#233;r&#233;es par l&#39;Assistant
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'Assistant Consommateur OLE DB ATL et l'Assistant Application MFC génèrent certaines fonctions que vous devez connaître.  Notez que certaines méthodes sont implémentées différemment dans les projets avec attributs, d'où la présence de quelques avertissements ; chaque cas est abordé ci\-après.  Pour plus d'informations sur l'affichage de code injecté, consultez [Débogage de code injecté](../Topic/How%20to:%20Debug%20Injected%20Code.md).  
  
-   `OpenAll` ouvre la source de données, les jeux de lignes et active les signets le cas échéant.  
  
-   `CloseAll` ferme tous les jeux de lignes ouverts et diffuse l'exécution de toutes les commandes.  
  
-   `OpenRowset` est appelée par OpenAll pour ouvrir les jeux de lignes du consommateur.  
  
-   `GetRowsetProperties` récupère un pointeur désignant le jeu de propriétés du jeu de lignes permettant de définir les propriétés.  
  
-   `OpenDataSource` ouvre la source de données à l'aide de la chaîne d'initialisation spécifiée dans la boîte de dialogue **Propriétés des liaisons de données**.  
  
-   `CloseDataSource` ferme la source de données d'une manière appropriée.  
  
## OpenAll et CloseAll  
  
```  
HRESULT OpenAll();   
void CloseAll();  
```  
  
 L'exemple suivant montre comment appeler `OpenAll` et `CloseAll` lorsque vous exécutez la même commande de façon répétée.  Comparez l'exemple de code suivant dans [CCommand::Close](../../data/oledb/ccommand-close.md), qui montre une variation qui appelle **Close** et `ReleaseCommand` à la place de `CloseAll`.  
  
```  
int main(int argc, char* argv[])  
{  
   HRESULT hr;  
  
   hr = CoInitialize(NULL);  
  
   CCustOrdersDetail rs;      // Your CCommand-derived class  
   rs.m_OrderID = 10248;      // Open order 10248  
   hr = rs.OpenAll();         // (Open also executes the command)  
   hr = rs.MoveFirst();         // Move to the first row and print it  
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );  
  
   // Close the first command execution  
   rs.Close();  
  
   rs.m_OrderID = 10249;      // Open order 10249 (a new order)  
   hr = rs.Open();            // (Open also executes the command)  
   hr = rs.MoveFirst();         // Move to the first row and print it  
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );  
  
   // Close the second command execution;  
   // Instead of rs.CloseAll() you could call  
   // rs.Close() and rs.ReleaseCommand():  
   rs.CloseAll();  
  
   CoUninitialize();  
   return 0;  
}  
```  
  
## Remarques  
 Remarquez que si vous définissez une méthode `HasBookmark`, le code `OpenAll` définit la propriété DBPROP\_IRowsetLocate ; veillez à n'effectuer une telle opération que si votre fournisseur prend en charge cette propriété.  
  
## OpenRowset  
  
```  
// OLE DB Template version:   
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);  
```  
  
 **OpenAll** appelle cette méthode pour ouvrir les jeux de lignes dans le consommateur.  En général, vous n'avez pas besoin d'appeler `OpenRowset` sauf si vous souhaitiez utiliser plusieurs sources de données\/sessions\/ensembles de lignes.  `OpenRowset` est déclaré dans la commande ou le fichier d'en\-tête de la classe de la table :  
  
```  
// OLE DB Template version:  
HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)  
{  
   HRESULT hr = Open(m_session, NULL, pPropSet);  
   #ifdef _DEBUG  
   if(FAILED(hr))  
      AtlTraceErrorRecords(hr);  
   #endif  
   return hr;  
}  
```  
  
 Les attributs implémentent cette méthode différemment.  Cette version accepte un objet session et une chaîne de commande qui correspond par défaut à la chaîne de commande spécifiée dans db\_command, même si vous pouvez en passer une autre.  Remarquez que si vous définissez une méthode `HasBookmark`, le code `OpenRowset` définit la propriété DBPROP\_IRowsetLocate ; veillez à n'effectuer une telle opération que si votre fournisseur prend en charge cette propriété.  
  
```  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand=NULL)  
{  
  
   DBPROPSET *pPropSet = NULL;  
   CDBPropSet propset(DBPROPSET_ROWSET);  
   __if_exists(HasBookmark)  
  
   {  
      propset.AddProperty(DBPROP_IRowsetLocate, true);  
      pPropSet= &propset;  
      }  
...  
}  
```  
  
## GetRowsetProperties  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet);  
```  
  
 Cette méthode extrait un pointeur vers le jeu de propriétés  de l'ensemble de lignes ; vous pouvez utiliser ce pointeur pour définir des propriétés telles que DBPROP\_IRowsetChange.  `GetRowsetProperties` est utilisé dans le type d'enregistrement d'utilisateur comme suit.  Vous pouvez modifier ce code afin de définir des propriétés supplémentaires pour le jeu de lignes :  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet)  
{  
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
}  
```  
  
## Remarques  
 Vous ne devez pas définir une méthode `GetRowsetProperties` globale, car elle risque d'entrer en conflit avec celle définie par l'Assistant.  Vous pouvez noter qu'il s'agit d'une méthode générée par l'Assistant que vous obtenez avec des projets pourvus de modèles et d'attributs ; les attributs n'injectent pas ce code.  
  
## OpenDataSource et CloseDataSource  
  
```  
HRESULT OpenDataSource();   
void CloseDataSource();  
```  
  
## Remarques  
 L'Assistant définit les méthodes `OpenDataSource` et `CloseDataSource` ; `OpenDataSource` appelle [CDataSource::OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md).  
  
## Voir aussi  
 [Création d'un consommateur OLE DB en utilisant l'Assistant](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)