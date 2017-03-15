---
title: "Recordset&#160;: signets et positions absolues (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetAbsolutePosition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "positions absolues, ODBC (recordsets)"
  - "signets"
  - "signets, CDBVariant"
  - "signets, ODBC (recordsets)"
  - "CDBVariant (classe), signets"
  - "ODBC (curseurs), position absolue dans les recordsets"
  - "GetBookmark (méthode)"
  - "ODBC (recordsets), positions absolues"
  - "ODBC (recordsets), signets"
  - "positionnement d'enregistrements"
  - "enregistrements (positions des)"
  - "recordsets, positions absolues"
  - "recordsets, signets"
  - "SetAbsolutePosition (méthode)"
  - "SetAbsolutePosition (méthode), signets"
  - "SetBookmark (méthode)"
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Recordset&#160;: signets et positions absolues (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Lorsque vous naviguez au sein d'un recordset, il arrive fréquemment que vous ayez besoin de revenir sur un enregistrement donné.  Deux méthodes, le signet et la position absolue, permettent de répondre à ce besoin.  
  
 Cette rubrique explique :  
  
-   [comment utiliser les signets](#_core_bookmarks_in_mfc_odbc) ;  
  
-   [comment attribuer une position absolue à l'enregistrement courant](#_core_absolute_positions_in_mfc_odbc).  
  
##  <a name="_core_bookmarks_in_mfc_odbc"></a> Signets dans ODBC MFC  
 Un signet identifie un enregistrement de façon unique.  Lorsque vous naviguez au sein d'un recordset, vous ne pouvez pas toujours vous fier à la position absolue d'un enregistrement dans la mesure où les enregistrements peuvent être supprimés du recordset.  La solution la plus fiable pour conserver la trace de la position d'un enregistrement consiste à utiliser un signet.  La classe `CRecordset` propose des fonctions membres pour :  
  
-   obtenir le signet de l'enregistrement courant, de telle sorte que vous puissiez le sauvegarder dans une variable \([GetBookmark](../Topic/CRecordset::GetBookmark.md)\) ;  
  
-   atteindre rapidement un enregistrement donné en indiquant son signet, préalablement sauvegardé dans une variable \([SetBookmark](../Topic/CRecordset::SetBookmark.md)\).  
  
 L'exemple ci\-après illustre comment utiliser les fonctions membres pour marquer l'enregistrement courant et y revenir par la suite.  
  
```  
// rs is a CRecordset or  
// CRecordset-derived object  
  
CDBVariant varRecordToReturnTo;  
rs.GetBookmark( varRecordToReturnTo );  
  
// More code in which you  
// move to other records  
  
rs.SetBookmark( varRecordToReturnTo );  
```  
  
 Il n'est pas nécessaire d'extraire le type de données sous\-jacent de l'objet [CDBVariant Class](../../mfc/reference/cdbvariant-class.md).  Assignez la valeur à l'aide de `GetBookmark` et accédez au signet avec `SetBookmark`.  
  
> [!NOTE]
>  Remarque   Il se peut, en fonction du pilote ODBC et du type du recordset, que les signets ne soient pas pris en charge.  Vous pouvez facilement savoir si les signets sont pris en charge en appelant [CRecordset::CanBookmark](../Topic/CRecordset::CanBookmark.md).  Par ailleurs, si les signets sont pris en charge, vous devez choisir explicitement de les implémenter en précisant l'option **CRecordset::useBookmarks** dans la fonction membre [CRecordset::Open](../Topic/CRecordset::Open.md).  Vous devez également vérifier que les signets persistent après certaines opérations sur les recordsets.  Par exemple, si vous effectuez une opération **Requery** \(lancement d'une nouvelle requête\) sur un recordset, il se peut que les signets ne soient plus valides.  Appelez [CDatabase::GetBookmarkPersistence](../Topic/CDatabase::GetBookmarkPersistence.md) pour vérifier si vous pouvez appeler `SetBookmark`sans risque.  
  
##  <a name="_core_absolute_positions_in_mfc_odbc"></a> Positions absolues dans ODBC MFC  
 Outre les signets, la classe `CRecordset` permet de définir l'enregistrement courant en indiquant sa position ordinale.  Cette méthode est appelée positionnement absolu.  
  
> [!NOTE]
>  Le positionnement absolu n'est pas disponible pour les recordsets en avant seulement.  Pour plus d'informations sur les recordsets en avant seulement, consultez [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md).  
  
 Pour déplacer le pointeur d'enregistrement actif qui utilise la position absolue, appelez [CRecordset::SetAbsolutePosition](../Topic/CRecordset::SetAbsolutePosition.md).  Lorsque vous passez une valeur à `SetAbsolutePosition`, l'enregistrement correspondant à cette position ordinale devient l'enregistrement courant.  
  
> [!NOTE]
>  La position absolue d'un enregistrement n'est potentiellement pas fiable.  Si l'utilisateur supprime des enregistrements du recordset; la position ordinale de tous les enregistrements suivants s'en trouve modifiée.  Les signets constituent la méthode recommandée pour déplacer l'enregistrement courant.  Pour plus d'informations, consultez [Signets dans ODBC MFC](#_core_bookmarks_in_mfc_odbc).  
  
 Pour plus d'informations sur la navigation au sein d'un recordset, consultez [Recordset : défilement \(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md).  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)