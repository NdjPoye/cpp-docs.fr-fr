---
title: Classe de CBitmapButton | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
dev_langs:
- C++
helpviewer_keywords:
- buttons, bitmap
- CBitmapButton class
- bitmaps, button controls
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
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
ms.sourcegitcommit: 0b07f6b12e178d8e324313ea3b0f6de9ae7420c9
ms.openlocfilehash: 16d39cb380b75e6dcef71dda01626f120d5c12fb
ms.lasthandoff: 02/24/2017

---
# <a name="cbitmapbutton-class"></a>Classe de CBitmapButton
Crée des contrôles de bouton de commande étiquetés avec des images bitmap au lieu de texte.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CBitmapButton : public CButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|Construit un objet `CBitmapButton`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CBitmapButton::AutoLoad](#autoload)|Associe un bouton dans une boîte de dialogue avec un objet de la `CBitmapButton` (classe), charge le bitmap(s) par nom et tailles, le bouton pour s’ajuster à l’image bitmap.|  
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|Initialise l’objet en chargement d’une ou plusieurs ressources bitmap nommée à partir du fichier de ressources de l’application et en associant les bitmaps à l’objet.|  
|[CBitmapButton::SizeToContent](#sizetocontent)|Redimensionne le bouton en fonction de l’image bitmap.|  
  
## <a name="remarks"></a>Notes  
 `CBitmapButton`les objets contiennent jusqu'à quatre images bitmap, qui contiennent des images pour les différents États qu’un bouton peut assumer : haut (ou normale), bas (ou sélectionnée), axé et désactivée. Seule la première bitmap est requise ; les autres sont facultatives.  
  
 Les images de boutons bitmap incluent la bordure autour de l’image, ainsi que l’image elle-même. La bordure généralement joue un rôle dans l’affichage de l’état du bouton. Par exemple, l’image bitmap de l’état actif est généralement comme celle de l’état des mais avec une marge de rectangle en pointillé à partir de la bordure ou un trait épais à la bordure. La bitmap de l’état désactivé généralement similaire à celui pour l’état opérationnel, mais n’a contraste inférieur (par exemple, une sélection de menu estompé ou grisé).  
  
 Ces images peuvent être de n’importe quelle taille, mais tous sont traités comme s’il s’agissait de la même taille que l’image bitmap de l’état opérationnel.  
  
 Différentes applications exigent des différentes combinaisons des images bitmap :  
  
|Monter|Bas|Avec focus|Désactivé|Application|  
|--------|----------|-------------|--------------|-----------------|  
|×||||Bitmap|  
|×|×|||Bouton sans **WS_TABSTOP** style|  
|×|×|×|×|Bouton de la boîte de dialogue avec tous les États|  
|×|×|×||Bouton de la boîte de dialogue avec **WS_TABSTOP** style|  
  
 Lorsque vous créez un contrôle de bouton de bitmap, définissez la **BS_OWNERDRAW** style pour spécifier que le bouton owner-drawn. Ainsi, Windows envoie le `WM_MEASUREITEM` et `WM_DRAWITEM` messages pour le bouton ; le framework traite ces messages et gère l’apparence du bouton pour vous.  
  
### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>Pour créer un contrôle de bouton de bitmap dans la zone cliente d’une fenêtre  
  
1.  Créer un à quatre images bitmap du bouton.  
  
2.  Construire la [CBitmapButton](#cbitmapbutton) objet.  
  
3.  Appelez le [créer](../../mfc/reference/cbutton-class.md#create) (fonction) pour créer le contrôle bouton Windows et l’attacher à la `CBitmapButton` objet.  
  
4.  Appelez le [LoadBitmaps](#loadbitmaps) fonction membre pour charger les ressources bitmap d’après le bouton bitmap est construit.  
  
### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>Pour inclure un contrôle bouton bitmap dans une boîte de dialogue  
  
1.  Créer un à quatre images bitmap du bouton.  
  
2.  Créer un modèle de boîte de dialogue avec un bouton de dessin positionné où vous souhaitez que le bouton de la bitmap. La taille du bouton dans le modèle n’a pas d’importance.  
  
3.  Définir la légende du bouton à une valeur comme « **MYIMAGE**» et définissez un symbole pour le bouton tel que **IDC_MYIMAGE**.  
  
4.  Dans le script de ressources de votre application, donnez à chacune des images créées pour le bouton d’un code construit en ajoutant une lettre « U », « D », « F », ou « X » (pour haut, bas, axé et désactivée) à la chaîne utilisée pour la légende du bouton dans l’étape 3. Pour la légende du bouton « **MYIMAGE**, », par exemple, l’ID est « **MYIMAGEU**, » « **MYIMAGED**, » » **MYIMAGEF**, » et « **MYIMAGEX**. » Vous **doit** spécifier l’ID de vos images dans des guillemets doubles. Dans le cas contraire, l’éditeur de ressources affecte un entier à la ressource et MFC échoue lors du chargement de l’image.  
  
5.  Dans la classe de boîte de dialogue de votre application (dérivée de `CDialog`), ajoutez un `CBitmapButton` objet membre.  
  
6.  Dans le `CDialog` l’objet [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) appel de routine, le `CBitmapButton` l’objet [AutoLoad](#autoload) fonction, à l’aide, en tant que paramètres, ID de contrôle du bouton et la `CDialog` l’objet **cela** pointeur.  
  
 Si vous souhaitez traiter les messages de notification de Windows, tel que **BN_CLICKED**, envoyé par un contrôle de bouton de la bitmap à son parent (généralement une classe dérivée de **CDialog)**, ajouter à la `CDialog`-objet une table des messages fonction de membre entrée et le Gestionnaire de messages pour chaque message dérivée. Les notifications envoyées par un `CBitmapButton` objet sont les mêmes que celles envoyées par une [CButton](../../mfc/reference/cbutton-class.md) objet.  
  
 La classe [CToolBar](../../mfc/reference/ctoolbar-class.md) adopte une approche différente pour les boutons de la bitmap.  
  
 Pour plus d’informations sur `CBitmapButton`, consultez [contrôles](../../mfc/controls-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxext.h  
  
##  <a name="autoload"></a>CBitmapButton::AutoLoad  
 Associe un bouton dans une boîte de dialogue avec un objet de la `CBitmapButton` (classe), charge le bitmap(s) par nom et tailles, le bouton pour s’ajuster à l’image bitmap.  
  
```  
BOOL AutoLoad(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 ID de contrôle. du bouton  
  
 `pParent`  
 Pointeur vers l’objet qui possède le bouton.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le `AutoLoad` fonction pour initialiser un bouton de dessin dans une boîte de dialogue un bouton bitmap. Des instructions pour l’utilisation de cette fonction se trouvent dans la section Notes pour la `CBitmapButton` classe.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#75;](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]  
  
##  <a name="cbitmapbutton"></a>CBitmapButton::CBitmapButton  
 Crée un objet `CBitmapButton`.  
  
```  
CBitmapButton();
```  
  
### <a name="remarks"></a>Remarques  
 Après avoir créé le C++ `CBitmapButton` de l’objet, appelez [CButton::Create](../../mfc/reference/cbutton-class.md#create) pour créer le contrôle bouton Windows et l’attacher à la `CBitmapButton` objet.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#57;](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]  
  
##  <a name="loadbitmaps"></a>CBitmapButton::LoadBitmaps  
 Utilisez cette fonction lorsque vous voulez charger des images bitmap identifiés par leurs noms de ressources ou les numéros d’identification, ou lorsque vous ne pouvez pas utiliser le `AutoLoad` car, par exemple, vous créez un bouton bitmap qui ne fait pas partie d’une boîte de dialogue de la fonction.  
  
```  
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,  
    LPCTSTR lpszBitmapResourceSel = NULL,  
    LPCTSTR lpszBitmapResourceFocus = NULL,  
    LPCTSTR lpszBitmapResourceDisabled = NULL);

 
BOOL LoadBitmaps(
    UINT nIDBitmapResource,  
    UINT nIDBitmapResourceSel = 0,  
    UINT nIDBitmapResourceFocus = 0,  
    UINT nIDBitmapResourceDisabled = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszBitmapResource*  
 Pointe vers la chaîne terminée par le caractère null qui contient le nom de la bitmap de l’option normal d’un bouton bitmap ou « up » de l’état. Obligatoire.  
  
 *lpszBitmapResourceSel*  
 Pointe vers la chaîne terminée par le caractère null qui contient le nom de l’image bitmap pour un bouton bitmap est sélectionné ou état « inactif ». Peut être **NULL**.  
  
 *lpszBitmapResourceFocus*  
 Pointe vers la chaîne terminée par le caractère null qui contient le nom de l’image bitmap pour un bouton bitmap axée sur l’état. Peut être **NULL**.  
  
 *lpszBitmapResourceDisabled*  
 Pointe vers la chaîne terminée par le caractère null qui contient le nom de la bitmap de l’état désactivé d’un bouton bitmap. Peut être **NULL**.  
  
 *nIDBitmapResource*  
 Spécifie le numéro d’ID de ressource de la ressource bitmap de l’option normal d’un bouton bitmap ou « up » de l’état. Obligatoire.  
  
 *nIDBitmapResourceSel*  
 Spécifie le numéro d’ID de ressource de la ressource bitmap pour un bouton bitmap est sélectionné ou à l’état « inactif ». Peut être 0.  
  
 *nIDBitmapResourceFocus*  
 Spécifie le numéro d’ID de ressource de la ressource bitmap de l’état actif d’un bouton bitmap. Peut être 0.  
  
 *nIDBitmapResourceDisabled*  
 Spécifie le numéro d’ID de ressource de la ressource bitmap de l’état désactivé d’un bouton bitmap. Peut être 0.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#58;](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]  
  
##  <a name="sizetocontent"></a>CBitmapButton::SizeToContent  
 Appelez cette fonction pour redimensionner un bouton bitmap à la taille de la bitmap.  
  
```  
void SizeToContent();
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#59;](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC CTRLTEST](../../visual-cpp-samples.md)   
 [CButton (classe)](../../mfc/reference/cbutton-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)

