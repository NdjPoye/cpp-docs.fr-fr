---
title: CSimpleDialog (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a4c17a1da8d1be00ebff171af09bc6c8eb81ed44
ms.lasthandoff: 02/24/2017

---
# <a name="csimpledialog-class"></a>CSimpleDialog (classe)
Cette classe implémente une boîte de dialogue modale base.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>  
class CSimpleDialog : public CDialogImplBase
```  
  
#### <a name="parameters"></a>Paramètres  
 *t_wDlgTemplateID*  
  
 L’ID de ressource de la ressource de modèle de boîte de dialogue.  
  
 *t_bCenter*  
 **TRUE** si l’objet de la boîte de dialogue est centrée sur la fenêtre propriétaire ; sinon **FALSE**.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](#domodal)|Crée une boîte de dialogue modale.|  
  
## <a name="remarks"></a>Remarques  
 Implémente une boîte de dialogue modale avec la fonctionnalité de base. `CSimpleDialog`prend en charge uniquement des contrôles communs Windows. Pour créer et afficher une boîte de dialogue modale, créez une instance de cette classe, en fournissant le nom d’un modèle de ressource de la boîte de dialogue. L’objet de boîte de dialogue se ferme lorsque l’utilisateur clique sur un contrôle avec une valeur prédéfinie (par exemple, IDOK ou IDCANCEL).  
  
 `CSimpleDialog`vous permet de créer uniquement des boîtes de dialogue modales. `CSimpleDialog`Fournit la procédure de boîte de dialogue, qui utilise la table des messages par défaut pour diriger les messages vers les gestionnaires appropriés.  
  
 Consultez la page [l’implémentation d’une boîte de dialogue](../../atl/implementing-a-dialog-box.md) pour plus d’informations.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
  
##  <a name="domodal"></a>CSimpleDialog::DoModal  
 Appelle une boîte de dialogue modale et retourne le résultat de la boîte de dialogue lorsque vous avez terminé.  
  
```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Paramètres  
 `hWndParent`  
 Handle vers le parent de la boîte de dialogue. Si aucune valeur n’est fournie, le parent est défini à la fenêtre active.  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’opération réussit, la valeur de retour est l’ID de ressource du contrôle qui a fermé la boîte de dialogue.  
  
 Si la fonction échoue, la valeur de retour est -1. Pour obtenir des informations plus complètes sur les erreurs, appelez `GetLastError`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode gère l’interaction avec l’utilisateur pendant que la boîte de dialogue est active. C’est ce qui rend la boîte de dialogue modale ; Autrement dit, l’utilisateur ne peut pas interagir avec d’autres fenêtres jusqu'à ce que la boîte de dialogue est fermée.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

