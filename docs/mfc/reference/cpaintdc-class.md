---
title: CPaintDC (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- OnPaint handler
- WM_PAINT message
- CPaintDC class
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
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
ms.openlocfilehash: b781db7d4a6676e6fc6ad5df7553b9c9a0154ab9
ms.lasthandoff: 02/24/2017

---
# <a name="cpaintdc-class"></a>CPaintDC (classe)
Une classe de contexte de périphérique dérivée de [CDC](../../mfc/reference/cdc-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CPaintDC : public CDC  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPaintDC::CPaintDC](#cpaintdc)|Construit un `CPaintDC` connecté spécifié [CWnd](../../mfc/reference/cwnd-class.md).|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPaintDC::m_ps](#m_ps)|Contient le [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) utilisé pour peindre la zone cliente.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CPaintDC::m_hWnd](#m_hwnd)|Le `HWND` auquel ce `CPaintDC` objet est attaché.|  
  
## <a name="remarks"></a>Remarques  
 Il effectue une [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) au moment de la construction et [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) au moment de la destruction.  
  
 A `CPaintDC` objet seulement peut être utilisé que lors de la réponse à une [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) d’un message, généralement dans votre `OnPaint` fonction membre de gestionnaire de messages.  
  
 Pour plus d’informations sur l’utilisation de `CPaintDC`, consultez [contextes de périphérique](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAPTURE DE DONNÉES MODIFIÉES](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="cpaintdc"></a>CPaintDC::CPaintDC  
 Construit un `CPaintDC` objet prépare la fenêtre d’application pour la peinture et stocke le [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) de la structure dans le [m_ps](#m_ps) variable membre.  
  
```  
explicit CPaintDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Pointe vers le `CWnd` objet auquel le `CPaintDC` objet appartient.  
  
### <a name="remarks"></a>Remarques  
 Une exception (de type `CResourceException`) est levée si les fenêtres [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) appel échoue. Un contexte de périphérique n’est peut-être pas disponible si Windows a déjà alloué tous ses contextes de périphérique disponible. Votre application est en concurrence pour les contextes d’affichage courants cinq disponibles à un moment donné sous Windows.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#97;](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CPaintDC::m_hWnd  
 Le `HWND` auquel ce `CPaintDC` objet est attaché.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Notes  
 `m_hWnd`est une variable de type protégée `HWND`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#98;](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]  
  
##  <a name="m_ps"></a>CPaintDC::m_ps  
 `m_ps`est une variable de membre public du type [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md).  
  
```  
PAINTSTRUCT m_ps;  
```  
  
### <a name="remarks"></a>Remarques  
 Il s’agit du `PAINTSTRUCT` qui est passé à et rempli par [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint).  
  
 Le `PAINTSTRUCT` contient des informations que l’application utilise pour peindre la zone cliente de la fenêtre associée à un `CPaintDC` objet.  
  
 Notez que vous pouvez accéder le handle de contexte de périphérique via le `PAINTSTRUCT`. Toutefois, vous pouvez accéder à la poignée plus directement via la `m_hDC` variable membre qui `CPaintDC` hérite de `CDC`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CPaintDC::m_hWnd](#m_hwnd).  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC MDI](../../visual-cpp-samples.md)   
 [CDC (classe)](../../mfc/reference/cdc-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




