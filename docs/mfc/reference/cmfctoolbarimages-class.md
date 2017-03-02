---
title: Classe de CMFCToolBarImages | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarImages
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarImages class
ms.assetid: d4e50518-9ffc-406f-9996-f79e5cd38155
caps.latest.revision: 31
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
ms.openlocfilehash: ff94497108033b17d52b79594fdbe30e8ed7da03
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarimages-class"></a>CMFCToolBarImages (classe)
Les images dans une barre d’outils. La `CMFCToolBarImages` classe gère les images de barre d’outils chargées à partir des ressources d’application ou de fichiers.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCToolBarImages : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolBarImages::CMFCToolBarImages](#cmfctoolbarimages)|Construit un objet `CMFCToolBarImages`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolBarImages::AdaptColors](#adaptcolors)||  
|[CMFCToolBarImages::AddIcon](#addicon)|Ajoute une icône pour les images de barre d’outils.|  
|[CMFCToolBarImages::AddImage](#addimage)|Ajoute une image bitmap pour les images de barre d’outils.|  
|[CMFCToolBarImages::CleanUp](#cleanup)||  
|[CMFCToolBarImages::Clear](#clear)|Libère les ressources système allouées à cet objet.|  
|[CMFCToolBarImages::ConvertTo32Bits](#convertto32bits)|Convertit souligné 32 bpp images bitmaps.|  
|[CMFCToolBarImages::CopyImageToClipboard](#copyimagetoclipboard)||  
|[CMFCToolBarImages::CopyTo](#copyto)||  
|[CMFCToolBarImages::CreateFromImageList](#createfromimagelist)|Initialise les images de barre d’outils à partir d’une liste d’images ( [CImageList (classe)](../../mfc/reference/cimagelist-class.md)).|  
|[CMFCToolBarImages::CreateRegionFromImage](#createregionfromimage)||  
|[CMFCToolBarImages::DeleteImage](#deleteimage)|Supprime l’image qui a un index spécifié à partir d’images de la barre d’outils si cet ensemble d’images de barre d’outils contient des images définies par l’utilisateur.|  
|[CMFCToolBarImages::Draw](#draw)|Dessine une image de la barre d’outils unique (bouton).|  
|[CMFCToolBarImages::DrawEx](#drawex)||  
|[CMFCToolBarImages::EnableRTL](#enablertl)||  
|[CMFCToolBarImages::EndDrawImage](#enddrawimage)|Libère les ressources système après qu’une image de la barre d’outils dessin.|  
|[CMFCToolBarImages::ExtractIcon](#extracticon)|Retourne l’icône qui possède un index d’image spécifié à partir d’images de la barre d’outils.|  
|[CMFCToolBarImages::FillDitheredRect](#fillditheredrect)|Remplit un rectangle à l’aide d’un pinceau qui a les couleurs d’arrière-plan de barre d’outils.|  
|[CMFCToolBarImages::GetAlwaysLight](#getalwayslight)||  
|[CMFCToolBarImages::GetBitsPerPixel](#getbitsperpixel)|Retourne la résolution actuelle des images soulignées.|  
|[CMFCToolBarImages::GetCount](#getcount)|Retourne le nombre d’images dans la barre d’outils.|  
|[CMFCToolBarImages::GetDisabledImageAlpha](#getdisabledimagealpha)|Retourne la valeur de canal alpha est utilisée pour les images désactivés.|  
|[CMFCToolBarImages::GetFadedImageAlpha](#getfadedimagealpha)||  
|[CMFCToolBarImages::GetImageSize](#getimagesize)|Récupère la taille des images de barre d’outils qui sont stockés dans la mémoire (taille de la source) ou la taille des images de barre d’outils qui sont dessinées à l’écran (taille de la destination).|  
|[CMFCToolBarImages::GetImageWell](#getimagewell)|Retourne le handle vers le bitmap qui contient toutes les images de barre d’outils.|  
|[CMFCToolBarImages::GetImageWellLight](#getimagewelllight)||  
|[CMFCToolBarImages::GetLastImageRect](#getlastimagerect)||  
|[CMFCToolBarImages::GetLightPercentage](#getlightpercentage)||  
|[CMFCToolBarImages::GetMapTo3DColors](#getmapto3dcolors)||  
|[CMFCToolBarImages::GetMask](#getmask)||  
|[CMFCToolBarImages::GetResourceOffset](#getresourceoffset)|Retourne l’index d’image pour un ID de ressource spécifié.|  
|[CMFCToolBarImages::GetScale](#getscale)|Retourne le rapport actuel d’échelle d’images soulignées.|  
|[CMFCToolBarImages::GetTransparentColor](#gettransparentcolor)||  
|[CMFCToolBarImages::GrayImages](#grayimages)|Grise les images de barre d’outils pour qu’elles aient désactivé.|  
|[CMFCToolBarImages::Is32BitTransparencySupported](#is32bittransparencysupported)|Détermine si le système d’exploitation prend en charge la fusion alpha 32 bits.|  
|[CMFCToolBarImages::IsPreMultiplyAutoCheck](#ispremultiplyautocheck)||  
|[CMFCToolBarImages::IsRTL](#isrtl)|Détermine si la prise en charge de droite à gauche (RTL) est activée.|  
|[CMFCToolBarImages::IsReadOnly](#isreadonly)|Détermine si les images de barre d’outils sont en lecture seule.|  
|[CMFCToolBarImages::IsScaled](#isscaled)|Indique si les images soulignés sont mis à l’échelle ou non.|  
|[CMFCToolBarImages::IsUserImagesList](#isuserimageslist)|Détermine si ce jeu d’images de barre d’outils contient des images définies par l’utilisateur.|  
|[CMFCToolBarImages::IsValid](#isvalid)|Détermine si ce jeu d’images de barre d’outils contient une image de la barre d’outils valide.|  
|[CMFCToolBarImages::Load](#load)|Charge des images de barre d’outils à partir des ressources système ou d’un fichier.|  
|[CMFCToolBarImages::LoadStr](#loadstr)||  
|[CMFCToolBarImages::MapFromSysColor](#mapfromsyscolor)||  
|[CMFCToolBarImages::MapTo3dColors](#mapto3dcolors)||  
|[CMFCToolBarImages::MapToSysColor](#maptosyscolor)||  
|[CMFCToolBarImages::MapToSysColorAlpha](#maptosyscoloralpha)||  
|[CMFCToolBarImages::Mirror](#mirror)|Horizontalement reflète toutes les images de barre d’outils.|  
|[CMFCToolBarImages::MirrorBitmap](#mirrorbitmap)|Horizontalement reflète une image bitmap.|  
|[CMFCToolBarImages::MirrorBitmapVert](#mirrorbitmapvert)||  
|[CMFCToolBarImages::MirrorVert](#mirrorvert)||  
|[CMFCToolBarImages::OnSysColorChange](#onsyscolorchange)||  
|[CMFCToolBarImages::PrepareDrawImage](#preparedrawimage)|Alloue les ressources qui sont nécessaires pour dessiner une image de la barre d’outils à une taille spécifiée.|  
|[CMFCToolBarImages::Save](#save)|Stocke les images de barre d’outils dans un fichier si ce jeu d’images de barre d’outils contient des images définies par l’utilisateur.|  
|[CMFCToolBarImages::SetAlwaysLight](#setalwayslight)||  
|[CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha)|Définit la valeur de canal alpha est utilisée pour les images désactivés.|  
|[CMFCToolBarImages::SetFadedImageAlpha](#setfadedimagealpha)||  
|[CMFCToolBarImages::SetImageSize](#setimagesize)|Définit la taille d’une image de la barre d’outils (taille de la source).|  
|[CMFCToolBarImages::SetLightPercentage](#setlightpercentage)||  
|[CMFCToolBarImages::SetMapTo3DColors](#setmapto3dcolors)||  
|[CMFCToolBarImages::SetPreMultiplyAutoCheck](#setpremultiplyautocheck)||  
|[CMFCToolBarImages::SetSingleImage](#setsingleimage)||  
|[CMFCToolBarImages::SetTransparentColor](#settransparentcolor)|Définit la couleur transparente des images de barre d’outils.|  
|[CMFCToolBarImages::SmoothResize](#smoothresize)|Sans heurts redimensionne les images soulignées.|  
|[CMFCToolBarImages::UpdateImage](#updateimage)|Met à jour une image de barre d’outils de défini par l’utilisateur à partir d’une image bitmap.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolBarImages::PreMultiplyAlpha](#premultiplyalpha)||  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolBarImages::m_bDisableTrueColorAlpha](#m_bdisabletruecoloralpha)|`TRUE`Si alpha vraies fusion (couleur&32; bits) est désactivé.|  
  
## <a name="remarks"></a>Notes  
 La bitmap complète des images de barre d’outils gérés par `CMFCToolbarImages` se compose d’une ou plusieurs images de petite barre d’outils (boutons) de taille fixe.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment configurer un `CMFCToolBarImages` à l’aide de différentes méthodes dans la `CMFCToolBarImages` classe. L’exemple montre comment définir la taille de l’image de la barre d’outils, charger une image et définir la couleur transparente de l’image. Cet extrait de code fait partie de la [exemple de Visual Studio démonstration](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo n°&32;](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo&#33;](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCToolBarImages`   
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtoolbarimages.h  
  
##  <a name="a-nameadaptcolorsa--cmfctoolbarimagesadaptcolors"></a><a name="adaptcolors"></a>CMFCToolBarImages::AdaptColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AdaptColors(
    COLORREF clrBase,  
    COLORREF clrTone);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `clrBase`  
 [in] `clrTone`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameaddicona--cmfctoolbarimagesaddicon"></a><a name="addicon"></a>CMFCToolBarImages::AddIcon  
 Ajoute une icône à la liste des images de barre d’outils.  
  
```  
int AddIcon(
    HICON hIcon,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hIcon`  
 Un handle de l’icône doit être ajouté.  
  
 [in] `bAlphaBlend`  
 `TRUE`Si cette icône est utilisée avec la fusion alpha ; dans le cas contraire `FALSE`.  
  
### <a name="return-value"></a>Valeur de retour  
 Index de base zéro de l’image de la barre d’outils qui a été ajouté si la méthode a réussi ; sinon -1.  
  
##  <a name="a-nameaddimagea--cmfctoolbarimagesaddimage"></a><a name="addimage"></a>CMFCToolBarImages::AddImage  
 Ajoute une image bitmap pour les images de barre d’outils.  
  
```  
int AddImage(
    HBITMAP hbmp,  
    BOOL bSetBitPerPixel=FALSE);

int AddImage(
    const CMFCToolBarImages& imageList,  
    int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hbmp`  
 Handle de l’image bitmap à ajouter.  
  
 [in] `bSetBitPerPixel`  
 `TRUE`Si le `CMFCToolBarImages` objet utilise la profondeur de couleur (en bits par pixel) de la nouvelle image ; `FALSE` si le `CMFCToolbarImages` objet conserve la profondeur de couleur actuelle.  
  
 [in] `imageList`  
 Une référence à un `CMFCToolbarImages` objet qui contient l’image à ajouter.  
  
 [in] `nIndex`  
 L’index de la source `CMFCToolbarImages` objet de l’image à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de barre d’outils de l’image qui le `CMFCToolBarImages` objet conserve une fois la nouvelle bitmap a été ajoutée avec succès ; -1 si l’opération a échoué.  
  
##  <a name="a-namecleanupa--cmfctoolbarimagescleanup"></a><a name="cleanup"></a>CMFCToolBarImages::CleanUp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall CleanUp();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namecleara--cmfctoolbarimagesclear"></a><a name="clear"></a>CMFCToolBarImages::Clear  
 Libère les ressources système qui le [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md) objet alloué.  
  
```  
void Clear();
```  
  
##  <a name="a-namecmfctoolbarimagesa--cmfctoolbarimagescmfctoolbarimages"></a><a name="cmfctoolbarimages"></a>CMFCToolBarImages::CMFCToolBarImages  
 Construit un objet `CMFCToolBarImages`.  
  
```  
CMFCToolBarImages();
```  
  
### <a name="remarks"></a>Notes  
 Construit un `CMFCToolBarImages` de l’objet, initialise le moteur de rendu et définit la taille de l’image à sa valeur par défaut de 16 x 15 pixels. Utilisez [CMFCToolBarImages::SetImageSize](#setimagesize) pour modifier la taille de l’image avant d’ajouter des images.  
  
##  <a name="a-namecopyimagetoclipboarda--cmfctoolbarimagescopyimagetoclipboard"></a><a name="copyimagetoclipboard"></a>CMFCToolBarImages::CopyImageToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyImageToClipboard(int iImage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iImage`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namecopytoa--cmfctoolbarimagescopyto"></a><a name="copyto"></a>CMFCToolBarImages::CopyTo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyTo(CMFCToolBarImages& imageList);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `imageList`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namecreatefromimagelista--cmfctoolbarimagescreatefromimagelist"></a><a name="createfromimagelist"></a>CMFCToolBarImages::CreateFromImageList  
 Initialise les images de barre d’outils à partir d’un [CImageList (classe)](../../mfc/reference/cimagelist-class.md) objet.  
  
```  
BOOL CreateFromImageList(const CImageList& imageList);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `imageList`  
 La liste d’images à utiliser comme source pour les images de barre d’outils.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours `TRUE`.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction pour initialiser rapidement la liste d’images de barre d’outils à partir d’une liste d’images externes.  
  
##  <a name="a-namecreateregionfromimagea--cmfctoolbarimagescreateregionfromimage"></a><a name="createregionfromimage"></a>CMFCToolBarImages::CreateRegionFromImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static HRGN __stdcall CreateRegionFromImage(
    HBITMAP bmp,  
    COLORREF clrTransparent);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bmp`  
 [in] `clrTransparent`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namedeleteimagea--cmfctoolbarimagesdeleteimage"></a><a name="deleteimage"></a>CMFCToolBarImages::DeleteImage  
 Supprime l’image définie par l’utilisateur qui possède un index spécifié à partir d’images de la barre d’outils.  
  
```  
BOOL DeleteImage(int iImage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iImage`  
 Spécifie l’index de base zéro de l’image à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’image a été supprimée avec succès ; `FALSE` si l’index d’image n’est pas valide, le `CMFCToolbarImages` objet est temporaire, la `CMFCToolbarImages` objet ne contient pas d’images défini par l’utilisateur, ou si une autre erreur s’est produite.  
  
##  <a name="a-namedrawa--cmfctoolbarimagesdraw"></a><a name="draw"></a>CMFCToolBarImages::Draw  
 Dessine une image de la barre d’outils unique.  
  
```  
BOOL Draw(
    CDC* pDC,  
    int x,  
    int y,  
    int iImageIndex,  
    BOOL bHilite=FALSE,  
    BOOL bDisabled=FALSE,  
    BOOL bIndeterminate=FALSE,  
    BOOL bShadow=FALSE,  
    BOOL bInactive=FALSE,  
    BYTE alphaSrc=255);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `x`  
 Coordonnée X du côté gauche du rectangle dans lequel l’image doit être dessiné.  
  
 [in] `y`  
 Coordonnée Y du bord supérieur du rectangle dans lequel l’image doit être dessiné.  
  
 [in] `iImageIndex`  
 Index de base zéro de l’image à afficher.  
  
 [in] `bHilite`  
 `TRUE`Si l’image doit être mis en surbrillance ; dans le cas contraire `FALSE`.  
  
 [in] `bDisabled`  
 `TRUE`Si l’image doit être dessiné dans le style désactivé ; dans le cas contraire `FALSE`.  
  
 [in] `bIndeterminate`  
 `TRUE`Si l’image doit être dessiné dans le style d’un état indéterminé ; dans le cas contraire `FALSE`.  
  
 [in] `bShadow`  
 `TRUE`Si l’image doit être dessiné avec une ombre portée ; dans le cas contraire `FALSE`.  
  
 [in] `bInactive`  
 `TRUE`Si l’image doit être dessiné dans le style de l’état inactif ; dans le cas contraire `FALSE`.  
  
 [in] `alphaSrc`  
 La valeur du canal alpha (opacité). Une valeur de 255 signifie que l’image est dessinée opaque. La valeur 0 signifie que l’image est dessinée transparent. Cette valeur est utilisée uniquement pour les images couleur 32 bits et des images qui affiche un style de verre de Windows Vista.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’image spécifiée était affichée avec succès ; `FALSE` si l’index d’image n’est pas valide ou une autre erreur s’est produite.  
  
##  <a name="a-namedrawexa--cmfctoolbarimagesdrawex"></a><a name="drawex"></a>CMFCToolBarImages::DrawEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL DrawEx(
    CDC* pDC,  
    CRect rect,  
    int iImageIndex,  
    ImageAlignHorz horzAlign = ImageAlignHorzLeft,  
    ImageAlignVert vertAlign = ImageAlignVertTop,  
    CRect rectSrc = CRect(0,
    0,
    0,
    0),  
    BYTE alphaSrc = 255);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 [in] `rect`  
 [in] `iImageIndex`  
 [in] `horzAlign`  
 [in] `vertAlign`  
 [in] `rectSrc`  
 [in] `0`  
 [in] `0)`  
 [in] `alphaSrc`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameenablertla--cmfctoolbarimagesenablertl"></a><a name="enablertl"></a>CMFCToolBarImages::EnableRTL  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall EnableRTL(BOOL bIsRTL = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bIsRTL`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameenddrawimagea--cmfctoolbarimagesenddrawimage"></a><a name="enddrawimage"></a>CMFCToolBarImages::EndDrawImage  
 Libère les ressources système qui [CMFCToolBarImages::PrepareDrawImage](#preparedrawimage) allouée une fois que vous dessinez une image de la barre d’outils en appelant [CMFCToolBarImages::Draw](#draw).  
  
```  
void EndDrawImage(CAfxDrawState& ds);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `ds`  
 Une référence à la `CAfxDrawState` objet qui a été passé à la `PrepareDrawImage` (méthode).  
  
##  <a name="a-nameextracticona--cmfctoolbarimagesextracticon"></a><a name="extracticon"></a>CMFCToolBarImages::ExtractIcon  
 Retourne l’icône qui possède un index d’image spécifié à partir d’images de la barre d’outils.  
  
```  
HICON ExtractIcon(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nIndex`  
 Index de base zéro dans la liste d’images à laquelle se trouve l’image doit être extraite en tant qu’icône.  
  
### <a name="return-value"></a>Valeur de retour  
 Un handle de l’icône extraite, ou `NULL` si `nIndex` est hors limites.  
  
##  <a name="a-namefillditheredrecta--cmfctoolbarimagesfillditheredrect"></a><a name="fillditheredrect"></a>CMFCToolBarImages::FillDitheredRect  
 Remplit un rectangle avec les couleurs d’arrière-plan de barre d’outils.  
  
```  
static void FillDitheredRect(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `rect`  
 Les coordonnées d’un rectangle à remplir.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour remplir un rectangle avec une couleur qui est la moyenne des couleurs système COLOR_BTNFACE et COLOR_BTNHIGHLIGHT. Si le système utilise moins de 256 couleurs, le rectangle sera rempli avec un modèle de ces deux couleurs dégradée à la place.  
  
##  <a name="a-namegetalwayslighta--cmfctoolbarimagesgetalwayslight"></a><a name="getalwayslight"></a>CMFCToolBarImages::GetAlwaysLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetAlwaysLight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetcounta--cmfctoolbarimagesgetcount"></a><a name="getcount"></a>CMFCToolBarImages::GetCount  
 Retourne le nombre d’images dans la liste d’images de barre d’outils.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’images dans le `CMFCToolBarImages` objet.  
  
##  <a name="a-namegetdisabledimagealphaa--cmfctoolbarimagesgetdisabledimagealpha"></a><a name="getdisabledimagealpha"></a>CMFCToolBarImages::GetDisabledImageAlpha  
 Retourne la valeur du canal alpha (opacité) qui est utilisée pour les images désactivés.  
  
```  
static BYTE GetDisabledImageAlpha();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur actuelle de canal alpha.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez appeler [CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha) pour modifier la valeur de canal alpha.  
  
##  <a name="a-namegetfadedimagealphaa--cmfctoolbarimagesgetfadedimagealpha"></a><a name="getfadedimagealpha"></a>CMFCToolBarImages::GetFadedImageAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BYTE __stdcall GetFadedImageAlpha();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetimagesizea--cmfctoolbarimagesgetimagesize"></a><a name="getimagesize"></a>CMFCToolBarImages::GetImageSize  
 Récupère la taille des images de barre d’outils qui sont stockés dans la mémoire (taille de la source) ou la taille des images de barre d’outils qui sont dessinées à l’écran (taille de la destination).  
  
```  
SIZE GetImageSize(BOOL bDest=FALSE) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bDest`  
 `TRUE`pour récupérer la taille de la destination ; `FALSE` pour récupérer la taille de l’image source.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `SIZE` structure qui spécifie la taille d’une image en pixels.  
  
### <a name="remarks"></a>Notes  
 La taille de l’image source est la taille des images qui sont stockés dans le [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md) objet. Vous pouvez appeler [CMFCToolBarImages::SetImageSize](#setimagesize) pour définir la taille de la source. La valeur par défaut est 16 x 15 pixels.  
  
 Par défaut, la taille d’image de destination est 0 x 0. Vous spécifiez la taille de destination lorsque vous appelez [CMFCToolBarImages::PrepareDrawImage](#preparedrawimage). Le [CMFCToolBarImages::EndDrawImage](#enddrawimage) méthode rétablit la valeur par défaut la taille de la destination.  
  
##  <a name="a-namegetimagewella--cmfctoolbarimagesgetimagewell"></a><a name="getimagewell"></a>CMFCToolBarImages::GetImageWell  
 Retourne le handle vers le bitmap qui contient toutes les images de barre d’outils.  
  
```  
HBITMAP GetImageWell() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Handle d’une bitmap qui contient les images de barre d’outils.  
  
### <a name="remarks"></a>Remarques  
 Les images de barre d’outils sont stockées dans une ligne dans une seule bitmap est appelée un *image bien*. Pour rechercher une image de la barre d’outils dans la barre d’outils image, multipliez l’index de l’image par la largeur des images de barre d’outils (voir [CMFCToolBarImages::GetImageSize](#getimagesize)) pour obtenir le décalage horizontal de l’image à l’intérieur de l’image correctement.  
  
##  <a name="a-namegetimagewelllighta--cmfctoolbarimagesgetimagewelllight"></a><a name="getimagewelllight"></a>CMFCToolBarImages::GetImageWellLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HBITMAP GetImageWellLight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetlastimagerecta--cmfctoolbarimagesgetlastimagerect"></a><a name="getlastimagerect"></a>CMFCToolBarImages::GetLastImageRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetLastImageRect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetlightpercentagea--cmfctoolbarimagesgetlightpercentage"></a><a name="getlightpercentage"></a>CMFCToolBarImages::GetLightPercentage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetLightPercentage() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetmapto3dcolorsa--cmfctoolbarimagesgetmapto3dcolors"></a><a name="getmapto3dcolors"></a>CMFCToolBarImages::GetMapTo3DColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetMapTo3DColors() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetmaska--cmfctoolbarimagesgetmask"></a><a name="getmask"></a>CMFCToolBarImages::GetMask  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HBITMAP GetMask(int iImage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iImage`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetresourceoffseta--cmfctoolbarimagesgetresourceoffset"></a><a name="getresourceoffset"></a>CMFCToolBarImages::GetResourceOffset  
 Retourne l’index d’image pour un ID de ressource spécifié.  
  
```  
int GetResourceOffset(UINT uiResId) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiResId`  
 Un ID de ressource d’image.  
  
### <a name="return-value"></a>Valeur de retour  
 Un index d’image si la méthode a réussi ; -1 si l’image avec l’ID de ressource spécifié n’existe pas.  
  
##  <a name="a-namegettransparentcolora--cmfctoolbarimagesgettransparentcolor"></a><a name="gettransparentcolor"></a>CMFCToolBarImages::GetTransparentColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
COLORREF GetTransparentColor() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegrayimagesa--cmfctoolbarimagesgrayimages"></a><a name="grayimages"></a>CMFCToolBarImages::GrayImages  
 Grise les images de barre d’outils pour qu’elles aient désactivé.  
  
```  
BOOL GrayImages(int nGrayImageLuminancePercentage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nGrayImageLuminancePercentage`  
 Pourcentage de luminance.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si les images de la collection ont été grisés avec succès ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode modifie les images de barre d’outils en moyenne les composants rouges, verts et bleus de chaque pixel et en multipliant le résultat par `nGrayImageLuminancePercentage` divisé par 100. Si `nGrayImageLuminancePercentage` est nul ou négatif, la valeur par défaut de 130 est utilisée à la place.  
  
> [!NOTE]
>  Si vous souhaitez annuler la modification, vous devez recharger les images à partir de la source. Vous pouvez cela en appelant [CMFCToolBarImages::Load](#load) ou [CMFCToolBarImages::UpdateImage](#updateimage) (uniquement pour les images définies par l’utilisateur), ou en appelant [CMFCToolBarImages::Clear](#clear) et ajouter les images à nouveau en appelant [CMFCToolBarImages::AddIcon](#addicon) ou [CMFCToolBarImages::AddImage](#addimage).  
  
##  <a name="a-nameis32bittransparencysupporteda--cmfctoolbarimagesis32bittransparencysupported"></a><a name="is32bittransparencysupported"></a>CMFCToolBarImages::Is32BitTransparencySupported  
 Spécifie si le système d’exploitation prend en charge la fusion alpha 32 bits.  
  
```  
static BOOL Is32BitTransparencySupported();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la fusion alpha 32 bits est pris en charge ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode statique permet de déterminer à l’exécution si le système d’exploitation prend en charge la fusion alpha 32 bits. Cette fonctionnalité est prise en charge sur [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] et versions ultérieures.  
  
##  <a name="a-nameispremultiplyautochecka--cmfctoolbarimagesispremultiplyautocheck"></a><a name="ispremultiplyautocheck"></a>CMFCToolBarImages::IsPreMultiplyAutoCheck  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsPreMultiplyAutoCheck() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisreadonlya--cmfctoolbarimagesisreadonly"></a><a name="isreadonly"></a>CMFCToolBarImages::IsReadOnly  
 Spécifie si les images de barre d’outils sont en lecture seule.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si les images de barre d’outils sont en lecture seule, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Le `CMFCToolbarImages` objet est en lecture seule lors du chargement de l’image bitmap avec des images de barre d’outils à partir d’un fichier en lecture seule, ou lorsque l’image bitmap a été copié à l’aide de la `CMFCToolBarImages::CopyTemp` méthode.  
  
##  <a name="a-nameisrtla--cmfctoolbarimagesisrtl"></a><a name="isrtl"></a>CMFCToolBarImages::IsRTL  
 Spécifie si la prise en charge de droite à gauche (RTL) est activée.  
  
```  
static BOOL IsRTL();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la prise en charge de droite à gauche est activé ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Prise en charge de droite à gauche est utilisée lorsque l’application est localisée dans une langue qui s’écrit de droite à gauche, telles que l’arabe, hébreu, persan et ourdou.  
  
##  <a name="a-nameisuserimageslista--cmfctoolbarimagesisuserimageslist"></a><a name="isuserimageslist"></a>CMFCToolBarImages::IsUserImagesList  
 Spécifie si cet ensemble d’images de barre d’outils contient des images définies par l’utilisateur.  
  
```  
BOOL IsUserImagesList() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le `CMFCToolBarImages` objet contient des images de barre d’outils de défini par l’utilisateur ; sinon `FALSE`.  
  
##  <a name="a-nameisvalida--cmfctoolbarimagesisvalid"></a><a name="isvalid"></a>CMFCToolBarImages::IsValid  
 Indique si cet ensemble d’images de barre d’outils contient une image de la barre d’outils valide.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si un `CMFCToolBarImages` objet est valide ; sinon `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Le `CMFCToolBarImages` objet n’est pas valide lorsque son handle à une bitmap avec des images de barre d’outils est `NULL`.  
  
##  <a name="a-nameloada--cmfctoolbarimagesload"></a><a name="load"></a>CMFCToolBarImages::Load  
 Charge des images de barre d’outils à partir des ressources système ou d’un fichier.  
  
```  
BOOL Load(
    UINT uiResID,  
    HINSTANCE hinstRes=NULL,  
    BOOL bAdd=FALSE);

BOOL Load(
    LPCTSTR lpszBmpFileName,   
    DWORD nMaxFileSize = 819200);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `uiResID`  
 L’ID d’une ressource bitmap.  
  
 [in] `hinstRes`  
 Une instance de la DLL de ressource.  
  
 [in] `bAdd`  
 `TRUE`Pour ajouter l’image bitmap chargé dans la bitmap existante, ou `FALSE` pour remplacer la bitmap existante.  
  
 [in] `lpszBmpFileName`  
 Un chemin d’accès à un fichier de disque à partir duquel charger l’image bitmap.  
  
 [in] `nMaxFileSize`  
 Nombre maximal d’octets dans le fichier bitmap. ou 0 pour charger l’image bitmap, quelle que soit la taille du fichier. Si la taille du fichier dépasse cette taille maximale, la méthode retourne `FALSE` et ne pas charger l’image bitmap.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’image bitmap a été chargé avec succès ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Si le fichier possède l’attribut lecture seule, la liste d’images est marquée en lecture seule.  
  
##  <a name="a-nameloadstra--cmfctoolbarimagesloadstr"></a><a name="loadstr"></a>CMFCToolBarImages::LoadStr  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL LoadStr(
    LPCTSTR lpszResourceName,  
    HINSTANCE hinstRes = NULL,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszResourceName`  
 [in] `hinstRes`  
 [in] `bAdd`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemapfromsyscolora--cmfctoolbarimagesmapfromsyscolor"></a><a name="mapfromsyscolor"></a>CMFCToolBarImages::MapFromSysColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapFromSysColor(
    COLORREF color,  
    BOOL bUseRGBQUAD = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `color`  
 [in] `bUseRGBQUAD`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namemapto3dcolorsa--cmfctoolbarimagesmapto3dcolors"></a><a name="mapto3dcolors"></a>CMFCToolBarImages::MapTo3dColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL MapTo3dColors(
    BOOL bUseRGBQUAD = TRUE,  
    COLORREF clrSrc = (COLORREF)-1,  
    COLORREF clrDest = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bUseRGBQUAD`  
 [in] `clrSrc`  
 [in] `clrDest`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namemaptosyscolora--cmfctoolbarimagesmaptosyscolor"></a><a name="maptosyscolor"></a>CMFCToolBarImages::MapToSysColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapToSysColor(
    COLORREF color,  
    BOOL bUseRGBQUAD = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `color`  
 [in] `bUseRGBQUAD`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemaptosyscoloralphaa--cmfctoolbarimagesmaptosyscoloralpha"></a><a name="maptosyscoloralpha"></a>CMFCToolBarImages::MapToSysColorAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapToSysColorAlpha(COLORREF color);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `color`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namemirrora--cmfctoolbarimagesmirror"></a><a name="mirror"></a>CMFCToolBarImages::Mirror  
 Remplace les images de barre d’outils avec leur image miroir horizontal.  
  
```  
BOOL Mirror();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si les images ont été correctement mis en miroir ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est utilisée pour prendre en charge des systèmes d’écriture de droite à gauche.  
  
##  <a name="a-namemirrorbitmapa--cmfctoolbarimagesmirrorbitmap"></a><a name="mirrorbitmap"></a>CMFCToolBarImages::MirrorBitmap  
 Remplace un bitmap avec son image miroir horizontal.  
  
```  
static BOOL MirrorBitmap(
    HBITMAP& hbmp,  
    int cxImage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in, out] `hbmp`  
 Handle de bitmap pour mettre en miroir.  
  
 [in] `cxImage`  
 Largeur de l’image en pixels.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’image a été correctement mis en miroir ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est utilisée pour prendre en charge des systèmes d’écriture de droite à gauche.  
  
##  <a name="a-namemirrorbitmapverta--cmfctoolbarimagesmirrorbitmapvert"></a><a name="mirrorbitmapvert"></a>CMFCToolBarImages::MirrorBitmapVert  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BOOL __stdcall MirrorBitmapVert(
    HBITMAP& hbmp,  
    int cyImage);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hbmp`  
 [in] `cyImage`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemirrorverta--cmfctoolbarimagesmirrorvert"></a><a name="mirrorvert"></a>CMFCToolBarImages::MirrorVert  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL MirrorVert();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonsyscolorchangea--cmfctoolbarimagesonsyscolorchange"></a><a name="onsyscolorchange"></a>CMFCToolBarImages::OnSysColorChange  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namepremultiplyalphaa--cmfctoolbarimagespremultiplyalpha"></a><a name="premultiplyalpha"></a>CMFCToolBarImages::PreMultiplyAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BOOL __stdcall PreMultiplyAlpha(
    HBITMAP hbmp,  
    BOOL bAutoCheckPremlt);

BOOL PreMultiplyAlpha(HBITMAP hbmp);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `hbmp`  
 [in] `bAutoCheckPremlt`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namembdisabletruecoloralphaa--cmfctoolbarimagesmbdisabletruecoloralpha"></a><a name="m_bdisabletruecoloralpha"></a>CMFCToolBarImages::m_bDisableTrueColorAlpha  
 `TRUE`Si alpha vraies fusion (couleur&32; bits) est désactivé.  
  
```  
static BOOL m_bDisableTrueColorAlpha;  
```  
  
### <a name="remarks"></a>Notes  
 Affectez à cette variable de membre `FALSE` pour activer les vraies mélange alpha pour les images de barre d’outils.  
  
 La valeur par défaut est `TRUE` pour la compatibilité descendante.  
  
##  <a name="a-namepreparedrawimagea--cmfctoolbarimagespreparedrawimage"></a><a name="preparedrawimage"></a>CMFCToolBarImages::PrepareDrawImage  
 Alloue les ressources qui sont nécessaires pour dessiner une image de la barre d’outils à une taille spécifiée.  
  
```  
BOOL PrepareDrawImage(
    CAfxDrawState& ds,  
    CSize sizeImageDest=CSize(0,
    0)  
    BOOL bFadeInactive=FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `ds`  
 Une référence à `CAfxDrawState` structure qui stocke les ressources allouées entre les phases de rendu d’image.  
  
 [in] `sizeImageDest`  
 Spécifie la taille d’une image de destination.  
  
 [in] `bFadeInactive`  
 `TRUE`Si vous souhaitez inactif dessin des images estompées.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si les ressources requises pour dessiner l’image de la barre d’outils ont été allouées avec succès, sinon `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Après avoir appelé cette méthode, vous pouvez appeler [CMFCToolBarImages::Draw](#draw) autant de fois. Fin de dessin, vous devez appeler [CMFCToolBarImages::EndDrawImage](#enddrawimage) pour libérer les ressources allouées par `PrepareDrawImage`.  
  
##  <a name="a-namesavea--cmfctoolbarimagessave"></a><a name="save"></a>CMFCToolBarImages::Save  
 Stocke les images de barre d’outils dans un fichier si ce jeu d’images de barre d’outils contient des images définies par l’utilisateur.  
  
```  
BOOL Save(LPCTSTR lpszBmpFileName=NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszBmpFileName`  
 Un chemin d’accès à un fichier disque.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si les images de barre d’outils ont été enregistrés avec succès ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette méthode pour stocker les images définies par l’utilisateur dans un fichier de disque. Si `lpszBmpFileName` est `NULL`, la méthode stocke l’image bitmap dans le fichier à partir duquel l’image bitmap a été chargé par le [CMFCToolBarImages::Load](#load) (méthode).  
  
##  <a name="a-namesetalwayslighta--cmfctoolbarimagessetalwayslight"></a><a name="setalwayslight"></a>CMFCToolBarImages::SetAlwaysLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetAlwaysLight(BOOL bAlwaysLight = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bAlwaysLight`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetdisabledimagealphaa--cmfctoolbarimagessetdisabledimagealpha"></a><a name="setdisabledimagealpha"></a>CMFCToolBarImages::SetDisabledImageAlpha  
 Définit la valeur du canal alpha (opacité) qui est utilisée pour les images désactivés.  
  
```  
static void SetDisabledImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nValue`  
 La nouvelle valeur du canal alpha.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette méthode pour définir une valeur alpha personnalisée pour les images désactivés. La valeur par défaut est de 127, ce qui entraîne des images de bouton désactivé soit translucide. Si vous affectez la valeur 0, les images désactivés est totalement transparents. Si vous définissez une valeur de 255, images désactivés sera complètement opaques.  
  
##  <a name="a-namesetfadedimagealphaa--cmfctoolbarimagessetfadedimagealpha"></a><a name="setfadedimagealpha"></a>CMFCToolBarImages::SetFadedImageAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall SetFadedImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nValue`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetimagesizea--cmfctoolbarimagessetimagesize"></a><a name="setimagesize"></a>CMFCToolBarImages::SetImageSize  
 Définit la taille de chaque image de la barre d’outils (taille de la source).  
  
```  
void SetImageSize(
    SIZE sizeImage,  
    BOOL bUpdateCount=FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `sizeImage`  
 La nouvelle taille des images de barre d’outils.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, la taille de l’image de la barre d’outils est 16 x 15 pixels. Appelez cette méthode si vous souhaitez utiliser des images de barre d’outils de taille différente.  
  
##  <a name="a-namesetlightpercentagea--cmfctoolbarimagessetlightpercentage"></a><a name="setlightpercentage"></a>CMFCToolBarImages::SetLightPercentage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetLightPercentage(int nValue);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nValue`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetmapto3dcolorsa--cmfctoolbarimagessetmapto3dcolors"></a><a name="setmapto3dcolors"></a>CMFCToolBarImages::SetMapTo3DColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetMapTo3DColors(BOOL bMapTo3DColors);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bMapTo3DColors`  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetpremultiplyautochecka--cmfctoolbarimagessetpremultiplyautocheck"></a><a name="setpremultiplyautocheck"></a>CMFCToolBarImages::SetPreMultiplyAutoCheck  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPreMultiplyAutoCheck(BOOL bAuto = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bAuto`  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetsingleimagea--cmfctoolbarimagessetsingleimage"></a><a name="setsingleimage"></a>CMFCToolBarImages::SetSingleImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetSingleImage();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesettransparentcolora--cmfctoolbarimagessettransparentcolor"></a><a name="settransparentcolor"></a>CMFCToolBarImages::SetTransparentColor  
 Définit la couleur transparente des images de barre d’outils.  
  
```  
COLORREF SetTransparentColor(COLORREF clrTransparent);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `clrTransparent`  
 Une valeur RVB.  
  
### <a name="return-value"></a>Valeur de retour  
 Couleur transparente précédente.  
  
### <a name="remarks"></a>Notes  
 Lorsque vous ou le framework appelle [CMFCToolBarImages::Draw](#draw), la méthode ne dessine pas tous les pixels qui correspond à la couleur spécifiée par `clrTransparent`.  
  
##  <a name="a-nameupdateimagea--cmfctoolbarimagesupdateimage"></a><a name="updateimage"></a>CMFCToolBarImages::UpdateImage  
 Met à jour une image de barre d’outils de défini par l’utilisateur à partir d’une image bitmap.  
  
```  
BOOL UpdateImage(
    int iImage,  
    HBITMAP hbmp);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `iImage`  
 Index de base zéro de l’image à mettre à jour.  
  
 [in] `hbmp`  
 Un handle de bitmap à partir de laquelle mettre à jour l’image.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si l’image a été mis à jour avec succès ; `FALSE` si la liste d’images n’est pas défini par l’utilisateur ou temporaire.  
  
##  <a name="a-nameconvertto32bitsa--cmfctoolbarimagesconvertto32bits"></a><a name="convertto32bits"></a>CMFCToolBarImages::ConvertTo32Bits  
 Convertit souligné 32 bpp images bitmaps.  
  
```  
BOOL ConvertTo32Bits(COLORREF clrTransparent = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Paramètres  
 `clrTransparent`  
 Spécifie la couleur transparente de soulignée bitmaps.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetbitsperpixela--cmfctoolbarimagesgetbitsperpixel"></a><a name="getbitsperpixel"></a>CMFCToolBarImages::GetBitsPerPixel  
 Retourne la résolution actuelle des images soulignées.  
  
```  
int GetBitsPerPixel() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur entière qui représente la résolution actuelle des images soulignés, en bits par pixel (bpp).  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetscalea--cmfctoolbarimagesgetscale"></a><a name="getscale"></a>CMFCToolBarImages::GetScale  
 Renvoie le rapport de mise à l’échelle actuelle d’images soulignées.  
  
```  
double GetScale() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur qui représente le rapport de mise à l’échelle actuelle.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisscaleda--cmfctoolbarimagesisscaled"></a><a name="isscaled"></a>CMFCToolBarImages::IsScaled  
 Indique si les images soulignés sont mis à l’échelle ou non.  
  
```  
BOOL IsScaled () const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si les images soulignés sont mis à l’échelle ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesmoothresizea--cmfctoolbarimagessmoothresize"></a><a name="smoothresize"></a>CMFCToolBarImages::SmoothResize  
 Sans heurts redimensionne les images soulignées.  
  
```  
BOOL SmoothResize(double dblImageScale);
```  
  
### <a name="parameters"></a>Paramètres  
 `dblImageScale`  
 Rapport de mise à l’échelle.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si le redimensionnement aboutit ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [CMFCToolBar (classe)](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton (classe)](../../mfc/reference/cmfctoolbarbutton-class.md)

