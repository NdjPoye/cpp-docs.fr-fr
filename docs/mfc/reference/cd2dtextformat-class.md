---
title: "Classe CD2DTextFormat | Microsoft Docs"
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
  - "afxrendertarget/CD2DTextFormat"
  - "CD2DTextFormat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DTextFormat (classe)"
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
caps.latest.revision: 16
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DTextFormat
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour IDWriteTextFormat.  
  
## Syntaxe  
  
```  
class CD2DTextFormat : public CD2DResource;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DTextFormat::CD2DTextFormat](../Topic/CD2DTextFormat::CD2DTextFormat.md)|Construit un objet CD2DTextFormat.|  
|[CD2DTextFormat::~CD2DTextFormat](../Topic/CD2DTextFormat::~CD2DTextFormat.md)|Le destructeur.  Appelé lorsqu'un objet format de texte D2D est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DTextFormat::Create](../Topic/CD2DTextFormat::Create.md)|Crée CD2DTextFormat.  \(Substitue [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DTextFormat::Destroy](../Topic/CD2DTextFormat::Destroy.md)|Détruit un objet CD2DTextFormat.  \(Substitue [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DTextFormat::Get](../Topic/CD2DTextFormat::Get.md)|Renvoie l'interface IDWriteTextFormat|  
|[CD2DTextFormat::GetFontFamilyName](../Topic/CD2DTextFormat::GetFontFamilyName.md)|Obtient une copie du nom de la famille des polices.|  
|[CD2DTextFormat::GetLocaleName](../Topic/CD2DTextFormat::GetLocaleName.md)|Obtient une copie du nom des paramètres régionaux.|  
|[CD2DTextFormat::IsValid](../Topic/CD2DTextFormat::IsValid.md)|Vérifie la validité des ressources \(substitue [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
|[CD2DTextFormat::ReCreate](../Topic/CD2DTextFormat::ReCreate.md)|Crée de nouveau un objet CD2DTextFormat.  \(Substitue [CD2DResource::ReCreate](../Topic/CD2DResource::ReCreate.md).\)|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DTextFormat::operator IDWriteTextFormat\*](../Topic/CD2DTextFormat::operator%20IDWriteTextFormat*.md)|Renvoie l'interface IDWriteTextFormat|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DTextFormat::m\_pTextFormat](../Topic/CD2DTextFormat::m_pTextFormat.md)|Pointeur vers un IDWriteTextFormat.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)