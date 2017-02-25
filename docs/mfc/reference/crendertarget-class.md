---
title: "Classe CRenderTarget | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRenderTarget"
  - "afxrendertarget/CRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRenderTarget (classe)"
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Classe CRenderTarget
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wrapper pour ID2D1RenderTarget.  
  
## Syntaxe  
  
```  
class CRenderTarget : public CObject;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRenderTarget::CRenderTarget](../Topic/CRenderTarget::CRenderTarget.md)|Construit un objet CRenderTarget.|  
|[CRenderTarget::~CRenderTarget](../Topic/CRenderTarget::~CRenderTarget.md)|Le destructeur.  Appelé lorsqu'un objet cible de rendu est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRenderTarget::Attach](../Topic/CRenderTarget::Attach.md)|Attache l'interface de la cible de rendu existante à l'objet|  
|[CRenderTarget::BeginDraw](../Topic/CRenderTarget::BeginDraw.md)|Démarre le dessin sur cette cible de rendu.|  
|[CRenderTarget::Clear](../Topic/CRenderTarget::Clear.md)|Efface la zone de dessin avec la couleur spécifiée.|  
|[CRenderTarget::COLORREF\_TO\_D2DCOLOR](../Topic/CRenderTarget::COLORREF_TO_D2DCOLOR.md)|Convertit la couleur GDI et les valeurs alpha en objet D2D1\_COLOR\_F.|  
|[CRenderTarget::CreateCompatibleRenderTarget](../Topic/CRenderTarget::CreateCompatibleRenderTarget.md)|Crée une nouvelle cible de rendu de l'image bitmap pour une utilisation pendant le dessin hors écran intermédiaire qui est compatible avec la cible de rendu en cours.|  
|[CRenderTarget::Destroy](../Topic/CRenderTarget::Destroy.md)|Supprime une ou plusieurs ressources|  
|[CRenderTarget::Detach](../Topic/CRenderTarget::Detach.md)|Détache l'interface de la cible de rendu de l'objet|  
|[CRenderTarget::DrawBitmap](../Topic/CRenderTarget::DrawBitmap.md)|Dessine le texte mis en forme décrit par l'objet IDWriteTextLayout spécifié.|  
|[CRenderTarget::DrawEllipse](../Topic/CRenderTarget::DrawEllipse.md)|Dessine le contour de l'ellipse spécifiée à l'aide du style du trait spécifié.|  
|[CRenderTarget::DrawGeometry](../Topic/CRenderTarget::DrawGeometry.md)|Dessine le contour de la géométrie spécifiée à l'aide du style du trait spécifié.|  
|[CRenderTarget::DrawGlyphRun](../Topic/CRenderTarget::DrawGlyphRun.md)|Dessine les glyphes spécifiés.|  
|[CRenderTarget::DrawLine](../Topic/CRenderTarget::DrawLine.md)|Trace une ligne entre les points spécifiés à l'aide du style de trait spécifié.|  
|[CRenderTarget::DrawRectangle](../Topic/CRenderTarget::DrawRectangle.md)|Dessine le contour d'un rectangle avec les dimensions et le style du trait spécifiés.|  
|[CRenderTarget::DrawRoundedRectangle](../Topic/CRenderTarget::DrawRoundedRectangle.md)|Dessine le contour d'un rectangle arrondi à l'aide du style du trait spécifié.|  
|[CRenderTarget::DrawText](../Topic/CRenderTarget::DrawText.md)|Dessine le texte spécifié à l'aide des informations de mise en forme fournies par un objet IDWriteTextFormat.|  
|[CRenderTarget::DrawTextLayout](../Topic/CRenderTarget::DrawTextLayout.md)|Dessine le texte mis en forme décrit par l'objet IDWriteTextLayout spécifié.|  
|[CRenderTarget::EndDraw](../Topic/CRenderTarget::EndDraw.md)|Termine les opérations de dessin sur la cible de rendu et indique l'état d'erreur actuel et les balises associées.|  
|[CRenderTarget::FillEllipse](../Topic/CRenderTarget::FillEllipse.md)|Peint l'intérieur de l'ellipse spécifiée.|  
|[CRenderTarget::FillGeometry](../Topic/CRenderTarget::FillGeometry.md)|Peint l'intérieur de la géométrie spécifiée.|  
|[CRenderTarget::FillMesh](../Topic/CRenderTarget::FillMesh.md)|Peint l'intérieur du maillage spécifié.|  
|[CRenderTarget::FillOpacityMask](../Topic/CRenderTarget::FillOpacityMask.md)|Applique le masque d'opacité décrit par l'image bitmap spécifiée à un pinceau et utilise ce pinceau pour peindre une région de la cible de rendu.|  
|[CRenderTarget::FillRectangle](../Topic/CRenderTarget::FillRectangle.md)|Peint l'intérieur du rectangle spécifié.|  
|[CRenderTarget::FillRoundedRectangle](../Topic/CRenderTarget::FillRoundedRectangle.md)|Peint l'intérieur du rectangle arrondi spécifié.|  
|[CRenderTarget::Flush](../Topic/CRenderTarget::Flush.md)|Exécute toutes les commandes de dessin en attente.|  
|[CRenderTarget::GetAntialiasMode](../Topic/CRenderTarget::GetAntialiasMode.md)|Extrait le mode d'anticrénelage en cours pour les opérations de dessin de non\-texte.|  
|[CRenderTarget::GetDpi](../Topic/CRenderTarget::GetDpi.md)|Retourne les points par pouce \(DPI\) de la cible de rendu|  
|[CRenderTarget::GetMaximumBitmapSize](../Topic/CRenderTarget::GetMaximumBitmapSize.md)|Obtient la taille maximale, en unités dépendantes du périphérique \(pixels\), d'une dimension quelconque de l'image bitmap prise en charge par la cible de rendu|  
|[CRenderTarget::GetPixelFormat](../Topic/CRenderTarget::GetPixelFormat.md)|Extrait le format de pixel et mode alpha de la cible de rendu|  
|[CRenderTarget::GetPixelSize](../Topic/CRenderTarget::GetPixelSize.md)|Retourne la taille de la cible de rendu en pixels du périphérique|  
|[CRenderTarget::GetRenderTarget](../Topic/CRenderTarget::GetRenderTarget.md)|Renvoie l'interface ID2D1RenderTarget|  
|[CRenderTarget::GetSize](../Topic/CRenderTarget::GetSize.md)|Renvoie la taille de la cible de rendu en DIP|  
|[CRenderTarget::GetTags](../Topic/CRenderTarget::GetTags.md)|Obtient l'étiquette pour les opérations de dessin suivantes.|  
|[CRenderTarget::GetTextAntialiasMode](../Topic/CRenderTarget::GetTextAntialiasMode.md)|Obtient le mode d'anticrénelage actuel pour les opérations de dessin de type texte et glyphe.|  
|[CRenderTarget::GetTextRenderingParams](../Topic/CRenderTarget::GetTextRenderingParams.md)|Extrait les options de rendu de texte actuelles de la cible de rendu.|  
|[CRenderTarget::GetTransform](../Topic/CRenderTarget::GetTransform.md)|Applique la transformation spécifiée à la cible de rendu remplaçant la transformation existante.  Toutes les opérations de dessin successives se produisent dans l'espace transformé.|  
|[CRenderTarget::IsSupported](../Topic/CRenderTarget::IsSupported.md)|Indique si la cible de rendu prend en charge les propriétés spécifiées|  
|[CRenderTarget::IsValid](../Topic/CRenderTarget::IsValid.md)|Vérifie la validité des ressources|  
|[CRenderTarget::PopAxisAlignedClip](../Topic/CRenderTarget::PopAxisAlignedClip.md)|Supprime le dernier clip aligné par axe de la cible de rendu.  Après avoir appelé cette méthode, le clip n'est plus appliqué aux opérations de dessin successives.|  
|[CRenderTarget::PopLayer](../Topic/CRenderTarget::PopLayer.md)|Arrête de rediriger les opérations de dessin vers la couche qui est spécifiée par le dernier appel PushLayer.|  
|[CRenderTarget::PushAxisAlignedClip](../Topic/CRenderTarget::PushAxisAlignedClip.md)|Supprime le dernier clip aligné par axe de la cible de rendu.  Après avoir appelé cette méthode, le clip n'est plus appliqué aux opérations de dessin successives.|  
|[CRenderTarget::PushLayer](../Topic/CRenderTarget::PushLayer.md)|Ajoute la couche spécifiée à la cible de rendu afin qu'elle reçoive toutes les opérations de dessin successives jusqu'à l'appel de PopLayer.|  
|[CRenderTarget::RestoreDrawingState](../Topic/CRenderTarget::RestoreDrawingState.md)|Définit l'état du dessin de la cible de rendu en fonction de l'état de l'objet ID2D1DrawingStateBlock spécifié.|  
|[CRenderTarget::SaveDrawingState](../Topic/CRenderTarget::SaveDrawingState.md)|Enregistre l'état de dessin actuel dans l'objet ID2D1DrawingStateBlock spécifié.|  
|[CRenderTarget::SetAntialiasMode](../Topic/CRenderTarget::SetAntialiasMode.md)|Définit le mode d'anticrénelage de la cible de rendu.  Le mode d'anticrénelage s'applique à toutes les opérations de dessin consécutives, à l'exception des opérations de dessin de type texte et glyphe.|  
|[CRenderTarget::SetDpi](../Topic/CRenderTarget::SetDpi.md)|Définit les points par pouce \(DPI\) de la cible de rendu.|  
|[CRenderTarget::SetTags](../Topic/CRenderTarget::SetTags.md)|Spécifie une étiquette pour les opérations de dessin consécutives.|  
|[CRenderTarget::SetTextAntialiasMode](../Topic/CRenderTarget::SetTextAntialiasMode.md)|Spécifie le mode d'anticrénelage à utiliser pour les opérations de dessin de texte et de glyphe consécutives.|  
|[CRenderTarget::SetTextRenderingParams](../Topic/CRenderTarget::SetTextRenderingParams.md)|Spécifie les options de rendu de texte à appliquer aux opérations de dessin de texte et de glyphe consécutives.|  
|[CRenderTarget::SetTransform](../Topic/CRenderTarget::SetTransform.md)|Surchargé.  Applique la transformation spécifiée à la cible de rendu remplaçant la transformation existante.  Toutes les opérations de dessin successives se produisent dans l'espace transformé.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CRenderTarget::VerifyResource](../Topic/CRenderTarget::VerifyResource.md)|Vérifie la validité de l'objet CD2DResource ; crée l'objet s'il n'existe pas.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRenderTarget::operator ID2D1RenderTarget\*](../Topic/CRenderTarget::operator%20ID2D1RenderTarget*.md)|Renvoie l'interface ID2D1RenderTarget|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CRenderTarget::m\_lstResources](../Topic/CRenderTarget::m_lstResources.md)|Liste de pointeurs vers les objets CD2DResource.|  
|[CRenderTarget::m\_pRenderTarget](../Topic/CRenderTarget::m_pRenderTarget.md)|Pointeur vers un objet ID2D1RenderTarget.|  
|[CRenderTarget::m\_pTextFormatDefault](../Topic/CRenderTarget::m_pTextFormatDefault.md)|Pointeur vers l'objet CD2DTextFormat qui contient un format texte par défaut.|  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## Configuration requise  
 **En\-tête :** afxrendertarget.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)