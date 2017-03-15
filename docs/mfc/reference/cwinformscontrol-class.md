---
title: Classe de CWinFormsControl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsControl
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsControl class
- Windows Forms [C++], MFC support
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
caps.latest.revision: 28
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
ms.openlocfilehash: 49e24c04deda3df5683908fa9ca485cf7802214b
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformscontrol-class"></a>CWinFormsControl (classe)
Fournit les fonctionnalités de base pour l'hébergement d'un contrôle Windows Forms.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### <a name="parameters"></a>Paramètres  
 `TManagedControl`  
 Un contrôle Windows Forms .NET Framework s’affichent dans l’application MFC.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|Construit un objet de wrapper de contrôle Windows Forms de MFC.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Crée un contrôle Windows Forms dans un conteneur de MFC.|  
|[CWinFormsControl::GetControl](#getcontrol)|Récupère un pointeur vers le contrôle Windows Forms.|  
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Récupère un handle pour le contrôle Windows Forms.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|Remplace [CWinFormsControl::GetControl](#getcontrol) dans les expressions.|  
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Convertit un type comme un pointeur vers un contrôle Windows Forms.|  
  
## <a name="remarks"></a>Remarques  
 La `CWinFormsControl` classe fournit les fonctionnalités de base pour l’hébergement d’un contrôle Windows Forms.  
  
 Pour plus d’informations sur l’utilisation de Windows Forms, consultez [à l’aide d’un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Votre code MFC ne doit pas mettre en cache des handles de fenêtre (généralement stockés dans `m_hWnd`). Certaines propriétés des contrôles Windows Forms exigent que Win32 sous-jacente `Window` détruit et recréé à l’aide de `DestroyWindow` et `CreateWindow`. Les handles d’implémentation MFC Windows Forms le `Destroy` et `Create` événements des contrôles pour mettre à jour le `m_hWnd` membre.  
  
> [!NOTE]
>  Intégration de MFC Windows Forms fonctionne uniquement dans les projets qui se lient dynamiquement avec MFC (dans lesquels AFXDLL est défini).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwinforms.h  
  
##  <a name="a-namecreatemanagedcontrola--cwinformscontrolcreatemanagedcontrol"></a><a name="createmanagedcontrol"></a>CWinFormsControl::CreateManagedControl  
 Crée un contrôle Windows Forms dans un conteneur de MFC.  
  
```  
inline BOOL CreateManagedControl(
    System::Type^ pType,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID)  
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);

 
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    int nPlaceHolderID,  
    CWnd* pParentWnd);

 
inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `pType`  
 Le type de données du contrôle à créer. Doit être un [Type](https://msdn.microsoft.com/en-us/library/system.type) type de données.  
  
 `dwStyle`  
 Style de fenêtre à appliquer au contrôle. Spécifier une combinaison de [Styles de fenêtre](../../mfc/reference/window-styles.md). Actuellement, seuls les styles suivants sont pris en charge : WS_TABSTOP, WS_VISIBLE, WS_DISABLED et WS_GROUP.  
  
 `rect`  
 A [Rect, Structure](../../mfc/reference/rect-structure1.md) qui définit les coordonnées des angles supérieur gauche et à droite du contrôle (première surcharge uniquement).  
  
 `nPlaceHolderID`  
 Le handle du contrôle statique titulaire placé dans l’éditeur de ressources. Le contrôle Windows Forms qui vient d’être créé remplace le contrôle statique, en supposant que sa position, ordre de plan et des styles (deuxième surcharge uniquement).  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parente.  
  
 `nID`  
 Le numéro d’ID de ressource à affecter au contrôle nouvellement créé.  
  
 `pControl`  
 Une instance d’un contrôle Windows Forms à associer à la [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) (surcharge quatrième uniquement) de l’objet.  
  
### <a name="return-value"></a>Valeur de retour  
 En cas de réussite, retourne une valeur différente de zéro. En cas d’échec, retourne zéro.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode instancie un contrôle Windows Forms .NET Framework dans un conteneur de MFC.  
  
 La première surcharge de la méthode accepte un type de données .NET Framework `pType` pour que MFC peuvent instancier un nouvel objet de ce type. `pType`doit être un [Type](https://msdn.microsoft.com/en-us/library/system.type) type de données.  
  
 La deuxième surcharge de la méthode crée un contrôle Windows Forms en fonction de la `TManagedControl` paramètre de modèle de la `CWinFormsControl` classe. La taille et la position du contrôle est basé sur le `RECT` structure passée à la méthode. Seulement `dwStyle` est important pour les styles.  
  
 La troisième surcharge de la méthode crée un contrôle Windows Forms qui remplace un contrôle statique, détruire et en supposant que sa position, ordre de plan et des styles. Le contrôle statique sert uniquement d’espace réservé pour le contrôle Windows Forms. Lors de la création du contrôle, cette surcharge combine les styles de `dwStyle` avec des styles de ressource d' un contrôle statique.  
  
 La quatrième surcharge de la méthode vous permet de passer d’un contrôle Windows Forms déjà instancié `pControl` qui encapsule MFC. Il doit être du même type que le `TManagedControl` paramètre de modèle de la `CWinFormsControl` classe.  
  
 Consultez la page [à l’aide d’un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) pour obtenir des exemples sur l’utilisation de Windows Form contrôle.  
  
##  <a name="a-namecwinformscontrola--cwinformscontrolcwinformscontrol"></a><a name="cwinformscontrol"></a>CWinFormsControl::CWinFormsControl  
 Construit un objet de wrapper de contrôle Windows Forms de MFC.  
  
```  
CWinFormsControl();
```  
  
### <a name="remarks"></a>Remarques  
 Le contrôle Windows Forms est instancié lorsque vous appelez [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="a-namegetcontrola--cwinformscontrolgetcontrol"></a><a name="getcontrol"></a>CWinFormsControl::GetControl  
 Récupère un pointeur vers le contrôle Windows Forms.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le contrôle Windows Forms.  
  
### <a name="example"></a>Exemple  
  Consultez la page [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="a-namegetcontrolhandlea--cwinformscontrolgetcontrolhandle"></a><a name="getcontrolhandle"></a>CWinFormsControl::GetControlHandle  
 Récupère un handle pour le contrôle Windows Forms.  
  
```  
inline HWND GetControlHandle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un handle pour le contrôle Windows Forms.  
  
### <a name="remarks"></a>Notes  
 `GetControlHandle`est une méthode d’assistance qui retourne le handle de fenêtre stocké dans les propriétés du contrôle .NET Framework. La valeur de handle de fenêtre est copiée vers [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) lors de l’appel à [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach).  
  
##  <a name="a-nameoperator-gta--cwinformscontroloperator--gt"></a><a name="operator_-_gt"></a>CWinFormsControl::operator-&gt;  
 Remplace [CWinFormsControl::GetControl](#getcontrol) dans les expressions.  
  
```  
inline TManagedControl^  operator->() const;  
```  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur fournit une syntaxe qui remplace `GetControl` dans les expressions.  
  
 Pour plus d’informations sur les Windows Forms, consultez [à l’aide d’un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="a-nameoperatortmanagedcontrola--cwinformscontroloperator-tmanagedcontrol"></a><a name="operator_tmanagedcontrol"></a>CWinFormsControl::operator TManagedControl ^  
 Convertit un type comme un pointeur vers un contrôle Windows Forms.  
  
```  
inline operator TManagedControl^() const;  
```  
  
### <a name="remarks"></a>Remarques  
 Cet opérateur passe `CWinFormsControl<``TManagedControl``>` aux fonctions qui acceptent un pointeur vers un contrôle Windows Forms.  
  
## <a name="see-also"></a>Voir aussi  
 [CWinFormsDialog (classe)](../../mfc/reference/cwinformsdialog-class.md)   
 [Classe CWinFormsView](../../mfc/reference/cwinformsview-class.md)

