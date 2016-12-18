---
title: "db_table | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_table"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_table attribute"
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# db_table
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ouvre une table OLE DB.  
  
## Syntaxe  
  
```  
  
      [ db_table(   
   db_table,   
   name,   
   source_name,   
   hresult   
) ]  
```  
  
#### Paramètres  
 *db\_table*  
 Chaîne spécifiant le nom d'une table de base de données \(tel que « products »\).  
  
 *nom* \(facultatif\)  
 Le nom du handle que vous utilisez pour utiliser le tableau.  Vous devez spécifier ce paramètre si vous souhaitez retourner plusieurs lignes de résultats.  **db\_table** génère une variable avec *le nom* spécifié peut être utilisé pour parcourir l'ensemble de lignes ou pour exécuter plusieurs requêtes Action.  
  
 *source\_name* \(facultatif\)  
 La variable d' `CSession` ou l'instance d'une classe qui a l'attribut d' `db_source` appliquée à celui\-ci sur lequel la commande s'exécute.  Consultez [db\_source](../windows/db-source.md).  
  
 `hresult` \(facultatif\)  
 Identifie la variable qui recevra `HRESULT` de cette commande de base de données.  si la variable n'existe pas, elle sera automatiquement injectée par l'attribut.  
  
## Notes  
 **db\_table** crée un objet de [CTable](../data/oledb/ctable-class.md) , qui est utilisé par un consommateur OLE DB pour ouvrir un tableau.  Vous pouvez utiliser cet attribut uniquement au niveau de la classe ; vous ne pouvez pas utiliser inline.  utilisation **db\_column** de lier des colonnes de table aux variables ; utilisez **db\_param** pour le délimiter \(défini le type de paramètre etc.\) des paramètres.  
  
 Lorsque le fournisseur d'attributs du consommateur applique cet attribut à une classe, le compilateur renommera la classe au \_YourClassNameAccessor, où *YourClassName* est le nom que vous avez donné à la classe, et le compilateur crée également une classe appelée *YourClassName,* qui dérive de \_YourClassNameAccessor.  Dans l'Affichage de classes, vous verrez les deux classes.  
  
## Exemple  
 L'exemple suivant ouvre la table Products pour une utilisation par d' `CProducts`.  
  
```  
// db_table.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_table(L"dbo.Products") ]  
class CProducts {  
   [ db_column("1") ] LONG m_ProductID;  
};  
```  
  
 Pour obtenir un exemple de cet attribut utilisé dans une application, consultez les exemples [AtlAgent](http://msdn.microsoft.com/fr-fr/52bef5da-c1a0-4223-b4e6-9e464b6db409) et [MultiRead](http://msdn.microsoft.com/fr-fr/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)