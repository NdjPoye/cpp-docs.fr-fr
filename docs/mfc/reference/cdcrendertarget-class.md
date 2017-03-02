---
title: Classe CDCRenderTarget | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CDCRenderTarget
- CDCRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CDCRenderTarget class
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
caps.latest.revision: 16
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2bbd62b06f4287904fce49f8a6ce9900476b07c0
ms.lasthandoff: 02/24/2017

---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget, classe
Wrapper pour ID2D1DCRenderTarget.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDCRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDCRenderTarget::CDCRenderTarget](#cdcrendertarget)|Construit un objet CDCRenderTarget.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDCRenderTarget::Attach](#attach)|Interface de cible à l’objet de rendu attache existant|  
|[CDCRenderTarget::BindDC](#binddc)|Lie la cible de rendu pour le contexte de périphérique auquel il envoie des commandes de dessin|  
|[CDCRenderTarget::Create](#create)|Crée CDCRenderTarget.|  
|[CDCRenderTarget::Detach](#detach)|Détache l’interface de cible de rendu de l’objet|  
|[CDCRenderTarget::GetDCRenderTarget](#getdcrendertarget)|Renvoie l’interface ID2D1DCRenderTarget|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDCRenderTarget::operator ID2D1DCRenderTarget *](#operator_id2d1dcrendertarget_star)|Renvoie l’interface ID2D1DCRenderTarget|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CDCRenderTarget::m_pDCRenderTarget](#m_pdcrendertarget)|Pointeur vers un objet ID2D1DCRenderTarget.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="a-nameattacha--cdcrendertargetattach"></a><a name="attach"></a>CDCRenderTarget::Attach  
 Interface de cible à l’objet de rendu attache existant  
  
```  
void Attach(ID2D1DCRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `pTarget`  
 Interface de cible de rendu existante. Ne peut pas être NULL  
  
##  <a name="a-namebinddca--cdcrendertargetbinddc"></a><a name="binddc"></a>CDCRenderTarget::BindDC  
 Lie la cible de rendu pour le contexte de périphérique auquel il envoie des commandes de dessin  
  
```  
BOOL BindDC(
    const CDC& dc,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Paramètres  
 `dc`  
 Le contexte de périphérique pour lequel la cible de rendu émet des commandes de dessin  
  
 `rect`  
 Les dimensions du handle à un contexte de périphérique (HDC) auquel est liée la cible de rendu  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne TRUE. Sinon, elle retourne FALSE.  
  
##  <a name="a-namecdcrendertargeta--cdcrendertargetcdcrendertarget"></a><a name="cdcrendertarget"></a>CDCRenderTarget::CDCRenderTarget  
 Construit un objet CDCRenderTarget.  
  
```  
CDCRenderTarget();
```  
  
##  <a name="a-namecreatea--cdcrendertargetcreate"></a><a name="create"></a>CDCRenderTarget::Create  
 Crée CDCRenderTarget.  
  
```  
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```  
  
### <a name="parameters"></a>Paramètres  
 `props`  
 Le mode de rendu, format de pixel, options de communication à distance, informations DPI et support DirectX minimum requis pour le rendu matériel.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne TRUE. Sinon, elle retourne FALSE.  
  
##  <a name="a-namedetacha--cdcrendertargetdetach"></a><a name="detach"></a>CDCRenderTarget::Detach  
 Détache l’interface de cible de rendu de l’objet  
  
```  
ID2D1DCRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Interface de cible de rendu de pointeur à détacher.  
  
##  <a name="a-namegetdcrendertargeta--cdcrendertargetgetdcrendertarget"></a><a name="getdcrendertarget"></a>CDCRenderTarget::GetDCRenderTarget  
 Renvoie l’interface ID2D1DCRenderTarget  
  
```  
ID2D1DCRenderTarget* GetDCRenderTarget();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1DCRenderTarget ou NULL si l’objet n’est pas encore initialisé.  
  
##  <a name="a-namempdcrendertargeta--cdcrendertargetmpdcrendertarget"></a><a name="m_pdcrendertarget"></a>CDCRenderTarget::m_pDCRenderTarget  
 Pointeur vers un objet ID2D1DCRenderTarget.  
  
```  
ID2D1DCRenderTarget* m_pDCRenderTarget;  
```  
  
##  <a name="a-nameoperatorid2d1dcrendertargetstara--cdcrendertargetoperator-id2d1dcrendertarget"></a><a name="operator_id2d1dcrendertarget_star"></a>CDCRenderTarget::operator ID2D1DCRenderTarget *  
 Renvoie l’interface ID2D1DCRenderTarget  
  
```  
operator ID2D1DCRenderTarget*();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1DCRenderTarget ou NULL si l’objet n’est pas encore initialisé.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

