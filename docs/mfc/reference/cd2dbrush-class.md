---
title: Classe de CD2DBrush | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrush class
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
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
ms.openlocfilehash: b9902445fb6e18df20073d132a2117c67e695b25
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dbrush-class"></a>CD2DBrush, classe
Wrapper pour ID2D1Brush.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DBrush::CD2DBrush](#cd2dbrush)|Construit un objet CD2DBrush.|  
|[CD2DBrush :: ~ CD2DBrush](#_dtorcd2dbrush)|Destructeur. Appelé lorsqu’un objet de brush D2D est détruit.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DBrush::Attach](#attach)|Attache existant à l’objet interface de la ressource|  
|[CD2DBrush::Destroy](#destroy)|Détruit un objet CD2DBrush. (Substitue [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DBrush::Detach](#detach)|Détache l’interface de la ressource à partir de l’objet|  
|[CD2DBrush::Get](#get)|Renvoie l’interface ID2D1Brush|  
|[CD2DBrush::GetOpacity](#getopacity)|Obtient le degré d’opacité de ce pinceau|  
|[CD2DBrush::GetTransform](#gettransform)|Obtient la transformation actuelle de la cible de rendu|  
|[CD2DBrush::IsValid](#isvalid)|Vérifie la validité des ressources (substitue [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DBrush::SetOpacity](#setopacity)|Définit le degré d’opacité de ce pinceau|  
|[CD2DBrush::setTransform](#settransform)|Applique la transformation spécifiée à la cible de rendu, en remplaçant la transformation existante. Toutes les opérations de dessin suivantes se produisent dans l’espace transformé|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DBrush::operator ID2D1Brush *](#operator_id2d1brush_star)|Renvoie l’interface ID2D1Brush|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DBrush::m_pBrush](#m_pbrush)|Stocke un pointeur vers un objet ID2D1Brush.|  
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|Propriétés de pinceau.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBrush`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="_dtorcd2dbrush"></a>CD2DBrush :: ~ CD2DBrush  
 Destructeur. Appelé lorsqu’un objet de brush D2D est détruit.  
  
```  
virtual ~CD2DBrush();
```  
  
##  <a name="attach"></a>CD2DBrush::Attach  
 Attache existant à l’objet interface de la ressource  
  
```  
void Attach(ID2D1Brush* pResource);
```  
  
### <a name="parameters"></a>Paramètres  
 `pResource`  
 Interface de la ressource existante. Ne peut pas être NULL  
  
##  <a name="cd2dbrush"></a>CD2DBrush::CD2DBrush  
 Construit un objet CD2DBrush.  
  
```  
CD2DBrush(
    CRenderTarget* pParentTarget,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentTarget`  
 Pointeur vers la cible de rendu.  
  
 `pBrushProperties`  
 Pointeur vers l’opacité et la transformation d’un pinceau.  
  
 `bAutoDestroy`  
 Indique que l’objet sera détruit par le propriétaire (pParentTarget).  
  
##  <a name="destroy"></a>CD2DBrush::Destroy  
 Détruit un objet CD2DBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DBrush::Detach  
 Détache l’interface de la ressource à partir de l’objet  
  
```  
ID2D1Brush* Detach();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’interface de la ressource détachée.  
  
##  <a name="get"></a>CD2DBrush::Get  
 Renvoie l’interface ID2D1Brush  
  
```  
ID2D1Brush* Get();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1Brush ou NULL si l’objet n’est pas encore initialisé.  
  
##  <a name="getopacity"></a>CD2DBrush::GetOpacity  
 Obtient le degré d’opacité de ce pinceau  
  
```  
FLOAT GetOpacity() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur comprise entre zéro et 1 qui indique l’opacité du pinceau. Cette valeur est un multiplicateur constant qui évolue de façon linéaire la valeur alpha de tous les pixels remplis par le pinceau. Les valeurs d’opacité sont ancrées dans la plage 0 à 1 avant d’être multipliées ensemble  
  
##  <a name="gettransform"></a>CD2DBrush::GetTransform  
 Obtient la transformation actuelle de la cible de rendu  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `transform`  
 Lorsque cela est retournée, contient la transformation actuelle de la cible de rendu. Ce paramètre est passé sans être initialisé  
  
##  <a name="isvalid"></a>CD2DBrush::IsValid  
 Vérifications de validité des ressources  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la ressource est valide ; Sinon, FALSE.  
  
##  <a name="m_pbrush"></a>CD2DBrush::m_pBrush  
 Stocke un pointeur vers un objet ID2D1Brush.  
  
```  
ID2D1Brush* m_pBrush;  
```  
  
##  <a name="m_pbrushproperties"></a>CD2DBrush::m_pBrushProperties  
 Propriétés de pinceau.  
  
```  
CD2DBrushProperties* m_pBrushProperties;  
```  
  
##  <a name="operator_id2d1brush_star"></a>CD2DBrush::operator ID2D1Brush *  
 Renvoie l’interface ID2D1Brush  
  
```  
operator ID2D1Brush*();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1Brush ou NULL si l’objet n’est pas encore initialisé.  
  
##  <a name="setopacity"></a>CD2DBrush::SetOpacity  
 Définit le degré d’opacité de ce pinceau  
  
```  
void SetOpacity(FLOAT opacity);
```  
  
### <a name="parameters"></a>Paramètres  
 `opacity`  
 Une valeur comprise entre zéro et 1 qui indique l’opacité du pinceau. Cette valeur est un multiplicateur constant qui évolue de façon linéaire la valeur alpha de tous les pixels remplis par le pinceau. Les valeurs d’opacité sont ancrées dans la plage 0 à 1 avant d’être multipliées ensemble  
  
##  <a name="settransform"></a>CD2DBrush::setTransform  
 Applique la transformation spécifiée à la cible de rendu, en remplaçant la transformation existante. Toutes les opérations de dessin suivantes se produisent dans l’espace transformé  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Paramètres  
 `transform`  
 La transformation à appliquer à la cible de rendu  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

