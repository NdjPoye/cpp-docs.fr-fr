---
title: Classe de CMultiPageDHtmlDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
dev_langs:
- C++
helpviewer_keywords:
- CMultiPageDHtmlDialog class
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c00af20731b2c47a0074366722da3f4a0711ef85
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmultipagedhtmldialog-class"></a>CMultiPageDHtmlDialog (classe)
Une boîte de dialogue multipage affiche plusieurs pages HTML de manière séquentielle et gère les événements de chaque page.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Construit un objet de boîte de dialogue multipage (de type Assistant) DHTML.|  
|[CMultiPageDHtmlDialog :: ~ CMultiPageDHtmlDialog](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|Détruit un objet de boîte de dialogue multipage DHTML.|  
  
## <a name="remarks"></a>Remarques  
 Le mécanisme de cette opération est un [table d’événements DHTML et l’URL](http://msdn.microsoft.com/en-us/2a7332f0-79d7-46e4-b816-0a618c46777a), qui contient [incorporé des tables d’événements](http://msdn.microsoft.com/library/5346210f-f8b7-4e28-9d2c-d9d7fd42421d) pour chaque page.  
  
## <a name="example"></a>Exemple  
 Cette boîte de dialogue multipage part du principe que les trois ressources HTML qui définissent les fonctionnalités de type Assistant simple. La première page a un `Next` bouton, le second un **Prev** et `Next` bouton et la troisième un **Prev** bouton. Lorsqu’un des boutons est activé, une fonction gestionnaire appelle [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) pour charger la nouvelle page appropriée.  
  
 Les parties pertinentes de la déclaration de classe (dans CMyMultiPageDlg.h) :  
  
 [!code-cpp[NVC_MFCDocView&#181;](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]  
  
 Les parties pertinentes de l’implémentation de classe (dans CMyMultipageDlg.cpp) :  
  
 [!code-cpp[NVC_MFCDocView&#182;](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdhtml.h  
  
##  <a name="cmultipagedhtmldialog"></a>CMultiPageDHtmlDialog::CMultiPageDHtmlDialog  
 Construit un objet de boîte de dialogue multipage (de type Assistant) DHTML.  
  
```  
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,  
    LPCTSTR szHtmlResID = NULL,  
    CWnd* pParentWnd = NULL);

 
CMultiPageDHtmlDialog(
    UINT nIDTemplate,  
    UINT nHtmlResID = 0,  
    CWnd* pParentWnd = NULL);  
  
CMultiPageDHtmlDialog();
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszTemplateName`  
 Chaîne terminée par le caractère null qui correspond au nom d’une ressource modèle de boîte de dialogue.  
  
 `szHtmlResID`  
 Chaîne terminée par le caractère null qui correspond au nom d’une ressource HTML.  
  
 `pParentWnd`  
 Un pointeur vers l’objet de fenêtre parente ou propriétaire (de type [CWnd](../../mfc/reference/cwnd-class.md)) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la boîte de dialogue fenêtre l’objet parent est définie dans la fenêtre principale de l’application.  
  
 `nIDTemplate`  
 Contient le numéro d’ID d’une ressource modèle de boîte de dialogue.  
  
 `nHtmlResID`  
 Contient le numéro d’ID d’une ressource HTML.  
  
##  <a name="_dtorcmultipagedhtmldialog"></a>CMultiPageDHtmlDialog :: ~ CMultiPageDHtmlDialog  
 Détruit un objet de boîte de dialogue multipage DHTML.  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>Voir aussi  
 [Classe CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)

