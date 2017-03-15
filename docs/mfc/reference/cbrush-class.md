---
title: CBrush (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBrush
dev_langs:
- C++
helpviewer_keywords:
- brushes, CBrush class
- CBrush class
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: efcbe2757de3a7e4621e2b20c88726ead111cf8c
ms.lasthandoff: 02/24/2017

---
# <a name="cbrush-class"></a>CBrush (classe)
Encapsule un pinceau GDI (Graphics Device Interface) Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CBrush : public CGdiObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CBrush::CBrush](#cbrush)|Construit un objet `CBrush`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CBrush::CreateBrushIndirect](#createbrushindirect)|Initialise un pinceau avec le style, la couleur et le modèle spécifié dans un [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) structure.|  
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|Initialise un pinceau avec un modèle spécifié par une image bitmap indépendante du périphérique (DIB).|  
|[CBrush::CreateHatchBrush](#createhatchbrush)|Initialise un pinceau avec le motif hachuré spécifié et la couleur.|  
|[CBrush::CreatePatternBrush](#createpatternbrush)|Initialise un pinceau avec un modèle spécifié par une image bitmap.|  
|[CBrush::CreateSolidBrush](#createsolidbrush)|Initialise un pinceau avec la couleur unie spécifiée.|  
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|Crée une forme qui est la couleur système par défaut.|  
|[CBrush::FromHandle](#fromhandle)|Retourne un pointeur vers un `CBrush` en fonction d’un handle Windows de l’objet `HBRUSH` objet.|  
|[CBrush::GetLogBrush](#getlogbrush)|Obtient un [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) structure.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CBrush::operator HBRUSH](#operator_hbrush)|Retourne le handle Windows associé à le `CBrush` objet.|  
  
## <a name="remarks"></a>Remarques  
 Pour utiliser un `CBrush` objet, construire un `CBrush` de l’objet et le passer à une `CDC` fonction membre qui nécessite un pinceau.  
  
 Pinceaux peuvent être plein, hachée, ou un motif.  
  
 Pour plus d’informations sur `CBrush`, consultez [objets graphiques](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="a-namecbrusha--cbrushcbrush"></a><a name="cbrush"></a>CBrush::CBrush  
 Construit un objet `CBrush`.  
  
```  
CBrush(); 
CBrush(COLORREF crColor); 
CBrush(int nIndex, COLORREF crColor); 
explicit CBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Paramètres  
 `crColor`  
 Spécifie la couleur de premier plan du pinceau comme une couleur RVB. Si le pinceau est hachée, ce paramètre spécifie la couleur des hachures.  
  
 `nIndex`  
 Spécifie le style de hachurage du pinceau. Il peut être l’une des valeurs suivantes :  
  
- `HS_BDIAGONAL`Hachage vers le bas (de gauche à droite) à 45 degrés  
  
- `HS_CROSS`Hachurage horizontal et vertical  
  
- `HS_DIAGCROSS`Hachage à 45 degrés  
  
- `HS_FDIAGONAL`Hachage vers le haut (de gauche à droite) à 45 degrés  
  
- `HS_HORIZONTAL`Hachage horizontal  
  
- `HS_VERTICAL`Hachage vertical  
  
 `pBitmap`  
 Pointe vers une `CBitmap` objet qui spécifie un bitmap avec lequel le pinceau peint.  
  
### <a name="remarks"></a>Remarques  
 `CBrush`a quatre surchargé constructeurs. Le constructeur sans arguments construit non initialisé `CBrush` objet doit être initialisé avant de pouvoir être utilisé.  
  
 Si vous utilisez le constructeur sans arguments, vous devez initialiser résultant `CBrush` avec l’objet [CreateSolidBrush](#createsolidbrush), [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), ou [CreateDIBPatternBrush](#createdibpatternbrush). Si vous utilisez un des constructeurs qui prend des arguments, puis plus aucune initialisation est nécessaire. Les constructeurs avec des arguments peuvent lever une exception si des erreurs surviennent, tandis que le constructeur sans arguments échoue jamais.  
  
 Le constructeur avec un seul [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) paramètre construit un pinceau uni avec la couleur spécifiée. Spécifie une valeur RVB de la couleur et peut être construite avec le `RGB` macro dans WINDOWS. H.  
  
 Le constructeur avec deux paramètres construit un pinceau à hachures. Le `nIndex` paramètre spécifie l’index d’un motif hachuré. Le `crColor` paramètre spécifie la couleur.  
  
 Le constructeur avec un `CBitmap` paramètre construit un pinceau à motif. Le paramètre identifie une image bitmap. La bitmap est censée ont été créés à l’aide de [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), ou [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap). La taille minimale pour une image bitmap à utiliser dans un motif de remplissage est 8 x 8 pixels.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView n °&21;](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]  
  
##  <a name="a-namecreatebrushindirecta--cbrushcreatebrushindirect"></a><a name="createbrushindirect"></a>CBrush::CreateBrushIndirect  
 Initialise un pinceau avec un style, la couleur et le modèle spécifié dans un [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) structure.  
  
```  
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpLogBrush*  
 Pointe vers une [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) structure qui contient des informations sur le pinceau.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Le pinceau peut ensuite être sélectionné comme le pinceau actuel pour n’importe quel contexte de périphérique.  
  
 Un pinceau créé à l’aide d’un bitmap monochrome (plan 1, 1 bit par pixel) est dessiné à l’aide de la couleur de texte et d’arrière-plan actuelle. Pixels représentés par un bit défini sur 0 seront dessinés avec la couleur de texte actuelle. Pixels représentés par un bit défini à 1 sont dessinés avec la couleur d’arrière-plan actuelle.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#22;](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]  
  
##  <a name="a-namecreatedibpatternbrusha--cbrushcreatedibpatternbrush"></a><a name="createdibpatternbrush"></a>CBrush::CreateDIBPatternBrush  
 Initialise un pinceau avec le modèle spécifié par une image bitmap indépendante du périphérique (DIB).  
  
```  
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,  
    UINT nUsage);

 
BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,  
    UINT nUsage);
```  
  
### <a name="parameters"></a>Paramètres  
 *hPackedDIB*  
 Identifie un objet mémoire globale contenant un bitmap d’indépendantes du périphérique (DIB) compressé.  
  
 *nUsage*  
 Spécifie si les **[] bmiColors** champs de la [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) structure de données (une partie de la « DIB comprimées ») contiennent explicite les valeurs RVB ou index dans la palette logique actuellement réalisée. Le paramètre doit être une des valeurs suivantes :  
  
- **DIB_PAL_COLORS** la table des couleurs se compose d’un tableau d’index 16 bits.  
  
- **DIB_RGB_COLORS** la table des couleurs contient des valeurs littérales.  
  
 *lpPackedDIB*  
 Pointe vers un DIB compressé consistant en un `BITMAPINFO` structure immédiatement suivie d’un tableau d’octets définissant les pixels de la bitmap.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Le pinceau peut par la suite être sélectionné pour n’importe quel contexte de périphérique qui prend en charge les opérations de trame.  
  
 Les deux versions diffèrent dans la façon dont vous gérez le DIB :  
  
-   Dans la première version, pour obtenir un handle du fichier DIB vous appelez Windows **GlobalAlloc** fonction à allouer un bloc de mémoire globale et remplissez la mémoire avec DIB compressé.  
  
-   Dans la deuxième version, il n’est pas nécessaire d’appeler **GlobalAlloc** pour allouer de la mémoire pour le fichier DIB compressé.  
  
 Un DIB compressé se compose d’un `BITMAPINFO` immédiatement suivi d’un tableau d’octets qui définit les pixels de la bitmap de structure de données. Bitmaps utilisés comme modèles de remplissage doit être de 8 x 8 pixels. Si la bitmap est supérieure, Windows crée un motif de remplissage à l’aide uniquement les bits correspondant aux 8 premières lignes et 8 colonnes de pixels dans le coin supérieur gauche de la bitmap.  
  
 Lorsqu’une application sélectionne une forme de motif de deux couleurs DIB dans un contexte de périphérique monochrome, Windows ignore les couleurs spécifiées dans le fichier DIB et affiche à la place le pinceau de modèle en utilisant les couleurs de texte et d’arrière-plan actuelles du contexte de périphérique. Pixels associés à la première couleur (au décalage 0 dans la table des couleurs DIB) du fichier DIB sont affichés à l’aide de la couleur du texte. Pixels associés à la deuxième couleur (au décalage 1 dans la table des couleurs) sont affichés à l’aide de la couleur d’arrière-plan.  
  
 Pour plus d’informations sur les fonctions suivantes de Windows, consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]:  
  
- [CreateDIBPatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183492) (cette fonction est fournie uniquement pour la compatibilité avec les applications écrites pour les versions de Windows antérieures à 3.0 ; utilisez la **CreateDIBPatternBrushPt** fonction.)  
  
- [CreateDIBPatternBrushPt](http://msdn.microsoft.com/library/windows/desktop/dd183493) (cette fonction doit être utilisée pour les applications Win32).  
  
- [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView n °&23;](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]  
  
##  <a name="a-namecreatehatchbrusha--cbrushcreatehatchbrush"></a><a name="createhatchbrush"></a>CBrush::CreateHatchBrush  
 Initialise un pinceau avec le motif hachuré spécifié et la couleur.  
  
```  
BOOL CreateHatchBrush(
    int nIndex,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Spécifie le style de hachurage du pinceau. Il peut être l’une des valeurs suivantes :  
  
- `HS_BDIAGONAL`Hachage vers le bas (de gauche à droite) à 45 degrés  
  
- `HS_CROSS`Hachurage horizontal et vertical  
  
- `HS_DIAGCROSS`Hachage à 45 degrés  
  
- `HS_FDIAGONAL`Hachage vers le haut (de gauche à droite) à 45 degrés  
  
- `HS_HORIZONTAL`Hachage horizontal  
  
- `HS_VERTICAL`Hachage vertical  
  
 `crColor`  
 Spécifie la couleur de premier plan du pinceau comme une couleur RVB (la couleur des trappes). Consultez la page [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Le pinceau peut ensuite être sélectionné comme le pinceau actuel pour n’importe quel contexte de périphérique.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#24;](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]  
  
##  <a name="a-namecreatepatternbrusha--cbrushcreatepatternbrush"></a><a name="createpatternbrush"></a>CBrush::CreatePatternBrush  
 Initialise un pinceau avec un modèle spécifié par une image bitmap.  
  
```  
BOOL CreatePatternBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Paramètres  
 `pBitmap`  
 Identifie un bitmap.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Le pinceau peut par la suite être sélectionné pour n’importe quel contexte de périphérique qui prend en charge les opérations de trame. La bitmap identifiée par `pBitmap` est initialisé en général à l’aide de la [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), ou [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) (fonction).  
  
 Bitmaps utilisés comme modèles de remplissage doit être de 8 x 8 pixels. Si la bitmap est supérieure, Windows utilisera uniquement les bits correspondant aux 8 premières lignes et colonnes de pixels dans le coin supérieur gauche de la bitmap.  
  
 Un pinceau de modèle peut être supprimé sans affecter la bitmap associée. Cela signifie que la bitmap peut servir à créer un nombre quelconque de formes de motif.  
  
 Un pinceau créé à l’aide d’un bitmap monochrome (plan de 1 couleur, 1 bit par pixel) est dessiné à l’aide de la couleur de texte et d’arrière-plan actuelle. Pixels représentés par un bit défini à 0 sont dessinés avec la couleur de texte actuelle. Pixels représentés par un bit défini à 1 sont dessinés avec la couleur d’arrière-plan actuelle.  
  
 Pour plus d’informations sur l’utilisation de [CreatePatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183508), une fonction de Windows, consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#25;](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]  
  
##  <a name="a-namecreatesolidbrusha--cbrushcreatesolidbrush"></a><a name="createsolidbrush"></a>CBrush::CreateSolidBrush  
 Initialise un pinceau avec une couleur unie spécifiée.  
  
```  
BOOL CreateSolidBrush(COLORREF crColor);
```  
  
### <a name="parameters"></a>Paramètres  
 `crColor`  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) structure qui spécifie la couleur du pinceau. Spécifie une valeur RVB de la couleur et peut être construite avec le `RGB` macro dans WINDOWS. H.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Le pinceau peut ensuite être sélectionné comme le pinceau actuel pour n’importe quel contexte de périphérique.  
  
 Lorsqu’une application a terminé d’utiliser le pinceau créé par `CreateSolidBrush`, elle doit sélectionner le pinceau hors du contexte de périphérique.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CBrush::CBrush](#cbrush).  
  
##  <a name="a-namecreatesyscolorbrusha--cbrushcreatesyscolorbrush"></a><a name="createsyscolorbrush"></a>CBrush::CreateSysColorBrush  
 Initialise une couleur.  
  
```  
BOOL CreateSysColorBrush(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Spécifie un index de couleur. Cette valeur correspond à la couleur utilisée pour peindre l’un des éléments de 21 fenêtre. Consultez la page [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour une liste de valeurs.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Le pinceau peut ensuite être sélectionné comme le pinceau actuel pour n’importe quel contexte de périphérique.  
  
 Lorsqu’une application a terminé d’utiliser le pinceau créé par `CreateSysColorBrush`, elle doit sélectionner le pinceau hors du contexte de périphérique.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#26;](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]  
  
##  <a name="a-namefromhandlea--cbrushfromhandle"></a><a name="fromhandle"></a>CBrush::FromHandle  
 Retourne un pointeur vers un `CBrush` en fonction d’un handle Windows de l’objet [HBRUSH](#operator_hbrush) objet.  
  
```  
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```  
  
### <a name="parameters"></a>Paramètres  
 `hBrush`  
 `HANDLE`un pinceau Windows GDI.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CBrush` objet en cas de réussite ; sinon **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Si un `CBrush` objet n’est pas déjà attaché au handle, temporaire `CBrush` objet est créé et attaché. Ce fichier temporaire `CBrush` objet est valide uniquement jusqu'à la prochaine fois que l’application a le temps d’inactivité dans sa boucle d’événements. À ce stade, tous les objets graphiques temporaires sont supprimés. En d’autres termes, l’objet temporaire est valide uniquement pendant le traitement du message de fenêtre.  
  
 Pour plus d’informations sur l’utilisation des objets graphiques, consultez [graphique objets](http://msdn.microsoft.com/library/windows/desktop/dd144962) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CBrush::CBrush](#cbrush).  
  
##  <a name="a-namegetlogbrusha--cbrushgetlogbrush"></a><a name="getlogbrush"></a>CBrush::GetLogBrush  
 Appelez cette fonction membre pour récupérer le `LOGBRUSH` structure.  
  
```  
int GetLogBrush(LOGBRUSH* pLogBrush);
```  
  
### <a name="parameters"></a>Paramètres  
 `pLogBrush`  
 Pointe vers une [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) structure qui contient des informations sur le pinceau.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la fonction réussit, et `pLogBrush` est un pointeur valid, la valeur de retour est le nombre d’octets stockés dans la mémoire tampon.  
  
 Si la fonction réussit, et `pLogBrush` est **NULL**, la valeur de retour est le nombre d’octets requis pour conserver les informations de la fonction stockent dans la mémoire tampon.  
  
 Si la fonction échoue, la valeur de retour est 0.  
  
### <a name="remarks"></a>Notes  
 Le `LOGBRUSH` structure définit le style, la couleur et le motif d’un pinceau.  
  
 Par exemple, appeler `GetLogBrush` pour faire correspondre la couleur ou le motif de la bitmap.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[27 NVC_MFCDocView](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]  
  
##  <a name="a-nameoperatorhbrusha--cbrushoperator-hbrush"></a><a name="operator_hbrush"></a>CBrush::operator HBRUSH  
 Utilisez cet opérateur pour obtenir le handle Windows GDI attaché de le `CBrush` objet.  
  
```  
operator HBRUSH() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si réussie, un handle vers l’objet Windows GDI représenté par le `CBrush` objet ; sinon **NULL**.  
  
### <a name="remarks"></a>Notes  
 Cet opérateur est un opérateur de cast, qui prend en charge l’utilisation directe d’une `HBRUSH` objet.  
  
 Pour plus d’informations sur l’utilisation des objets graphiques, consultez [graphique objets](http://msdn.microsoft.com/library/windows/desktop/dd144962) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#28;](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC PROPDLG](../../visual-cpp-samples.md)   
 [CGdiObject (classe)](../../mfc/reference/cgdiobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CBitmap (classe)](../../mfc/reference/cbitmap-class.md)   
 [CDC (classe)](../../mfc/reference/cdc-class.md)

