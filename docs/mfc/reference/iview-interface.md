---
title: Interface IView | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IView
- No header/IView
- No header/IView::OnActivateView
- No header/IView::OnInitialUpdate
- No header/IView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class
- views, classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: 23
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
ms.openlocfilehash: 9a8b5f2d9d123aa3032cb30ecdbdd1cd380b32f8
ms.lasthandoff: 02/24/2017

---
# <a name="iview-interface"></a>Interface IView
Implémente plusieurs méthodes qui [CWinFormsView](../../mfc/reference/cwinformsview-class.md) utilise pour envoyer des notifications d’affichage pour un contrôle géré.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
interface class IView  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[IView::OnActivateView](#onactivateview)|Appelée par MFC lorsqu’une vue est activée ou désactivée.|  
|[IView::OnInitialUpdate](#oninitialupdate)|Appelée par l’infrastructure une fois que la vue est d’abord attachée au document, mais avant l’affichage initial.|  
|[IView::OnUpdate](#onupdate)|Appelée par MFC après que le document de la vue a été modifié ; Cette fonction permet l’affichage pour mettre à jour son affichage afin de refléter les modifications.|  
  
## <a name="remarks"></a>Notes  
 `IView`implémente plusieurs méthodes qui `CWinFormsView` utilise pour transmettre des notifications d’affichage pour un contrôle géré hébergé communes. Il s’agit des [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) et [OnActivateView](#onactivateview).  
  
 `IView`est semblable à [CView](../../mfc/reference/cview-class.md), mais est utilisé uniquement avec les vues gérés et des contrôles.  
  
 Pour plus d’informations sur l’utilisation de Windows Forms, consultez [à l’aide d’un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  

## <a name="requirements"></a>Spécifications  
 En-tête : les afxwinforms.h (défini dans l’assembly atlmfc\lib\mfcmifc80.dll)  

## <a name="onactivateview"></a>IView::OnActivateView  
Appelée par MFC lorsqu’une vue est activée ou désactivée.
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>Paramètres
`activate`  
Indique si la vue est activée ou désactivée.  

## <a name="oninitialupdate"></a>IView::OnInitialUpdate
Appelée par l’infrastructure une fois que la vue est d’abord attachée au document, mais avant l’affichage initial.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a>IView::OnUpdate 
Appelé par MFC lorsque document de la vue a été modifié.  
```
void OnUpdate();
```
## <a name="remarks"></a>Remarques  
Cette fonction permet l’affichage pour mettre à jour son affichage afin de refléter les modifications.

## <a name="see-also"></a>Voir aussi  
 [Classe CWinFormsView](../../mfc/reference/cwinformsview-class.md)   
 [CView (classe)](../../mfc/reference/cview-class.md)

