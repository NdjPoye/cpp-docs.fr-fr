---
title: "CRowset::FindNextRow | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset.FindNextRow"
  - "CRowset<TAccessor>.FindNextRow"
  - "ATL::CRowset::FindNextRow"
  - "CRowset::FindNextRow"
  - "CRowset<TAccessor>::FindNextRow"
  - "CRowset.FindNextRow"
  - "ATL.CRowset<TAccessor>.FindNextRow"
  - "ATL::CRowset<TAccessor>::FindNextRow"
  - "FindNextRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FindNextRow (méthode)"
ms.assetid: 36484df9-3625-4f15-bf69-db73a8d91c55
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::FindNextRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recherche la ligne correspondante suivante après le signet spécifié.  
  
## Syntaxe  
  
```  
  
      HRESULT FindNextRow(   
   DBCOMPAREOP op,   
   BYTE* pData,   
   DBTYPE wType,   
   DBLENGTH nLength,   
   BYTE bPrecision,   
   BYTE bScale,   
   BOOL bSkipCurrent = TRUE,   
   CBookmarkBase* pBookmark = NULL    
) throw( );  
```  
  
#### Paramètres  
 `op`  
 \[in\] l'opération à utiliser lors de la comparaison de valeurs de ligne.  Pour obtenir des valeurs, consultez [IRowsetFind::FindNextRow](https://msdn.microsoft.com/en-us/library/ms723091.aspx).  
  
 `pData`  
 \[in\] pointeur à la valeur du paramètre à trouver.  
  
 `wType`  
 \[in\] indique le type de données du composant de la mémoire tampon.  Pour plus d'informations sur les indicateurs de type, consultez [Data Types](https://msdn.microsoft.com/en-us/library/ms723969.aspx) dans *OLE DB Programmer's Reference* dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nLength`  
 \[in\] longueur, en octets, de la structure de données client allouée pour la valeur de données.  Pour plus d'informations, consultez la description de **cbMaxLen** dans [Structures DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) dans *OLE DB Programmer's Reference*.  
  
 `bPrecision`  
 \[in\] la précision maximale utilisée lors de l'obtention de données.  Requis si `wType` est `DBTYPE_NUMERIC`.  Pour plus d'informations, consultez [Conversions impliquant DBTYPE\_NUMERIC ou DBTYPE\_DECIMAL](https://msdn.microsoft.com/en-us/library/ms719714.aspx) dans *OLE DB Programmer's Reference*.  
  
 `bScale`  
 \[in\] l'échelle utilisée lors de l'obtention de données.  Utilisé uniquement si `wType` est `DBTYPE_NUMERIC` ou **DBTYPE\_DECIMAL**.  Pour plus d'informations, consultez [Conversions impliquant DBTYPE\_NUMERIC ou DBTYPE\_DECIMAL](https://msdn.microsoft.com/en-us/library/ms719714.aspx) dans *OLE DB Programmer's Reference*.  
  
 *bSkipCurrent*  
 \[in\] nombre de lignes à partir du signet auquel on démarre la recherche.  
  
 `pBookmark`  
 \[in\] le signet de l'emplacement à partir duquel commencer la recherche.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Cette méthode requiert l'interface facultative **IRowsetFind**, qui peut ne pas être prise en charge sur tous les fournisseurs ; dans ce cas, la méthode retourne **E\_NOINTERFACE**.  Vous devez également définir **DBPROP\_IRowsetFind** sur `VARIANT_TRUE` avant d'appeler **Ouvrir** sur la table ou la commande contenant l'ensemble de lignes.  
  
 Pour plus d'informations sur l'utilisation de signets dans les consommateurs, consultez [Utilisation de signets](../../data/oledb/using-bookmarks.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)   
 [DBBINDING Structures](https://msdn.microsoft.com/en-us/library/ms716845.aspx)