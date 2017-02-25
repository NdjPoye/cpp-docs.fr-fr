---
title: "CDynamicStringAccessor, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicStringAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicStringAccessor (classe)"
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CDynamicStringAccessor, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous permet d'accéder à une source de données lorsque vous n'avez aucune connaissance du schéma de la base de données \(la structure sous\-jacente de la base de données\).  
  
## Syntaxe  
  
```  
  
      template< typename BaseType, DBTYPEENUM OleDbType >  
class CDynamicStringAccessorT : public CDynamicAccessor  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)|Récupère les données de la colonne spécifiée sous forme de chaîne.|  
|[SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)|Définit les données de la colonne spécifiée sous forme de chaîne.|  
  
## Notes  
 Alors que [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) demande des données dans le format natif indiqué par le fournisseur, `CDynamicStringAccessor` demande que le fournisseur récupère toutes les données ayant fait l'objet d'un accès à partir du magasin de données en tant que données de type chaîne.  Cette approche est particulièrement utile pour des tâches simples qui n'exigent pas de calcul de valeurs dans le magasin de données, comme l'affichage ou l'impression du contenu du magasin de données.  
  
 Le type de données natif de la colonne dans la banque de données n'a pas d'importance ; tant que le fournisseur peut prendre en charge la conversion de données, il fournit les données au format chaîne.  Si le fournisseur ne prend pas en charge la conversion du type de données natif en une chaîne \(non commune\), l'appel de demande retourne la valeur **DB\_S\_ERRORSOCCURED** de succès, et l'état de la colonne correspondante indique un problème de conversion avec **DBSTATUS\_E\_CANTCONVERTVALUE**.  
  
 Utilisez les méthodes `CDynamicStringAccessor` pour récupérer des informations sur les colonnes.  Vous utilisez ces informations sur les colonnes pour créer un accesseur de manière dynamique au moment de l'exécution.  
  
 Les informations sur les colonnes sont stockées dans une mémoire tampon qui est créée et managée par cette classe.  Récupérez les données à partir de la mémoire tampon en utilisant [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md), ou stockez\-les dans la mémoire tampon à l'aide de [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).  
  
 Pour obtenir des informations et des exemples d'utilisation des classes d'accesseur dynamiques, consultez [Utilisation des accesseurs dynamiques](../../data/oledb/using-dynamic-accessors.md).  
  
## Configuration requise  
 **En\-tête :**: atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor, classe](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor, classe](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessorA, classe](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW, classe](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CXMLAccessor, classe](../../data/oledb/cxmlaccessor-class.md)