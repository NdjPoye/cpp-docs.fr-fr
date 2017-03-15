---
title: CPrintInfo (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintInfo
dev_langs:
- C++
helpviewer_keywords:
- CPrintInfo structure
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ffa72acc58e0ac1a387e67e6542abcd466be9640
ms.lasthandoff: 02/24/2017

---
# <a name="cprintinfo-structure"></a>CPrintInfo (Structure)
Stocke les informations relatives à un travail d’impression ou Aperçu avant impression.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CPrintInfo  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CPrintInfo::GetFromPage](#getfrompage)|Retourne le numéro de la première page imprimée.|  
|[CPrintInfo::GetMaxPage](#getmaxpage)|Retourne le numéro de la dernière page du document.|  
|[CPrintInfo::GetMinPage](#getminpage)|Retourne le numéro de la première page du document.|  
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|Retourne le nombre de pages qui précède la première page d’un élément DocObject imprimée dans un travail d’impression DocObject combiné.|  
|[CPrintInfo::GetToPage](#gettopage)|Retourne le numéro de la dernière page imprimée.|  
|[CPrintInfo::SetMaxPage](#setmaxpage)|Définit le numéro de la dernière page du document.|  
|[CPrintInfo::SetMinPage](#setminpage)|Définit le numéro de la première page du document.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|Contient un indicateur qui signale si l’infrastructure doit continuer la boucle d’impression.|  
|[CPrintInfo::m_bDirect](#m_bdirect)|Contient un indicateur qui indique si le document est imprimé directement (sans afficher la boîte de dialogue d’impression).|  
|[CPrintInfo::m_bDocObject](#m_bdocobject)|Contient un indicateur qui indique si le document imprimé est un DocObject.|  
|[CPrintInfo::m_bPreview](#m_bpreview)|Contient un indicateur qui indique si le document est affiché en aperçu.|  
|[CPrintInfo::m_dwFlags](#m_dwflags)|Spécifie les opérations d’impression DocObject.|  
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|Contient un pointeur vers une structure créée par l’utilisateur.|  
|[CPrintInfo::m_nCurPage](#m_ncurpage)|Identifie le numéro de la page en cours d’impression.|  
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|Spécifie le numéro de projet attribué par le système d’exploitation pour le travail d’impression|  
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|Identifie le nombre de pages affichées dans la fenêtre d’aperçu. 1 ou 2.|  
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|Spécifie le décalage de la première page de DocObject particulier dans un travail d’impression DocObject combiné.|  
|[CPrintInfo::m_pPD](#m_ppd)|Contient un pointeur vers le `CPrintDialog` objet utilisé pour la boîte de dialogue d’impression.|  
|[CPrintInfo::m_rectDraw](#m_rectdraw)|Spécifie un rectangle définissant la zone utilisable en cours.|  
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|Contient une chaîne de format pour l’affichage des numéros de page.|  
  
## <a name="remarks"></a>Remarques  
 `CPrintInfo`est une structure et ne dispose pas d’une classe de base.  
  
 L’infrastructure crée un objet de `CPrintInfo` chaque fois que l’impression ou la commande Aperçu avant impression est choisi et détruit lorsque la commande est terminée.  
  
 `CPrintInfo`contient des informations sur le travail d’impression dans son ensemble, telles que la plage de pages à imprimer et l’état actuel du travail d’impression, telles que la page en cours d’impression. Certaines informations sont stockées dans un [CPrintDialog](../../mfc/reference/cprintdialog-class.md) objet ; cet objet contient les valeurs entrées par l’utilisateur dans la boîte de dialogue d’impression.  
  
 Un `CPrintInfo` objet est passé entre l’infrastructure et votre classe d’affichage pendant le processus d’impression et est utilisé pour échanger des informations entre les deux. Par exemple, le framework informe la classe de vue quelle page du document à imprimer en affectant une valeur à la `m_nCurPage` membre `CPrintInfo`; la vue classe récupère la valeur et effectue l’impression réelle de la page spécifiée.  
  
 Un autre exemple est le cas dans laquelle la longueur du document n’est pas connue jusqu'à ce qu’il est imprimé. Dans ce cas, la classe d’affichage teste la fin du document chaque fois qu’une page est imprimée. Lorsque la fin est atteinte, la classe d’affichage définit les `m_bContinuePrinting` membre `CPrintInfo` à **FALSE**; Cela permet d’informer l’infrastructure pour arrêter la boucle d’impression.  
  
 `CPrintInfo`est utilisé par les fonctions membres de `CView` répertorié sous « Voir aussi ». Pour plus d’informations sur l’architecture d’impression fournie par la bibliothèque Microsoft Foundation Class, consultez [fenêtres Frame](../../mfc/frame-windows.md) et [Architecture Document/vue](../../mfc/document-view-architecture.md) et les articles [d’impression](../../mfc/printing.md) et [d’impression : Documents multipages](../../mfc/multipage-documents.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CPrintInfo`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxext.h  
  
##  <a name="a-namegetfrompagea--cprintinfogetfrompage"></a><a name="getfrompage"></a>CPrintInfo::GetFromPage  
 Appelez cette fonction pour récupérer le numéro de la première page à imprimer.  
  
```  
UINT GetFromPage() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le numéro de la première page à imprimer.  
  
### <a name="remarks"></a>Remarques  
 Ceci est la valeur spécifiée par l’utilisateur dans la boîte de dialogue d’impression, et il est stocké dans le `CPrintDialog` objet référencé par le `m_pPD` membre. Si l’utilisateur n’a pas spécifié de valeur, la valeur par défaut est la première page du document.  
  
##  <a name="a-namegetmaxpagea--cprintinfogetmaxpage"></a><a name="getmaxpage"></a>CPrintInfo::GetMaxPage  
 Appelez cette fonction pour récupérer le numéro de la dernière page du document.  
  
```  
UINT GetMaxPage() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le numéro de la dernière page du document.  
  
### <a name="remarks"></a>Remarques  
 Cette valeur est stockée dans le `CPrintDialog` objet référencé par le `m_pPD` membre.  
  
##  <a name="a-namegetminpagea--cprintinfogetminpage"></a><a name="getminpage"></a>CPrintInfo::GetMinPage  
 Appelez cette fonction pour récupérer le numéro de la première page du document.  
  
```  
UINT GetMinPage() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le numéro de la première page du document.  
  
### <a name="remarks"></a>Notes  
 Cette valeur est stockée dans le `CPrintDialog` objet référencé par le `m_pPD` membre.  
  
##  <a name="a-namegetoffsetpagea--cprintinfogetoffsetpage"></a><a name="getoffsetpage"></a>CPrintInfo::GetOffsetPage  
 Appelez cette fonction pour récupérer le décalage lors de l’impression de plusieurs éléments DocObject à partir d’un client DocObject.  
  
```  
UINT GetOffsetPage() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de pages qui précède la première page d’un élément DocObject imprimée dans un travail d’impression DocObject combiné.  
  
### <a name="remarks"></a>Remarques  
 Cette valeur est référencée par la **m_nOffsetPage** membre. La première page de votre document est numérotée le **m_nOffsetPage** valeur + 1 lors de l’impression DocObject avec d’autres documents actives. Le **m_nOffsetPage** membre est valide uniquement si la **m_bDocObject** valeur **TRUE**.  
  
##  <a name="a-namegettopagea--cprintinfogettopage"></a><a name="gettopage"></a>CPrintInfo::GetToPage  
 Appelez cette fonction pour récupérer le numéro de la dernière page à imprimer.  
  
```  
UINT GetToPage() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le numéro de la dernière page à imprimer.  
  
### <a name="remarks"></a>Remarques  
 Ceci est la valeur spécifiée par l’utilisateur dans la boîte de dialogue d’impression, et il est stocké dans le `CPrintDialog` objet référencé par le `m_pPD` membre. Si l’utilisateur n’a pas spécifié de valeur, la valeur par défaut est la dernière page du document.  
  
##  <a name="a-namembcontinueprintinga--cprintinfombcontinueprinting"></a><a name="m_bcontinueprinting"></a>CPrintInfo::m_bContinuePrinting  
 Contient un indicateur qui signale si l’infrastructure doit continuer la boucle d’impression.  
  
### <a name="remarks"></a>Notes  
 Si vous effectuez la pagination de délai d’impression, vous pouvez définir ce membre **FALSE** de la substitution de `CView::OnPrepareDC` après la fin du document a été atteinte. Vous n’êtes pas obligé de modifier cette variable si vous avez spécifié la longueur du document au début de la tâche d’impression à l’aide du `SetMaxPage` fonction membre. Le `m_bContinuePrinting` membre est une variable publique de type **BOOL**.  
  
##  <a name="a-namembdirecta--cprintinfombdirect"></a><a name="m_bdirect"></a>CPrintInfo::m_bDirect  
 L’infrastructure définit ce membre sur **TRUE** si la boîte de dialogue d’impression est ignorée pour l’impression directe ; **FALSE** dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 La boîte de dialogue d’impression est contournée normalement lorsque vous imprimez à partir de l’interpréteur de commandes ou lors de l’impression s’effectue à l’aide de l’ID de commande **ID_FILE_PRINT_DIRECT**.  
  
 Vous ne modifiez pas ce membre, normalement mais si vous la modifiez, modifiez-le avant appel [CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting) de la substitution de [comme CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="a-namembdocobjecta--cprintinfombdocobject"></a><a name="m_bdocobject"></a>CPrintInfo::m_bDocObject  
 Contient un indicateur qui indique si le document imprimé est un DocObject.  
  
### <a name="remarks"></a>Notes  
 Données membres `m_dwFlags` et **m_nOffsetPage** ne sont pas valides, sauf si cet indicateur est **TRUE**.  
  
##  <a name="a-namembpreviewa--cprintinfombpreview"></a><a name="m_bpreview"></a>CPrintInfo::m_bPreview  
 Contient un indicateur qui indique si le document est affiché en aperçu.  
  
### <a name="remarks"></a>Remarques  
 Il est défini par le framework selon laquelle l’utilisateur de commande exécutée. La boîte de dialogue ne s’affiche pas pour un travail de l’aperçu avant impression. Le **m_bPreview** membre est une variable publique de type **BOOL**.  
  
##  <a name="a-namemdwflagsa--cprintinfomdwflags"></a><a name="m_dwflags"></a>CPrintInfo::m_dwFlags  
 Contient une combinaison d’indicateurs qui spécifient des opérations d’impression DocObject.  
  
### <a name="remarks"></a>Notes  
 Valide uniquement si le membre de données **m_bDocObject** est **TRUE**.  
  
 Les indicateurs peuvent être un ou plusieurs des valeurs suivantes :  
  
- **PRINTFLAG_MAYBOTHERUSER**  
  
- **PRINTFLAG_PROMPTUSER**  
  
- **PRINTFLAG_USERMAYCHANGEPRINTER**  
  
- **PRINTFLAG_RECOMPOSETODEVICE**  
  
- **PRINTFLAG_DONTACTUALLYPRINT**  
  
- **PRINTFLAG_FORCEPROPERTIES**  
  
- **PRINTFLAG_PRINTTOFILE**  
  
##  <a name="a-namemlpuserdataa--cprintinfomlpuserdata"></a><a name="m_lpuserdata"></a>CPrintInfo::m_lpUserData  
 Contient un pointeur vers une structure créée par l’utilisateur.  
  
### <a name="remarks"></a>Notes  
 Cela permet de stocker des données spécifiques à l’impression que vous ne souhaitez pas stocker dans votre classe d’affichage. Le **m_lpUserData** membre est une variable publique de type **LPVOID**.  
  
##  <a name="a-namemncurpagea--cprintinfomncurpage"></a><a name="m_ncurpage"></a>CPrintInfo::m_nCurPage  
 Contient le numéro de la page actuelle.  
  
### <a name="remarks"></a>Remarques  
 Le framework appelle `CView::OnPrepareDC` et `CView::OnPrint` une fois pour chaque page du document, en spécifiant une valeur différente pour ce membre ; chaque fois que ses valeurs comprises entre la valeur retournée par `GetFromPage` à celui retourné par `GetToPage`. Utilisez ce membre dans vos remplacements de `CView::OnPrepareDC` et `CView::OnPrint` pour imprimer la page du document spécifiée.  
  
 Lorsque le mode aperçu est appelé en premier, le framework lit la valeur de ce membre pour déterminer quelle page du document doit être prévisualisée initialement. Vous pouvez définir la valeur de ce membre de la substitution de `CView::OnPreparePrinting` pour mettre à jour la position actuelle de l’utilisateur dans le document lors de l’entrée en mode Aperçu. Le `m_nCurPage` membre est une variable publique de type **UINT**.  
  
##  <a name="a-namemnjobnumbera--cprintinfomnjobnumber"></a><a name="m_njobnumber"></a>CPrintInfo::m_nJobNumber  
 Indique le numéro de projet attribué par le système d’exploitation pour le travail d’impression en cours.  
  
### <a name="remarks"></a>Remarques  
 Cette valeur peut être **SP_ERROR** si le travail n’a pas encore réussi (autrement dit, si le `CPrintInfo` objet est construit récemment et n’a pas encore été utilisé pour imprimer), ou si une erreur s’est produite lors du démarrage de la tâche.  
  
##  <a name="a-namemnnumpreviewpagesa--cprintinfomnnumpreviewpages"></a><a name="m_nnumpreviewpages"></a>CPrintInfo::m_nNumPreviewPages  
 Contient le nombre de pages affichées en mode Aperçu. Il peut être 1 ou 2.  
  
### <a name="remarks"></a>Notes  
 Le **m_nNumPreviewPages** membre est une variable publique de type **UINT**.  
  
##  <a name="a-namemnoffsetpagea--cprintinfomnoffsetpage"></a><a name="m_noffsetpage"></a>CPrintInfo::m_nOffsetPage  
 Contient le nombre de pages qui précède la première page de DocObject particulier dans un travail d’impression DocObject combiné.  
  
##  <a name="a-namemppda--cprintinfomppd"></a><a name="m_ppd"></a>CPrintInfo::m_pPD  
 Contient un pointeur vers le `CPrintDialog` objet utilisé pour afficher la boîte de dialogue d’impression du travail d’impression.  
  
### <a name="remarks"></a>Remarques  
 Le `m_pPD` membre est une variable publique est déclarée comme pointeur vers `CPrintDialog`.  
  
##  <a name="a-namemrectdrawa--cprintinfomrectdraw"></a><a name="m_rectdraw"></a>CPrintInfo::m_rectDraw  
 Spécifie la zone de dessin utilisable de la page en coordonnées logiques.  
  
### <a name="remarks"></a>Notes  
 Vous souhaiterez faire cela dans la substitution de `CView::OnPrint`. Vous pouvez utiliser ce membre pour suivre quelle zone reste utilisable après l’impression des en-têtes, pieds de page et ainsi de suite. Le **m_rectDraw** membre est une variable publique de type `CRect`.  
  
##  <a name="a-namemstrpagedesca--cprintinfomstrpagedesc"></a><a name="m_strpagedesc"></a>CPrintInfo::m_strPageDesc  
 Contient une chaîne de format utilisée pour afficher les numéros de page lors de l’aperçu avant impression ; Cette chaîne est constituée de deux sous-chaînes, un pour l’affichage de page unique et un pour l’affichage page double, chacun se terminent par un caractère « \n ».  
  
### <a name="remarks"></a>Remarques  
 L’infrastructure utilise « Page %u\nPages % u-%u\n » comme valeur par défaut. Si vous souhaitez un autre format pour les numéros de page, spécifiez une chaîne de format de la substitution de `CView::OnPreparePrinting`. Le **m_strPageDesc** membre est une variable publique de type `CString`.  
  
##  <a name="a-namesetmaxpagea--cprintinfosetmaxpage"></a><a name="setmaxpage"></a>CPrintInfo::SetMaxPage  
 Appelez cette fonction pour spécifier le numéro de la dernière page du document.  
  
```  
void SetMaxPage(UINT nMaxPage);
```  
  
### <a name="parameters"></a>Paramètres  
 *nMaxPage*  
 Numéro de la dernière page du document.  
  
### <a name="remarks"></a>Remarques  
 Cette valeur est stockée dans le `CPrintDialog` objet référencé par le `m_pPD` membre. Si la longueur du document est connue avant de l’imprimer, appelez cette fonction à partir de la substitution de `CView::OnPreparePrinting`. Si la longueur du document dépend d’un paramètre spécifié par l’utilisateur dans la boîte de dialogue d’impression, appelez cette fonction à partir de la substitution de `CView::OnBeginPrinting`. Si la longueur du document n’est pas connue jusqu'à ce qu’il est imprimé, utilisez le `m_bContinuePrinting` membres pour contrôler la boucle d’impression.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [comme CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="a-namesetminpagea--cprintinfosetminpage"></a><a name="setminpage"></a>CPrintInfo::SetMinPage  
 Appelez cette fonction pour spécifier le numéro de la première page du document.  
  
```  
void SetMinPage(UINT nMinPage);
```  
  
### <a name="parameters"></a>Paramètres  
 *nMinPage*  
 Numéro de la première page du document.  
  
### <a name="remarks"></a>Remarques  
 Normalement, les numéros de page commencent à 1. Cette valeur est stockée dans le `CPrintDialog` objet référencé par le `m_pPD` membre.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC DIBLOOK](../../visual-cpp-samples.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)   
 [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)   
 [CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)   
 [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)   
 [Comme CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)   
 [CView::OnPrint](../../mfc/reference/cview-class.md#onprint)




