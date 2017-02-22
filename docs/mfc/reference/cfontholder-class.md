---
title: "CFontHolder Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFontHolder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFontHolder class"
  - "custom fonts"
  - "polices, contrôles ActiveX"
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CFontHolder Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente la propriété stock Font et encapsule les fonctionnalités d'un objet de police windows et de l'interface d' `IFont` .  
  
## Syntaxe  
  
```  
class CFontHolder  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFontHolder::CFontHolder](../Topic/CFontHolder::CFontHolder.md)|Construit un objet `CFontHolder`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFontHolder::GetDisplayString](../Topic/CFontHolder::GetDisplayString.md)|Extrait la chaîne affichée dans l'Explorateur de propriétés d'un conteneur.|  
|[CFontHolder::GetFontDispatch](../Topic/CFontHolder::GetFontDispatch.md)|Retourne l'interface d' `IDispatch` de police.|  
|[CFontHolder::GetFontHandle](../Topic/CFontHolder::GetFontHandle.md)|Retourne un handle à une police windows.|  
|[CFontHolder::InitializeFont](../Topic/CFontHolder::InitializeFont.md)|Initialise un objet `CFontHolder`.|  
|[CFontHolder::QueryTextMetrics](../Topic/CFontHolder::QueryTextMetrics.md)|Récupère les informations pour la police relative.|  
|[CFontHolder::ReleaseFont](../Topic/CFontHolder::ReleaseFont.md)|Déconnecte l'objet d' `CFontHolder` les interfaces d' `IFont` et d' `IFontNotification` .|  
|[CFontHolder::Select](../Topic/CFontHolder::Select.md)|Sélectionne une ressource de police dans un contexte de périphérique.|  
|[CFontHolder::SetFont](../Topic/CFontHolder::SetFont.md)|Connecte l'objet d' `CFontHolder` à une interface d' `IFont` .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFontHolder::m\_pFont](../Topic/CFontHolder::m_pFont.md)|Pointeur vers l'interface d' `IFont` de l'objet d' `CFontHolder` .|  
  
## Notes  
 `CFontHolder` n'a pas de classe de base.  
  
 Utilisez cette classe pour implémenter des propriétés de police à la carte pour votre contrôle.  Pour plus d'informations sur la création de ces propriétés, consultez l'article [Contrôles ActiveX : Utilisation de polices](../../mfc/mfc-activex-controls-using-fonts.md).  
  
## Hiérarchie d'héritage  
 `CFontHolder`  
  
## Configuration requise  
 **Header:** afxctl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CPropExchange Class](../../mfc/reference/cpropexchange-class.md)