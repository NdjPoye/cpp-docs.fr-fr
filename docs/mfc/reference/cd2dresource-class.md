---
title: Classe de CD2DResource | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DResource
- CD2DResource
dev_langs:
- C++
helpviewer_keywords:
- CD2DResource class
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
caps.latest.revision: 18
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
ms.openlocfilehash: b5a357a3653e2126de85b21efddca881c6c43a09
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dresource-class"></a>CD2DResource, classe
Une classe abstraite qui fournit une interface pour créer et gérer des ressources D2D telles que des pinceaux, des couches et des textes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DResource : public CObject;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DResource::CD2DResource](#cd2dresource)|Construit un objet CD2DResource.|  
|[CD2DResource :: ~ CD2DResource](#cd2dresource__~cd2dresource)|Destructeur. Appelé lorsqu’un objet de ressource D2D est détruit.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DResource::Create](#create)|Crée un CD2DResource.|  
|[CD2DResource::Destroy](#destroy)|Détruit un objet CD2DResource.|  
|[CD2DResource::IsValid](#isvalid)|Vérifications de validité des ressources|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DResource::IsAutoDestroy](#isautodestroy)|Indicateur de destruction automatique de vérification.|  
|[CD2DResource::ReCreate](#recreate)|Crée de nouveau un CD2DResource.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DResource::m_bIsAutoDestroy](#m_bisautodestroy)|Ressource sera détruite par le propriétaire (CRenderTarget)|  
|[CD2DResource::m_pParentTarget](#m_pparenttarget)|Pointeur vers le parent CRenderTarget)|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CD2DResource`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dresourcea--cd2dresourcecd2dresource"></a><a name="_dtorcd2dresource"></a>CD2DResource :: ~ CD2DResource  
 Destructeur. Appelé lorsqu’un objet de ressource D2D est détruit.  
  
```  
virtual ~CD2DResource();
```  
  
##  <a name="a-namecd2dresourcea--cd2dresourcecd2dresource"></a><a name="cd2dresource"></a>CD2DResource::CD2DResource  
 Construit un objet CD2DResource.  
  
```  
CD2DResource(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentTarget`  
 Pointeur vers la cible de rendu.  
  
 `bAutoDestroy`  
 Indique que l’objet sera détruit par le propriétaire (pParentTarget).  
  
##  <a name="a-namecreatea--cd2dresourcecreate"></a><a name="create"></a>CD2DResource::Create  
 Crée un CD2DResource.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pRenderTarget`  
 Pointeur vers la cible de rendu.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne S_OK. Sinon, elle retourne un code d’erreur HRESULT.  
  
##  <a name="a-namedestroya--cd2dresourcedestroy"></a><a name="destroy"></a>CD2DResource::Destroy  
 Détruit un objet CD2DResource.  
  
```  
virtual void Destroy() = 0;  
```  
  
##  <a name="a-nameisautodestroya--cd2dresourceisautodestroy"></a><a name="isautodestroy"></a>CD2DResource::IsAutoDestroy  
 Indicateur de destruction automatique de vérification.  
  
```  
BOOL IsAutoDestroy() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si l’objet sera détruit par son propriétaire ; Sinon, FALSE.  
  
##  <a name="a-nameisvalida--cd2dresourceisvalid"></a><a name="isvalid"></a>CD2DResource::IsValid  
 Vérifications de validité des ressources  
  
```  
virtual BOOL IsValid() const = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la ressource est valide ; Sinon, FALSE.  
  
##  <a name="a-namembisautodestroya--cd2dresourcembisautodestroy"></a><a name="m_bisautodestroy"></a>CD2DResource::m_bIsAutoDestroy  
 Ressource sera détruite par le propriétaire (CRenderTarget)  
  
```  
BOOL m_bIsAutoDestroy;  
```  
  
##  <a name="a-namempparenttargeta--cd2dresourcempparenttarget"></a><a name="m_pparenttarget"></a>CD2DResource::m_pParentTarget  
 Pointeur vers le parent CRenderTarget)  
  
```  
CRenderTarget* m_pParentTarget;  
```  
  
##  <a name="a-namerecreatea--cd2dresourcerecreate"></a><a name="recreate"></a>CD2DResource::ReCreate  
 Crée de nouveau un CD2DResource.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `pRenderTarget`  
 Pointeur vers la cible de rendu.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne S_OK. Sinon, elle retourne un code d’erreur HRESULT.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

