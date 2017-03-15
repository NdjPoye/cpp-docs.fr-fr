---
title: "CSQLLanguages, CSQLLanguageInfo | Microsoft Docs"
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
  - "CSQLLanguageInfo"
  - "m_szProgrammingLanguage"
  - "m_szImplementation"
  - "m_szIntegrity"
  - "m_szBindingStyle"
  - "m_szConformance"
  - "m_szSource"
  - "m_szYear"
  - "CSQLLanguages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSQLLanguageInfo (classe de paramètre)"
  - "CSQLLanguages (classe typedef)"
  - "m_szBindingStyle"
  - "m_szConformance"
  - "m_szImplementation"
  - "m_szIntegrity"
  - "m_szProgrammingLanguage"
  - "m_szSource"
  - "m_szYear"
ms.assetid: 9c36c5bb-6917-49c3-9ac3-942339893f19
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSQLLanguages, CSQLLanguageInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelez la classe **CSQLLanguages** de typedef pour implémenter\+ la classe **CSQLLanguageInfo**de paramètre.  
  
## Notes  
 Voir [Classes d'ensemble de lignes de schéma et de classes typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) pour plus d'informations sur l'utilisation des classes de typedef.  
  
 Cette classe identifie les niveaux de conformité, les options et les dialectes pris en charge par l'implémentation SQL traitant les données définies dans le catalogue.  
  
 Le tableau suivant répertorie les membres de la classe de donnée et leurs colonnes OLE DB correspondantes.  Voir [Ensemble de lignes TRANSLATIONS](https://msdn.microsoft.com/en-us/library/ms714374.aspx) dans *OLE DB guide de référence du programmeur* pour plus d'informations sur le schéma et les colonnes.  
  
|Données concernées|Colonnes OLE DB|  
|------------------------|---------------------|  
|m\_szSource|SQL\_LANGUAGE\_SOURCE|  
|m\_szAnnée|SQL\_LANGUAGE\_YEAR|  
|m\_szConformité|SQL\_LANGUAGE\_CONFORMANCE|  
|m\_szIntégrité|SQL\_LANGUAGE\_INTEGRITY|  
|m\_szImplementation|SQL\_LANGUAGE\_IMPLEMENTATION|  
|m\_szBindingStyle|SQL\_LANGUAGE\_BINDING\_STYLE|  
|m\_szLanguageProgrammation|SQL\_LANGUAGE\_PROGRAMMING\_LANGUAGE|  
  
## Conditions requises  
 **En\-tête :** atldbsch.h  
  
## Voir aussi  
 [CRestrictions, classe](../../data/oledb/crestrictions-class.md)