---
title: "CTranslations, CTranslationInfo | Microsoft Docs"
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
  - "m_szCatalog"
  - "m_szSourceCatalog"
  - "m_szTargetSchema"
  - "m_szTargetCatalog"
  - "m_szTargetName"
  - "CTranslationInfo"
  - "m_szSourceName"
  - "m_szSchema"
  - "CTranslations"
  - "m_szName"
  - "m_szSourceSchema"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTranslationInfo (classe de paramètre)"
  - "CTranslations (classe typedef)"
  - "m_szCatalog"
  - "m_szName"
  - "m_szSchema"
  - "m_szSourceCatalog"
  - "m_szSourceName"
  - "m_szSourceSchema"
  - "m_szTargetCatalog"
  - "m_szTargetName"
  - "m_szTargetSchema"
ms.assetid: 19a64828-2d4c-42a0-8bfb-b010e334a9b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTranslations, CTranslationInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelez la classe **CTranslations** de typedef pour implémenter la classe de paramètre **CTranslationInfo**.  
  
## Notes  
 Voir [Classes d'ensemble de lignes de schéma et de classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes de typedef.  
  
 Cette classe identifie les traductions des caractères définies dans le catalogue qui sont accessibles à un utilisateur donné.  
  
 Le tableau suivant répertorie les données membres de la classe et leurs colonnes correspondantes OLE DB.  Voir le [Ensemble de lignes TRANSLATIONS](https://msdn.microsoft.com/en-us/library/ms725365.aspx) dans *OLE DB guide de référence du programmeur* pour plus d'informations sur le schéma et les colonnes.  
  
|Membres de données|Colonnes OLE DB|  
|------------------------|---------------------|  
|m\_szCatalog|TRANSLATION\_CATALOG|  
|m\_szSchema|TRANSLATION\_SCHEMA|  
|m\_szName|TRANSLATION\_NAME|  
|m\_szSourceCatalog|SOURCE\_CHARACTER\_SET\_CATALOG|  
|m\_szSourceSchema|SOURCE\_CHARACTER\_SET\_SCHEMA|  
|m\_szSourceName|SOURCE\_CHARACTER\_SET\_NAME|  
|m\_szTargetCatalog|TARGET\_CHARACTER\_SET\_CATALOG|  
|m\_szTargetSchema|TARGET\_CHARACTER\_SET\_SCHEMA|  
|m\_szTargetName|TARGET\_CHARACTER\_SET\_NAME|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CatDB](../../top/visual-cpp-samples.md)   
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)