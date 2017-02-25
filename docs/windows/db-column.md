---
title: "db_column | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_column"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_column attribute"
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# db_column
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lie une colonne spécifiée à une variable du jeu de lignes.  
  
## Syntaxe  
  
```  
  
      [ db_column(   
   ordinal,   
   dbtype,   
   precision,   
   scale,   
   status,   
   length   
) ]  
```  
  
#### Paramètres  
 `ordinal`  
 Le numéro de colonne ordinale \(nombre ordinal de**DBCOLUMNINFO** \) ou nom de colonne \(ANSI ou chaîne Unicode\) correspondant à un champ dans le jeu de lignes auquel lier des données.  Si vous utilisez des nombres, vous pouvez ignorer les ordinaux consécutifs \(par exemple : 1, 2, 3, 5\).  Le nom peut contenir des espaces si le fournisseur OLE DB que vous utilisez prend en charge par.  par exemple, vous pouvez utiliser l'un ou l'autre des formats suivants :  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
 *dbtype* \(facultatif\)  
 OLE DB [indicateur de type](https://msdn.microsoft.com/en-us/library/ms711251.aspx) pour l'entrée de colonne.  
  
 *précision* \(facultatif\)  
 la précision à utiliser pour l'entrée de colonne.  Pour plus d'informations, consultez la description de l'élément d' `bPrecision` de [structure de DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *échelle* \(facultatif\)  
 l'échelle à utiliser pour l'entrée de colonne.  Pour plus d'informations, consultez la description de l'élément d' `bScale` de [structure de DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *état* \(facultatif\)  
 une variable membre utilisée pour maintenir l'état de cette colonne.  Le rapport indique si la valeur de la colonne est une valeur de données ou une autre valeur, telle que **NULL**.  Pour les valeurs possibles, consultez l' [état](https://msdn.microsoft.com/en-us/library/ms722617.aspx) dans *OLE DB Programmer's Reference*.  
  
 *longueur* \(facultatif\)  
 une variable membre utilisée pour maintenir la taille de la colonne en octets.  
  
## Notes  
 **db\_column** lie la colonne de table spécifiée à une variable du jeu de lignes.  Il délimite les données membres qui peuvent participer à la liaison basée sur OLE DB `IAccessor`.  Cet attribut a installé le mappage de colonnes normalement défini à l'aide de les macros du consommateur OLE DB [BEGIN\_COLUMN\_MAP](../data/oledb/begin-column-map.md), [END\_COLUMN\_MAP](../data/oledb/end-column-map.md), et [COLUMN\_ENTRY](../data/oledb/column-entry.md).  Ceux\-ci manipulent OLE DB [structure de DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) pour lier la colonne.  Chaque membre que vous avez identifié par l'attribut de **db\_column** occupera une entrée dans le mappage de colonnes sous la forme d'entrée de colonne.  Par conséquent, vous appelez cet attribut dans laquelle vous placez le mappage de colonnes, c. autrement dit., dans l'ordre ou la classe de table.  
  
 Utilisez **db\_column** avec les attributs de [db\_table](../windows/db-table.md) ou de [db\_command](../windows/db-command.md) .  
  
 Lorsque le fournisseur d'attributs du consommateur applique cet attribut à une classe, le compilateur renommera la classe au \_YourClassNameAccessor, où *YourClassName* est le nom que vous avez donné à la classe, et le compilateur crée également une classe appelée *YourClassName,* qui dérive de \_YourClassNameAccessor.  Dans l'Affichage de classes, vous verrez les deux classes.  
  
 Pour obtenir des exemples de cet attribut utilisé dans une application, consultez les exemples [AtlAgent](http://msdn.microsoft.com/fr-fr/52bef5da-c1a0-4223-b4e6-9e464b6db409), et le [MultiRead](http://msdn.microsoft.com/fr-fr/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## Exemple  
 Cet exemple lie une colonne d'une table à une donnée membre de **long** et spécifie les champs d'état et de longueur.  
  
```  
// db_column_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   DBSTATUS m_dwProductIDStatus;  
   DBLENGTH m_dwProductIDLength;  
  
   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;  
};  
```  
  
## Exemple  
 Cet exemple lie quatre colonnes à **long**, une chaîne de caractères, un horodatage, et d'un entier de **DB\_NUMERIC** , dans cet ordre.  
  
```  
// db_column_2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   [db_column("1")] LONG m_OrderID;  
   [db_column("2")] TCHAR m_CustomerID[6];  
   [db_column("4")] DB_NUMERIC m_OrderDate;     
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`, membre, méthode|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)