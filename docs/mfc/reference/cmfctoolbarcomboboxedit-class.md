---
title: Classe de CMFCToolBarComboBoxEdit | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCComboEdit
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarComboBoxEdit class
- CMFCToolBarComboBoxEdit::PreTranslateMessage method
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
caps.latest.revision: 25
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
ms.openlocfilehash: 3c0f2ade3292fb238a227e881951604606baec79
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarcomboboxedit-class"></a>CMFCToolBarComboBoxEdit (classe)
L’infrastructure utilise la `CMFCToolBarComboBoxEdit` classe pour créer un bouton de barre d’outils qui se comporte comme un contrôle de zone de liste déroulante modifiable.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCToolBarComboBoxEdit : public CEdit  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit](#cmfctoolbarcomboboxedit)|Construit un objet `CMFCToolBarComboBoxEdit`.|  
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|Convertit les messages de fenêtre avant qu’ils soient distribués à le [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) fonctions de Windows. (Substitue [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
  
### <a name="remarks"></a>Remarques  
 Dérivez une classe de la `CMFCToolBarComboBoxEdit` classe pour personnaliser ses opérations de modification.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtoolbarcomboboxbutton.h  
  
##  <a name="a-namecmfctoolbarcomboboxedita--cmfctoolbarcomboboxeditcmfctoolbarcomboboxedit"></a><a name="cmfctoolbarcomboboxedit"></a>CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit  
 Construit un objet `CMFCToolBarComboBoxEdit`.  
  
```  
CMFCToolBarComboBoxEdit(CMFCToolBarComboBoxButton& combo);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `combo`  
 Une référence à un [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) objet, qui est un bouton de barre d’outils qui contient un contrôle de zone de liste déroulante.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un objet de la `CMFCToolBarComboBoxEdit` classe. Cet extrait de code fait partie de la [exemple de démonstration d’IE](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo n °&5;](../../mfc/reference/codesnippet/cpp/cmfctoolbarcomboboxedit-class_1.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarComboBoxButton (classe)](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

