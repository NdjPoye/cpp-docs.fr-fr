---
title: CPalette (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPalette
- HPALETTE
dev_langs:
- C++
helpviewer_keywords:
- CPalette class
- HPALETTE
- color palettes, MFC
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6ccd389eaf765993c59311cc1041893f2cf9fbfa
ms.lasthandoff: 02/24/2017

---
# <a name="cpalette-class"></a>CPalette (classe)
Encapsule une palette de couleurs Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CPalette : public CGdiObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPalette::CPalette](#cpalette)|Construit un `CPalette` objet avec aucune palette Windows attaché. Vous devez initialiser le `CPalette` objet avec l’une des fonctions membres d’initialisation avant de pouvoir être utilisé.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CPalette::AnimatePalette](#animatepalette)|Remplace les entrées dans la palette logique identifié par le `CPalette` objet. L’application n’a pas mettre à jour sa zone cliente, car Windows mappe les nouvelles entrées dans la palette système immédiatement.|  
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|Crée une palette de demi-teintes pour le contexte de périphérique et l’attache à le `CPalette` objet.|  
|[CPalette::CreatePalette](#createpalette)|Crée une palette de couleurs Windows et l’attache à le `CPalette` objet.|  
|[CPalette::FromHandle](#fromhandle)|Retourne un pointeur vers un `CPalette` de l’objet en fonction d’un handle d’un objet de palette Windows.|  
|[CPalette::GetEntryCount](#getentrycount)|Récupère le nombre d’entrées dans une palette logique de la palette.|  
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|Retourne l’index de l’entrée de la palette logique qui correspond le mieux à une valeur de couleur.|  
|[CPalette::GetPaletteEntries](#getpaletteentries)|Récupère une plage d’entrées de palette dans une palette logique.|  
|[CPalette::ResizePalette](#resizepalette)|Modifie la taille de la palette logique spécifiée par la `CPalette` objet pour le nombre d’entrées spécifié.|  
|[CPalette::SetPaletteEntries](#setpaletteentries)|Définit les indicateurs et les valeurs de couleur dans une plage d’entrées dans une palette logique.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPalette::operator HPALETTE](#operator_hpalette)|Retourne le `HPALETTE` attaché à la `CPalette`.|  
  
## <a name="remarks"></a>Remarques  
 Une palette fournit une interface entre une application et un périphérique de sortie de couleur (par exemple, un périphérique d’affichage). L’interface permet à l’application tirer pleinement parti des fonctionnalités du périphérique de sortie couleur sans gravement interférer avec les couleurs affichées par d’autres applications. Windows utilise une palette logique de l’application (une liste de couleurs si nécessaires) et la palette système (qui définit les couleurs disponibles) pour déterminer les couleurs utilisées.  
  
 Un `CPalette` objet propose des fonctions membres pour manipuler la palette concernée par l’objet. Construire un `CPalette` de l’objet et utiliser ses fonctions membres pour créer la palette réelle, un objet graphics device interface (GDI) et de manipuler ses entrées et autres propriétés.  
  
 Pour plus d’informations sur l’utilisation de `CPalette`, consultez [objets graphiques](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="a-nameanimatepalettea--cpaletteanimatepalette"></a><a name="animatepalette"></a>CPalette::AnimatePalette  
 Remplace les entrées dans la palette logique attaché à la `CPalette` objet.  
  
```  
void AnimatePalette(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>Paramètres  
 `nStartIndex`  
 Spécifie la première entrée dans la palette s’anime.  
  
 `nNumEntries`  
 Spécifie le nombre d’entrées dans la palette s’anime.  
  
 `lpPaletteColors`  
 Pointe vers le premier membre d’un tableau de [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) structures pour remplacer les entrées de palette identifiées par `nStartIndex` et `nNumEntries`.  
  
### <a name="remarks"></a>Notes  
 Lorsqu’une application appelle `AnimatePalette`, il n’a pas mettre à jour sa zone cliente, car Windows mappe les nouvelles entrées dans la palette système immédiatement.  
  
 Le `AnimatePalette` fonction passera uniquement les entrées avec le **PC_RESERVED** l’indicateur est défini dans le **palPaletteEntry** membre de la [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) structure qui est attaché à la `CPalette` objet. Consultez la page **LOGPALETTE** dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur cette structure.  
  
##  <a name="a-namecpalettea--cpalettecpalette"></a><a name="cpalette"></a>CPalette::CPalette  
 Construit un objet `CPalette`.  
  
```  
CPalette();
```  
  
### <a name="remarks"></a>Notes  
 L’objet n’a aucune palette attaché jusqu'à ce que vous appeliez `CreatePalette` pour attacher un.  
  
##  <a name="a-namecreatehalftonepalettea--cpalettecreatehalftonepalette"></a><a name="createhalftonepalette"></a>CPalette::CreateHalftonePalette  
 Crée une palette de demi-teintes pour le contexte de périphérique.  
  
```  
BOOL CreateHalftonePalette(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Identifie le contexte de périphérique.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Une application doit créer une palette de demi-teintes quand le mode d’étirement d’un contexte de périphérique a la valeur **demi-teintes**. La palette logique de demi-teintes retournée par la [CreateHalftonePalette](http://msdn.microsoft.com/library/windows/desktop/dd183503) fonction membre doit être sélectionnée et réalisée dans le contexte de périphérique avant du [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) ou [StretchDIBits](http://msdn.microsoft.com/library/windows/desktop/dd145121) fonction est appelée.  
  
 Consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur `CreateHalftonePalette` et **StretchDIBits**.  
  
##  <a name="a-namecreatepalettea--cpalettecreatepalette"></a><a name="createpalette"></a>CPalette::CreatePalette  
 Initialise un `CPalette` objet en créant une palette de couleurs logique de Windows et en attachant à la `CPalette` objet.  
  
```  
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpLogPalette`  
 Pointe vers une [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) structure qui contient des informations sur les couleurs de la palette logique.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur la **LOGPALETTE** structure.  
  
##  <a name="a-namefromhandlea--cpalettefromhandle"></a><a name="fromhandle"></a>CPalette::FromHandle  
 Retourne un pointeur vers un `CPalette` de l’objet en fonction d’un handle d’un objet de palette Windows.  
  
```  
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```  
  
### <a name="parameters"></a>Paramètres  
 `hPalette`  
 Handle vers une palette de couleurs Windows GDI.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CPalette` objet en cas de réussite ; sinon **NULL**.  
  
### <a name="remarks"></a>Notes  
 Si un `CPalette` objet n’est pas déjà attaché à la palette de Windows, un objet temporaire `CPalette` objet est créé et attaché. Ce fichier temporaire `CPalette` objet est valide uniquement jusqu'à la prochaine fois que l’application dispose de temps d’inactivité dans sa boucle d’événements, alors graphique temporaire de tous les objets sont supprimés. En d’autres termes, l’objet temporaire est valide uniquement pendant le traitement du message de fenêtre.  
  
##  <a name="a-namegetentrycounta--cpalettegetentrycount"></a><a name="getentrycount"></a>CPalette::GetEntryCount  
 Appelez cette fonction membre pour récupérer le nombre d’entrées dans une palette logique donnée.  
  
```  
int GetEntryCount();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d’entrées dans une palette logique.  
  
##  <a name="a-namegetnearestpaletteindexa--cpalettegetnearestpaletteindex"></a><a name="getnearestpaletteindex"></a>CPalette::GetNearestPaletteIndex  
 Retourne l’index de l’entrée de la palette logique qui correspond le mieux à la valeur de la couleur spécifiée.  
  
```  
UINT GetNearestPaletteIndex(COLORREF crColor) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `crColor`  
 Spécifie la couleur à mettre en correspondance.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index d’une entrée dans une palette logique. L’entrée contient la couleur presque correspondant à la couleur spécifiée.  
  
##  <a name="a-namegetpaletteentriesa--cpalettegetpaletteentries"></a><a name="getpaletteentries"></a>CPalette::GetPaletteEntries  
 Récupère une plage d’entrées de palette dans une palette logique.  
  
```  
UINT GetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nStartIndex`  
 Spécifie la première entrée de la palette logique doit être récupéré.  
  
 `nNumEntries`  
 Spécifie le nombre d’entrées dans la palette logique doit être récupéré.  
  
 `lpPaletteColors`  
 Pointe vers un tableau de [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) des structures de données pour recevoir les entrées de palette. Le tableau doit contenir au moins autant de structures de données comme spécifié par `nNumEntries`.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’entrées récupérées à partir de la palette logique. 0 si la fonction a échoué.  
  
##  <a name="a-nameoperatorhpalettea--cpaletteoperator-hpalette"></a><a name="operator_hpalette"></a>CPalette::operator HPALETTE  
 Utilisez cet opérateur pour obtenir le handle Windows GDI attaché de le `CPalette` objet.  
  
```  
operator HPALETTE() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si réussie, un handle vers l’objet Windows GDI représenté par le `CPalette` objet ; sinon **NULL**.  
  
### <a name="remarks"></a>Notes  
 Cet opérateur est un opérateur de cast, qui prend en charge l’utilisation directe d’une `HPALETTE` objet.  
  
 Pour plus d’informations sur l’utilisation des objets graphiques, consultez l’article [graphique objets](http://msdn.microsoft.com/library/windows/desktop/dd144962) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameresizepalettea--cpaletteresizepalette"></a><a name="resizepalette"></a>CPalette::ResizePalette  
 Modifie la taille de la palette logique attachée à la `CPalette` objet pour le nombre d’entrées spécifié par `nNumEntries`.  
  
```  
BOOL ResizePalette(UINT nNumEntries);
```  
  
### <a name="parameters"></a>Paramètres  
 `nNumEntries`  
 Spécifie le nombre d’entrées dans la palette après que qu’il a été redimensionné.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la palette est redimensionnée avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Si une application appelle `ResizePalette` pour réduire la taille de la palette, les entrées restantes dans la palette de redimensionnement sont identiques. Si l’application appelle `ResizePalette` pour agrandir la palette, les entrées de palette supplémentaires sont définies sur noir (les valeurs rouges, verts et bleus sont tous des 0) et les indicateurs pour toutes les entrées supplémentaires sont définies sur 0.  
  
 Pour plus d’informations sur l’API Windows `ResizePalette`, consultez [ResizePalette](http://msdn.microsoft.com/library/windows/desktop/dd162928) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetpaletteentriesa--cpalettesetpaletteentries"></a><a name="setpaletteentries"></a>CPalette::SetPaletteEntries  
 Définit les indicateurs et les valeurs de couleur dans une plage d’entrées dans une palette logique.  
  
```  
UINT SetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>Paramètres  
 `nStartIndex`  
 Spécifie la première entrée de la palette logique à définir.  
  
 `nNumEntries`  
 Spécifie le nombre d’entrées dans la palette logique à définir.  
  
 `lpPaletteColors`  
 Pointe vers un tableau de [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) des structures de données pour recevoir les entrées de palette. Le tableau doit contenir au moins autant de structures de données comme spécifié par `nNumEntries`.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’entrées dans la palette logique ; 0 si la fonction a échoué.  
  
### <a name="remarks"></a>Remarques  
 Si la palette logique est sélectionnée dans un contexte de périphérique lorsque l’application appelle `SetPaletteEntries`, les modifications ne prendront pas effet tant que l’application appelle [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette).  
  
 Pour plus d’informations sur la structure Windows **PALETTEENTRY**, consultez [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC DIBLOOK](../../visual-cpp-samples.md)   
 [CGdiObject (classe)](../../mfc/reference/cgdiobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](#getpaletteentries)   
 [CPalette::SetPaletteEntries](#setpaletteentries)




