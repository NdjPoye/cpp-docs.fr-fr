---
title: Classe de CMFCToolBarInfo | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCToolBarInfo [MFC], m_uiColdResID
- CMFCToolBarInfo [MFC], m_uiDisabledResID
- CMFCToolBarInfo [MFC], m_uiHotResID
- CMFCToolBarInfo [MFC], m_uiLargeColdResID
- CMFCToolBarInfo [MFC], m_uiLargeDisabledResID
- CMFCToolBarInfo [MFC], m_uiLargeHotResID
- CMFCToolBarInfo [MFC], m_uiMenuDisabledResID
- CMFCToolBarInfo [MFC], m_uiMenuResID
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de968fe53348b4cfa3f46e999da37cdca6f88c90
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfctoolbarinfo-class"></a>Classe de CMFCToolBarInfo
Contient les ID de ressources des images de barre d'outils dans différents états. `CMFCToolBarInfo` est une classe d’assistance qui est utilisée en tant que paramètre de la [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) (méthode).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCToolBarInfo  
```  
  
## <a name="members"></a>Membres  
  
### <a name="data-members"></a>Membres de données  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|ID de ressource de la bitmap de barre d’outils qui contient des images d’une barre d’outils (froid) standard.|  
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|ID de ressource de la bitmap de barre d’outils qui contient des images de barre d’outils désactivées.|  
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|ID de ressource de la bitmap de barre d’outils qui contient des images de barre d’outils (à chaud) sélectionnée.|  
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|ID de ressource de la bitmap de barre d’outils qui contient des images de grande barre d’outils standard.|  
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|ID de ressource de la bitmap de barre d’outils qui contient un grand, désactivé les images de barre d’outils.|  
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|ID de ressource de la bitmap de barre d’outils qui contient des images de barre d’outils de grande taille, sélectionné.|  
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|ID de ressource de la bitmap de barre d’outils qui contient les images de menu désactivées.|  
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|ID de ressource de la bitmap de barre d’outils qui contient les images de menu.|  
  
## <a name="remarks"></a>Notes  
 Une image bitmap de barre d’outils complète se compose d’images de petite barre d’outils (boutons) de taille fixe. Chaque ID de ressource qui est stocké dans un `CMFCToolBarInfo` objet est une image bitmap qui contient un ensemble complet d’images de barre d’outils dans un état unique (par exemple, sélectionné désactivé, grande ou des images de menu).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtoolbar.h  
  
##  <a name="m_uicoldresid"></a>  CMFCToolBarInfo::m_uiColdResID  
 Spécifie un ID de ressource pour toutes les images de bouton normal d’une barre d’outils.  
  
```  
UINT m_uiColdResID;  
```  
  
##  <a name="m_uidisabledresid"></a>  CMFCToolBarInfo::m_uiDisabledResID  
 Spécifie un ID de ressource pour les images non disponible de bouton de barre d’outils.  
  
```  
UINT m_uiDisabledResID;  
```  
  
##  <a name="m_uihotresid"></a>  CMFCToolBarInfo::m_uiHotResID  
 Spécifie un ID de ressource pour toutes les images de bouton en surbrillance d’une barre d’outils.  
  
```  
UINT m_uiHotResID  
```  
  
##  <a name="m_uilargecoldresid"></a>  CMFCToolBarInfo::m_uiLargeColdResID  
 Spécifie un ID de ressource pour toutes les images de grand bouton normal d’une barre d’outils.  
  
```  
UINT m_uiLargeColdResID  
```  
  
##  <a name="m_uilargedisabledresid"></a>  CMFCToolBarInfo::m_uiLargeDisabledResID  
 Spécifie un ID de ressource pour toutes les images de grande taille bouton désactivé d’une barre d’outils.  
  
```  
UINT m_uiLargeDisabledResID;  
```  
  
##  <a name="m_uilargehotresid"></a>  CMFCToolBarInfo::m_uiLargeHotResID  
 Spécifie un ID de ressource pour toutes les images volumineux en surbrillance d’une barre d’outils.  
  
```  
UINT m_uiLargeHotResID;  
```  
  
##  <a name="m_uimenudisabledresid"></a>  CMFCToolBarInfo::m_uiMenuDisabledResID  
 Spécifie un ID de ressource pour les images non disponible de commande d’une barre d’outils.  
  
```  
UINT m_uiMenuDisabledResID;  
```  
  
##  <a name="m_uimenuresid"></a>  CMFCToolBarInfo::m_uiMenuResID  
 Spécifie un ID de ressource pour toutes les images d’élément de menu standard d’une barre d’outils.  
  
```  
UINT m_uiMenuResID;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar, classe](../../mfc/reference/cmfctoolbar-class.md)
