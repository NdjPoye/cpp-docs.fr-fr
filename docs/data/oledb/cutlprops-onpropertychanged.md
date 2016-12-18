---
title: "CUtlProps::OnPropertyChanged | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnPropertyChanged"
  - "CUtlProps.OnPropertyChanged"
  - "CUtlProps::OnPropertyChanged"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnPropertyChanged (méthode)"
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps::OnPropertyChanged
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelé après avoir défini une propriété pour gérer les propriétés chaînées.  
  
## Syntaxe  
  
```  
  
      virtual HRESULT OnPropertyChanged(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
```  
  
#### Paramètres  
 `iCurSet`  
 L'index dans le tableau de propriété ; zéro s'il n'existe qu'un seul jeu de propriétés.  
  
 `pDBProp`  
 L'ID de propriété et une nouvelle valeur dans une structure [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx).  
  
## Valeur de retour  
 Un `HRESULT` standard.  La valeur renvoyée par défaut est `S_OK`.  
  
## Notes  
 Si vous souhaitez gérer les propriétés chaînées, telles que les signets ou mises à jour dont les valeurs dépendent d'une autre valeur de la propriété, vous devez remplacer cette fonction.  
  
## Exemple  
 Dans cette fonction, l'utilisateur obtient l'ID de propriété depuis le paramètre `DBPROP*`.  Maintenant, il est possible de comparer l'ID et la propriété à chaîner.  Lorsque la propriété est trouvée, `SetProperties` est appelé avec la propriété qui est maintenant définie avec l'autre propriété.  Dans ce cas, si on obtient `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS`, ou la propriété `DBPROP_ORDEREDBOOKMARKS`, il est possible de définir la propriété `DBPROP_BOOKMARKS`.  
  
 [!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/CPP/cutlprops-onpropertychanged_1.h)]  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [CUtlProps, classe](../../data/oledb/cutlprops-class.md)