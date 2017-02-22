---
title: "CDynamicAccessor, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDynamicAccessor"
  - "ATL::CDynamicAccessor"
  - "CDynamicAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicAccessor (classe)"
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CDynamicAccessor, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous permet d'accéder à une source de données lorsque vous n'avez aucune connaissance du schéma de la base de données \(la structure sous\-jacente de la base de données\).  
  
## Syntaxe  
  
```  
class CDynamicAccessor : public CAccessorBase  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cdynamicaccessor-addbindentry.md)|Ajoute une entrée de liaison aux colonnes de sortie lors du remplacement de l'accesseur par défaut.|  
|[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)|Instancie et initialise l'objet `CDynamicAccessor`.|  
|[Fermer](../../data/oledb/cdynamicaccessor-close.md)|Annule la liaison des colonnes, libère la mémoire allouée, et libère le pointeur d'interface [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) de la classe.|  
|[GetBookmark](../../data/oledb/cdynamicaccessor-getbookmark.md)|Récupère le signet pour la ligne actuelle.|  
|[GetBlobHandling](../../data/oledb/cdynamicaccessor-getblobhandling.md)|Récupère la valeur de gestion BLOB pour la ligne actuelle.|  
|[GetBlobSizeLimit](../../data/oledb/cdynamicaccessor-getblobsizelimit.md)|Récupère la taille maximale du BLOB en octets.|  
|[GetColumnCount](../../data/oledb/cdynamicaccessor-getcolumncount.md)|Récupère le nombre de colonnes dans l'ensemble de lignes.|  
|[GetColumnFlags](../../data/oledb/cdynamicaccessor-getcolumnflags.md)|Récupère les caractéristiques de colonne.|  
|[GetColumnInfo](../../data/oledb/cdynamicaccessor-getcolumninfo.md)|Récupère les métadonnées de colonne.|  
|[GetColumnName](../../data/oledb/cdynamicaccessor-getcolumnname.md)|Récupère le nom d'une colonne spécifiée.|  
|[GetColumnType](../../data/oledb/cdynamicaccessor-getcolumntype.md)|Récupère le type de données d'une colonne spécifiée.|  
|[GetLength](../../data/oledb/cdynamicaccessor-getlength.md)|Récupère la longueur maximale possible pour une colonne en octets.|  
|[GetOrdinal](../../data/oledb/cdynamicaccessor-getordinal.md)|Récupère l'indice d'une colonne à partir d'un nom de colonne.|  
|[GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)|Récupère l'état d'une colonne spécifiée.|  
|[GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)|Récupère les données de la mémoire tampon.|  
|[SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)|Règle la valeur de gestion BLOB pour la ligne actuelle.|  
|[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)|Règle la taille maximale du BLOB en octets.|  
|[GetLength](../../data/oledb/cdynamicaccessor-setlength.md)|Règle la longueur de la colonne en octets.|  
|[SetStatus](../../data/oledb/cdynamicaccessor-setstatus.md)|Fixe l'état d'une colonne spécifiée.|  
|[SetValue](../../data/oledb/cdynamicaccessor-setvalue.md)|Stocke les données dans la mémoire tampon.|  
  
## Notes  
 Utilisez les méthodes `CDynamicAccessor` pour obtenir des informations sur la colonne telles que les noms de colonne, nombre, type de données, etc.  Vous utilisez ensuite ces informations sur les colonnes pour créer un accesseur de manière dynamique au moment de l'exécution.  
  
 Les informations sur les colonnes sont stockées dans une mémoire tampon qui est créé et managée par cette classe.  Récupérez les données à partir de la mémoire tampon en utilisant la méthode [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md).  
  
 Pour obtenir des informations et des exemples d'utilisation des classes d'accesseur dynamiques, consultez [Utilisation des accesseurs dynamiques](../../data/oledb/using-dynamic-accessors.md).  
  
## Configuration requise  
 **En\-tête :**: atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor, classe](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor, classe](../../data/oledb/cmanualaccessor-class.md)