---
title: "Recordset&#160;: d&#233;filement (ODBC) | Microsoft Docs"
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
  - "Move (méthode des recordsets)"
  - "navigation (C++), recordsets"
  - "ODBC (recordsets), défilement"
  - "recordsets (C++), début de"
  - "recordsets (C++), fin de"
  - "recordsets (C++), atteindre un enregistrement"
  - "recordsets (C++), naviguer"
  - "défilement (C++), recordsets"
ms.assetid: f38d2dcb-1e88-4e41-af25-98b00c276be4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset&#160;: d&#233;filement (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Après avoir ouvert un recordset, vous avez besoin d'accéder aux enregistrements pour, entre autres, afficher les valeurs, effectuer des calculs ou générer des états.  Le défilement permet de passer d'un enregistrement à l'autre au sein de votre recordset.  
  
 Cette rubrique explique :  
  
-   [comment passer d'un enregistrement à l'autre au sein d'un recordset](#_core_scrolling_from_one_record_to_another) ;  
  
-   [dans quels cas le défilement est pris en charge](#_core_when_scrolling_is_supported).  
  
##  <a name="_core_scrolling_from_one_record_to_another"></a> Défilement d'un enregistrement à l'autre  
 La classe `CRecordset` propose les fonctions membres **Move** pour faire défiler un recordset.  Ces fonctions déplacent l'enregistrement courant par jeu de lignes.  Si vous avez implémenté l'extraction de lignes en bloc, l'opération **Move** repositionne le recordset en fonction de la taille du jeu de lignes.  Dans le cas contraire, l'appel de la fonction **Move** repositionne les enregistrements du jeu un par un.  Pour plus d'informations sur l'extraction de lignes en bloc, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Lorsque vous vous déplacez dans un recordset, les enregistrements supprimés ne peuvent pas être ignorés.  Pour plus d'informations, consultez la fonction membre [IsDeleted](../Topic/CRecordset::IsDeleted.md).  
  
 En dehors des fonctions **Move**, `CRecordset` propose des fonctions membres permettant de vérifier si vous avez atteint la fin ou le début du recordset.  
  
 Pour déterminer si le défilement est possible au sein de votre recordset, appelez la fonction membre `CanScroll`.  
  
#### Pour défiler  
  
1.  vers l'avant d'un enregistrement ou d'un jeu de lignes à la fois, appelez la fonction membre [MoveNext](../Topic/CRecordset::MoveNext.md) ;  
  
2.  vers l'arrière d'un enregistrement ou d'un jeu de lignes à la fois, appelez la fonction membre [MovePrev](../Topic/CRecordset::MovePrev.md) ;  
  
3.  jusqu'au premier enregistrement du recordset, appelez la fonction membre [MoveFirst](../Topic/CRecordset::MoveFirst.md) ;  
  
4.  jusqu'au dernier enregistrement du recordset ou jusqu'au dernier jeu de lignes, appelez la fonction membre [MoveLast](../Topic/CRecordset::MoveLast.md) ;  
  
5.  de *N* enregistrements à partir de la position courante, appelez la fonction membre [Move](../Topic/CRecordset::Move.md).  
  
#### Pour tester le début ou la fin d'un recordset  
  
1.  Vous êtes\-vous déplacé au\-delà du dernier enregistrement ?  Appelez la fonction membre [IsEOF](../Topic/CRecordset::IsEOF.md).  
  
2.  Si vous avez atteint le premier enregistrement \(déplacement vers l'arrière\),  Appelez la fonction membre [IsBOF](../Topic/CRecordset::IsBOF.md).  
  
 Le code ci\-après constitue un exemple d'utilisation de `IsBOF` et de `IsEOF` pour détecter le début ou la fin du recordset lorsque vous défilez vers l'avant ou vers l'arrière.  
  
```  
// Open a recordset; first record is current  
CCustSet rsCustSet( NULL );  
rsCustSet.Open( );  
  
if( rsCustSet.IsBOF( ) )  
    return;  
    // The recordset is empty  
  
// Scroll to the end of the recordset, past  
// the last record, so no record is current  
while ( !rsCustSet.IsEOF( ) )  
    rsCustSet.MoveNext( );  
  
// Move to the last record  
rsCustSet.MoveLast( );  
  
// Scroll to beginning of the recordset, before  
// the first record, so no record is current  
while( !rsCustSet.IsBOF( ) )  
    rsCustSet.MovePrev( );  
  
// First record is current again  
rsCustSet.MoveFirst( );  
```  
  
 `IsEOF` retourne une valeur différente de zéro si le recordset est positionné au\-delà du dernier enregistrement.  `IsBOF` retourne une valeur différente de zéro si le recordset est positionné avant le premier enregistrement \(avant tous les enregistrements\).  Dans les deux cas, il n'y a pas d'enregistrement actuel sur lequel opérer.  Si vous appelez `MovePrev` alors que `IsBOF` a déjà la valeur **TRUE**, ou si vous appelez `MoveNext` alors que `IsEOF` a déjà la valeur **TRUE**, l'infrastructure lève une exception `CDBException`.  Vous pouvez aussi utiliser `IsBOF` et `IsEOF` pour vérifier si un recordset est vide.  
  
 Pour plus d'informations sur la navigation au sein d'un recordset, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="_core_when_scrolling_is_supported"></a> Prise en charge du défilement  
 Tel qu'il fut conçu à l'origine, SQL ne permettait que le défilement vers l'avant. ODBC enrichit les possibilités de défilement.  Le niveau de prise en charge disponible dépend des pilotes ODBC utilisés par votre application, du niveau de conformité de l'API ODBC du pilote et de l'éventuel chargement en mémoire de la bibliothèque de curseurs ODBC.  Pour plus d'informations, consultez [ODBC](../../data/odbc/odbc-basics.md) et [ODBC : bibliothèque de curseurs ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!TIP]
>  Vous pouvez contrôler si la bibliothèque de curseurs est utilisée.  Consultez les paramètres `bUseCursorLib` et `dwOptions` de [CDatabase::Open](../Topic/CDatabase::Open.md).  
  
> [!NOTE]
>  Contrairement aux classes DAO MFC, les classes ODBC MFC ne fournissent pas de fonctions **Find** pour rechercher le prochain ou le précédent enregistrement obéissant à des critères définis.  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::CanScroll](../Topic/CRecordset::CanScroll.md)   
 [CRecordset::CheckRowsetError](../Topic/CRecordset::CheckRowsetError.md)   
 [Recordset : filtrage d'enregistrements \(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)