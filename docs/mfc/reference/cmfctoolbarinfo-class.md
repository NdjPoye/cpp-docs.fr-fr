---
title: Classe de CMFCToolBarInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarInfo class
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
caps.latest.revision: 22
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
ms.openlocfilehash: a9e66ffa0b5a751a7e5711ed20927a6adcede45d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarinfo-class"></a>CMFCToolBarInfo (classe)
Contient les ID de ressources des images de barre d'outils dans différents états. `CMFCToolBarInfo`est une classe d’assistance qui est utilisée en tant que paramètre de la [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) (méthode).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCToolBarInfo  
```  
  
## <a name="members"></a>Membres  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|ID de ressource de la bitmap de la barre d’outils qui contient des images de barre d’outils (à froid) standard.|  
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|ID de ressource de la bitmap de la barre d’outils qui contient des images de barre d’outils désactivés.|  
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|ID de ressource de la bitmap de la barre d’outils qui contient des images de barre d’outils (à chaud) sélectionné.|  
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|ID de ressource de la bitmap de la barre d’outils qui contient des images de grande barre d’outils standard.|  
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|ID de ressource de la bitmap de la barre d’outils qui contient un grand, désactivé les images de barre d’outils.|  
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|ID de ressource de la bitmap de la barre d’outils qui contient des images de grande barre d’outils sélectionné.|  
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|ID de ressource de la bitmap de la barre d’outils qui contient des images de menu désactivé.|  
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|ID de ressource de la bitmap de la barre d’outils qui contient des images de menu.|  
  
## <a name="remarks"></a>Notes  
 Une image bitmap de barre d’outils complète se compose d’images de petite barre d’outils (boutons) de taille fixe. Chaque ID de ressource qui est stocké dans un `CMFCToolBarInfo` objet est une image bitmap qui contient un ensemble d’images de barre d’outils dans un état unique (par exemple, sélectionné, désactivé, grand ou images de menu).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtoolbar.h  
  
##  <a name="m_uicoldresid"></a>CMFCToolBarInfo::m_uiColdResID  
 Spécifie un ID de ressource pour toutes les images de bouton standard d’une barre d’outils.  
  
```  
UINT m_uiColdResID;  
```  
  
##  <a name="m_uidisabledresid"></a>CMFCToolBarInfo::m_uiDisabledResID  
 Spécifie un ID de ressource pour les images non disponible de bouton de barre d’outils.  
  
```  
UINT m_uiDisabledResID;  
```  
  
##  <a name="m_uihotresid"></a>CMFCToolBarInfo::m_uiHotResID  
 Spécifie un ID de ressource pour toutes les images de bouton en surbrillance d’une barre d’outils.  
  
```  
UINT m_uiHotResID  
```  
  
##  <a name="m_uilargecoldresid"></a>CMFCToolBarInfo::m_uiLargeColdResID  
 Spécifie un ID de ressource pour toutes les images de grand bouton normal d’une barre d’outils.  
  
```  
UINT m_uiLargeColdResID  
```  
  
##  <a name="m_uilargedisabledresid"></a>CMFCToolBarInfo::m_uiLargeDisabledResID  
 Spécifie un ID de ressource pour toutes les images de grand bouton désactivé des barres d’outils.  
  
```  
UINT m_uiLargeDisabledResID;  
```  
  
##  <a name="m_uilargehotresid"></a>CMFCToolBarInfo::m_uiLargeHotResID  
 Spécifie un ID de ressource pour toutes les images volumineux en surbrillance d’une barre d’outils.  
  
```  
UINT m_uiLargeHotResID;  
```  
  
##  <a name="m_uimenudisabledresid"></a>CMFCToolBarInfo::m_uiMenuDisabledResID  
 Spécifie un ID de ressource pour les images non disponible de commande d’une barre d’outils.  
  
```  
UINT m_uiMenuDisabledResID;  
```  
  
##  <a name="m_uimenuresid"></a>CMFCToolBarInfo::m_uiMenuResID  
 Spécifie un ID de ressource pour toutes les images d’élément de menu classique d’une barre d’outils.  
  
```  
UINT m_uiMenuResID;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar (classe)](../../mfc/reference/cmfctoolbar-class.md)
