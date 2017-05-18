---
title: Classe de CGdiObject | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- brushes, base class for
- fonts, base class for
- regions, base class for
- pens, base class for
- palettes, base class for
- CGdiObject class
- GDI objects, base class for
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
caps.latest.revision: 21
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
ms.openlocfilehash: 7fb0cd49c6a20263a5cae305b7f08f2733033ff2
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cgdiobject-class"></a>CGdiObject (classe)
Fournit une classe de base pour différents genres d'objets GDI (Graphics Device Interface) Windows, par exemple des images bitmap, des zones, des pinceaux, des plumes, des palettes et des polices.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CGdiObject : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CGdiObject::CGdiObject](#cgdiobject)|Construit un objet `CGdiObject`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CGdiObject::Attach](#attach)|Attache un objet GDI Windows à un `CGdiObject` objet.|  
|[CGdiObject::CreateStockObject](#createstockobject)|Récupère un handle vers un des stylets stocks prédéfinies de Windows, des formes ou des polices.|  
|[CGdiObject::DeleteObject](#deleteobject)|Supprime l’objet GDI Windows associé à le `CGdiObject` l’objet de la mémoire à libérer tout le stockage système associé à l’objet.|  
|[CGdiObject::DeleteTempMap](#deletetempmap)|Supprime tout fichier temporaire `CGdiObject` les objets créés par `FromHandle`.|  
|[CGdiObject::Detach](#detach)|Détache un objet GDI de Windows à partir d’un `CGdiObject` de l’objet et retourne un handle vers l’objet Windows GDI.|  
|[CGdiObject::FromHandle](#fromhandle)|Retourne un pointeur vers un `CGdiObject` objet reçoit un descripteur vers un objet Windows GDI.|  
|[CGdiObject::GetObject](#getobject)|Remplit un tampon avec des données qui décrivent l’objet Windows GDI attaché à la `CGdiObject` objet.|  
|[CGdiObject::GetObjectType](#getobjecttype)|Récupère le type de l’objet GDI.|  
|[CGdiObject::GetSafeHandle](#getsafehandle)|Retourne `m_hObject` , sauf si `this` est `NULL`, auquel cas `NULL` est retourné.|  
|[CGdiObject::UnrealizeObject](#unrealizeobject)|Réinitialise l’origine d’un pinceau ou réinitialise une palette logique.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CGdiObject::operator ! =](#operator_neq)|Détermine si deux objets GDI sont logiquement pas égales.|  
|[CGdiObject::operator ==](#operator_eq_eq)|Détermine si deux objets GDI sont logiquement égales.|  
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|Récupère un `HANDLE` à l’objet Windows GDI attaché.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CGdiObject::m_hObject](#m_hobject)|A `HANDLE` contenant le `HBITMAP`, `HPALETTE`, `HRGN`, `HBRUSH`, `HPEN`, ou `HFONT` associé à cet objet.|  
  
## <a name="remarks"></a>Remarques  
 Vous ne créez jamais un `CGdiObject` directement. Au lieu de cela, vous créez un objet à partir d’une de ses classes dérivées, telles que `CPen` ou `CBrush`.  
  
 Pour plus d’informations sur `CGdiObject`, consultez [objets graphiques](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="attach"></a>CGdiObject::Attach  
 Attache un objet GDI Windows à un `CGdiObject` objet.  
  
```  
BOOL Attach(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `hObject`  
 A `HANDLE` à un objet GDI Windows (par exemple, `HPEN` ou `HBRUSH`).  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la pièce jointe a réussi ; sinon 0.  
  
##  <a name="cgdiobject"></a>CGdiObject::CGdiObject  
 Construit un objet `CGdiObject`.  
  
```  
CGdiObject();
```  
  
### <a name="remarks"></a>Notes  
 Vous ne créez jamais un `CGdiObject` directement. Au lieu de cela, vous créez un objet à partir d’une de ses classes dérivées, telles que `CPen` ou **Cbrush**.  
  
##  <a name="createstockobject"></a>CGdiObject::CreateStockObject  
 Récupère un handle à l’un de le prédéfinis stock Windows GDI stylets, pinceaux ou polices et attache un objet GDI pour le `CGdiObject` objet.  
  
```  
BOOL CreateStockObject(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Constante spécifiant le type d’objet de stock souhaité. Consultez le paramètre *fnObject* de [GetStockObject](http://msdn.microsoft.com/library/windows/desktop/dd144925) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour obtenir une description des valeurs appropriées.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Appel de cette fonction avec l’un des dérivés des classes qui correspond au type d’objet Windows GDI, telles que `CPen` d’un stylet.  
  
##  <a name="deleteobject"></a>CGdiObject::DeleteObject  
 Supprime l’objet de Windows GDI attaché à partir de la mémoire en libérant de tout le stockage système associé à l’objet Windows GDI.  
  
```  
BOOL DeleteObject();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’objet GDI a été supprimé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Le stockage associé à le `CGdiObject` objet n’est pas affecté par cet appel. Une application ne doit pas appeler `DeleteObject` sur une `CGdiObject` objet actuellement sélectionné dans un contexte de périphérique.  
  
 Lorsqu’un pinceau de modèle est supprimé, la bitmap associée au pinceau n’est pas supprimée. La bitmap doit être supprimée séparément.  
  
##  <a name="deletetempmap"></a>CGdiObject::DeleteTempMap  
 Appelée automatiquement par le `CWinApp` Gestionnaire de durée d’inactivité, `DeleteTempMap` supprime tout fichier temporaire `CGdiObject` les objets créés par `FromHandle`.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>Notes  
 `DeleteTempMap`Détache l’objet Windows GDI attaché à un objet temporaire `CGdiObject` objet avant de supprimer le `CGdiObject` objet.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#175;](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]  
  
##  <a name="detach"></a>CGdiObject::Detach  
 Détache un objet GDI de Windows à partir d’un `CGdiObject` de l’objet et retourne un handle vers l’objet Windows GDI.  
  
```  
HGDIOBJ Detach();
```  
  
### <a name="return-value"></a>Valeur de retour  
 A `HANDLE` à l’interface GDI Windows de l’objet détaché ; sinon **NULL** si aucun objet GDI n’est attaché.  
  
##  <a name="fromhandle"></a>CGdiObject::FromHandle  
 Retourne un pointeur vers un `CGdiObject` objet reçoit un descripteur vers un objet Windows GDI.  
  
```  
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `hObject`  
 Un `HANDLE` à un objet Windows GDI.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CGdiObject` qui peut être temporaire ou permanent.  
  
### <a name="remarks"></a>Notes  
 Si un `CGdiObject` objet n’est pas déjà attaché à l’objet Windows GDI, temporaire `CGdiObject` objet est créé et attaché.  
  
 Ce fichier temporaire `CGdiObject` objet est uniquement valide jusqu'à la prochaine fois que l’application a le temps d’inactivité dans sa boucle d’événement, date à laquelle tous les objets graphiques temporaires sont supprimés. Une autre façon de dire cela est que l’objet temporaire est uniquement valide pendant le traitement du message de fenêtre.  
  
##  <a name="getobject"></a>CGdiObject::GetObject  
 Remplit une mémoire tampon de données qui définit un objet spécifié.  
  
```  
int GetObject(
    int nCount,  
    LPVOID lpObject) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nCount`  
 Spécifie le nombre d’octets à copier dans le `lpObject` mémoire tampon.  
  
 `lpObject`  
 Pointe vers une mémoire tampon fournie par l’utilisateur qui doit recevoir les informations.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’octets récupérés ; Sinon, 0 si une erreur se produit.  
  
### <a name="remarks"></a>Remarques  
 La fonction récupère une structure de données dont le type varie selon le type d’objet graphique, comme indiqué par la liste suivante :  
  
|Objet|Type de tampon|  
|------------|-----------------|  
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|  
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|  
|`CFont`|[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)|  
|`CBitmap`|[IMAGE BITMAP](../../mfc/reference/bitmap-structure.md)|  
|`CPalette`|**WORD**|  
|`CRgn`|Non pris en charge|  
  
 Si l’objet est un `CBitmap` objet `GetObject` retourne uniquement la largeur, hauteur et des informations de format de couleur de l’image bitmap. Les bits réels peuvent être récupérées à l’aide de [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits).  
  
 Si l’objet est un `CPalette` objet, `GetObject` récupère un **WORD** qui spécifie le nombre d’entrées dans la palette. La fonction ne récupère pas les [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) structure qui définit la palette. Une application peut obtenir des informations sur les entrées de palette en appelant [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries).  
  
##  <a name="getobjecttype"></a>CGdiObject::GetObjectType  
 Récupère le type de l’objet GDI.  
  
```  
UINT GetObjectType() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le type de l’objet, en cas de réussite ; sinon 0. La valeur peut être une des opérations suivantes :  
  
- **OBJ_BITMAP** Bitmap  
  
- **OBJ_BRUSH** pinceau  
  
- **OBJ_FONT** police  
  
- **OBJ_PAL** Palette  
  
- **OBJ_PEN** stylet  
  
- **OBJ_EXTPEN** étendue stylet  
  
- **OBJ_REGION** région  
  
- **OBJ_DC** contexte de périphérique  
  
- **OBJ_MEMDC** contexte de périphérique de mémoire  
  
- **OBJ_METAFILE** métafichier  
  
- **OBJ_METADC** contexte de périphérique de métafichier  
  
- **OBJ_ENHMETAFILE** métafichier amélioré  
  
- **OBJ_ENHMETADC** contexte de périphérique de métafichier amélioré  
  
##  <a name="getsafehandle"></a>CGdiObject::GetSafeHandle  
 Retourne `m_hObject` , sauf si **cela** est **NULL**, auquel cas **NULL** est retourné.  
  
```  
HGDIOBJ GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A `HANDLE` à l’objet Windows GDI attaché ; sinon **NULL** si aucun objet n’est attaché.  
  
### <a name="remarks"></a>Remarques  
 Cela fait partie du paradigme interface handle général et est utile lorsque **NULL** est une valeur valide ou spéciale pour un handle.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled).  
  
##  <a name="m_hobject"></a>CGdiObject::m_hObject  
 A `HANDLE` contenant le `HBITMAP`, **HRGN**, `HBRUSH`, `HPEN`, `HPALETTE`, ou **HFONT** associé à cet objet.  
  
```  
HGDIOBJ m_hObject;  
```  
  
##  <a name="operator_neq"></a>CGdiObject::operator ! =  
 Détermine si deux objets GDI sont logiquement pas égales.  
  
```  
BOOL operator!=(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `obj`  
 Un pointeur vers un existant `CGdiObject`.  
  
### <a name="remarks"></a>Remarques  
 Détermine si un objet GDI sur le côté gauche n’est pas égal à un objet GDI sur le côté droit.  
  
##  <a name="operator_eq_eq"></a>CGdiObject::operator ==  
 Détermine si deux objets GDI sont logiquement égales.  
  
```  
BOOL operator==(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `obj`  
 Une référence à un fichier `CGdiObject`.  
  
### <a name="remarks"></a>Remarques  
 Détermine si un objet GDI sur le côté gauche est égal à un objet GDI sur le côté droit.  
  
##  <a name="operator_hgdiobj"></a>CGdiObject::operator HGDIOBJ  
 Récupère un `HANDLE` à l’objet Windows GDI attaché ; sinon **NULL** si aucun objet n’est attaché.  
  
```  
operator HGDIOBJ() const;  
```  
  
##  <a name="unrealizeobject"></a>CGdiObject::UnrealizeObject  
 Réinitialise l’origine d’un pinceau ou réinitialise une palette logique.  
  
```  
BOOL UnrealizeObject();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Bien que `UnrealizeObject` est une fonction membre de la `CGdiObject` (classe), elle doit être appelée uniquement sur `CBrush` ou `CPalette` objets.  
  
 Pour `CBrush` objets `UnrealizeObject` force le système à l’origine de la forme donnée de réinitialisation de la prochaine fois qu’il est sélectionné dans un contexte de périphérique. Si l’objet est un `CPalette` objet `UnrealizeObject` force le système à réaliser la palette comme s’il n’avait pas été précédemment réalisé. La prochaine fois que l’application appelle la [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) fonction de la palette spécifiée, le système remappe complètement la palette logique de la palette système.  
  
 Le `UnrealizeObject` fonction ne doit pas être utilisée avec les objets de stock. Le `UnrealizeObject` fonction doit être appelée chaque fois qu’un nouveau pinceau d’origine (au moyen de la [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) fonction). Le `UnrealizeObject` fonction ne doit pas être appelée pour la brosse actuellement sélectionnée ou palette actuellement sélectionné de n’importe quel contexte complet.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CBitmap (classe)](../../mfc/reference/cbitmap-class.md)   
 [CBrush (classe)](../../mfc/reference/cbrush-class.md)   
 [CFont (classe)](../../mfc/reference/cfont-class.md)   
 [CPalette (classe)](../../mfc/reference/cpalette-class.md)   
 [CPen (classe)](../../mfc/reference/cpen-class.md)   
 [CRgn (classe)](../../mfc/reference/crgn-class.md)

