---
title: "CSchemata, CSchemataInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DEFAULT_CHARACTER_SET_CATALOG"
  - "DEFAULT_CHARACTER_SET_SCHEMA"
  - "m_szCharName"
  - "CSchemataInfo"
  - "m_szCatalog"
  - "m_szCharCatalog"
  - "m_szOwner"
  - "m_szCharSchema"
  - "CSchemata"
  - "m_szName"
  - "DEFAULT_CHARACTER_SET_NAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSchemata (classe typedef)"
  - "CSchemataInfo (classe de paramètre)"
  - "DEFAULT_CHARACTER_SET_CATALOG"
  - "DEFAULT_CHARACTER_SET_NAME"
  - "DEFAULT_CHARACTER_SET_SCHEMA"
  - "m_szCatalog"
  - "m_szCharCatalog"
  - "m_szCharName"
  - "m_szCharSchema"
  - "m_szName"
  - "m_szOwner"
ms.assetid: 9d06d65a-c27b-446d-bc42-c7e487b0d9c5
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CSchemata, CSchemataInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelez la classe **CSchemata** de typedef pour implémenter la classe **CSchemataInfo**de paramètre.  
  
## Notes  
 Voir [Classes d'ensemble de lignes de schéma et de classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes de typedef.  
  
 Cette classe identifie les schémas détenus par un utilisateur donné.  
  
 Le tableau suivant répertorie les membres de la classe de donnée et leurs colonnes OLE DB correspondantes.  Voir [Ensemble de lignes SCHEMATA](https://msdn.microsoft.com/en-us/library/ms716887.aspx) dans *OLE DB guide de référence du programmeur* pour plus d'informations sur le schéma et les colonnes.  
  
|Données membres|Colonnes OLE DB|  
|---------------------|---------------------|  
|m\_szCatalogue|CATALOG\_NAME|  
|m\_szNom|SCHEMA\_NAME|  
|m\_szPropriétaire|SCHEMA\_OWNER|  
|m\_szCatalogueCaractères|ENSEMBLE\_CATALOGUE\_CARACTERE\_DEFAUT|  
|m\_szSchemaCaractere|ENSEMBLE\_SCHEMA\_CARACTERE\_DEFAUT|  
|m\_szNomCaracteres|ENSEMBLE\_NOM\_CARACTERE\_DEFAUT|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)