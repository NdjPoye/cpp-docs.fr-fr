---
title: Classe CRenderTarget | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRenderTarget
- AFXRENDERTARGET/CRenderTarget
- AFXRENDERTARGET/CRenderTarget::CRenderTarget
- AFXRENDERTARGET/CRenderTarget::Attach
- AFXRENDERTARGET/CRenderTarget::BeginDraw
- AFXRENDERTARGET/CRenderTarget::Clear
- AFXRENDERTARGET/CRenderTarget::COLORREF_TO_D2DCOLOR
- AFXRENDERTARGET/CRenderTarget::CreateCompatibleRenderTarget
- AFXRENDERTARGET/CRenderTarget::Destroy
- AFXRENDERTARGET/CRenderTarget::Detach
- AFXRENDERTARGET/CRenderTarget::DrawBitmap
- AFXRENDERTARGET/CRenderTarget::DrawEllipse
- AFXRENDERTARGET/CRenderTarget::DrawGeometry
- AFXRENDERTARGET/CRenderTarget::DrawGlyphRun
- AFXRENDERTARGET/CRenderTarget::DrawLine
- AFXRENDERTARGET/CRenderTarget::DrawRectangle
- AFXRENDERTARGET/CRenderTarget::DrawRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::DrawText
- AFXRENDERTARGET/CRenderTarget::DrawTextLayout
- AFXRENDERTARGET/CRenderTarget::EndDraw
- AFXRENDERTARGET/CRenderTarget::FillEllipse
- AFXRENDERTARGET/CRenderTarget::FillGeometry
- AFXRENDERTARGET/CRenderTarget::FillMesh
- AFXRENDERTARGET/CRenderTarget::FillOpacityMask
- AFXRENDERTARGET/CRenderTarget::FillRectangle
- AFXRENDERTARGET/CRenderTarget::FillRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::Flush
- AFXRENDERTARGET/CRenderTarget::GetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetDpi
- AFXRENDERTARGET/CRenderTarget::GetMaximumBitmapSize
- AFXRENDERTARGET/CRenderTarget::GetPixelFormat
- AFXRENDERTARGET/CRenderTarget::GetPixelSize
- AFXRENDERTARGET/CRenderTarget::GetRenderTarget
- AFXRENDERTARGET/CRenderTarget::GetSize
- AFXRENDERTARGET/CRenderTarget::GetTags
- AFXRENDERTARGET/CRenderTarget::GetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::GetTransform
- AFXRENDERTARGET/CRenderTarget::IsSupported
- AFXRENDERTARGET/CRenderTarget::IsValid
- AFXRENDERTARGET/CRenderTarget::PopAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PopLayer
- AFXRENDERTARGET/CRenderTarget::PushAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PushLayer
- AFXRENDERTARGET/CRenderTarget::RestoreDrawingState
- AFXRENDERTARGET/CRenderTarget::SaveDrawingState
- AFXRENDERTARGET/CRenderTarget::SetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetDpi
- AFXRENDERTARGET/CRenderTarget::SetTags
- AFXRENDERTARGET/CRenderTarget::SetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::SetTransform
- AFXRENDERTARGET/CRenderTarget::VerifyResource
- AFXRENDERTARGET/CRenderTarget::m_lstResources
- AFXRENDERTARGET/CRenderTarget::m_pRenderTarget
- AFXRENDERTARGET/CRenderTarget::m_pTextFormatDefault
dev_langs:
- C++
helpviewer_keywords:
- CRenderTarget class
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6f77d482e7ee3bf0798ad488067893b3712aac62
ms.lasthandoff: 02/24/2017

---
# <a name="crendertarget-class"></a>CRenderTarget, classe
Wrapper pour ID2D1RenderTarget.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CRenderTarget : public CObject;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRenderTarget::CRenderTarget](#crendertarget)|Construit un objet CRenderTarget.|  
|[CRenderTarget :: ~ CRenderTarget](#crendertarget__~crendertarget)|Destructeur. Appelé lorsqu’un objet cible de rendu est détruit.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CRenderTarget::Attach](#attach)|Interface de cible à l’objet de rendu attache existant|  
|[CRenderTarget::BeginDraw](#begindraw)|Démarre le dessin sur cette cible de rendu.|  
|[CRenderTarget::Clear](#clear)|Efface la zone de dessin avec la couleur spécifiée.|  
|[CRenderTarget::COLORREF_TO_D2DCOLOR](#colorref_to_d2dcolor)|Convertit les valeurs de couleur et alpha GDI pour l’objet D2D1_COLOR_F.|  
|[CRenderTarget::CreateCompatibleRenderTarget](#createcompatiblerendertarget)|Crée une nouvelle cible de rendu de bitmap pour une utilisation pendant le dessin hors écran intermédiaire qui est compatible avec la cible de rendu actuelle.|  
|[CRenderTarget::Destroy](#destroy)|Supprime une ou plusieurs ressources|  
|[CRenderTarget::Detach](#detach)|Détache l’interface de cible de rendu de l’objet|  
|[CRenderTarget::DrawBitmap](#drawbitmap)|Dessine le texte mis en forme décrit par l’objet IDWriteTextLayout spécifié.|  
|[CRenderTarget::DrawEllipse](#drawellipse)|Dessine le contour de l’ellipse spécifiée à l’aide du style de trait spécifié.|  
|[CRenderTarget::DrawGeometry](#drawgeometry)|Dessine le contour de la géométrie spécifiée à l’aide du style de trait spécifié.|  
|[CRenderTarget::DrawGlyphRun](#drawglyphrun)|Dessine les glyphes spécifiés.|  
|[CRenderTarget::DrawLine](#drawline)|Dessine une ligne entre les points spécifiés à l’aide du style de trait spécifié.|  
|[CRenderTarget::DrawRectangle](#drawrectangle)|Dessine le contour d’un rectangle qui contient les dimensions spécifiées et le style de trait.|  
|[CRenderTarget::DrawRoundedRectangle](#drawroundedrectangle)|Dessine le contour du rectangle arrondi spécifié à l’aide du style de trait spécifié.|  
|[CRenderTarget::DrawText](#drawtext)|Dessine le texte spécifié à l’aide des informations de format fournies par un objet IDWriteTextFormat.|  
|[CRenderTarget::DrawTextLayout](#drawtextlayout)|Dessine le texte mis en forme décrit par l’objet IDWriteTextLayout spécifié.|  
|[CRenderTarget::EndDraw](#enddraw)|Fin des opérations de dessin sur la cible de rendu et indique l’état d’erreur actuel et les balises associées.|  
|[CRenderTarget::FillEllipse](#fillellipse)|Peint l’intérieur de l’ellipse spécifiée.|  
|[CRenderTarget::FillGeometry](#fillgeometry)|Peint l’intérieur de la géométrie spécifiée.|  
|[CRenderTarget::FillMesh](#fillmesh)|Peint l’intérieur du maillage spécifié.|  
|[CRenderTarget::FillOpacityMask](#fillopacitymask)|Applique le masque d’opacité décrit par l’image bitmap spécifiée à un pinceau et l’utilise pour peindre une région de la cible de rendu.|  
|[CRenderTarget::FillRectangle](#fillrectangle)|Peint l’intérieur du rectangle spécifié.|  
|[CRenderTarget::FillRoundedRectangle](#fillroundedrectangle)|Peint l’intérieur du rectangle arrondi spécifié.|  
|[CRenderTarget::Flush](#flush)|Exécute toutes les commandes de dessin en attente.|  
|[CRenderTarget::GetAntialiasMode](#getantialiasmode)|Récupère le mode d’anticrénelage actuel pour les opérations de dessin de non-texte.|  
|[CRenderTarget::GetDpi](#getdpi)|Retourne le rendu des points de la cible par pouce (PPP)|  
|[CRenderTarget::GetMaximumBitmapSize](#getmaximumbitmapsize)|Obtient la taille maximale, en unités dépendantes du périphérique (pixels), de toute dimension d’un bitmap pris en charge par la cible de rendu|  
|[CRenderTarget::GetPixelFormat](#getpixelformat)|Récupère le mode d’alpha et du format de pixel de la cible de rendu|  
|[CRenderTarget::GetPixelSize](#getpixelsize)|Retourne la taille de la cible de rendu en pixels de périphérique|  
|[CRenderTarget::GetRenderTarget](#getrendertarget)|Renvoie l’interface ID2D1RenderTarget|  
|[CRenderTarget::GetSize](#getsize)|Retourne la taille de la cible de rendu en pixels indépendants du périphérique|  
|[CRenderTarget::GetTags](#gettags)|Obtient l’étiquette pour les opérations de dessin suivantes.|  
|[CRenderTarget::GetTextAntialiasMode](#gettextantialiasmode)|Obtient le mode d’anticrénelage actuel pour le texte et les opérations de dessin de glyphe.|  
|[CRenderTarget::GetTextRenderingParams](#gettextrenderingparams)|Récupère les options de rendu de texte en cours de la cible de rendu.|  
|[CRenderTarget::GetTransform](#gettransform)|Applique la transformation spécifiée à la cible de rendu, en remplaçant la transformation existante. Toutes les opérations de dessin suivantes se produisent dans l’espace transformé.|  
|[CRenderTarget::IsSupported](#issupported)|Indique si la cible de rendu prend en charge les propriétés spécifiées|  
|[CRenderTarget::IsValid](#isvalid)|Vérifications de validité des ressources|  
|[CRenderTarget::PopAxisAlignedClip](#popaxisalignedclip)|Supprime le dernier élément aligné sur l’axe de la cible de rendu. Une fois que cette méthode est appelée, l’élément n’est plus appliqué aux opérations de dessin suivantes.|  
|[CRenderTarget::PopLayer](#poplayer)|Arrête de rediriger les opérations de dessin à la couche qui est spécifiée par la dernière PushLayer appeler.|  
|[CRenderTarget::PushAxisAlignedClip](#pushaxisalignedclip)|Supprime le dernier élément aligné sur l’axe de la cible de rendu. Une fois que cette méthode est appelée, l’élément n’est plus appliqué aux opérations de dessin suivantes.|  
|[CRenderTarget::PushLayer](#pushlayer)|Ajoute la couche spécifiée à la cible de rendu afin qu’elle reçoive toutes les opérations de dessin successives jusqu'à l’appel de PopLayer.|  
|[CRenderTarget::RestoreDrawingState](#restoredrawingstate)|Définit l’état du dessin de la cible de rendu à celui de la ID2D1DrawingStateBlock spécifié.|  
|[CRenderTarget::SaveDrawingState](#savedrawingstate)|Enregistre l’état actuel du dessin pour le ID2D1DrawingStateBlock spécifié.|  
|[CRenderTarget::SetAntialiasMode](#setantialiasmode)|Définit le mode d’anticrénelage de la cible de rendu. Le mode d’anticrénelage s’applique à toutes les opérations de dessin suivantes, à l’exception de texte et le glyphe d’opérations de dessin.|  
|[CRenderTarget::SetDpi](#setdpi)|Définit la taille en points par pouce (PPP) de la cible de rendu.|  
|[CRenderTarget::SetTags](#settags)|Spécifie une étiquette pour les opérations de dessin suivantes.|  
|[CRenderTarget::SetTextAntialiasMode](#settextantialiasmode)|Spécifie le mode d’anticrénelage à utiliser pour le texte suivant et les opérations de dessin de glyphe.|  
|[CRenderTarget::SetTextRenderingParams](#settextrenderingparams)|Spécifie les options de rendu de texte à appliquer à tout type texte et glyphe opérations de dessin.|  
|[CRenderTarget::SetTransform](#settransform)|Surchargé. Applique la transformation spécifiée à la cible de rendu, en remplaçant la transformation existante. Toutes les opérations de dessin suivantes se produisent dans l’espace transformé.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CRenderTarget::VerifyResource](#verifyresource)|Vérifie la validité de l’objet CD2DResource ; crée l’objet s’il n’existe pas.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRenderTarget::operator ID2D1RenderTarget *](#operator_id2d1rendertarget_star)|Renvoie l’interface ID2D1RenderTarget|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CRenderTarget::m_lstResources](#m_lstresources)|Une liste de pointeurs vers les objets CD2DResource.|  
|[CRenderTarget::m_pRenderTarget](#m_prendertarget)|Pointeur vers un objet ID2D1RenderTarget.|  
|[CRenderTarget::m_pTextFormatDefault](#m_ptextformatdefault)|Pointeur vers l’objet CD2DTextFormat qui contient un format de texte par défaut.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="_dtorcrendertarget"></a>CRenderTarget :: ~ CRenderTarget  
 Destructeur. Appelé lorsqu’un objet cible de rendu est détruit.  
  
```  
virtual ~CRenderTarget();
```  
  
##  <a name="attach"></a>CRenderTarget::Attach  
 Interface de cible à l’objet de rendu attache existant  
  
```  
void Attach(ID2D1RenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `pRenderTarget`  
 Interface de cible de rendu existante. Ne peut pas être NULL  
  
##  <a name="begindraw"></a>CRenderTarget::BeginDraw  
 Démarre le dessin sur cette cible de rendu.  
  
```  
void BeginDraw();
```  
  
##  <a name="clear"></a>CRenderTarget::Clear  
 Efface la zone de dessin avec la couleur spécifiée.  
  
```  
void Clear(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>Paramètres  
 `color`  
 La couleur à laquelle la zone de dessin est désactivée.  
  
##  <a name="colorref_to_d2dcolor"></a>CRenderTarget::COLORREF_TO_D2DCOLOR  
 Convertit les valeurs de couleur et alpha GDI pour l’objet D2D1_COLOR_F.  
  
```  
static D2D1_COLOR_F COLORREF_TO_D2DCOLOR(
    COLORREF color,  
    int nAlpha = 255);
```  
  
### <a name="parameters"></a>Paramètres  
 `color`  
 Valeur RVB.  
  
 `nAlpha`  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur D2D1_COLOR_F.  
  
##  <a name="createcompatiblerendertarget"></a>CRenderTarget::CreateCompatibleRenderTarget  
 Crée une nouvelle cible de rendu de bitmap pour une utilisation pendant le dessin hors écran intermédiaire qui est compatible avec la cible de rendu actuelle.  
  
```  
BOOL CreateCompatibleRenderTarget(
    CBitmapRenderTarget& bitmapTarget,  
    CD2DSizeF sizeDesired = CD2DSizeF(0., 0.), 
    CD2DSizeU sizePixelDesired = CD2DSizeU(0, 0), 
    D2D1_PIXEL_FORMAT* desiredFormat = NULL,  
    D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS options = D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bitmapTarget`  
 Lorsque cette méthode est retournée, contient l’adresse d’un pointeur vers une nouvelle cible de rendu de bitmap. Ce paramètre est passé sans être initialisé.  
  
 `sizeDesired`  
 Taille souhaitée de la nouvelle cible de rendu en pixels indépendants du périphérique si elle doit être différent de celui d’origine cible de rendu ou NULL. Pour plus d'informations, consultez la section Remarques.  
  
 `sizePixelDesired`  
 Taille souhaitée de la nouvelle cible de rendu en pixels si elle doit être différent de celui d’origine cible de rendu ou NULL. Pour plus d'informations, consultez la section Remarques.  
  
 `desiredFormat`  
 Le format de pixel souhaité et mode alpha de la nouvelle cible de rendu ou NULL. Si le format de pixel est défini à DXGI_FORMAT_UNKNOWN ou si ce paramètre est null, la nouvelle cible de rendu utilise le même format de pixel comme cible de rendu d’origine. Si le mode alpha est D2D1_ALPHA_MODE_UNKNOWN ou si ce paramètre est NULL, le mode alpha de la cible de rendu de D2D1_ALPHA_MODE_PREMULTIPLIED par défaut. Pour plus d’informations sur les formats de pixel pris en charge, consultez prise en charge des Formats de Pixel et Modes d’Alpha.  
  
 `options`  
 Une valeur qui indique si la nouvelle cible de rendu doit être compatible avec GDI.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne TRUE. Sinon, elle retourne FALSE.  
  
##  <a name="crendertarget"></a>CRenderTarget::CRenderTarget  
 Construit un objet CRenderTarget.  
  
```  
CRenderTarget();
```  
  
##  <a name="destroy"></a>CRenderTarget::Destroy  
 Supprime une ou plusieurs ressources  
  
```  
BOOL Destroy(BOOL bDeleteResources = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bDeleteResources`  
 Si bDeleteResources est TRUE, toutes les ressources situées dans m_lstResources sont automatiquement détruites.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne TRUE. Sinon, elle retourne FALSE  
  
##  <a name="detach"></a>CRenderTarget::Detach  
 Détache l’interface de cible de rendu de l’objet  
  
```  
ID2D1RenderTarget* Detach ();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Interface de cible de rendu de pointeur à détacher.  
  
##  <a name="drawbitmap"></a>CRenderTarget::DrawBitmap  
 Dessine le texte mis en forme décrit par l’objet IDWriteTextLayout spécifié.  
  
```  
void DrawBitmap(
    CD2DBitmap* pBitmap,  
    const CD2DRectF& rectDest,  
    float fOpacity = 1.0,  
    D2D1_BITMAP_INTERPOLATION_MODE interpolationMode = D2D1_BITMAP_INTERPOLATION_MODE_LINEAR,  
    const CD2DRectF* pRectSrc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pBitmap`  
 L’image bitmap à restituer.  
  
 `rectDest`  
 La taille et position, en pixels indépendants du périphérique dans l’espace de coordonnées de la cible de rendu de la zone à laquelle le bitmap est dessiné. Si le rectangle n’est pas bien ordonné, rien n’est dessiné, mais la cible de rendu n’entre pas un état d’erreur.  
  
 `fOpacity`  
 Une valeur comprise entre 0.0f et 1.0f compris, qui spécifie une valeur d’opacité à appliquer à la bitmap. Cette valeur est multipliée par les valeurs alpha du contenu de la bitmap.  
  
 `interpolationMode`  
 Le mode d’interpolation à utiliser si la bitmap est mis à l’échelle ou pivotée par l’opération de dessin.  
  
 `pRectSrc`  
 La taille et position, en pixels indépendants du périphérique dans l’espace de coordonnées de la bitmap, de la zone dans l’image bitmap à dessiner.  
  
##  <a name="drawellipse"></a>CRenderTarget::DrawEllipse  
 Dessine le contour de l’ellipse spécifiée à l’aide du style de trait spécifié.  
  
```  
void DrawEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `ellipse`  
 La position et le rayon de l’ellipse à tracer en pixels indépendants du périphérique.  
  
 `pBrush`  
 Le pinceau utilisé pour peindre le contour de l’ellipse.  
  
 `fStrokeWidth`  
 Épaisseur du contour de l’ellipse. Le trait est centré sur le contour de l’ellipse.  
  
 `strokeStyle`  
 Style de trait à appliquer au contour de l’ellipse, ou NULL pour peindre un trait plein.  
  
##  <a name="drawgeometry"></a>CRenderTarget::DrawGeometry  
 Dessine le contour de la géométrie spécifiée à l’aide du style de trait spécifié.  
  
```  
void DrawGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pGeometry`  
 Géométrie à dessiner.  
  
 `pBrush`  
 Le pinceau utilisé pour peindre le contour de la géométrie.  
  
 `fStrokeWidth`  
 L’épaisseur de trait de la géométrie. Le trait est centré sur le contour de la géométrie.  
  
 `strokeStyle`  
 Style de trait à appliquer au contour de la géométrie, ou NULL pour peindre un trait plein.  
  
##  <a name="drawglyphrun"></a>CRenderTarget::DrawGlyphRun  
 Dessine les glyphes spécifiés.  
  
```  
void DrawGlyphRun(
    const CD2DPointF& ptBaseLineOrigin,  
    const DWRITE_GLYPH_RUN& glyphRun,  
    CD2DBrush* pForegroundBrush,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptBaseLineOrigin`  
 L’origine, en pixels indépendants du périphérique, de ligne de base des glyphes.  
  
 `glyphRun`  
 Les glyphes à restituer.  
  
 `pForegroundBrush`  
 Le pinceau utilisé pour peindre les glyphes spécifiés.  
  
 `measuringMode`  
 Une valeur qui indique comment les mesures de glyphe sont utilisés pour mesurer le texte lorsqu’il est mis en forme. La valeur par défaut est DWRITE_MEASURING_MODE_NATURAL.  
  
##  <a name="drawline"></a>CRenderTarget::DrawLine  
 Dessine une ligne entre les points spécifiés à l’aide du style de trait spécifié.  
  
```  
void DrawLine(
    const CD2DPointF& ptFrom,  
    const CD2DPointF& ptTo,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptFrom`  
 Le point de départ de la ligne, en pixels indépendants du périphérique.  
  
 `ptTo`  
 Le point de terminaison de la ligne, en pixels indépendants du périphérique.  
  
 `pBrush`  
 Le pinceau utilisé pour peindre le trait de.  
  
 `fStrokeWidth`  
 Une valeur supérieure ou égale à 0,0 f qui spécifie la largeur du trait. Si ce paramètre n’est pas spécifié, la valeur par défaut est 1.0f. Le trait est centré sur la ligne.  
  
 `strokeStyle`  
 Style de trait à peindre, ou NULL pour peindre un trait plein.  
  
##  <a name="drawrectangle"></a>CRenderTarget::DrawRectangle  
 Dessine le contour d’un rectangle qui contient les dimensions spécifiées et le style de trait.  
  
```  
void DrawRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `rect`  
 Les dimensions du rectangle à tracer en pixels indépendants du périphérique  
  
 `pBrush`  
 Le pinceau utilisé pour peindre le trait du rectangle  
  
 `fStrokeWidth`  
 Une valeur supérieure ou égale à 0,0 f qui spécifie la largeur du trait du rectangle. Le trait est centré sur le contour du rectangle.  
  
 `strokeStyle`  
 Le style de trait à peindre, ou NULL pour peindre un trait plein.  
  
##  <a name="drawroundedrectangle"></a>CRenderTarget::DrawRoundedRectangle  
 Dessine le contour du rectangle arrondi spécifié à l’aide du style de trait spécifié.  
  
```  
void DrawRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `rectRounded`  
 Les dimensions du rectangle arrondi à tracer en pixels indépendants du périphérique.  
  
 `pBrush`  
 Le pinceau utilisé pour peindre le contour du rectangle arrondi.  
  
 `fStrokeWidth`  
 La largeur de trait du rectangle arrondi. Le trait est centré sur le contour du rectangle arrondi. La valeur par défaut est 1.0f.  
  
 `strokeStyle`  
 Style de trait du rectangle arrondi, ou NULL pour peindre un trait plein. La valeur par défaut est NULL.  
  
##  <a name="drawtext"></a>CRenderTarget::DrawText  
 Dessine le texte spécifié à l’aide des informations de format fournies par un objet IDWriteTextFormat.  
  
```  
void DrawText(
    const CString& strText,  
    const CD2DRectF& rect,  
    CD2DBrush* pForegroundBrush,  
    CD2DTextFormat* textFormat = NULL,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>Paramètres  
 `strText`  
 Pointeur vers un tableau de caractères Unicode à tracer.  
  
 `rect`  
 La taille et la position de la zone dans laquelle le texte est dessiné.  
  
 `pForegroundBrush`  
 Le pinceau utilisé pour peindre le texte.  
  
 `textFormat`  
 Un objet qui décrit la mise en forme du texte à dessiner, telles que la police, la taille de police et la direction du flux d’informations.  
  
 `options`  
 Une valeur qui indique si le texte doit être aligné aux limites en pixels et si le texte doit être découpé le rectangle de présentation. La valeur par défaut est D2D1_DRAW_TEXT_OPTIONS_NONE, ce qui indique que texte doit être aligné sur les limites des pixels et il ne doit pas être découpé le rectangle de disposition.  
  
 `measuringMode`  
 Une valeur qui indique comment les mesures de glyphe sont utilisés pour mesurer le texte lorsqu’il est mis en forme. La valeur par défaut est DWRITE_MEASURING_MODE_NATURAL.  
  
##  <a name="drawtextlayout"></a>CRenderTarget::DrawTextLayout  
 Dessine le texte mis en forme décrit par l’objet IDWriteTextLayout spécifié.  
  
```  
void DrawTextLayout(
    const CD2DPointF& ptOrigin,  
    CD2DTextLayout* textLayout,  
    CD2DBrush* pBrushForeground,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptOrigin`  
 Point, décrit en pixels indépendants du périphérique auquel le coin supérieur gauche du texte décrit par textLayout est dessiné.  
  
 `textLayout`  
 Le texte mis en forme à dessiner. Les effets de dessin qui n’héritent pas d’ID2D1Resource sont ignorés. Si des effets de dessin qui héritent d’ID2D1Resource qui ne sont pas des pinceaux, cette méthode échoue et la cible de rendu est placée dans un état d’erreur.  
  
 `pBrushForeground`  
 Le pinceau utilisé pour peindre n’importe quel texte dans textLayout qui n’a pas déjà un pinceau associé comme effet de dessin (spécifié par la méthode IDWriteTextLayout::SetDrawingEffect).  
  
 `options`  
 Une valeur qui indique si le texte doit être aligné aux limites en pixels et si le texte doit être découpé le rectangle de présentation. La valeur par défaut est D2D1_DRAW_TEXT_OPTIONS_NONE, ce qui indique que texte doit être aligné sur les limites des pixels et il ne doit pas être découpé le rectangle de disposition.  
  
##  <a name="enddraw"></a>CRenderTarget::EndDraw  
 Fin des opérations de dessin sur la cible de rendu et indique l’état d’erreur actuel et les balises associées.  
  
```  
HRESULT EndDraw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne S_OK. Sinon, elle retourne un code d’erreur HRESULT.  
  
##  <a name="fillellipse"></a>CRenderTarget::FillEllipse  
 Peint l’intérieur de l’ellipse spécifiée.  
  
```  
void FillEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Paramètres  
 `ellipse`  
 Position et rayon, en pixels indépendants du périphérique, de l’ellipse à peindre.  
  
 `pBrush`  
 Le pinceau utilisé pour peindre l’intérieur de l’ellipse.  
  
##  <a name="fillgeometry"></a>CRenderTarget::FillGeometry  
 Peint l’intérieur de la géométrie spécifiée.  
  
```  
void FillGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    CD2DBrush* pOpacityBrush = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pGeometry`  
 Géométrie à peindre.  
  
 `pBrush`  
 Le pinceau utilisé pour peindre la géométrie 's intérieur.  
  
 `pOpacityBrush`  
 Le masque d’opacité à appliquer à la géométrie ; NULL pour aucun masque d’opacité. Si un masque d’opacité (paramètre opacityBrush) est spécifié, pinceau doit être un ID2D1BitmapBrush ayant ses modes x et y étendre la valeur D2D1_EXTEND_MODE_CLAMP. Pour plus d'informations, consultez la section Remarques.  
  
##  <a name="fillmesh"></a>CRenderTarget::FillMesh  
 Peint l’intérieur du maillage spécifié.  
  
```  
void FillMesh(
    CD2DMesh* pMesh,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Paramètres  
 `pMesh`  
 Maillage à peindre.  
  
 `pBrush`  
 Pinceau utilisé pour peindre le maillage.  
  
##  <a name="fillopacitymask"></a>CRenderTarget::FillOpacityMask  
 Applique le masque d’opacité décrit par l’image bitmap spécifiée à un pinceau et l’utilise pour peindre une région de la cible de rendu.  
  
```  
void FillOpacityMask(
    CD2DBitmap* pOpacityMask,  
    CD2DBrush* pBrush,  
    D2D1_OPACITY_MASK_CONTENT content,  
    const CD2DRectF& rectDest,  
    const CD2DRectF& rectSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 `pOpacityMask`  
 Position et rayon, en pixels indépendants du périphérique, de l’ellipse à peindre.  
  
 `pBrush`  
 Le pinceau utilisé pour peindre la région de la cible de rendu spécifiée par destinationRectangle.  
  
 `content`  
 Le type de contenu que contient le masque d’opacité. La valeur est utilisée pour déterminer l’espace colorimétrique dans lequel le masque d’opacité est fusionnée.  
  
 `rectDest`  
 La région de la cible de rendu pour peindre, en pixels indépendants du périphérique.  
  
 `rectSrc`  
 La région de l’image bitmap à utiliser comme masque d’opacité, en pixels indépendants du périphérique.  
  
##  <a name="fillrectangle"></a>CRenderTarget::FillRectangle  
 Peint l’intérieur du rectangle spécifié.  
  
```  
void FillRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Paramètres  
 `rect`  
 La dimension du rectangle à peindre en pixels indépendants du périphérique.  
  
 `pBrush`  
 Le pinceau utilisé pour peindre le rectangle de 's intérieur.  
  
##  <a name="fillroundedrectangle"></a>CRenderTarget::FillRoundedRectangle  
 Peint l’intérieur du rectangle arrondi spécifié.  
  
```  
void FillRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Paramètres  
 `rectRounded`  
 Les dimensions du rectangle arrondi à peindre en pixels indépendants du périphérique.  
  
 `pBrush`  
 Le pinceau utilisé pour peindre l’intérieur du rectangle arrondi.  
  
##  <a name="flush"></a>CRenderTarget::Flush  
 Exécute toutes les commandes de dessin en attente.  
  
```  
void Flush(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `tag1`  
 Contient la balise pour les opérations qui a provoqué des erreurs ou 0 si aucune erreur de dessin. Ce paramètre est passé sans être initialisé.  
  
 `tag2`  
 Contient la balise pour les opérations qui a provoqué des erreurs ou 0 si aucune erreur de dessin. Ce paramètre est passé sans être initialisé.  
  
##  <a name="getantialiasmode"></a>CRenderTarget::GetAntialiasMode  
 Récupère le mode d’anticrénelage actuel pour les opérations de dessin de non-texte.  
  
```  
D2D1_ANTIALIAS_MODE GetAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Mode d’anticrénelage actuel pour les opérations de dessin de non-texte.  
  
##  <a name="getdpi"></a>CRenderTarget::GetDpi  
 Retourne le rendu des points de la cible par pouce (PPP)  
  
```  
CD2DSizeF GetDpi() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Points de la cible de rendu par pouce (PPP).  
  
##  <a name="getmaximumbitmapsize"></a>CRenderTarget::GetMaximumBitmapSize  
 Obtient la taille maximale, en unités dépendantes du périphérique (pixels), de toute dimension d’un bitmap pris en charge par la cible de rendu  
  
```  
UINT32 GetMaximumBitmapSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La taille maximale, en pixels, d’une dimension de l’image bitmap pris en charge par la cible de rendu  
  
##  <a name="getpixelformat"></a>CRenderTarget::GetPixelFormat  
 Récupère le mode d’alpha et du format de pixel de la cible de rendu  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le format de pixel alpha mode de la cible de rendu  
  
##  <a name="getpixelsize"></a>CRenderTarget::GetPixelSize  
 Retourne la taille de la cible de rendu en pixels de périphérique  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La taille de la cible de rendu en pixels de périphérique  
  
##  <a name="getrendertarget"></a>CRenderTarget::GetRenderTarget  
 Renvoie l’interface ID2D1RenderTarget  
  
```  
ID2D1RenderTarget* GetRenderTarget();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1RenderTarget ou NULL si l’objet n’est pas encore initialisé.  
  
##  <a name="getsize"></a>CRenderTarget::GetSize  
 Retourne la taille de la cible de rendu en pixels indépendants du périphérique  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La taille actuelle de la cible de rendu en pixels indépendants du périphérique  
  
##  <a name="gettags"></a>CRenderTarget::GetTags  
 Obtient l’étiquette pour les opérations de dessin suivantes.  
  
```  
void GetTags(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `tag1`  
 Contient la première étiquette des opérations de dessin suivantes. Ce paramètre est passé sans être initialisé. Si NULL est spécifié, aucune valeur n’est récupérée pour ce paramètre.  
  
 `tag2`  
 Contient la deuxième étiquette des opérations de dessin suivantes. Ce paramètre est passé sans être initialisé. Si NULL est spécifié, aucune valeur n’est récupérée pour ce paramètre.  
  
##  <a name="gettextantialiasmode"></a>CRenderTarget::GetTextAntialiasMode  
 Obtient le mode d’anticrénelage actuel pour le texte et les opérations de dessin de glyphe.  
  
```  
D2D1_TEXT_ANTIALIAS_MODE GetTextAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Mode d’anticrénelage actuel pour le texte et les opérations de dessin de glyphe.  
  
##  <a name="gettextrenderingparams"></a>CRenderTarget::GetTextRenderingParams  
 Récupère les options de rendu de texte en cours de la cible de rendu.  
  
```  
void GetTextRenderingParams(IDWriteRenderingParams** textRenderingParams);
```  
  
### <a name="parameters"></a>Paramètres  
 `textRenderingParams`  
 Lorsque cette méthode est retournée, textRenderingParamscontains l’adresse d’un pointeur vers la cible de rendu actuelle du options de rendu de texte.  
  
##  <a name="gettransform"></a>CRenderTarget::GetTransform  
 Applique la transformation spécifiée à la cible de rendu, en remplaçant la transformation existante. Toutes les opérations de dessin suivantes se produisent dans l’espace transformé.  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Paramètres  
 `transform`  
 La transformation à appliquer à la cible de rendu.  
  
##  <a name="issupported"></a>CRenderTarget::IsSupported  
 Indique si la cible de rendu prend en charge les propriétés spécifiées  
  
```  
BOOL IsSupported(const D2D1_RENDER_TARGET_PROPERTIES& renderTargetProperties) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `renderTargetProperties`  
 Les propriétés de cible de rendu à tester  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si les propriétés de cible de rendu spécifiée sont prises en charge par cette cible de rendu ; Sinon, FALSE  
  
##  <a name="isvalid"></a>CRenderTarget::IsValid  
 Vérifications de validité des ressources  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la ressource est valide ; Sinon, FALSE.  
  
##  <a name="m_lstresources"></a>CRenderTarget::m_lstResources  
 Une liste de pointeurs vers les objets CD2DResource.  
  
```  
CObList m_lstResources;  
```  
  
##  <a name="m_prendertarget"></a>CRenderTarget::m_pRenderTarget  
 Pointeur vers un objet ID2D1RenderTarget.  
  
```  
ID2D1RenderTarget* m_pRenderTarget;  
```  
  
##  <a name="m_ptextformatdefault"></a>CRenderTarget::m_pTextFormatDefault  
 Pointeur vers l’objet CD2DTextFormat qui contient un format de texte par défaut.  
  
```  
CD2DTextFormat* m_pTextFormatDefault;  
```  
  
##  <a name="operator_id2d1rendertarget_star"></a>CRenderTarget::operator ID2D1RenderTarget *  
 Renvoie l’interface ID2D1RenderTarget  
  
```  
operator ID2D1RenderTarget*();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1RenderTarget ou NULL si l’objet n’est pas encore initialisé.  
  
##  <a name="popaxisalignedclip"></a>CRenderTarget::PopAxisAlignedClip  
 Supprime le dernier élément aligné sur l’axe de la cible de rendu. Une fois que cette méthode est appelée, l’élément n’est plus appliqué aux opérations de dessin suivantes.  
  
```  
void PopAxisAlignedClip();
```  
  
##  <a name="poplayer"></a>CRenderTarget::PopLayer  
 Arrête de rediriger les opérations de dessin à la couche qui est spécifiée par la dernière PushLayer appeler.  
  
```  
void PopLayer();
```  
  
##  <a name="pushaxisalignedclip"></a>CRenderTarget::PushAxisAlignedClip  
 Supprime le dernier élément aligné sur l’axe de la cible de rendu. Une fois que cette méthode est appelée, l’élément n’est plus appliqué aux opérations de dessin suivantes.  
  
```  
void PushAxisAlignedClip(
    const CD2DRectF& rectClip,  
    D2D1_ANTIALIAS_MODE mode = D2D1_ANTIALIAS_MODE_PER_PRIMITIVE);
```  
  
### <a name="parameters"></a>Paramètres  
 `rectClip`  
 La taille et la position de la zone de découpage, en pixels indépendants du périphérique.  
  
 `mode`  
 Mode d’anticrénelage utilisé pour dessiner les bords des rectangles de détourage qui ont des limites de sous-pixel et pour fusionner le clip avec le contenu de la scène. La fusion est exécutée une fois lorsque la méthode PopAxisAlignedClip est appelée et ne s’applique pas à chaque primitive au sein de la couche.  
  
##  <a name="pushlayer"></a>CRenderTarget::PushLayer  
 Ajoute la couche spécifiée à la cible de rendu afin qu’elle reçoive toutes les opérations de dessin successives jusqu'à l’appel de PopLayer.  
  
```  
void PushLayer(
    const D2D1_LAYER_PARAMETERS& layerParameters,  
    CD2DLayer& layer);
```  
  
### <a name="parameters"></a>Paramètres  
 `layerParameters`  
 Les limites du contenu, masque géométrique, opacité, masque d’opacité et options d’anticrénelage de la couche.  
  
 `layer`  
 La couche qui reçoit les opérations de dessin suivantes.  
  
##  <a name="restoredrawingstate"></a>CRenderTarget::RestoreDrawingState  
 Définit l’état du dessin de la cible de rendu à celui de la ID2D1DrawingStateBlock spécifié.  
  
```  
void RestoreDrawingState(ID2D1DrawingStateBlock& drawingStateBlock);
```  
  
### <a name="parameters"></a>Paramètres  
 `drawingStateBlock`  
 Le nouvel état de dessin de la cible de rendu.  
  
##  <a name="savedrawingstate"></a>CRenderTarget::SaveDrawingState  
 Enregistre l’état actuel du dessin pour le ID2D1DrawingStateBlock spécifié.  
  
```  
void SaveDrawingState(ID2D1DrawingStateBlock& drawingStateBlock) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `drawingStateBlock`  
 Lorsque cette méthode est retournée, contient l’état actuel du dessin de la cible de rendu. Ce paramètre doit être initialisé avant de le transmettre à la méthode.  
  
##  <a name="setantialiasmode"></a>CRenderTarget::SetAntialiasMode  
 Définit le mode d’anticrénelage de la cible de rendu. Le mode d’anticrénelage s’applique à toutes les opérations de dessin suivantes, à l’exception de texte et le glyphe d’opérations de dessin.  
  
```  
void SetAntialiasMode(D2D1_ANTIALIAS_MODE antialiasMode);
```  
  
### <a name="parameters"></a>Paramètres  
 `antialiasMode`  
 Mode d’anticrénelage pour les futures opérations de dessin.  
  
##  <a name="setdpi"></a>CRenderTarget::SetDpi  
 Définit la taille en points par pouce (PPP) de la cible de rendu.  
  
```  
void SetDpi(const CD2DSizeF& sizeDPI);
```  
  
### <a name="parameters"></a>Paramètres  
 `sizeDPI`  
 Une valeur supérieure ou égale à zéro qui spécifie le DPI horizontal/vertical de la cible de rendu.  
  
##  <a name="settags"></a>CRenderTarget::SetTags  
 Spécifie une étiquette pour les opérations de dessin suivantes.  
  
```  
void SetTags(
    D2D1_TAG tag1,  
    D2D1_TAG tag2);
```  
  
### <a name="parameters"></a>Paramètres  
 `tag1`  
 Une étiquette à appliquer aux opérations de dessin suivantes.  
  
 `tag2`  
 Une étiquette à appliquer aux opérations de dessin suivantes.  
  
##  <a name="settextantialiasmode"></a>CRenderTarget::SetTextAntialiasMode  
 Spécifie le mode d’anticrénelage à utiliser pour le texte suivant et les opérations de dessin de glyphe.  
  
```  
void SetTextAntialiasMode(D2D1_TEXT_ANTIALIAS_MODE textAntialiasMode);
```  
  
### <a name="parameters"></a>Paramètres  
 `textAntialiasMode`  
 Mode d’anticrénelage à utiliser pour le texte et glyphe opérations de dessin.  
  
##  <a name="settextrenderingparams"></a>CRenderTarget::SetTextRenderingParams  
 Spécifie les options de rendu de texte à appliquer à tout type texte et glyphe opérations de dessin.  
  
```  
void SetTextRenderingParams(IDWriteRenderingParams* textRenderingParams = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `textRenderingParams`  
 Les options de rendu de texte à appliquer à tout type texte et glyphe opérations ; NULL pour effacer les options de rendu de texte actuelles.  
  
##  <a name="settransform"></a>CRenderTarget::SetTransform  
 Applique la transformation spécifiée à la cible de rendu, en remplaçant la transformation existante. Toutes les opérations de dessin suivantes se produisent dans l’espace transformé.  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);  
void SetTransform(const D2D1_MATRIX_3X2_F& transform);
```  
  
### <a name="parameters"></a>Paramètres  
 `transform`  
 La transformation à appliquer à la cible de rendu.  
  
##  <a name="verifyresource"></a>CRenderTarget::VerifyResource  
 Vérifie la validité de l’objet CD2DResource ; crée l’objet s’il n’existe pas.  
  
```  
BOOL VerifyResource(CD2DResource* pResource);
```  
  
### <a name="parameters"></a>Paramètres  
 `pResource`  
 Pointeur vers l’objet CD2DResource.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE est l’objet s’il est valide ; Sinon, FALSE.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)
