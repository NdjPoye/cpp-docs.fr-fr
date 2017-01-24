---
title: "Classe CD2DSizeF | Microsoft Docs"
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
  - "afxrendertarget/CD2DSizeF"
  - "CD2DSizeF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DSizeF (classe)"
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DSizeF
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour D2D1\_SIZE\_F.  
  
## Syntaxe  
  
```  
class CD2DSizeF : public D2D1_SIZE_F;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DSizeF::CD2DSizeF](../Topic/CD2DSizeF::CD2DSizeF.md)|Surchargé.  Construit un objet d' `CD2DSizeF` d'objet d' `D2D1_SIZE_F` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DSizeF::IsNull](../Topic/CD2DSizeF::IsNull.md)|Retourne une valeur d' `boolean` qui indique si une expression ne contient pas de données valide \(`null`\).|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DSizeF::operator CSize](../Topic/CD2DSizeF::operator%20CSize.md)|Convertit `CD2DSizeF` à l'objet d' `CSize` .|  
  
## Hiérarchie d'héritage  
 `D2D1_SIZE_F`  
  
 [CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)