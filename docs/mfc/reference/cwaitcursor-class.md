---
title: Classe de CWaitCursor | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
dev_langs:
- C++
helpviewer_keywords:
- cursors, wait cursor
- CWaitCursor class
- wait cursors
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
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
ms.openlocfilehash: f72598c356add5d891b013f1fd7b87665c5a6c63
ms.lasthandoff: 02/24/2017

---
# <a name="cwaitcursor-class"></a>CWaitCursor (classe)
Permet en une ligne d'afficher un curseur d'attente, généralement sous forme de sablier, pendant que vous effectuez une longue opération.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CWaitCursor  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWaitCursor::CWaitCursor](#cwaitcursor)|Construit un `CWaitCursor` de l’objet et affiche le curseur d’attente.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWaitCursor::Restore](#restore)|Restaure le curseur d’attente après que qu’il a été modifié.|  
  
## <a name="remarks"></a>Remarques  
 `CWaitCursor`n’a pas d’une classe de base.  
  
 Windows de bonnes pratiques de programmation nécessitent que vous afficher un curseur d’attente chaque fois que vous effectuez une opération qui prend beaucoup de temps.  
  
 Pour afficher un curseur d’attente, définissez simplement un `CWaitCursor` variable avant le code qui effectue l’opération longue. Constructeur de l’objet entraîne automatiquement le curseur d’attente s’affiche.  
  
 Lorsque l’objet est hors de portée (à la fin du bloc dans lequel la `CWaitCursor` d’un objet), son destructeur définit le curseur jusqu’au curseur précédente. En d’autres termes, l’objet effectue automatiquement le nettoyage nécessaire.  
  
> [!NOTE]
>  En raison de leurs constructeurs et destructeurs de fonctionnement, `CWaitCursor` objets sont toujours déclarés en tant que variables locales, elles ne sont jamais déclarées comme des variables globales ni allouées avec **nouveau**.  
  
 Si vous effectuez une opération qui peut provoquer le curseur à modifier, tel que l’affichage d’une boîte de message ou la boîte de dialogue, l’appel de la [restauration](#restore) fonction membre pour restaurer le curseur d’attente. Il s’agit d’appeler OK **restauration** même lorsqu’un curseur d’attente est affiché.  
  
 Une autre façon d’afficher un curseur d’attente consiste à utiliser la combinaison de [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)et peut-être [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). Cependant, `CWaitCursor` est plus facile à utiliser, car vous n’avez pas besoin de définir le curseur jusqu’au curseur précédente lorsque vous avez terminé avec l’opération longue.  
  
> [!NOTE]
>  MFC définit et restaure le curseur à l’aide de la [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) fonction virtuelle. Vous pouvez remplacer cette fonction pour fournir un comportement personnalisé.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CWaitCursor`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
## <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#62;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]  
  
##  <a name="cwaitcursor"></a>CWaitCursor::CWaitCursor  
 Pour afficher un curseur d’attente, déclarez un `CWaitCursor` objet avant le code qui effectue l’opération longue.  
  
```  
CWaitCursor();
```  
  
### <a name="remarks"></a>Remarques  
 Le constructeur entraîne automatiquement le curseur d’attente s’affiche.  
  
 Lorsque l’objet est hors de portée (à la fin du bloc dans lequel la `CWaitCursor` d’un objet), son destructeur définit le curseur jusqu’au curseur précédente. En d’autres termes, l’objet effectue automatiquement le nettoyage nécessaire.  
  
 Vous pouvez tirer parti du fait que le destructeur est appelé à la fin du bloc (qui peut être avant la fin de la fonction) pour activer le curseur d’attente qu’une partie de votre fonction. Cette technique est illustrée dans le deuxième exemple ci-dessous.  
  
> [!NOTE]
>  En raison de leurs constructeurs et destructeurs de fonctionnement, `CWaitCursor` objets sont toujours déclarés en tant que variables locales, elles ne sont jamais déclarées comme des variables globales, ni allouées avec **nouveau**.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#63;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]  
  
##  <a name="restore"></a>CWaitCursor::Restore  
 Pour restaurer le curseur d’attente, appelez cette fonction après une opération, tel que l’affichage d’une boîte de message ou de la boîte de dialogue, ce qui peut modifier le curseur d’attente à un autre curseur.  
  
```  
void Restore();
```  
  
### <a name="remarks"></a>Remarques  
 Il s’agit de OK à appeler **restauration** même lorsque le curseur d’attente est affiché.  
  
 Si vous devez restaurer le curseur d’attente dans une fonction autre que celui dans lequel le `CWaitCursor` objet est déclaré, vous pouvez appeler [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCWindowing&#64;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)   
 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)   
 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)   
 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)   
 [Comment faire : modifier le curseur de souris dans une Application Microsoft Foundation](http://go.microsoft.com/fwlink/linkid=128044)




