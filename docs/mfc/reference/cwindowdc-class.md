---
title: Classe de CWindowDC | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWindowDC
- No header/CWindowDC
- No header/CWindowDC::CWindowDC
- No header/CWindowDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- device contexts, window
- screen output classes
- CWindowDC class
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
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
ms.openlocfilehash: 8a941e1b6f8a398706498ec5d1ce1bfc9156f115
ms.lasthandoff: 02/24/2017

---
# <a name="cwindowdc-class"></a>CWindowDC (classe)
Dérivée de `CDC`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CWindowDC : public CDC  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWindowDC::CWindowDC](#cwindowdc)|Construit un objet `CWindowDC`.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CWindowDC::m_hWnd](#m_hwnd)|Le `HWND` à laquelle cet `CWindowDC` est attaché.|  
  
## <a name="remarks"></a>Remarques  
 Appelle la fonction Windows [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)au moment de la construction et [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx) au moment de la destruction. Cela signifie qu’un `CWindowDC` objet accède à la zone de l’écran d’un [CWnd](../../mfc/reference/cwnd-class.md) (les zones clientes et).  
  
 Pour plus d’informations sur l’utilisation de `CWindowDC`, consultez [contextes de périphérique](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAPTURE DE DONNÉES MODIFIÉES](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>Spécifications  
 En-tête : afxwin.h  
  
##  <a name="cwindowdc"></a>CWindowDC::CWindowDC  
 Construit un `CWindowDC` objet qui accède à la zone de l’écran (le client et non) de la `CWnd` objet pointé par `pWnd`.  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 La fenêtre dont l’objet de contexte de périphérique accéderont à la zone cliente.  
  
### <a name="remarks"></a>Notes  
 Le constructeur appelle la fonction Windows [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947).  
  
 Une exception (de type `CResourceException`) est levée si les fenêtres `GetWindowDC` appel échoue. Un contexte de périphérique n’est peut-être pas disponible si Windows a déjà alloué tous ses contextes de périphérique disponible. Votre application est en concurrence pour les contextes d’affichage courants cinq disponibles à un moment donné sous Windows.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#188;](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CWindowDC::m_hWnd  
 Le `HWND` de la `CWnd` pointeur est utilisé pour construire le `CWindowDC` objet.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Remarques  
 `m_hWnd`est une variable de type protégée `HWND`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CWindowDC::CWindowDC](#cwindowdc).  
  
## <a name="see-also"></a>Voir aussi  
 [CDC (classe)](../../mfc/reference/cdc-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CDC (classe)](../../mfc/reference/cdc-class.md)

