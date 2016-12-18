---
title: "CRestrictions::Open | Microsoft Docs"
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
  - "CRestrictions.Open"
  - "ATL::CRestrictions::Open"
  - "ATL.CRestrictions.Open"
  - "CRestrictions::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open (méthode)"
ms.assetid: 0aff0cc3-543a-47d2-8d6b-ebb36926b6db
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRestrictions::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne un jeu de résultats en fonction des restrictions fournies par l'utilisateur.  
  
## Syntaxe  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true  
);  
```  
  
#### Paramètres  
 `session`  
 \[in\] spécifie un objet de session existant utilisé pour se connecter à la source de données.  
  
 *lpszParam*  
 \[in\] spécifie les restrictions d'ensemble de lignes de schéma.  
  
 `bBind`  
 \[in\] spécifie s'il faut lier le mappage de colonnes automatiquement.  La valeur par défaut est **true**, ce qui entraîne le mappage de colonnes à lier automatiquement.  Mettre le paramètre `bBind` à **faux** empêche la liaison automatique du mappage de colonnes afin de pouvoir effectuer la liaison manuellement. \(La liaison manuelle présente un intérêt tout particulier aux utilisateurs d'OLAP\).  
  
## Valeur de retour  
 Une des valeurs standard `HRESULT`  
  
## Notes  
 Vous pouvez spécifier jusqu'à sept restrictions sur un ensemble de lignes de schéma.  
  
 Voir le [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) pour plus d'informations sur les restrictions définies à chaque ensemble de lignes de schéma.  
  
## Configuration requise  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)   
 [Classes de jeu de lignes du schéma et classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)