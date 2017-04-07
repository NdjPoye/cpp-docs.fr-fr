---
title: CBitmap (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
dev_langs:
- C++
helpviewer_keywords:
- drawing, tools
- CBitmap class
- GDI bitmap
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ccfe592bbbae8c0eff22baa6e1baac56754ef6fc
ms.lasthandoff: 02/24/2017

---
# <a name="cbitmap-class"></a>CBitmap (classe)
Encapsule une bitmap GDI (Graphics Device Interface) Windows et fournit des fonctions membres pour la manipuler.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CBitmap : public CGdiObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CBitmap::CBitmap](#cbitmap)|Construit un objet `CBitmap`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CBitmap::CreateBitmap](#createbitmap)|Initialise l’objet avec une bitmap dépendant du périphérique mémoire qui a une largeur spécifiée, la hauteur et le modèle binaire.|  
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|Initialise l’objet avec une bitmap avec la largeur, la hauteur et le modèle binaire (le cas échéant) dans un **BITMAP** structure.|  
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|Initialise l’objet avec une image bitmap afin qu’il soit compatible avec un périphérique spécifié.|  
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|Initialise l’objet avec une image bitmap pouvant être éliminée qui est compatible avec un périphérique donné.|  
|[CBitmap::FromHandle](#fromhandle)|Retourne un pointeur vers un `CBitmap` en fonction d’un handle Windows de l’objet `HBITMAP` bitmap.|  
|[CBitmap::GetBitmap](#getbitmap)|Remplit un **BITMAP** structure avec des informations sur l’image bitmap.|  
|[CBitmap::GetBitmapBits](#getbitmapbits)|Copie les bits de la bitmap spécifiée dans la mémoire tampon spécifiée.|  
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|Retourne la largeur et la hauteur de la bitmap. La hauteur et la largeur sont supposées avoir été définie précédemment par le [SetBitmapDimension](#setbitmapdimension) fonction membre.|  
|[CBitmap::LoadBitmap](#loadbitmap)|Initialise l’objet à charger une ressource bitmap nommée à partir du fichier exécutable de l’application et l’attachement de la bitmap à l’objet.|  
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|Charge une image bitmap et mappe les couleurs les couleurs système en cours.|  
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|Initialise l’objet en chargeant une bitmap Windows prédéfinie et en attachant la bitmap à l’objet.|  
|[CBitmap::SetBitmapBits](#setbitmapbits)|Définit les bits de la bitmap pour les valeurs de bits spécifié.|  
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|Assigne une largeur et une hauteur à une image bitmap en unités de 0,1 millimètres.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CBitmap::operator HBITMAP](#operator_hbitmap)|Retourne le handle Windows associé à le `CBitmap` objet.|  
  
## <a name="remarks"></a>Notes  
 Pour utiliser un `CBitmap` de l’objet, construisez l’objet, attacher un handle de bitmap avec l’une des fonctions membres d’initialisation et appelez ensuite les fonctions membres de l’objet.  
  
 Pour plus d’informations sur l’utilisation des objets graphiques comme `CBitmap`, consultez [les objets de graphique](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="cbitmap"></a>CBitmap::CBitmap  
 Construit un objet `CBitmap`.  
  
```  
CBitmap();
```  
  
### <a name="remarks"></a>Notes  
 L’objet qui en résulte doit être initialisé avec l’une des fonctions membres d’initialisation.  
  
##  <a name="createbitmap"></a>CBitmap::CreateBitmap  
 Initialise une image bitmap de mémoire dépendante de l’appareil avec la largeur, la hauteur et le modèle binaire spécifiés.  
  
```  
BOOL CreateBitmap(
    int nWidth,  
    int nHeight,  
    UINT nPlanes,  
    UINT nBitcount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>Paramètres  
 `nWidth`  
 Spécifie la largeur (en pixels) de l’image bitmap.  
  
 `nHeight`  
 Spécifie la hauteur (en pixels) de l’image bitmap.  
  
 `nPlanes`  
 Spécifie le nombre de plans de couleur de l’image bitmap.  
  
 `nBitcount`  
 Spécifie le nombre de bits de couleur par pixel d’affichage.  
  
 `lpBits`  
 Pointe vers un tableau d’octets qui contient les valeurs de bit de l’image bitmap initiale. Si elle a la valeur **NULL**, la nouvelle image bitmap n’est pas initialisée.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Pour une image bitmap de couleur, le paramètre `nPlanes` ou `nBitcount` doit être défini avec la valeur 1. Si ces deux paramètres sont définis avec la valeur 1, `CreateBitmap` crée une image bitmap monochrome.  
  
 Bien qu’une image bitmap ne peut pas être directement activée pour un périphérique d’affichage, il peut être sélectionné en tant que l’image bitmap actuelle pour un « contexte de périphérique de mémoire » à l’aide de [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) et copiés vers n’importe quel contexte de périphérique compatible à l’aide de la [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) (fonction).  
  
 Quand vous en avez terminé avec l’objet `CBitmap` créé par la fonction `CreateBitmap` , commencez par sélectionner l’image bitmap hors du contexte de périphérique, puis supprimez l’objet `CBitmap` .  
  
 Pour plus d’informations, consultez la description du champ **bmBits** de la structure **BITMAP** . Le [BITMAP](../../mfc/reference/bitmap-structure.md) structure est décrit sous le [CBitmap::CreateBitmapIndirect](#createbitmapindirect) fonction membre.  
  
##  <a name="createbitmapindirect"></a>CBitmap::CreateBitmapIndirect  
 Initialise un bitmap de la largeur, la hauteur et le modèle binaire (le cas échéant) figurant à la structure vers laquelle pointe `lpBitmap`.  
  
```  
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpBitmap`  
 Pointe vers une [BITMAP](../../mfc/reference/bitmap-structure.md) structure qui contient des informations sur l’image bitmap.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Bien qu’une image bitmap ne peut pas être directement activée pour un périphérique d’affichage, il peut être sélectionné en tant que l’image bitmap actuelle pour un contexte de périphérique de mémoire à l’aide de [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) et copiés vers n’importe quel contexte de périphérique compatible à l’aide de la [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) ou [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) (fonction). (Le [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) fonction peut copier le fichier bitmap pour le pinceau actuel directement dans le contexte de périphérique d’affichage.)  
  
 Si le **BITMAP** structure vers laquelle pointe le `lpBitmap` paramètre a été renseigné à l’aide de la `GetObject` (fonction), les bits de la bitmap ne sont pas spécifiées et l’image bitmap n’est pas initialisé. Pour initialiser le bitmap, une application peut utiliser une fonction comme [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) ou [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) pour copier les bits du bitmap identifiée par le premier paramètre de `CGdiObject::GetObject` à l’image créée par `CreateBitmapIndirect`.  
  
 Lorsque vous avez terminé avec le `CBitmap` objet créé avec `CreateBitmapIndirect` fonctionne, tout d’abord sélectionner l’image bitmap hors du contexte de périphérique, puis supprimez le `CBitmap` objet.  
  
##  <a name="createcompatiblebitmap"></a>CBitmap::CreateCompatibleBitmap  
 Initialise une bitmap qui est compatible avec l’appareil spécifié par `pDC`.  
  
```  
BOOL CreateCompatibleBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Spécifie le contexte de périphérique.  
  
 `nWidth`  
 Spécifie la largeur (en pixels) de l’image bitmap.  
  
 `nHeight`  
 Spécifie la hauteur (en pixels) de l’image bitmap.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 La bitmap possède le même nombre de plans de couleur ou le même format de bits par pixel que le contexte de périphérique spécifié. Il peut être sélectionné comme l’image bitmap actuelle pour n’importe quel périphérique mémoire compatible avec celui spécifié par `pDC`.  
  
 Si `pDC` est un contexte de périphérique mémoire, la bitmap retournée a le même format que le bitmap sélectionné dans ce contexte de périphérique. Un « contexte de périphérique mémoire » est un bloc de mémoire qui représente une surface d’affichage. Il peut être utilisé pour préparer des images en mémoire avant de les copier à la surface d’affichage du périphérique compatible.  
  
 Création d’un contexte de périphérique mémoire, GDI sélectionne automatiquement un bitmap monochrome stock pour elle.  
  
 Comme un contexte de périphérique mémoire couleur peut avoir des couleurs ou les images bitmap monochromes sélectionnés, le format de l’image bitmap retournée par le `CreateCompatibleBitmap` fonction n’est pas toujours le même ; Toutefois, le format d’une bitmap compatible pour un contexte de périphérique sans mémoire est toujours dans le format de l’appareil.  
  
 Lorsque vous avez terminé avec le `CBitmap` objet créé avec le `CreateCompatibleBitmap` fonctionne, tout d’abord sélectionner l’image bitmap hors du contexte de périphérique, puis supprimez le `CBitmap` objet.  
  
##  <a name="creatediscardablebitmap"></a>CBitmap::CreateDiscardableBitmap  
 Initialise une bitmap pouvant être éliminée qui est compatible avec le contexte de périphérique identifié par `pDC`.  
  
```  
BOOL CreateDiscardableBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Spécifie un contexte de périphérique.  
  
 `nWidth`  
 Spécifie la largeur (en bits) de l’image bitmap.  
  
 `nHeight`  
 Spécifie la hauteur (en bits) de l’image bitmap.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La bitmap possède le même nombre de plans de couleur ou le même format de bits par pixel que le contexte de périphérique spécifié. Une application peut sélectionner cette image bitmap en tant que l’image bitmap actuelle pour un périphérique mémoire compatible avec celui spécifié par `pDC`.  
  
 Windows peut ignorer une image créée par cette fonction uniquement si une application ne le n'a pas sélectionné dans un contexte d’affichage. Si Windows ignore la bitmap lorsqu’il n’est pas sélectionnée et ultérieurement l’application tente de sélectionner le [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) fonction retournera **NULL**.  
  
 Lorsque vous avez terminé avec le `CBitmap` objet créé avec le `CreateDiscardableBitmap` fonctionne, tout d’abord sélectionner l’image bitmap hors du contexte de périphérique, puis supprimez le `CBitmap` objet.  
  
##  <a name="fromhandle"></a>CBitmap::FromHandle  
 Retourne un pointeur vers un `CBitmap` de l’objet en fonction d’un handle vers une bitmap GDI de Windows.  
  
```  
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Paramètres  
 `hBitmap`  
 Spécifie une bitmap GDI de Windows.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CBitmap` objet en cas de réussite ; sinon **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Si un `CBitmap` objet n’est pas déjà attaché au handle, temporaire `CBitmap` objet est créé et attaché. Ce fichier temporaire `CBitmap` objet est valide uniquement jusqu'à la prochaine fois que l’application dispose de temps d’inactivité dans sa boucle d’événements, alors graphique temporaire de tous les objets sont supprimés. Une autre façon de dire cela est que l’objet temporaire est uniquement valide pendant le traitement du message de fenêtre.  
  
##  <a name="getbitmap"></a>CBitmap::GetBitmap  
 Récupère les propriétés de l’image pour l’image bitmap attaché.  
  
```  
int GetBitmap(BITMAP* pBitMap);
```  
  
### <a name="parameters"></a>Paramètres  
 `pBitMap`  
 Pointeur vers un [Structure BITMAP](../../mfc/reference/bitmap-structure.md) structure qui doit recevoir les propriétés de l’image. Ce paramètre ne doit pas être `NULL`.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la méthode a réussi ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getbitmapbits"></a>CBitmap::GetBitmapBits  
 Copie le modèle binaire de l’image bitmap attaché dans la mémoire tampon spécifiée.  
  
```  
DWORD GetBitmapBits(
    DWORD dwCount,  
    LPVOID lpBits) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `dwCount`  
 Nombre d’octets à copier dans la mémoire tampon.  
  
 `lpBits`  
 Pointeur vers la mémoire tampon qui recevra l’image bitmap.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’octets copiés dans la mémoire tampon si la méthode a réussi ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Utilisez [CBitmap::GetBitmap](#getbitmap) pour déterminer la taille de la mémoire tampon requise.  
  
##  <a name="getbitmapdimension"></a>CBitmap::GetBitmapDimension  
 Retourne la largeur et la hauteur de la bitmap.  
  
```  
CSize GetBitmapDimension() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La largeur et la hauteur de la bitmap, mesurée en unités de 0,1 millimètres. La hauteur est dans le **cy** membre de la `CSize` objet et la largeur est dans le **cx** membre. Si la hauteur et la largeur de la bitmap n’ont pas été définies à l’aide de `SetBitmapDimension`, la valeur de retour est 0.  
  
### <a name="remarks"></a>Remarques  
 La hauteur et la largeur sont supposées avoir été définie précédemment à l’aide de la [SetBitmapDimension](#setbitmapdimension) fonction membre.  
  
##  <a name="loadbitmap"></a>CBitmap::LoadBitmap  
 Charge la ressource de bitmap nommée par `lpszResourceName` ou identifiée par le numéro d’ID dans `nIDResource` à partir du fichier exécutable de l’application.  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszResourceName`  
 Pointe vers une chaîne terminée par le caractère null qui contient le nom de la ressource bitmap.  
  
 `nIDResource`  
 Spécifie le numéro d’ID de ressource de la ressource bitmap.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 La bitmap chargée est attachée à la `CBitmap` objet.  
  
 Si la bitmap est identifié par `lpszResourceName` n’existe pas ou si la mémoire est insuffisante pour charger l’image bitmap, la fonction retourne 0.  
  
 Vous pouvez utiliser la [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) (fonction) pour supprimer la bitmap chargé par le `LoadBitmap` (fonction), ou le `CBitmap` destructeur supprime l’objet pour vous.  
  
> [!CAUTION]
>  Avant de supprimer l’objet, assurez-vous qu’il n’est pas sélectionnée dans un contexte de périphérique.  
  
 Les images suivantes ont été ajoutées à Windows 3.1 et versions ultérieures :  
  
 **OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI**  
  
 Ces bitmaps ne figurent pas dans les pilotes de périphériques pour les versions de Windows 3.0 et versions antérieures. Pour obtenir une liste complète des images bitmap et un affichage de leur apparition, consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="loadmappedbitmap"></a>CBitmap::LoadMappedBitmap  
 Appelez cette fonction membre pour charger une image bitmap et de mapper les couleurs pour les couleurs système en cours.  
  
```  
BOOL LoadMappedBitmap(
    UINT nIDBitmap,  
    UINT nFlags = 0,  
    LPCOLORMAP lpColorMap = NULL,  
    int nMapSize = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDBitmap`  
 L’ID de la ressource bitmap.  
  
 `nFlags`  
 Un indicateur pour une image bitmap. Peut être zéro ou **CMB_MASKED**.  
  
 `lpColorMap`  
 Un pointeur vers un **COLORMAP** structure qui contient les informations de couleur nécessaires pour mapper les bitmaps. Si ce paramètre est **NULL**, la fonction utilise la table des couleurs par défaut.  
  
 *nMapSize*  
 Le nombre de mappages de couleurs désigné par `lpColorMap`.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, `LoadMappedBitmap` mappera couleurs couramment utilisées dans les glyphes de bouton.  
  
 Pour plus d’informations sur la création d’une image bitmap mappée, consultez la fonction Windows [CreateMappedBitmap](http://go.microsoft.com/fwlink/linkid=230562) et [COLORMAP](http://msdn.microsoft.com/library/windows/desktop/bb760448) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="loadoembitmap"></a>CBitmap::LoadOEMBitmap  
 Charge une bitmap prédéfinie utilisée par Windows.  
  
```  
BOOL LoadOEMBitmap(UINT nIDBitmap);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDBitmap`  
 Numéro d’identification de la bitmap Windows prédéfinie. Les valeurs possibles sont répertoriées ci-dessous à partir de WINDOWS. H :  
  
|||  
|-|-|  
|**OBM_BTNCORNERS**|**OBM_OLD_RESTORE**|  
|**OBM_BTSIZE**|**OBM_OLD_RGARROW**|  
|**OBM_CHECK**|**OBM_OLD_UPARROW**|  
|**OBM_CHECKBOXES**|**OBM_OLD_ZOOM**|  
|**OBM_CLOSE**|**OBM_REDUCE**|  
|**OBM_COMBO**|**OBM_REDUCED**|  
|**OBM_DNARROW**|**OBM_RESTORE**|  
|**OBM_DNARROWD**|**OBM_RESTORED**|  
|**OBM_DNARROWI**|**OBM_RGARROW**|  
|**OBM_LFARROW**|**OBM_RGARROWD**|  
|**OBM_LFARROWD**|**OBM_RGARROWI**|  
|**OBM_LFARROWI**|**OBM_SIZE**|  
|**OBM_MNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_CLOSE**|**OBM_UPARROWD**|  
|**OBM_OLD_DNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_LFARROW**|**OBM_ZOOM**|  
|**OBM_OLD_REDUCE**|**OBM_ZOOMD**|  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Bitmap des noms qui commencent par **OBM_OLD** représentent les bitmaps utilisées par les versions de Windows antérieures à 3.0.  
  
 Notez que la constante **OEMRESOURCE** doit être défini avant d’inclure WINDOWS. H pour pouvoir utiliser le **OBM_** constantes.  
  
##  <a name="operator_hbitmap"></a>CBitmap::operator HBITMAP  
 Utilisez cet opérateur pour obtenir le handle Windows GDI attaché de le `CBitmap` objet.  
  
```  
operator HBITMAP() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si réussie, un handle vers l’objet Windows GDI représenté par le `CBitmap` objet ; sinon **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur est un opérateur de cast, qui prend en charge l’utilisation directe d’une `HBITMAP` objet.  
  
 Pour plus d’informations sur l’utilisation des objets graphiques, consultez [graphique objets](http://msdn.microsoft.com/library/windows/desktop/dd144962) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setbitmapbits"></a>CBitmap::SetBitmapBits  
 Définit les bits d’une image bitmap pour les valeurs de bits donnés par `lpBits`.  
  
```  
DWORD SetBitmapBits(
    DWORD dwCount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwCount`  
 Spécifie le nombre d’octets indiqué par `lpBits`.  
  
 `lpBits`  
 Pointe vers le **octets** tableau qui contient les valeurs de pixels à copier vers le `CBitmap` objet. Dans l’ordre de l’image bitmap pouvoir afficher l’image correctement, les valeurs doivent être formatés pour respecter les valeurs de profondeur de couleur, la largeur et la hauteur spécifiées lors de la création de l’instance CBitmap. Pour plus d’informations, consultez [CBitmap::CreateBitmap](#createbitmap).  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’octets utilisés lors de la définition des bits de la bitmap ; 0 si la fonction échoue.  
  
##  <a name="setbitmapdimension"></a>CBitmap::SetBitmapDimension  
 Assigne une largeur et une hauteur à une image bitmap en unités de 0,1 millimètres.  
  
```  
CSize SetBitmapDimension(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Paramètres  
 `nWidth`  
 Spécifie la largeur de la bitmap (en unités de 0,1-millimètre).  
  
 `nHeight`  
 Spécifie la hauteur de l’image bitmap (en unités de 0,1-millimètre).  
  
### <a name="return-value"></a>Valeur de retour  
 Les dimensions de bitmap précédente. Hauteur est dans le **cy** variable de membre de la `CSize` objet et la largeur est dans le **cx** variable membre.  
  
### <a name="remarks"></a>Remarques  
 L’interface GDI n’utilise pas ces valeurs à l’exception afin les retourner lorsqu’une application appelle la [GetBitmapDimension](#getbitmapdimension) fonction membre.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC MDI](../../visual-cpp-samples.md)   
 [CGdiObject (classe)](../../mfc/reference/cgdiobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)


