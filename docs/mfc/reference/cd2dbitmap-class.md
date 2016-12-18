---
title: "Classe CD2DBitmap | Microsoft Docs"
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
  - "afxrendertarget/CD2DBitmap"
  - "CD2DBitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBitmap (classe)"
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CD2DBitmap
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1Bitmap.  
  
## Syntaxe  
  
```  
class CD2DBitmap : public CD2DResource;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBitmap::CD2DBitmap](../Topic/CD2DBitmap::CD2DBitmap.md)|Surchargé.  Construit un objet CD2DBitmap de HBITMAP.|  
|[CD2DBitmap::~CD2DBitmap](../Topic/CD2DBitmap::~CD2DBitmap.md)|Le destructeur.  Appelé lorsqu'un objet image bitmap D2D est détruit.|  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBitmap::CD2DBitmap](../Topic/CD2DBitmap::CD2DBitmap.md)|Surchargé.  Construit un objet CD2DBitmap.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBitmap::Attach](../Topic/CD2DBitmap::Attach.md)|Attache l'interface de la ressource existante à l'objet|  
|[CD2DBitmap::CopyFromBitmap](../Topic/CD2DBitmap::CopyFromBitmap.md)|Copie la région spécifiée de l'image bitmap spécifiée dans l'image bitmap actuelle|  
|[CD2DBitmap::CopyFromMemory](../Topic/CD2DBitmap::CopyFromMemory.md)|Copie la région spécifiée de la mémoire dans l'image bitmap actuelle|  
|[CD2DBitmap::CopyFromRenderTarget](../Topic/CD2DBitmap::CopyFromRenderTarget.md)|Copie la région spécifiée de la cible de rendu spécifiée dans l'image bitmap actuelle|  
|[CD2DBitmap::Create](../Topic/CD2DBitmap::Create.md)|Crée CD2DBitmap.  \(Substitue [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DBitmap::Destroy](../Topic/CD2DBitmap::Destroy.md)|Détruit un objet CD2DBitmap.  \(Substitue [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DBitmap::Detach](../Topic/CD2DBitmap::Detach.md)|Détache l'interface de la ressource de l'objet|  
|[CD2DBitmap::Get](../Topic/CD2DBitmap::Get.md)|Renvoie l'interface ID2D1Bitmap|  
|[CD2DBitmap::GetDPI](../Topic/CD2DBitmap::GetDPI.md)|Renvoie les points par pouce \(PPP\) de l'image bitmap.|  
|[CD2DBitmap::GetPixelFormat](../Topic/CD2DBitmap::GetPixelFormat.md)|Extrait le format de pixel et mode alpha de l'image bitmap|  
|[CD2DBitmap::GetPixelSize](../Topic/CD2DBitmap::GetPixelSize.md)|Retourne la taille de l'image bitmap, en unités dépendantes du périphérique \(pixels\)|  
|[CD2DBitmap::GetSize](../Topic/CD2DBitmap::GetSize.md)|Retourne la taille d'origine de l'image bitmap, en unités dépendantes du périphérique \(PPP\)|  
|[CD2DBitmap::IsValid](../Topic/CD2DBitmap::IsValid.md)|Vérifie la validité des ressources \(substitue [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBitmap::CommonInit](../Topic/CD2DBitmap::CommonInit.md)|Initialise l'objet|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBitmap::operator ID2D1Bitmap\*](../Topic/CD2DBitmap::operator%20ID2D1Bitmap*.md)|Renvoie l'interface ID2D1Bitmap|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CD2DBitmap::m\_bAutoDestroyHBMP](../Topic/CD2DBitmap::m_bAutoDestroyHBMP.md)|TRUE si m\_hBmpSrc doit être détruit ; sinon FALSE.|  
|[CD2DBitmap::m\_hBmpSrc](../Topic/CD2DBitmap::m_hBmpSrc.md)|Handle de l'image bitmap source.|  
|[CD2DBitmap::m\_lpszType](../Topic/CD2DBitmap::m_lpszType.md)|Type de ressource.|  
|[CD2DBitmap::m\_pBitmap](../Topic/CD2DBitmap::m_pBitmap.md)|Stocke un pointeur à un objet ID2D1Bitmap.|  
|[CD2DBitmap::m\_sizeDest](../Topic/CD2DBitmap::m_sizeDest.md)|Taille de destination de la bitmap.|  
|[CD2DBitmap::m\_strPath](../Topic/CD2DBitmap::m_strPath.md)|Chemin d'accès du fichier bitmap.|  
|[CD2DBitmap::m\_uiResID](../Topic/CD2DBitmap::m_uiResID.md)|ID de ressource de la bitmap.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBitmap](../../mfc/reference/cd2dbitmap-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)