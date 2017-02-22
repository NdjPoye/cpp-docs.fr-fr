---
title: "CPictureHolder Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "Picture"
  - "CPictureHolder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [MFC], OLE"
  - "CPictureHolder class"
  - "contrôles OLE, image"
  - "Picture property"
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CPictureHolder Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente une propriété d'image, qui permet à l'utilisateur d'afficher une image dans votre contrôle.  
  
## Syntaxe  
  
```  
class CPictureHolder  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPictureHolder::CPictureHolder](../Topic/CPictureHolder::CPictureHolder.md)|Construit un objet `CPictureHolder`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPictureHolder::CreateEmpty](../Topic/CPictureHolder::CreateEmpty.md)|Crée un objet `CPictureHolder` vide.|  
|[CPictureHolder::CreateFromBitmap](../Topic/CPictureHolder::CreateFromBitmap.md)|Crée un objet d' `CPictureHolder` d'une bitmap.|  
|[CPictureHolder::CreateFromIcon](../Topic/CPictureHolder::CreateFromIcon.md)|Crée un objet d' `CPictureHolder` d'une icône.|  
|[CPictureHolder::CreateFromMetafile](../Topic/CPictureHolder::CreateFromMetafile.md)|Crée un objet d' `CPictureHolder` d'un métafichier.|  
|[CPictureHolder::GetDisplayString](../Topic/CPictureHolder::GetDisplayString.md)|Extrait la chaîne affichée dans l'Explorateur de propriétés d'un conteneur de contrôle.|  
|[CPictureHolder::GetPictureDispatch](../Topic/CPictureHolder::GetPictureDispatch.md)|Retourne l'interface d' `IDispatch` de l'objet d' `CPictureHolder` .|  
|[CPictureHolder::GetType](../Topic/CPictureHolder::GetType.md)|Indique si l'objet d' `CPictureHolder` est une bitmap, un métafichier, ou une icône.|  
|[CPictureHolder::Render](../Topic/CPictureHolder::Render.md)|Affiche l'image.|  
|[CPictureHolder::SetPictureDispatch](../Topic/CPictureHolder::SetPictureDispatch.md)|Définit l'interface d' `IDispatch` de l'objet d' `CPictureHolder` .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPictureHolder::m\_pPict](../Topic/CPictureHolder::m_pPict.md)|Un pointeur vers un objet image.|  
  
## Notes  
 `CPictureHolder` n'a pas de classe de base.  
  
 Avec la propriété d'image boursières, le développeur peut spécifier une bitmap, une icône, ou un métafichier pour l'affichage.  
  
 Pour plus d'informations sur la création des propriétés d'images personnalisées, consultez l'article [Contrôles ActiveX MFC : Utilisation des images dans un contrôle ActiveX](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md).  
  
## Hiérarchie d'héritage  
 `CPictureHolder`  
  
## Configuration requise  
 **Header:** afxctl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFontHolder Class](../../mfc/reference/cfontholder-class.md)