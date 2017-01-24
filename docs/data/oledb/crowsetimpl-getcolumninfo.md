---
title: "CRowsetImpl::GetColumnInfo | Microsoft Docs"
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
  - "GetColumnInfo"
  - "CRowsetImpl.GetColumnInfo"
  - "CRowsetImpl::GetColumnInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnInfo (méthode)"
ms.assetid: 9ef76525-f996-4c6f-81b9-68eb260350ef
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::GetColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère les informations de colonne pour une demande d'un client particulière.  
  
## Syntaxe  
  
```  
  
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(  
   T* pv,  
   ULONG* pcCols   
);  
```  
  
#### Paramètres  
 `pv`  
 \[in\] le pointeur à `CRowsetImpl` de l'utilisateur est dérivé la classe.  
  
 `pcCols`  
 \[in\] le pointeur d'un objet \(sortie\) vers le nombre de colonnes retourné.  
  
## Valeur de retour  
 Pointeur vers une structure de **ATLCOLUMNINFO** statique.  
  
## Notes  
 Cette méthode est une substitution avancée.  
  
 Cette méthode est appelée par plusieurs classes de base d'implémentation pour extraire les informations de colonne pour une demande d'un client particulière.  Généralement, cette méthode est appelée par `IColumnsInfoImpl`.  Si vous remplacez cette méthode, vous devez placer une version dans la méthode dans votre `CRowsetImpl`\- classe dérivée.  Comme la méthode peut être placée dans une classe non mise en modèle, vous devez modifier `pv` à la classe dérivée de `CRowsetImpl`appropriée.  
  
 L'exemple suivant illustre l'utilisation de **GetColumnInfo's**.  Dans cet exemple, **CMyRowset** est `CRowsetImpl`\- une classe dérivée.  Pour remplacer `GetColumnInfo` pour toutes les instances de cette classe, placez la méthode suivante dans la définition de la classe de **CMyRowset**:  
  
 [!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/CPP/crowsetimpl-getcolumninfo_1.h)]  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [CRowsetImpl, classe](../../data/oledb/crowsetimpl-class.md)