---
title: Classe de CD2DPathGeometry | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::Attach
- AFXRENDERTARGET/CD2DPathGeometry::Create
- AFXRENDERTARGET/CD2DPathGeometry::Destroy
- AFXRENDERTARGET/CD2DPathGeometry::Detach
- AFXRENDERTARGET/CD2DPathGeometry::GetFigureCount
- AFXRENDERTARGET/CD2DPathGeometry::GetSegmentCount
- AFXRENDERTARGET/CD2DPathGeometry::Open
- AFXRENDERTARGET/CD2DPathGeometry::Stream
- AFXRENDERTARGET/CD2DPathGeometry::m_pPathGeometry
dev_langs:
- C++
helpviewer_keywords:
- CD2DPathGeometry class
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
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
ms.openlocfilehash: 1c1158e55bf12d44f34896dd6752c9b8706db636
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dpathgeometry-class"></a>CD2DPathGeometry, classe
Wrapper pour ID2D1PathGeometry.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DPathGeometry : public CD2DGeometry;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DPathGeometry::CD2DPathGeometry](#cd2dpathgeometry)|Construit un objet CD2DPathGeometry.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DPathGeometry::Attach](#attach)|Attache existant à l’objet interface de la ressource|  
|[CD2DPathGeometry::Create](#create)|Crée un CD2DPathGeometry. (Substitue [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DPathGeometry::Destroy](#destroy)|Détruit un objet CD2DPathGeometry. (Substitue [CD2DGeometry::Destroy](../../mfc/reference/cd2dgeometry-class.md#destroy).)|  
|[CD2DPathGeometry::Detach](#detach)|Détache l’interface de la ressource à partir de l’objet|  
|[CD2DPathGeometry::GetFigureCount](#getfigurecount)|Récupère le nombre de chiffres dans la géométrie de tracé.|  
|[CD2DPathGeometry::GetSegmentCount](#getsegmentcount)|Récupère le nombre de segments dans la géométrie de tracé.|  
|[CD2DPathGeometry::Open](#open)|Récupère le récepteur de la géométrie qui est utilisé pour remplir la géométrie de tracé avec les figures et les segments.|  
|[CD2DPathGeometry::Stream](#stream)|Copie le contenu de la géométrie de tracé vers le ID2D1GeometrySink spécifié.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DPathGeometry::m_pPathGeometry](#m_ppathgeometry)|Pointeur vers un ID2D1PathGeometry.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)  
  
 `CD2DPathGeometry`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="attach"></a>CD2DPathGeometry::Attach  
 Attache existant à l’objet interface de la ressource  
  
```  
void Attach(ID2D1PathGeometry* pResource);
```  
  
### <a name="parameters"></a>Paramètres  
 `pResource`  
 Interface de la ressource existante. Ne peut pas être NULL  
  
##  <a name="cd2dpathgeometry"></a>CD2DPathGeometry::CD2DPathGeometry  
 Construit un objet CD2DPathGeometry.  
  
```  
CD2DPathGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentTarget`  
 Pointeur vers la cible de rendu.  
  
 `bAutoDestroy`  
 Indique que l’objet sera détruit par le propriétaire (pParentTarget).  
  
##  <a name="create"></a>CD2DPathGeometry::Create  
 Crée un CD2DPathGeometry.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `pRenderTarget`  
 Pointeur vers la cible de rendu.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne S_OK. Sinon, elle retourne un code d’erreur HRESULT.  
  
##  <a name="destroy"></a>CD2DPathGeometry::Destroy  
 Détruit un objet CD2DPathGeometry.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DPathGeometry::Detach  
 Détache l’interface de la ressource à partir de l’objet  
  
```  
ID2D1PathGeometry* Detach();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’interface de la ressource détachée.  
  
##  <a name="getfigurecount"></a>CD2DPathGeometry::GetFigureCount  
 Récupère le nombre de chiffres dans la géométrie de tracé.  
  
```  
int GetFigureCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de chiffres dans la géométrie de tracé.  
  
##  <a name="getsegmentcount"></a>CD2DPathGeometry::GetSegmentCount  
 Récupère le nombre de segments dans la géométrie de tracé.  
  
```  
int GetSegmentCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de segments dans la géométrie de tracé.  
  
##  <a name="m_ppathgeometry"></a>CD2DPathGeometry::m_pPathGeometry  
 Pointeur vers un ID2D1PathGeometry.  
  
```  
ID2D1PathGeometry* m_pPathGeometry;  
```  
  
##  <a name="open"></a>CD2DPathGeometry::Open  
 Récupère le récepteur de la géométrie qui est utilisé pour remplir la géométrie de tracé avec les figures et les segments.  
  
```  
ID2D1GeometrySink* Open();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le ID2D1GeometrySink qui est utilisé pour remplir la géométrie de tracé avec les figures et les segments.  
  
##  <a name="stream"></a>CD2DPathGeometry::Stream  
 Copie le contenu de la géométrie de tracé vers le ID2D1GeometrySink spécifié.  
  
```  
BOOL Stream(ID2D1GeometrySink* geometrySink);
```  
  
### <a name="parameters"></a>Paramètres  
 `geometrySink`  
 Le récepteur dans lequel le contenu de la géométrie de tracé est copiés. Modification de ce récepteur ne modifie pas le contenu de cette géométrie de tracé.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne TRUE. Sinon, elle retourne FALSE.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

