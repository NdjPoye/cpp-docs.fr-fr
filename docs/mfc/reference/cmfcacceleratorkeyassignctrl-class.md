---
title: Classe de CMFCAcceleratorKeyAssignCtrl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::GetAccel
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsFocused
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::ResetKey
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl class
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
caps.latest.revision: 33
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
ms.openlocfilehash: 23687cf4c13881293d10a5f816a2c825180df49c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl, classe
Le `CMFCAcceleratorKeyAssignCtrl` classe étend la [classe CEdit](../../mfc/reference/cedit-class.md) pour prendre en charge des boutons système supplémentaires tels que ALT, CONTROL et SHIFT.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCAcceleratorKeyAssignCtrl : public CEdit  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](#cmfcacceleratorkeyassignctrl)|Construit un objet `CMFCAcceleratorKeyAssignCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel)|Récupère la structure `ACCEL` pour une touche de raccourci enfoncée dans l'objet `CMFCAcceleratorKeyAssignCtrl`.|  
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](#isfocused)||  
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|Détermine si une touche de raccourci a été définie.|  
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|Utilisé par la classe [CWinApp](../../mfc/reference/cwinapp-class.md) pour convertir des messages de fenêtre avant qu’ils soient distribués à le [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) fonctions de Windows. (Substitue [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|Réinitialise la touche de raccourci.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe étend les fonctionnalités de la classe `CEdit` en prenant en charge les touches de raccourci, aussi appelées touches accélérateur. Le `CMFCAcceleratorKeyAssignCtrl` classe fonctionne comme un [classe CEdit](../../mfc/reference/cedit-class.md) et il peut également reconnaître des boutons système.  
  
 Cette classe mappe les combinaisons de touches de raccourci physiques à des valeurs de chaîne. Par exemple, supposons que la combinaison de touches Alt+B est mappé à la chaîne « Alt+B ». Quand l'utilisateur appuie sur cette combinaison de touches dans un objet `CMFCAcceleratorKeyAssignCtrl`, « Alt+B » est présenté à l'utilisateur. Pour plus d’informations sur le mappage entre les touches de raccourci et un format de chaîne, consultez la page [CMFCAcceleratorKey classe](../../mfc/reference/cmfcacceleratorkey-class.md).  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment construire un objet `CMFCAcceleratorKeyAssignCtrl` et utiliser sa méthode `ResetKey` pour réinitialiser la touche de raccourci.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#31;](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CMFCAcceleratorKeyAssignCtrl`   
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxacceleratorkeyassignctrl.h  
  
##  <a name="cmfcacceleratorkeyassignctrl"></a>CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl  
 Construit un [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) objet.  
  
```  
CMFCAcceleratorKeyAssignCtrl();
```  
  
##  <a name="getaccel"></a>CMFCAcceleratorKeyAssignCtrl::GetAccel  
 Récupère le `ACCEL` de la structure d’une touche de raccourci enfoncée dans le [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) objet.  
  
```  
ACCEL const* GetAccel() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `ACCEL` structure qui décrit la touche de raccourci.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction permet de récupérer le `ACCEL` structure d’une touche de raccourci entré par l’utilisateur dans votre `CMFCAcceleratorKeyAssignCtrl` objet.  
  
##  <a name="isfocused"></a>CMFCAcceleratorKeyAssignCtrl::IsFocused  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsFocused() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="iskeydefined"></a>CMFCAcceleratorKeyAssignCtrl::IsKeyDefined  
 Détermine si une touche de raccourci a été définie dans le [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) objet.  
  
```  
BOOL IsKeyDefined() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’utilisateur a déjà activé une combinaison valide de clés qui définissent une touche de raccourci ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction pour déterminer si l’utilisateur a entré une touche de raccourci valide dans votre `CMFCAcceleratorKeyAssignCtrl` objet. Si une touche de raccourci existe, vous pouvez utiliser [CMFCAcceleratorKeyAssignCtrl::GetAccel](#getaccel) méthode pour obtenir le `ACCEL` structure associée à cette touche de raccourci.  
  
##  <a name="pretranslatemessage"></a>CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pMsg`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="resetkey"></a>CMFCAcceleratorKeyAssignCtrl::ResetKey  
 Réinitialise la touche de raccourci.  
  
```  
void ResetKey();
```  
  
### <a name="remarks"></a>Remarques  
 La fonction efface le texte du contrôle edit. Cela inclut les raccourcis clavier que l’utilisateur a appuyé.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCAcceleratorKey (classe)](../../mfc/reference/cmfcacceleratorkey-class.md)

