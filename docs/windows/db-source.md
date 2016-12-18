---
title: "db_source | Microsoft Docs"
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
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_source attribute"
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# db_source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

crée une connexion à une source de données.  
  
## Syntaxe  
  
```  
  
      [ db_source(   
   db_source,   
   name,   
   hresult   
) ]  
```  
  
#### Paramètres  
 *db\_source*  
 la chaîne de connexion utilisée pour se connecter à la source de données.  Pour le format de la chaîne de connexion, consultez [Chaînes de connexion et les liaisons de données](https://msdn.microsoft.com/en-us/library/ms718376.aspx) dans Microsoft Data Access Components \(MDAC\) SDK.  
  
 *nom* \(facultatif\)  
 Lorsque vous utilisez `db_source` sur une classe, *le nom* est une instance d'un objet source de données qui contient l'attribut d' `db_source` appliqué à elle \(voir l'exemple 1\).  Lorsque vous utilisez `db_source` inline dans une implémentation de méthode, *le nom* est une variable \(local à la méthode\) qui peut être utilisée pour accéder à la source de données \(voir l'exemple 2\).  vous passez ce *nom au* paramètre d' `source_name` de **db\_command** pour associer la source de données avec une commande.  
  
 `hresult` \(facultatif\)  
 Identifie la variable qui recevra `HRESULT` de cette commande de base de données.  si la variable n'existe pas, elle sera automatiquement injectée par l'attribut.  
  
## Notes  
 `db_source` crée [CDataSource](../data/oledb/cdatasource-class.md) et un objet de [CSession](../data/oledb/csession-class.md) , qui représentent ensemble une connexion à une source de données du consommateur OLE DB.  
  
 Lorsque vous utilisez `db_source` sur une classe, l'objet d' `CSession` devient un membre de la classe.  
  
 Lorsque vous utilisez `db_source` dans une méthode, le code injecté sera exécuté dans la portée de la méthode, et l'objet d' `CSession` est créé comme variable locale.  
  
 `db_source` ajoute des propriétés de la source de données à une classe ou dans une méthode.  Il est utilisé avec **db\_command** \(qui accepte*le paramètre name* d' `db_source`comme paramètre d' `source_name` \).  
  
 Lorsque le fournisseur d'attributs du consommateur applique cet attribut à une classe, le compilateur renommera la classe au \_YourClassNameAccessor, où *YourClassName* est le nom que vous avez donné à la classe, et le compilateur crée également une classe appelée *YourClassName,* qui dérive de \_YourClassNameAccessor.  Dans l'Affichage de classes, vous verrez les deux classes.  
  
 Pour obtenir un exemple de cet attribut utilisé dans une application, consultez les exemples [AtlAgent](http://msdn.microsoft.com/fr-fr/52bef5da-c1a0-4223-b4e6-9e464b6db409) et [MultiRead](http://msdn.microsoft.com/fr-fr/5a2a915a-77dc-492f-94b2-1b809995dd5e).  
  
## Exemple  
 Cet exemple appelle `db_source` sur une classe pour créer une connexion à la source de données `ds` utilisation de la base de données Northwind.  `ds` est un handle de la source de données, qui peut être utilisée en interne à la classe d' `CMyCommand` .  
  
```  
// db_source_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[  
  db_source(L"my_connection_string", name="ds"),  
  db_command(L"select * from Products")  
]  
class CMyCommand {};  
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