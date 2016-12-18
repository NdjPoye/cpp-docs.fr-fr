---
title: "CMFCFontInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCFontInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCFontInfo class"
  - "CMFCFontInfo::CMFCFontInfo constructor"
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCFontInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCFontInfo` décrit le nom et d'autres attributs d'une police.  
  
## Syntaxe  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCFontInfo`|Construit un objet `CMFCFontInfo`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCFontInfo::GetFullName](../Topic/CMFCFontInfo::GetFullName.md)|Récupère les noms concaténés d'une police et de son jeu de caractères \(script\).|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCFontInfo::m\_nCharSet](../Topic/CMFCFontInfo::m_nCharSet.md)|Valeur qui spécifie le jeu de caractères \(script\) associé à la police.|  
|[CMFCFontInfo::m\_nPitchAndFamily](../Topic/CMFCFontInfo::m_nPitchAndFamily.md)|Valeur qui spécifie pas le et la famille de polices.|  
|[CMFCFontInfo::m\_nType](../Topic/CMFCFontInfo::m_nType.md)|Valeur qui spécifie le type de police.|  
|[CMFCFontInfo::m\_strName](../Topic/CMFCFontInfo::m_strName.md)|Le nom de la police ; par exemple, **arial**.|  
|[CMFCFontInfo::m\_strScript](../Topic/CMFCFontInfo::m_strScript.md)|Le nom d'un jeu de caractères \(script\) associé à la police.|  
  
## Notes  
 Vous pouvez joindre un objet d' `CMFCFontInfo` à un élément de la classe de [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md) .  Appelez la méthode de [CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md) pour récupérer un pointeur vers un objet d' `CMFCFontInfo` .  
  
## Exemple  
 L'exemple suivant montre comment utiliser différents membres de la classe d' `CMFCFontInfo` .  L'exemple montre comment obtenir un objet d' `CMFCFontInfo` d' `CMFCRibbonFontComboBox`, et comment accéder à ses variables locales.  Cet exemple est extrait d' [Exemple 2007 de démonstration de MS Office](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/CPP/cmfcfontinfo-class_1.cpp)]  
  
## Configuration requise  
 **en\-tête :** afxtoolbarfontcombobox.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCToolBarFontSizeComboBox Class](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)