---
title: "Les Macros d’assistance DDX_DHtml | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- AFXDHTML/DDX_DHtml_ElementValue
- AFXDHTML/DDX_DHtml_ElementInnerText
- AFXDHTML/DDX_DHtml_ElementInnerHtml
- AFXDHTML/DDX_DHtml_Anchor_Href
- AFXDHTML/DDX_DHtml_Anchor_Target
- AFXDHTML/DDX_DHtml_Img_Src
- AFXDHTML/DDX_DHtml_Frame_Src
- AFXDHTML/DDX_DHtml_IFrame_Src
dev_langs:
- C++
helpviewer_keywords:
- macros, exchanging data with HMTL pages
- DDX macros
- HTML pages, helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros, DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
caps.latest.revision: 14
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
ms.openlocfilehash: d3c5136b52206a1ec67e1e1fc78ec291a2954faf
ms.lasthandoff: 02/24/2017

---
# <a name="ddxdhtml-helper-macros"></a>Macros d’assistance DDX_DHtml
Les macros d’assistance DDX_DHtml permettent un accès facile aux propriétés courantes des contrôles sur une page HTML.  
  
### <a name="data-exchange-macros"></a>Macros de données Exchange  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Définit ou récupère la propriété Value du contrôle sélectionné.|  
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Définit ou récupère le texte entre les balises de début et de fin de l’élément actuel.|  
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Définit ou récupère le code HTML entre les balises de début et de fin de l’élément actuel.|  
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Définit ou récupère la destination URL ou point d’ancrage.|  
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Définit ou récupère la fenêtre ou frame cible.|  
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Définit ou récupère le nom d’une image ou un clip vidéo dans le document.|  
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|Définit ou extrait l’URL de l’image associée.|  
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|Définit ou extrait l’URL de l’image associée.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdhtml.h  

## <a name="ddx_dhtml_anchor_href"></a>DDX_DHtml_Anchor_Href
Définit ou récupère la destination URL ou point d’ancrage.  
  
  
  
```  
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dx`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `name`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 `var`  
 La valeur qui est échangée.  
  
## <a name="remarks"></a>Remarques  
 Cette macro appelle la [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) ID de dispatch de fonction à l’aide de la DISPID_IHTMLANCHORELEMENT_HREF

## <a name="ddx_dhtml_anchor_target"></a>DDX_DHtml_Anchor_Target
 Définit ou récupère la fenêtre ou frame cible.  
    
```  
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dx`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `name`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 `var`  
 La valeur qui est échangée.  
  
## <a name="remarks"></a>Notes  
 Cette macro appelle la [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) ID de dispatch de fonction à l’aide de la DISPID_IHTMLANCHORELEMENT_TARGET  

## <a name="ddx_dhtml_elementinnerhtml"></a>DDX_DHtml_ElementInnerHtml
 Définit ou récupère le code HTML entre les balises de début et de fin de l’élément actuel.  
  
  
  
```  
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dx`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `name`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 `var`  
 La valeur qui est échangée.  
  
## <a name="remarks"></a>Remarques  
 Cette macro appelle la [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) ID de dispatch de fonction à l’aide de la DISPID_IHTMLELEMENT_INNERHTML  
  

## <a name="ddx_dhtml_elementinnertext"></a>DDX_DHtml_ElementInnerText
Définit ou récupère le texte entre les balises de début et de fin de l’élément actuel.  
  
  
  
```  
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dx`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `name`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 `var`  
 La valeur qui est échangée.  
  
## <a name="remarks"></a>Remarques  
 Cette macro appelle la [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) ID de dispatch de fonction à l’aide de la DISPID_IHTMLELEMENT_INNERTEXT 

## <a name="ddx_dhtml_elementvalue"></a>DDX_DHtml_ElementValue  
Définit ou récupère la propriété Value du contrôle sélectionné.  
 
```  
DDX_DHtml_ElementValue(
    CDataExchange* dx,  
    LPCTSTR name,
    var)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dx`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `name`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 `var`  
 La valeur qui est échangée. Consultez la page *valeur* dans [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).  
  
## <a name="remarks"></a>Remarques  
 Cette macro réussira uniquement lors de l’exécuter sur des contrôles qui ont une valeur de propriété. Les contrôles qui ont une valeur de propriété comprennent des zones d’édition, les zones de liste et les zones de liste déroulante.  
  
 Cette macro appelle la [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) ID de dispatch de fonction à l’aide de la DISPID_A_VALUE  

## <a name="ddx_dhtml_frame_src"></a>DDX_DHtml_Frame_Src
Définit ou extrait l’URL de l’image associée.  
  
```  
DDX_DHtml_Frame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dx`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `name`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 `var`  
 La valeur qui est échangée.  
  
## <a name="remarks"></a>Remarques  
 Cette macro appelle la [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) ID de dispatch de fonction à l’aide de la DISPID_IHTMLFRAMEBASE_SRC  

## <a name="ddx_dhtml_iframe_src"></a>DDX_DHtml_IFrame_Src
Définit ou extrait l’URL de l’image associée.  
  
  
  
```  
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dx`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `name`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 `var`  
 La valeur qui est échangée.  
  
## <a name="remarks"></a>Notes  
 Cette macro appelle la [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) ID de dispatch de fonction à l’aide de la DISPID_IHTMLFRAMEBASE_SRC 

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src
Obtient ou récupère le nom d’une image ou un clip vidéo dans le document.  
  
```  
DDX_DHtml_Img_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dx`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet.  
  
 `name`  
 La valeur que vous avez spécifié pour le paramètre d’ID du contrôle HTML.  
  
 `var`  
 La valeur qui est échangée.  
  
## <a name="remarks"></a>Notes  
 Lorsque vous utilisez la `DDX_DHtml_Img_Src` macro pour récupérer la propriété src d’un élément d’IMAGE, l’objet d’image Internet Explorer renvoie l’URL entièrement avec séquence d’échappement pour la source de l’image. Par exemple, si vous utilisez la `DDX_DHtml_Img_Src` macro pour définir la propriété src de l’élément d’IMAGE à la chaîne « certains image intéressante », lorsque vous récupérez cette propriété, Internet Explorer retourne la chaîne « res://d:\myapplication\myapp.exe/some%20interesting%20picture ».  
  
 Cette macro appelle la [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) ID de dispatch de fonction à l’aide de la DISPID_IHTMLIMGELEMENT_SRC  

  
## <a name="see-also"></a>Voir aussi  
 [Classe CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)

