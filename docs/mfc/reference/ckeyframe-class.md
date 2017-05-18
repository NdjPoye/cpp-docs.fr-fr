---
title: Classe CKeyFrame | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
dev_langs:
- C++
helpviewer_keywords:
- CKeyFrame class
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d8ecff2e36148fb114ee708712b6e8bd0fe558ed
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ckeyframe-class"></a>CKeyFrame, classe
Représente une image clé de l'animation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CKeyFrame::CKeyFrame](#ckeyframe)|Surchargé. Construit une image clé qui dépend d’autres images clés.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Ajoute une image clé à un storyboard. (Substitue [CBaseKeyFrame::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|  
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Ajoute une image clé au storyboard après la transition.|  
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Ajoute une image clé au storyboard à l’offset.|  
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Retourne un pointeur vers une image clé que dépend cette image clé.|  
|[CKeyFrame::GetOffset](#getoffset)|Retourne un offset à partir d’autres images clés.|  
|[CKeyFrame::GetTransition](#gettransition)|Retourne un pointeur à une transition dont dépend cette image clé.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CKeyFrame::m_offset](#m_offset)|Spécifie le décalage de l’image clé à partir d’une image clé stockée dans m_pExistingKeyFrame.|  
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Stocke un pointeur vers une image clé existante. Cette image clé est ajoutée au storyboard avec m_offset à l’image clé existante.|  
|[CKeyFrame::m_pTransition](#m_ptransition)|Stocke un pointeur vers la transition qui commence à cette image clé.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe implémente une image clé de l’animation. Une image clé représente un moment dans une table de montage séquentiel et peut servir à spécifier les heures de début et de fin des transitions. Une image clé peut être basée sur une autre image clé et avoir un décalage (en secondes) à partir de celui-ci, ou peut être basée sur une transition et représente un instant lorsque cette transition se termine.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>CKeyFrame::AddToStoryboard  
 Ajoute une image clé à un storyboard.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStoryboard`  
 Pointeur vers un storyboard.  
  
 `bDeepAdd`  
 Spécifie s’il faut ajouter des images clés ou de manière récursive la transition.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si l’image clé a été ajoutée avec succès.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode ajoute une image clé au storyboard. Si elle dépend d’autres images clés ou de transition et que bDeepAdd a la valeur TRUE, cette méthode tente d’ajouter de manière récursive.  
  
##  <a name="addtostoryboardaftertransition"></a>CKeyFrame::AddToStoryboardAfterTransition  
 Ajoute une image clé au storyboard après la transition.  
  
```  
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStoryboard`  
 Pointeur vers un storyboard.  
  
 `bDeepAdd`  
 Spécifie s’il faut ajouter une transition de manière récursive.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si l’image clé a été ajoutée avec succès.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est appelée par l’infrastructure pour ajouter une image clé au storyboard après la transition.  
  
##  <a name="addtostoryboardatoffset"></a>CKeyFrame::AddToStoryboardAtOffset  
 Ajoute une image clé au storyboard à l’offset.  
  
```  
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStoryboard`  
 Pointeur vers un storyboard.  
  
 `bDeepAdd`  
 Spécifie si cette image clé dépendante de façon récursive pour ajouter une image clé.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si l’image clé a été ajoutée avec succès.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est appelée par l’infrastructure pour ajouter une image clé au storyboard à l’offset.  
  
##  <a name="ckeyframe"></a>CKeyFrame::CKeyFrame  
 Construit une image clé qui dépend d’une transition.  
  
```  
CKeyFrame(CBaseTransition* pTransition);

 
CKeyFrame(
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>Paramètres  
 `pTransition`  
 Pointeur vers une transition.  
  
 `pKeyframe`  
 Pointeur vers une image clé.  
  
 `offset`  
 Offset, en secondes, à partir de l’image clé spécifiée par pKeyframe.  
  
### <a name="remarks"></a>Notes  
 Les images clés construites représentent un moment dans le temps dans un storyboard lors de la transition spécifiée prend fin.  
  
##  <a name="getexistingkeyframe"></a>CKeyFrame::GetExistingKeyframe  
 Retourne un pointeur vers une image clé que dépend cette image clé.  
  
```  
CBaseKeyFrame* GetExistingKeyframe();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur valide pour l’image clé, ou NULL si cette image clé ne dépend pas d’autres images clés.  
  
### <a name="remarks"></a>Remarques  
 Il s’agit d’un accesseur à une image clé que dépend cette image clé.  
  
##  <a name="getoffset"></a>CKeyFrame::GetOffset  
 Retourne un offset à partir d’autres images clés.  
  
```  
UI_ANIMATION_SECONDS GetOffset();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Offset en secondes à partir d’autres images clés.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode doit être appelée pour déterminer un offset en secondes à partir d’autres images clés.  
  
##  <a name="gettransition"></a>CKeyFrame::GetTransition  
 Retourne un pointeur à une transition dont dépend cette image clé.  
  
```  
CBaseTransition* GetTransition();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur valide vers la transition, ou NULL si cette image clé ne dépend pas de transition.  
  
### <a name="remarks"></a>Notes  
 Il s’agit d’un accesseur à une transition dont dépend cette image clé.  
  
##  <a name="m_offset"></a>CKeyFrame::m_offset  
 Spécifie le décalage de l’image clé à partir d’une image clé stockée dans m_pExistingKeyFrame.  
  
```  
UI_ANIMATION_SECONDS m_offset;  
```  
  
##  <a name="m_pexistingkeyframe"></a>CKeyFrame::m_pExistingKeyFrame  
 Stocke un pointeur vers une image clé existante. Cette image clé est ajoutée au storyboard avec m_offset à l’image clé existante.  
  
```  
CBaseKeyFrame* m_pExistingKeyFrame;  
```  
  
##  <a name="m_ptransition"></a>CKeyFrame::m_pTransition  
 Stocke un pointeur vers la transition qui commence à cette image clé.  
  
```  
CBaseTransition* m_pTransition;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

