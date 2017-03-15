---
title: "Acc&#232;s aux donn&#233;es XML | Microsoft Docs"
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
  - "CStreamRowset (classe), récupérer les données XML"
  - "CXMLAccessor (classe), récupérer les données XML"
  - "données (C++), données XML data (accès)"
  - "accès aux données (C++), données XML"
  - "jeux de lignes (C++), récupérer les données XML"
  - "XML (C++), accéder aux données"
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Acc&#232;s aux donn&#233;es XML
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Il existe deux méthodes distinctes pour la récupération de données XML à partir d'une source de données : la première utilise [CStreamRowset](../../data/oledb/cstreamrowset-class.md) et la seconde [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) :  
  
|Fonctionnalité|CStreamRowset|CXMLAccessor|  
|--------------------|-------------------|------------------|  
|Quantité de données transférées|Récupère les données à partir de toutes les colonnes et les lignes simultanément.|Récupère des données de toutes les colonnes mais une seule ligne à la fois.  Vous devez toujours parcourir les lignes en utilisant des méthodes telles que `MoveNext`.|  
|Formatage de la chaîne|SQL Server formate la chaîne XML et l'envoie au consommateur.|Récupère les données du jeu de lignes dans son format natif \(demande que le fournisseur les envoie en tant que chaînes Unicode\), puis construit la chaîne contenant les données au format XML.|  
|Contrôle du formatage|Vous avez un certain niveau de contrôle sur la façon dont la chaîne XML est mise en forme en définissant quelques propriétés spécifiques de SQL Server 2000.|Vous n'avez aucun contrôle sur le format de la chaîne XML générée.|  
  
 Si `CStreamRowset` constitue globalement une méthode plus efficace pour la récupération de données au format XML, elle n'est prise en charge que par SQL Server 2000.  
  
## Récupération de données XML à l'aide de CStreamRowset  
 Vous devez spécifier [CStreamRowset](../../data/oledb/cstreamrowset-class.md) en tant que type de jeu de lignes dans votre déclaration de `CCommand` ou de `CTable`.  Vous pouvez l'utiliser avec votre propre accesseur ou sans accesseur, par exemple :  
  
```  
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;  
```  
  
 ou  
  
```  
CCommand<CNoAccessor, CStreamRowset> myCmd;  
```  
  
 Normalement, lorsque vous appelez `CCommand::Open` \(en spécifiant par exemple `CRowset` comme classe `TRowset` \), il obtient un pointeur `IRowset`.  `ICommand::Execute` retourne un pointeur `IRowset`, stocké dans le membre `m_spRowset` de l'objet `CRowset`.  Les méthodes telles que `MoveFirst`, `MoveNext` et `GetData` utilisent ce pointeur pour récupérer des données.  
  
 En revanche, lorsque vous appelez `CCommand::Open` \(mais spécifiez `CStreamRowset` comme classe `TRowset` \), `ICommand::Execute` retourne un pointeur `ISequentialStream`, stocké dans les données `m_spStream` membres de [CStreamRowset](../../data/oledb/cstreamrowset-class.md).  Vous pouvez alors utiliser la méthode `Read` pour récupérer les données \(chaîne Unicode\) au format XML.  Par exemple :  
  
```  
myCmd.m_spStream->Read()  
```  
  
 SQL Server 2000 effectue la mise en forme XML et retourne toutes les colonnes et toutes les lignes du jeu de lignes en tant que chaînes XML uniques.  
  
 Pour obtenir un exemple d'utilisation de la méthode `Read`, consultez « Ajout de la prise en charge XML au consommateur » dans [Implémentation d'un consommateur simple](../../data/oledb/implementing-a-simple-consumer.md) \(page éventuellement en anglais\).  
  
> [!NOTE]
>  La prise en charge de XML à l'aide de `CStreamRowset` fonctionne seulement avec SQL Server 2000, et requiert le fournisseur OLE DB pour SQL Server 2000 \(installé avec MDAC\).  
  
## Récupération de données XML à l'aide de CXMLAccessor  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) vous permet d'accéder aux données d'une source de données comme données de chaîne lorsque vous n'avez aucune connaissance du schéma du magasin de données.  `CXMLAccessor` fonctionne comme `CDynamicStringAccessorW`, sauf que ce dernier convertit toutes les données accessibles depuis le magasin de données au format XML \(référencé\).  Les noms des balises XML correspondent aux noms des colonnes du magasin de données aussi étroitement que possible.  
  
 Utilisez `CXMLAccessor` comme n'importe quelle autre classe d'accesseur, en la passant en tant que paramètre de modèle à `CCommand` ou `CTable` :  
  
```  
CTable<CXMLAccessor, CRowset> rs;  
```  
  
 Utilisez [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) pour récupérer les données de la table une ligne à la fois, et parcourez les lignes en faisant appel à des méthodes telles que `MoveNext`, par exemple :  
  
```  
// Open data source, session, and rowset  
hr = rs.MoveFirst();  
while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
{  
    CStringW strRowData;  
    myCmd.GetXMLRowData(strRowData);  
  
    printf_s( "%S\n", strRowData );  
  
    hr = rs.MoveNext();  
}  
```  
  
 Vous pouvez utiliser [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) pour récupérer des informations sur les colonnes \(type de données\) en tant que données de type chaîne au format XML.  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)