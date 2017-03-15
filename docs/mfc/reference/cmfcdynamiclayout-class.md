---
title: Classe de CMFCDynamicLayout | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
caps.latest.revision: 16
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
ms.openlocfilehash: 3066da5e1f874c2f0f2a2564b15582d7238c539b
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdynamiclayout-class"></a>CMFCDynamicLayout Class
Spécifie comment les contrôles dans une fenêtre sont déplacés et redimensionnés à mesure que l'utilisateur redimensionne la fenêtre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCDynamicLayout : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCDynamicLayout::CMFCDynamicLayout`|Construit un objet `CMFCDynamicLayout`.|  
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCDynamicLayout::AddItem](#additem)|Ajoute une fenêtre enfant, généralement un contrôle, à la liste des fenêtres contrôlées par le gestionnaire de disposition dynamique.|  
|[CMFCDynamicLayout::Adjust](#adjust)|Ajoute une fenêtre enfant, généralement un contrôle, à la liste des fenêtres contrôlées par le gestionnaire de disposition dynamique.|  
|[CMFCDynamicLayout::Create](#create)|Stocke et valide la fenêtre hôte.|  
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|Retourne un pointeur vers une fenêtre hôte.|  
|[CMFCDynamicLayout::GetMinSize](#getminsize)|Retourne la taille de fenêtre en dessous de laquelle la disposition n'est pas ajustée.|  
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|Récupère le rectangle pour la zone cliente active de la fenêtre.|  
|[CMFCDynamicLayout::HasItem](#hasitem)|Vérifie si un contrôle enfant a été ajouté à la disposition dynamique.|  
|[CMFCDynamicLayout::IsEmpty](#isempty)|Vérifie qu'aucune fenêtre enfant n'a été ajoutée à une disposition dynamique.|  
|[CMFCDynamicLayout::LoadResource](#loadresource)|Lit la disposition dynamique de la ressource AFX_DIALOG_LAYOUT, puis applique la disposition à la fenêtre hôte.|  
|statique [CMFCDynamicLayout::MoveHorizontal](#movehorizontal)|Obtient un [MoveSettings](#movesettings_structure) valeur qui définit le degré de contrôle enfant est déplacé horizontalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.|  
|statique [CMFCDynamicLayout::MoveHorizontalAndVertical](#movehorizontalandvertical)|Obtient un [MoveSettings](#movesettings_structure) valeur qui définit le degré de contrôle enfant est déplacé horizontalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.|  
|statique [CMFCDynamicLayout::MoveNone](#movenone)|Obtient un [MoveSettings](#movesettings_structure) valeur représentant aucun mouvement, verticale ou horizontale, pour un contrôle enfant.|  
|statique [CMFCDynamicLayout::MoveVertical](#movevertical)|Obtient un [MoveSettings](#movesettings_structure) valeur qui définit le degré de contrôle enfant est déplacé verticalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.|  
|[CMFCDynamicLayout::SetMinSize](#setminsize)|Définit la taille de fenêtre en dessous de laquelle la disposition n'est pas ajustée.|  
|statique [CMFCDynamicLayout::SizeHorizontal](#sizehorizontal)|Obtient un [SizeSettings](#sizesettings_structure) valeur qui définit le degré de contrôle enfant est redimensionné horizontalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.|  
|statique [CMFCDynamicLayout::SizeHorizontalAndVertical](#sizehorizontalandvertical)|Obtient un [SizeSettings](#sizesettings_structure) valeur qui définit le degré de contrôle enfant est redimensionné horizontalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.|  
|statique [CMFCDynamicLayout::SizeNone](#sizenone)|Obtient un [SizeSettings](#sizesettings_structure) valeur représentant aucune modification de la taille d’un contrôle enfant.|  
|statique [CMFCDynamicLayout::SizeVertical](#sizevertical)|Obtient un [SizeSettings](#sizesettings_structure) valeur qui définit le degré de contrôle enfant est redimensionné verticalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.|  
  
## <a name="nested-types"></a>Types imbriqués  
  
|Nom|Description|  
|----------|-----------------|  
|[Structure de CMFCDynamicLayout::MoveSettings](#movesettings_structure)|Encapsule les données de déplacement des contrôles dans une disposition dynamique.|  
|[Structure de CMFCDynamicLayout::SizeSettings](#sizesettings_structure)|Encapsule les données de changement de taille des contrôles dans une disposition dynamique.|  
  
## <a name="remarks"></a>Remarques  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxlayout.h  
  
##  <a name="a-nameadditema--cmfcdynamiclayoutadditem"></a><a name="additem"></a>CMFCDynamicLayout::AddItem  
 Ajoute une fenêtre enfant, généralement un contrôle, à la liste des fenêtres contrôlées par le gestionnaire de disposition dynamique.  
  
```  
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

 
BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```  
  
### <a name="parameters"></a>Paramètres  
 `hwnd`  
 Handle de la fenêtre à ajouter.  
  
 `nID`  
 ID du contrôle enfant à ajouter.  
  
 `moveSettings`  
 Structure qui décrit la façon dont le contrôle doit être déplacé quand la taille de fenêtre change.  
  
 `sizeSettings`  
 Structure qui décrit la façon dont le contrôle doit être redimensionné quand la taille de fenêtre change.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si l'élément a bien été ajouté ; sinon, FALSE.  
  
### <a name="remarks"></a>Notes  
 La position et la taille d'un contrôle enfant change de façon dynamique quand une fenêtre hôte est redimensionnée.  
  
##  <a name="a-nameadjusta--cmfcdynamiclayoutadjust"></a><a name="adjust"></a>CMFCDynamicLayout::Adjust  
 Ajoute une fenêtre enfant, généralement un contrôle, à la liste des fenêtres contrôlées par le gestionnaire de disposition dynamique.  
  
```  
void Adjust();
```  
  
### <a name="remarks"></a>Notes  
 La position et la taille d'un contrôle enfant change de façon dynamique quand une fenêtre hôte est redimensionnée.  
  
##  <a name="a-namecreatea--cmfcdynamiclayoutcreate"></a><a name="create"></a>CMFCDynamicLayout::Create  
 Stocke et valide la fenêtre hôte.  
  
```  
BOOL Create(CWnd* pHostWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 pHostWnd  
 Pointeur vers la fenêtre hôte.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la création a abouti ; sinon, FALSE.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegethostwnda--cmfcdynamiclayoutgethostwnd"></a><a name="gethostwnd"></a>CMFCDynamicLayout::GetHostWnd  
 Retourne un pointeur vers une fenêtre hôte.  
  
```  
CWnd* GetHostWnd();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la fenêtre hôte.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, la position de tous les contrôles enfants est recalculée par rapport à cette fenêtre.  
  
##  <a name="a-namegetminsizea--cmfcdynamiclayoutgetminsize"></a><a name="getminsize"></a>CMFCDynamicLayout::GetMinSize  
 Retourne la taille de fenêtre en dessous de laquelle la disposition n'est pas ajustée.  
  
```  
CSize GetMinSize();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Taille de fenêtre en dessous de laquelle la disposition n'est pas ajustée.  
  
### <a name="remarks"></a>Notes  
 La position et la taille d'un contrôle enfant sont modifiées de façon dynamique du moment où une fenêtre hôte est redimensionnée, mais il y a une taille minimale en dessous de laquelle la disposition n'est pas ajustée. L'utilisateur peut réduire la taille de la fenêtre, mais certaines parties de la fenêtre sont alors masquées.  
  
##  <a name="a-namegetwindowrecta--cmfcdynamiclayoutgetwindowrect"></a><a name="getwindowrect"></a>CMFCDynamicLayout::GetWindowRect  
 Récupère le rectangle pour la zone cliente active de la fenêtre.  
  
```  
void GetHostWndRect(CRect& rect,);
```  
  
### <a name="parameters"></a>Paramètres  
 `rect`  
 Une fois que la fonction a retourné une valeur, ce paramètre contient le rectangle englobant de la zone de présentation. Il s'agit d'un paramètre de sortie ; la valeur d'entrée est remplacée.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namehasitema--cmfcdynamiclayouthasitem"></a><a name="hasitem"></a>CMFCDynamicLayout::HasItem  
 Vérifie si un contrôle enfant a été ajouté à la disposition dynamique.  
  
```  
BOOL HasItem(HWND hwnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `hwnd`  
 Handle de fenêtre pour le contrôle.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la disposition contient déjà cet élément ; sinon, FALSE.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameisemptya--cmfcdynamiclayoutisempty"></a><a name="isempty"></a>CMFCDynamicLayout::IsEmpty  
 Vérifie qu'aucune fenêtre enfant n'a été ajoutée à une disposition dynamique.  
  
```  
BOOL IsEmpty();
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la disposition n'a pas d'éléments ; sinon, FALSE.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameloadresourcea--cmfcdynamiclayoutloadresource"></a><a name="loadresource"></a>CMFCDynamicLayout::LoadResource  
 Lit la disposition dynamique de la ressource AFX_DIALOG_LAYOUT, puis applique la disposition à la fenêtre hôte.  
  
```  
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);  
```  
  
### <a name="parameters"></a>Paramètres  
 `pHostWnd`  
 Pointeur vers la fenêtre hôte.  
  
 `lpResource`  
 Pointeur vers la mémoire tampon qui contient la ressource AFX_DIALOG_LAYOUT.  
  
 `dwSize`  
 Taille de la mémoire tampon en octets.  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la ressource est chargée et appliquée à la fenêtre hôte ; sinon, FALSE.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemovehorizontala--cmfcdynamiclayoutmovehorizontal"></a><a name="movehorizontal"></a>CMFCDynamicLayout::MoveHorizontal  
 Obtient un [MoveSettings](#movesettings_structure) valeur qui définit le degré de contrôle enfant est déplacé horizontalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.  
  
```  
static MoveSettings MoveHorizontal(int nRatio);  
```  
  
### <a name="parameters"></a>Paramètres  
 `nRatio`  
 Définit sous forme de pourcentage l'amplitude du déplacement d'un contrôle enfant sur le plan horizontal quand l'utilisateur redimensionne la fenêtre hôte.  
  
### <a name="return-value"></a>Valeur de retour  
 A [MoveSettings](#movesettings_structure) valeur encapsulée demandé par déplacer le rapport.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemovehorizontalandverticala--cmfcdynamiclayoutmovehorizontalandvertical"></a><a name="movehorizontalandvertical"></a>CMFCDynamicLayout::MoveHorizontalAndVertical  
 Obtient un [MoveSettings](#movesettings_structure) valeur qui définit le degré de contrôle enfant est déplacé horizontalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.  
  
```  
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);  
```  
  
### <a name="parameters"></a>Paramètres  
 `nXRatio`  
 Définit sous forme de pourcentage l'amplitude du déplacement d'un contrôle enfant sur le plan horizontal quand l'utilisateur redimensionne la fenêtre hôte.  
  
 `nYRatio`  
 Définit sous forme de pourcentage l'amplitude du déplacement d'un contrôle enfant sur le plan vertical quand l'utilisateur redimensionne la fenêtre hôte.  
  
### <a name="return-value"></a>Valeur de retour  
 A [MoveSettings](#movesettings_structure) valeur encapsulée demandé par déplacer le rapport.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemovenonea--cmfcdynamiclayoutmovenone"></a><a name="movenone"></a>CMFCDynamicLayout::MoveNone  
 Obtient un [MoveSettings](#movesettings_structure) valeur représentant aucun mouvement, verticale ou horizontale, pour un contrôle enfant.  
  
```  
static MoveSettings MoveNone();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [MoveSettings](#movesettings_structure) valeur qui résout le contrôle en place, afin qu’il ne déplace pas lorsque l’utilisateur redimensionne la fenêtre hôte.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemovesettingsstructurea--cmfcdynamiclayoutmovesettings-structure"></a><a name="movesettings_structure"></a>Structure de CMFCDynamicLayout::MoveSettings  
 Encapsule les données de déplacement des contrôles dans une disposition dynamique.  
  
```  
struct CMFCDynamicLayout::MoveSettings;  
```  
  
### <a name="remarks"></a>Remarques  
 Il s'agit d'une classe imbriquée dans `CMFCDynamicLayout`.  

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFCDynamicLayout::MoveSettings::IsHorizontal
Vérifie si les données de déplacement spécifient un déplacement horizontal différent de zéro.  
  

```  
BOOL IsHorizontal() const 
```  
  
## <a name="return-value"></a>Valeur de retour  
 TRUE si l'objet `MoveSettings` spécifie un déplacement horizontal différent de zéro.  

 ## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFCDynamicLayout::MoveSettings::IsNone
 Vérifie si les données de déplacement ne spécifient aucun déplacement.  
  
```  
BOOL IsNone() const 
```  
  
## <a name="return-value"></a>Valeur de retour  
 TRUE si l'objet `MoveSettings` ne spécifie aucun déplacement.  

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFCDynamicLayout::MoveSettings::IsVertical
  Vérifie si les données de déplacement spécifient un déplacement vertical différent de zéro.  
  
```  
BOOL IsVertical() const 
```  
  
## <a name="return-value"></a>Valeur de retour  
 TRUE si l'objet `MoveSettings` spécifie un déplacement vertical différent de zéro.  

##  <a name="a-namemoveverticala--cmfcdynamiclayoutmovevertical"></a><a name="movevertical"></a>CMFCDynamicLayout::MoveVertical  
 Obtient un [MoveSettings](#movesettings_structure) valeur qui définit le degré de contrôle enfant est déplacé verticalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.  
  
```  
static MoveSettings MoveVertical(int nRatio);  
```  
  
### <a name="parameters"></a>Paramètres  
 `nRatio`  
 Définit sous forme de pourcentage l'amplitude du déplacement d'un contrôle enfant sur le plan vertical quand l'utilisateur redimensionne la fenêtre hôte.  
  
### <a name="return-value"></a>Valeur de retour  
 A [MoveSettings](#movesettings_structure) valeur encapsulée demandé par déplacer le rapport.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetminsizea--cmfcdynamiclayoutsetminsize"></a><a name="setminsize"></a>CMFCDynamicLayout::SetMinSize  
 Définit la taille de fenêtre en dessous de laquelle la disposition n'est pas ajustée.  
  
```  
void SetMinSize(const CSize& size);
```  
  
### <a name="parameters"></a>Paramètres  
 `size`  
 Taille souhaitée en dessous de laquelle la disposition n'est pas ajustée.  
  
### <a name="remarks"></a>Remarques  
 La position et la taille d'un contrôle enfant sont modifiées de façon dynamique du moment où une fenêtre hôte est redimensionnée, mais il y a une taille minimale en dessous de laquelle la disposition n'est pas ajustée. L'utilisateur peut réduire la taille de la fenêtre, mais certaines parties de la fenêtre sont alors masquées.  
  
##  <a name="a-namesizehorizontala--cmfcdynamiclayoutsizehorizontal"></a><a name="sizehorizontal"></a>CMFCDynamicLayout::SizeHorizontal  
 Obtient un [SizeSettings](#sizesettings_structure) valeur qui définit le degré de contrôle enfant est redimensionné horizontalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.  
  
```  
static SizeSettings SizeHorizontal(int nRatio);  
```  
  
### <a name="parameters"></a>Paramètres  
 `nRatio`  
 Définit sous forme de pourcentage l'amplitude du redimensionnement d'un contrôle enfant sur le plan horizontal quand l'utilisateur redimensionne la fenêtre hôte.  
  
### <a name="return-value"></a>Valeur de retour  
 A [SizeSettings](#sizesettings_structure) valeur qui encapsule le ratio de la taille demandée.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesizehorizontalandverticala--cmfcdynamiclayoutsizehorizontalandvertical"></a><a name="sizehorizontalandvertical"></a>CMFCDynamicLayout::SizeHorizontalAndVertical  
 Obtient un [SizeSettings](#sizesettings_structure) valeur qui définit le degré de contrôle enfant est redimensionné horizontalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.  
  
```  
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);  
```  
  
### <a name="parameters"></a>Paramètres  
 `nXRatio`  
 Définit sous forme de pourcentage l'amplitude du redimensionnement d'un contrôle enfant sur le plan horizontal quand l'utilisateur redimensionne la fenêtre hôte.  
  
 `nYRatio`  
 Définit sous forme de pourcentage l'amplitude du redimensionnement d'un contrôle enfant sur le plan vertical quand l'utilisateur redimensionne la fenêtre hôte.  
  
### <a name="return-value"></a>Valeur de retour  
 A [SizeSettings](#sizesettings_structure) valeur qui encapsule le ratio de la taille demandée.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesizenonea--cmfcdynamiclayoutsizenone"></a><a name="sizenone"></a>CMFCDynamicLayout::SizeNone  
 Obtient un [SizeSettings](#sizesettings_structure) valeur représentant aucune modification de la taille d’un contrôle enfant.  
  
```  
static SizeSettings SizeNone();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [SizeSettings](#sizesettings_structure) valeur qui résout le contrôle à une certaine taille, afin qu’il ne modifie pas la taille lorsque l’utilisateur redimensionne la fenêtre hôte.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesizesettingsstructurea--cmfcdynamiclayoutsizesettings-structure"></a><a name="sizesettings_structure"></a>Structure de CMFCDynamicLayout::SizeSettings  
 Encapsule les données de changement de taille des contrôles dans une disposition dynamique.  
  
```  
struct CMFCDynamicLayout::SizeSettings;  
```  
  
### <a name="remarks"></a>Remarques  
 Il s'agit d'une classe imbriquée dans `CMFCDynamicLayout`.  

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFCDynamicLayout::SizeSettings::IsHorizontal
Vérifie si les données de redimensionnement spécifient un redimensionnement horizontal différent de zéro.  
  
```  
BOOL IsHorizontal() const 
```  
  
## <a name="return-value"></a>Valeur de retour  
 TRUE si l'objet `SizeSettings` spécifie un redimensionnement horizontal différent de zéro. 

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>CMFCDynamicLayout::SizeSettings::IsNone
Vérifie si les données de redimensionnement ne spécifient aucun redimensionnement.  
  
```  
BOOL IsNone() const 
```  
  
## <a name="return-value"></a>Valeur de retour  
 TRUE si l'objet `SizeSettings` ne spécifie aucun redimensionnement.  

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>CMFCDynamicLayout::SizeSettings::IsVertical
Vérifie si les données de redimensionnement spécifient un redimensionnement vertical différent de zéro.  
  
```  
BOOL IsVertical() const 
```  
  
## <a name="return-value"></a>Valeur de retour  
 TRUE si l'objet `SizeSettings` spécifie un redimensionnement vertical différent de zéro.  

##  <a name="a-namesizeverticala--cmfcdynamiclayoutsizevertical"></a><a name="sizevertical"></a>CMFCDynamicLayout::SizeVertical  
 Obtient un [SizeSettings](#sizesettings_structure) valeur qui définit le degré de contrôle enfant est redimensionné verticalement lorsque l’utilisateur redimensionne la fenêtre d’hébergement.  
  
```  
static SizeSettings SizeVertical(int nRatio);  
```  
  
### <a name="parameters"></a>Paramètres  
 `nRatio`  
 Définit sous forme de pourcentage l'amplitude du redimensionnement d'un contrôle enfant sur le plan vertical quand l'utilisateur redimensionne la fenêtre hôte.  
  
### <a name="return-value"></a>Valeur de retour  
 A [SizeSettings](#sizesettings_structure) valeur qui encapsule le ratio de la taille demandée.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

