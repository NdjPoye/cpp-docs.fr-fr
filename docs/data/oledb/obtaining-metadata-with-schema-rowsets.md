---
title: "R&#233;cup&#233;ration de m&#233;tadonn&#233;es &#224; l&#39;aide de jeux de lignes du sch&#233;ma | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "métadonnées, obtenir (modèles OLE DB)"
  - "OLE DB (modèles du consommateur), obtenir les métadonnées du fournisseur"
  - "jeux de lignes du schéma, obtenir les métadonnées du fournisseur OLE DB"
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;cup&#233;ration de m&#233;tadonn&#233;es &#224; l&#39;aide de jeux de lignes du sch&#233;ma
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous avez parfois besoin d'obtenir des informations sur le fournisseur, un ensemble de lignes, une table, des colonnes ou d'autres informations de base de données sans ouvrir l'ensemble de lignes.  Les données relatives à la structure de base de données s'appellent des métadonnées et peuvent être récupérées par différentes méthodes.  L'une d'elles consiste à utiliser des ensembles de lignes de schéma.  
  
 Les modèles OLE DB fournissent un ensemble de classes qui permettent de récupérer des informations de schéma ; ces classes créent des ensembles de lignes de schéma prédéfinis et sont répertoriés dans [Classes d'ensembles de lignes de schéma et classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
> [!NOTE]
>  Si vous utilisez OLAP et que certains de vos ensembles de lignes ne sont pas pris en charge par les classes d'ensembles de lignes de schéma \(par exemple, si vous avez un nombre variable de colonnes\), envisagez d'utiliser `CManualAccessor` ou `CDynamicAccessor`.  Vous pouvez parcourir les colonnes et utiliser des instructions case pour gérer les types de données possibles de chaque colonne.  
  
## Modèle catalogue\/schéma  
 SQL ANSI définit un modèle catalogue\/schéma pour les magasins de données ; OLE DB utilise ce modèle.  Dans ce modèle, les catalogues \(bases de données\) contiennent des schémas et les schémas contiennent des tables.  
  
-   **Catalogue** : catalogue est un synonyme de base de données.  Il s'agit d'une collection de schémas associés.  Pour répertorier les catalogues \(bases de données\) appartenant à une source de données déterminée, utilisez [CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md).  Dans la mesure où la plupart des bases de données n'ont qu'un seul catalogue, les métadonnées sont parfois simplement appelées informations de schéma.  
  
-   **Schéma** : un schéma est une collection d'objets de base de données qui sont la propriété ou la création d'un utilisateur déterminé.  Pour répertorier les schémas appartenant à un utilisateur donné, utilisez [CSchemata](../../data/oledb/cschemata-cschematainfo.md).  
  
     Dans la terminologie Microsoft SQL Server et ODBC 2.x, un schéma est un propriétaire \(par exemple, dbo est un nom de schéma type\).  De même, SQL Server stocke les métadonnées dans un ensemble de tables : une de ces tables contient la liste de toutes les tables et une autre contient la liste de toutes les colonnes.  Il n'existe pas d'équivalent à un schéma dans une base de données Microsoft Access.  
  
-   **Table** : les tables sont des collections de colonnes organisées dans un ordre spécifique.  Pour répertorier les tables définies dans un catalogue donné \(base de données\) et obtenir les informations sur ces tables, utilisez [CTables](../../data/oledb/ctables-ctableinfo.md)\).  
  
## Restrictions  
 Quand il s'agit de rechercher des informations de schéma, vous pouvez utiliser des restrictions pour spécifier le type d'information qui vous intéresse.  Les restrictions s'apparentent à un filtre ou à un qualificateur de requête.  Par exemple, dans la requête suivante :  
  
```  
SELECT * FROM authors where l_name = 'pivo'  
```  
  
 `l_name` est une restriction.  Il s'agit d'un exemple très simple à une seule restriction ; les classes d'ensembles de lignes de schéma prennent en charge plusieurs restrictions.  
  
 Les [classes typedef d'ensembles de lignes de schéma](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) encapsulent tous les ensembles de lignes de schéma OLE DB pour vous permettre d'accéder à un ensemble de lignes de schéma comme n'importe quel autre ensemble de lignes en l'instanciant et en l'ouvrant.  Par exemple, la classe typedef [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) est définie comme suit :  
  
```  
CRestrictions<CAccessor<CColumnsInfo>  
```  
  
 La classe [CRestrictions](../../data/oledb/crestrictions-class.md) assure la prise en charge des restrictions.  Après avoir créé une instance de l'ensemble de lignes de schéma, appelez [CRestrictions::Open](../../data/oledb/crestrictions-open.md).  Cette méthode retourne un jeu de résultats basé sur les restrictions que vous spécifiez.  
  
 Pour spécifier des restrictions, consultez [Annexe B : ensembles de lignes de schéma](http://go.microsoft.com/fwlink/?LinkId=64681) et recherchez l'ensemble de lignes que vous utilisez.  Par exemple, **CColumns** correspond à l'[ensemble de lignes COLUMNS](http://go.microsoft.com/fwlink/?LinkId=64682) ; cette rubrique répertorie les colonnes de restrictions de l'ensemble de lignes COLUMNS : TABLE\_CATALOG, TABLE\_SCHEMA, TABLE\_NAME, COLUMN\_NAME.  Vous devez suivre cet ordre quand vous spécifiez vos restrictions.  
  
 Ainsi, par exemple, si vous voulez appliquer une restriction par nom de table, notez que TABLE\_NAME est la troisième colonne de restriction. Appelez ensuite **Open** en spécifiant le nom de la table voulue comme troisième paramètre de restriction, comme dans l'exemple suivant.  
  
#### Pour utiliser des ensembles de lignes de schéma  
  
1.  Vous devez inclure le fichier d'en\-tête Atldbsch.h \(bien entendu, vous avez aussi besoin d'Atldbcli.h pour la prise en charge du consommateur\).  
  
2.  Instanciez un objet ensemble de lignes de schéma dans le fichier d'en\-tête du consommateur ou du document.  Si vous voulez des informations sur les tables, déclarez un objet **CTables** ; si vous voulez des informations sur les colonnes, déclarez un objet **CColumns**.  Cet exemple montre comment récupérer les colonnes de la table « authors » :  
  
    ```  
    CDataSource ds;  
    ds.Open();  
    CSession ss;  
    ss.Open();  
    CColumns ColumnSchemaRowset;  
    // TABLE_NAME is the third restriction column, so  
    // specify "authors" as the third restriction parameter:  
    hr = ColumnSchemaRowset.Open(ss, NULL, NULL, "authors");  
    hr = ColumnSchemaRowset.MoveFirst();  
    while (hr == S_OK)  
    {  
       hr = ColumnSchemaRowset.MoveNext();  
    }  
    ```  
  
3.  Pour extraire les informations, accédez au membre de données approprié de l'objet ensemble de lignes de schéma, par exemple, `ColumnSchemaRowset.m_szColumnName`.  Il s'agit ici de COLUMN\_NAME.  Pour savoir à quelle colonne OLE DB chaque membre de données correspond, consultez [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md).  
  
 Pour obtenir des références sur les classes d'ensembles de lignes de schéma et Typedef fournies dans les modèles OLE DB, consultez [Classes d'ensembles de lignes de schéma et classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
 Pour plus d'informations sur les ensembles de lignes de schéma OLE DB, y compris sur les colonnes de restriction, consultez [Annexe B : ensembles de lignes de schéma](http://go.microsoft.com/fwlink/?LinkId=64681) dans le Guide de référence du programmeur OLE DB.  
  
 Pour obtenir des exemples plus complexes sur la façon d'utiliser les classes d'ensembles de lignes de schéma, consultez les exemples [CatDB](http://msdn.microsoft.com/fr-fr/003d516b-2bf6-444e-8be5-4ebaa0b66046) et [DBViewer](http://msdn.microsoft.com/fr-fr/07620f99-c347-4d09-9ebc-2459e8049832).  
  
 Pour plus d'informations sur la prise en charge des ensembles de lignes de schéma par le fournisseur, consultez [Prise en charge des ensembles de lignes de schéma](../../data/oledb/supporting-schema-rowsets.md).  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)