---
title: "db_param | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_param"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_param attribute"
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# db_param
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

associe la variable membre spécifiée avec une entrée ou un paramètre de sortie et délimite la variable.  
  
## Syntaxe  
  
```  
  
      [ db_param(   
   ordinal,   
   paramtype="DBPARAMIO_INPUT",   
   dbtype,   
   precision,   
   scale,   
   status,   
   length  
) ]  
```  
  
#### Paramètres  
 `ordinal`  
 Le numéro de colonne \(nombre ordinal de**DBCOLUMNINFO** \) correspondant à un champ dans le jeu de lignes auquel lier des données.  
  
 *paramtype* \(facultatif\)  
 Le type à l'ensemble du paramètre.  Les fournisseurs prennent uniquement en charge les types d'E\/S de paramètre pris en charge par la source de données sous\-jacente.  Le type est une combinaison d'une ou plusieurs valeurs de **DBPARAMIOENUM** :  
  
-   **DBPARAMIO\_INPUT** un paramètre d'entrée.  
  
-   **DBPARAMIO\_OUTPUT** un paramètre de sortie.  
  
-   **DBPARAMIO\_NOTPARAM** l'accesseur n'a pas de paramètre.  Le paramètre **eParamIO** à cette valeur dans les accesseurs de ligne rappelle l'utilisateur que les paramètres sont ignorés.  
  
 *dbtype* \(facultatif\)  
 OLE DB [indicateur de type](https://msdn.microsoft.com/en-us/library/ms711251.aspx) pour l'entrée de colonne.  
  
 *précision* \(facultatif\)  
 la précision à utiliser pour l'entrée de colonne.  Pour plus d'informations, consultez la description de l'élément de **bPrecision** de [structure de DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *échelle* \(facultatif\)  
 l'échelle à utiliser pour l'entrée de colonne.  Pour plus d'informations, consultez la description de l'élément de **bScale** de [structure de DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *état* \(facultatif\)  
 une variable membre utilisée pour maintenir l'état de cette colonne.  Le rapport indique si la valeur de la colonne est une valeur de données ou une autre valeur, telle que **NULL**.  Pour les valeurs possibles, consultez l' [état](https://msdn.microsoft.com/en-us/library/ms722617.aspx) dans *OLE DB Programmer's Reference*.  
  
 *longueur* \(facultatif\)  
 une variable membre utilisée pour maintenir la taille de la colonne en octets.  
  
## Notes  
 **db\_param** définit les paramètres que vous utilisez dans les commandes ; par conséquent vous utilisez avec **db\_command**.  Par exemple, vous pouvez utiliser **db\_param** aux paramètres de liaison dans les requêtes SQL ou des procédures stockées.  Les paramètres d'une procédure stockée sont dénotés par les points d'interrogation \(?\), et vous devez lier les données membres dans l'ordre dans lequel les paramètres apparaissent.  
  
 **db\_param** délimite les données membres qui peuvent participer à la liaison basée sur OLE DB `ICommandWithParameters`.  Il définit le type de paramètre \(entrée ou de sortie\), le type OLE DB, la précision, l'échelle, l'état, et la longueur du paramètre spécifié.  Cet attribut insère les macros BEGIN\_PARAM\_MAP du consommateur OLE DB…  END\_PARAM\_MAP.  Chaque membre que vous avez identifié par l'attribut de **db\_param** occupera une entrée dans la table sous la forme COLUMN\_ENTRY.  
  
 **db\_param** est utilisé avec les attributs de [db\_table](../windows/db-table.md) ou de [db\_command](../windows/db-command.md) .  
  
 Lorsque le fournisseur d'attributs du consommateur applique cet attribut à une classe, le compilateur renommera la classe au \_YourClassNameAccessor, où *YourClassName* est le nom que vous avez donné à la classe, et le compilateur crée également une classe appelée *YourClassName,* qui dérive de \_YourClassNameAccessor.  Dans l'Affichage de classes, vous verrez les deux classes.  
  
## Exemple  
 L'exemple suivant crée une classe de commande en fonction de la procédure stockée de SalesbyYear dans la base de données Northwind.  Il associe le premier paramètre de la procédure stockée à la variable d' `m_RETURN_VALUE` , et le définit comme paramètre de sortie.  Elle associe les deux derniers paramètres d'entrée \(\) avec `m_Beginning_Date` et `m_Ending_Date`.  
  
 l'exemple suivant associe la variable d' `nOutput` avec un paramètre de sortie.  
  
```  
// db_param.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_source(L"my_connection_string"),   
  db_command(L"{ ? = CALL dbo.\"Sales by Year\"(?,?) }")   
]  
struct CSalesbyYear {  
   DBSTATUS m_dwShippedDateStatus;  
   DBSTATUS m_dwOrderIDStatus;  
   DBSTATUS m_dwSubtotalStatus;  
   DBSTATUS m_dwYearStatus;  
  
   DBLENGTH m_dwShippedDateLength;  
   DBLENGTH m_dwOrderIDLength;  
   DBLENGTH m_dwSubtotalLength;  
   DBLENGTH m_dwYearLength;  
  
   // Bind columns  
   [ db_column("1", status="m_dwShippedDateStatus", length="m_dwShippedDateLength") ] DBTIMESTAMP m_ShippedDate;  
   [ db_column("2", status="m_dwOrderIDStatus", length="m_dwOrderIDLength") ] LONG m_OrderID;  
   [ db_column("3", status="m_dwSubtotalStatus", length="m_dwSubtotalLength") ] CURRENCY m_Subtotal;  
   [ db_column("4", status="m_dwYearStatus", length="m_dwYearLength") ] TCHAR m_Year[31];  
  
   // Bind parameters  
   [ db_param("1", paramtype="DBPARAMIO_OUTPUT") ] LONG m_RETURN_VALUE;  
   [ db_param("2", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Beginning_Date;  
   [ db_param("3", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Ending_Date;  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`, membre, méthode, les variables locales|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)