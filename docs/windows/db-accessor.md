---
title: "db_accessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_accessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_accessor attribute"
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# db_accessor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

attributs de **db\_column** de groupes qui participent à la liaison basée sur d' `IAccessor`.  
  
## Syntaxe  
  
```  
  
      [ db_accessor(   
   num,   
   auto   
) ]  
```  
  
#### Paramètres  
 *num*  
 Spécifie le numéro de l'accesseur \(un index d'entiers de base zéro\).  Vous devez spécifier des numéros d'accesseur en augmentant la commande, à des entiers ou des valeurs définies.  
  
 *auto*  
 Valeur booléenne qui spécifie, que l'accesseur est automatiquement extrait \(**TRUE**\) ou échec de l'extraction \(**FALSE**\).  
  
## Notes  
 **db\_accessor** définit l'accesseur sous\-jacent OLE DB pour **db\_column** suivant les attributs et de **db\_param** dans la même classe ou la fonction.  **db\_accessor** est utilisable au niveau de le membre et est utilisé pour grouper les attributs de **db\_column** qui participent à la liaison basée sur OLE DB `IAccessor`.  Il est utilisé avec les attributs de **db\_table** ou de **db\_command** .  Appeler cet attribut revient à appeler des macros de [BEGIN\_ACCESSOR](../data/oledb/begin-accessor.md) et d' [END\_ACCESSOR](../data/oledb/end-accessor.md) .  
  
 **db\_accessor** génère un ensemble de lignes et des liens aux tables de correspondance d'accesseur.  Si vous n'appelez pas **db\_accessor**, l'accesseur 0 sera généré automatiquement, et toutes les liaisons des colonnes sont mappées à ce bloc d'accesseur.  
  
 **db\_accessor** groupe des liaisons des colonnes de base de données dans un ou plusieurs accesseurs.  Pour en savoir plus sur les scénarios dans lesquels vous devez utiliser plusieurs accesseurs, consultez l' [Utilisation de plusieurs accesseurs dans un jeu de lignes](../data/oledb/using-multiple-accessors-on-a-rowset.md).  Voir aussi « prise en charge d'enregistrement utilisateur de plusieurs accesseurs » dans [Enregistrements utilisateur](../data/oledb/user-records.md).  
  
 Lorsque le fournisseur d'attributs du consommateur applique cet attribut à une classe, le compilateur renommera la classe au \_YourClassNameAccessor, où *YourClassName* est le nom que vous avez donné à la classe, et le compilateur crée également une classe appelée *YourClassName,* qui dérive de \_YourClassNameAccessor.  Dans l'Affichage de classes, vous verrez les deux classes.  
  
## Exemple  
 L'exemple suivant utilise **db\_accessor** pour regrouper des colonnes de la table Orders de la base de données Northwind dans deux accesseurs.  L'accesseur 0 est un accesseur automatique, les accesseurs et 1 n'est pas.  
  
```  
// cpp_attr_ref_db_accessor.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include <atlbase.h>  
#include <atldbcli.h>  
  
[ db_command(L"SELECT LastName, FirstName FROM Orders") ]  
class CEmployees {  
public:  
   [ db_accessor(0, TRUE) ];  
   [ db_column("1") ] LONG m_OrderID;  
   [ db_column("2") ] TCHAR m_CustomerID[6];  
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;   
  
   [ db_accessor(1, FALSE) ];  
   [ db_column("8") ] CURRENCY m_Freight;  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|blocs d'attributs|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)