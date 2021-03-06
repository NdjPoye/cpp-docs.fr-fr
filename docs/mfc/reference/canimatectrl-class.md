---
title: CAnimateCtrl (classe) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimateCtrl
- AFXCMN/CAnimateCtrl
- AFXCMN/CAnimateCtrl::CAnimateCtrl
- AFXCMN/CAnimateCtrl::Close
- AFXCMN/CAnimateCtrl::Create
- AFXCMN/CAnimateCtrl::CreateEx
- AFXCMN/CAnimateCtrl::IsPlaying
- AFXCMN/CAnimateCtrl::Open
- AFXCMN/CAnimateCtrl::Play
- AFXCMN/CAnimateCtrl::Seek
- AFXCMN/CAnimateCtrl::Stop
dev_langs:
- C++
helpviewer_keywords:
- CAnimateCtrl [MFC], CAnimateCtrl
- CAnimateCtrl [MFC], Close
- CAnimateCtrl [MFC], Create
- CAnimateCtrl [MFC], CreateEx
- CAnimateCtrl [MFC], IsPlaying
- CAnimateCtrl [MFC], Open
- CAnimateCtrl [MFC], Play
- CAnimateCtrl [MFC], Seek
- CAnimateCtrl [MFC], Stop
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1032ffac46af6370c45f4bcb2c251ddae73ce69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="canimatectrl-class"></a>CAnimateCtrl (classe)
Fournit les fonctionnalités du contrôle commun d'animation Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CAnimateCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|Construit un objet `CAnimateCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAnimateCtrl::Close](#close)|Ferme le clip AVI.|  
|[CAnimateCtrl::Create](#create)|Crée un contrôle animation et l’attache à un `CAnimateCtrl` objet.|  
|[CAnimateCtrl::CreateEx](#createex)|Crée un contrôle animation avec les styles étendus Windows spécifiés et l’attache à un `CAnimateCtrl` objet.|  
|[CAnimateCtrl::IsPlaying](#isplaying)|Indique si un clip Audio-Video Interleaved (AVI) en cours de lecture.|  
|[CAnimateCtrl::Open](#open)|Ouvre un clip AVI à partir d’un fichier ou une ressource et affiche le premier frame.|  
|[CAnimateCtrl::Play](#play)|Lit le clip AVI sans son.|  
|[CAnimateCtrl::Seek](#seek)|Affiche un frame unique sélectionné du clip AVI.|  
|[CAnimateCtrl::Stop](#stop)|Arrête la lecture du clip AVI.|  
  
## <a name="remarks"></a>Notes  
 Ce contrôle (et par conséquent la `CAnimateCtrl` classe) est disponible uniquement pour les programmes s’exécutant sous Windows 95, Windows 98 et Windows NT version 3.51 et ultérieures.  
  
 Un contrôle animation est une fenêtre rectangulaire qui affiche un clip au format AVI (Audio Video Interleaved), le format audio/vidéo Windows standard. Un clip AVI est une série d’images bitmap, comme un film.  
  
 Contrôles animation peuvent lire uniquement les éléments AVI simples. Plus précisément, les éléments devant être lu par un contrôle animation doivent remplir les conditions suivantes :  
  
-   Il doit y avoir un seul flux vidéo et doit avoir au moins une image.  
  
-   Il peut y avoir au plus deux flux de données dans le fichier (en général, l’autres flux de données, le cas échéant, est un flux audio, bien que le contrôle animation ignore les informations audio).  
  
-   L’élément doit être décompressé ou compressé avec la compression de RLE8.  
  
-   Aucune modification de la palette est autorisée dans le flux vidéo.  
  
 Vous pouvez ajouter du clip AVI à votre application comme une ressource AVI, ou elle peut accompagner votre application dans un fichier AVI distinct.  
  
 Étant donné que votre thread continue de s’exécuter pendant que le clip AVI est affiché, une utilisation courante d’un contrôle animation consiste à indiquer l’activité du système pendant une longue opération. Par exemple, la boîte de dialogue Rechercher de l’Explorateur de fichiers affiche une loupe qui se déplace en tant que le système recherche un fichier.  
  
 Si vous créez un `CAnimateCtrl` de l’objet dans une boîte de dialogue zone ou à partir d’une ressource de boîte de dialogue à l’aide de l’éditeur de boîte de dialogue, il est automatiquement détruit lorsque l’utilisateur ferme la boîte de dialogue.  
  
 Si vous créez un `CAnimateCtrl` de l’objet dans une fenêtre, vous devrez peut-être à détruire. Si vous créez le `CAnimateCtrl` de l’objet sur la pile, il est supprimé automatiquement. Si vous créez le `CAnimateCtrl` objet sur le tas à l’aide de la **nouveau** (fonction), vous devez appeler **supprimer** sur l’objet à détruire. Si vous dérivez une nouvelle classe à partir de `CAnimateCtrl` et allouer de mémoire dans cette classe, remplacez le `CAnimateCtrl` destructeur pour éliminer les allocations.  
  
 Pour plus d’informations sur l’utilisation de `CAnimateCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et [à l’aide de CAnimateCtrl](../../mfc/using-canimatectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxcmn.h  
  
##  <a name="canimatectrl"></a>  CAnimateCtrl::CAnimateCtrl  
 Construit un objet `CAnimateCtrl`.  
  
```  
CAnimateCtrl();
```  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler la [créer](#create) fonction membre avant d’effectuer d’autres opérations sur l’objet que vous créez.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]  
  
##  <a name="close"></a>  CAnimateCtrl::Close  
 Ferme le clip AVI qui a été précédemment ouvert dans le contrôle animation (le cas échéant) et le supprime de la mémoire.  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="create"></a>  CAnimateCtrl::Create  
 Crée un contrôle animation et l’attache à un `CAnimateCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Spécifie le style du contrôle de l’animation. Appliquer n’importe quelle combinaison de styles décrits dans la section Notes ci-dessous et les styles de contrôle animation décrites dans windows [Styles de contrôle Animation](http://msdn.microsoft.com/library/windows/desktop/bb761886) dans le Kit de développement logiciel Windows.  
  
 `rect`  
 Spécifie la position et la taille d' un contrôle animation. Il peut être soit un [CRect](../../atl-mfc-shared/reference/crect-class.md) objet ou un [RECT](../../mfc/reference/rect-structure1.md) structure.  
  
 `pParentWnd`  
 Spécifie les fenêtre parente d' un contrôle animation généralement un `CDialog`. Il ne doit pas être **NULL.**  
  
 `nID`  
 Spécifie l’ID. du contrôle de l’animation  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Vous construisez un `CAnimateCtrl` en deux étapes. Tout d’abord, appelez le constructeur, puis **créer**, ce qui crée le contrôle de l’animation et l’attache à le `CAnimateCtrl` objet.  
  
 Appliquez ce qui suit [styles de fenêtre](../../mfc/reference/styles-used-by-mfc.md#window-styles) à un contrôle de l’animation.  
  
- **WS_CHILD** toujours  
  
- **WS_VISIBLE** généralement  
  
- **WS_DISABLED** rarement  
  
 Si vous souhaitez utiliser les styles étendus windows avec votre contrôle animation, appelez [CreateEx](#createex) au lieu de **créer**.  
  
 Outre les styles de fenêtre répertoriés ci-dessus, il pouvez que vous souhaitez appliquer une ou plusieurs des styles de contrôle animation à un contrôle animation. Consultez le Kit de développement logiciel Windows pour plus d’informations sur [styles de contrôle animation](http://msdn.microsoft.com/library/windows/desktop/bb761886).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="createex"></a>  CAnimateCtrl::CreateEx  
 Crée un contrôle (une fenêtre enfant) et l’associe le `CAnimateCtrl` objet.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwExStyle`  
 Spécifie le style étendu du contrôle en cours de création. Pour obtenir la liste des styles étendus de Windows, consultez le `dwExStyle` paramètre [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) dans le Kit de développement logiciel Windows.  
  
 `dwStyle`  
 Spécifie le style du contrôle de l’animation. Appliquer n’importe quelle combinaison de la fenêtre et de styles de contrôle animation décrites dans [Styles de contrôle Animation](http://msdn.microsoft.com/library/windows/desktop/bb761886) dans le Kit de développement logiciel Windows.  
  
 `rect`  
 Une référence à un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure décrivant la taille et la position de la fenêtre doit être créée, en coordonnées clientes de `pParentWnd`.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre qui est le parent du contrôle.  
  
 `nID`  
 ID de fenêtre enfant. du contrôle  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Utilisez `CreateEx` au lieu de [créer](#create) pour appliquer des styles étendus Windows spécifiés par la préface style étendu de Windows **WS_EX_**.  
  
##  <a name="isplaying"></a>  CAnimateCtrl::IsPlaying  
 Indique si un clip Audio-Video Interleaved (AVI) en cours de lecture.  
  
```  
BOOL IsPlaying() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` la lecture d’un clip AVI ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [ACM_ISPLAYING](http://msdn.microsoft.com/library/windows/desktop/bb761895) message, ce qui est décrit dans le Kit de développement logiciel Windows.  
  
##  <a name="open"></a>  CAnimateCtrl::Open  
 Appelez cette fonction pour ouvrir un clip AVI et afficher sa première image.  
  
```  
BOOL Open(LPCTSTR lpszFileName);  
BOOL Open(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFileName`  
 A `CString` objet ou un pointeur vers une chaîne se terminant par null qui contient le nom du fichier AVI ou le nom d’une ressource AVI. Si ce paramètre est **NULL**, le système ferme le clip AVI qui a été ouverte précédemment pour le contrôle de l’animation, le cas échéant.  
  
 `nID`  
 L’identificateur de ressource AVI. Si ce paramètre est **NULL**, le système ferme le clip AVI qui a été ouverte précédemment pour le contrôle de l’animation, le cas échéant.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 La ressource AVI est chargée à partir du module qui a créé le contrôle de l’animation.  
  
 **Ouvrez** ne prend pas en charge son dans un clip AVI ; vous pouvez ouvrir uniquement les éléments AVI en mode silencieux.  
  
 Si le contrôle de l’animation a la `ACS_AUTOPLAY` style, le contrôle animation démarre automatiquement la lecture de l’élément immédiatement après, il s’ouvre. Il continue à lire l’élément en arrière-plan pendant que votre thread continue l’exécution. Lorsque l’élément est effectuée pour la lecture, il sera automatiquement répété.  
  
 Si le contrôle de l’animation a la `ACS_CENTER` du clip AVI sera centré dans le contrôle de style, et la taille du contrôle ne change pas. Si le contrôle animation n’a pas la `ACS_CENTER` style, le contrôle doit être redimensionné à la taille des images du clip AVI ouverture du clip AVI. La position de l’angle supérieur gauche du contrôle pas change, uniquement la taille du contrôle.  
  
 Si le contrôle de l’animation a la `ACS_TRANSPARENT` style, la première image sera dessinée à l’aide d’un arrière-plan transparent au lieu de la couleur d’arrière-plan spécifiée dans l’élément d’animation.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="play"></a>  CAnimateCtrl::Play  
 Appelez cette fonction pour lire un clip AVI dans un contrôle de l’animation.  
  
```  
BOOL Play(
    UINT nFrom,  
    UINT nTo,  
    UINT nRep);
```  
  
### <a name="parameters"></a>Paramètres  
 `nFrom`  
 Index de base zéro de l’image où la lecture commence. Valeur doit être inférieure à 65 536. Valeur 0 signifie commence par le premier frame du clip AVI.  
  
 `nTo`  
 Index de base zéro de l’image où lecture se termine. Valeur doit être inférieure à 65 536. Une valeur de - 1 signifie la dernière image du clip AVI.  
  
 *nRep*  
 Nombre de fois pour relire le clip AVI. Une valeur de - 1 signifie que le fichier de relecture indéfiniment.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Le contrôle de l’animation est lue l’élément en arrière-plan pendant que votre thread continue l’exécution. Si le contrôle de l’animation a `ACS_TRANSPARENT` style, du clip AVI est lu à l’aide d’un arrière-plan transparent, plutôt que la couleur d’arrière-plan spécifiée dans l’élément d’animation.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="seek"></a>  CAnimateCtrl::Seek  
 Appelez cette fonction pour afficher statiquement un seul frame de votre clip AVI.  
  
```  
BOOL Seek(UINT nTo);
```  
  
### <a name="parameters"></a>Paramètres  
 `nTo`  
 Index de base zéro de l’image à afficher. Valeur doit être inférieure à 65 536. La valeur 0 permet d’afficher le premier frame du clip AVI. La valeur -1 permet d’afficher la dernière image du clip AVI.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="remarks"></a>Notes  
 Si le contrôle de l’animation a `ACS_TRANSPARENT` style, du clip AVI sera dessiné à l’aide d’un arrière-plan transparent au lieu de la couleur d’arrière-plan spécifiée dans l’élément d’animation.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
##  <a name="stop"></a>  CAnimateCtrl::Stop  
 Appelez cette fonction pour arrêter la lecture d’un clip AVI dans un contrôle de l’animation.  
  
```  
BOOL Stop();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro en cas de réussite ; sinon, zéro.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CAnimateCtrl::CAnimateCtrl](#canimatectrl).  
  
## <a name="see-also"></a>Voir aussi  
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](#create)   
 [ON_CONTROL](message-map-macros-mfc.md#on_control)

