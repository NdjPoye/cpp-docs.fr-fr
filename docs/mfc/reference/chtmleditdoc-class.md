---
title: Classe de CHtmlEditDoc | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditDoc class
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
caps.latest.revision: 24
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
ms.openlocfilehash: 1d9651c5009fd8f4c742c6b9bf08e32bd67c7d30
ms.lasthandoff: 02/24/2017

---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc (classe)
Avec [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), fournit les fonctionnalités de la plateforme d’édition WebBrowser dans le contexte de l’architecture document / vue MFC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|Construit un objet `CHtmlEditDoc`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CHtmlEditDoc::GetView](#getview)|Récupère le `CHtmlEditView` objet attaché à ce document.|  
|[CHtmlEditDoc::IsModified](#ismodified)|Indique si le contrôle WebBrowser de la vue associée contient un document qui a été modifié par l’utilisateur.|  
|[CHtmlEditDoc::OpenURL](#openurl)|Ouvre une URL.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `CHtmlEditDoc`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxhtml.h  
  
##  <a name="chtmleditdoc"></a>CHtmlEditDoc::CHtmlEditDoc  
 Construit un **CHtmlEditDoc** objet.  
  
```  
CHtmlEditDoc();
```  
  
##  <a name="getview"></a>CHtmlEditDoc::GetView  
 Récupère le [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) objet attaché à ce document.  
  
```  
virtual CHtmlEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le document **CHtmlEditView** objet.  
  
##  <a name="ismodified"></a>CHtmlEditDoc::IsModified  
 Indique si le contrôle WebBrowser de la vue associée contient un document qui a été modifié par l’utilisateur.  
  
```  
virtual BOOL IsModified();
```  
  
##  <a name="openurl"></a>CHtmlEditDoc::OpenURL  
 Ouvre une URL.  
  
```  
virtual BOOL OpenURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszURL`  
 L’URL à ouvrir.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **TRUE** en cas de réussite, **FALSE** en cas d’échec.  
  
## <a name="see-also"></a>Voir aussi  
 [HTMLEdit, exemple](../../visual-cpp-samples.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)


