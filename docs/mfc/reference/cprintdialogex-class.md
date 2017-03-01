---
title: Classe de CPrintDialogEx | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintDialogEx
dev_langs:
- C++
helpviewer_keywords:
- Print Setup dialog box
- CPrintDialogEx class
- Print dialog box
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
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
ms.openlocfilehash: 8dc8f01eef42b54af18ed07520d547768c931748
ms.lasthandoff: 02/24/2017

---
# <a name="cprintdialogex-class"></a>CPrintDialogEx (classe)
Encapsule les services fournis par la feuille de propriétés d'impression Windows 2000.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Construit un objet `CPrintDialogEx`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Crée un contexte de périphérique d’imprimante sans afficher la boîte de dialogue d’impression.|  
|[CPrintDialogEx::DoModal](#domodal)|Affiche la boîte de dialogue et permet à l’utilisateur d’effectuer des sélections.|  
|[CPrintDialogEx::GetCopies](#getcopies)|Récupère le nombre de copies demandé.|  
|[CPrintDialogEx::GetDefaults](#getdefaults)|Récupère les valeurs par défaut de l’appareil sans afficher une boîte de dialogue.|  
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Récupère le nom de l’imprimante actuellement sélectionnée.|  
|[CPrintDialogEx::GetDevMode](#getdevmode)|Récupère le `DEVMODE` structure.|  
|[CPrintDialogEx::GetDriverName](#getdrivername)|Récupère le nom du pilote de périphérique d’imprimante définis par le système.|  
|[CPrintDialogEx::GetPortName](#getportname)|Récupère le nom du port imprimante actuellement sélectionnée.|  
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Récupère un handle vers le contexte de l’imprimante.|  
|[CPrintDialogEx::PrintAll](#printall)|Détermine s’il faut imprimer toutes les pages du document.|  
|[CPrintDialogEx::PrintCollate](#printcollate)|Détermine si les copies assemblées copies sont demandées.|  
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Détermine s’il faut imprimer la page active du document.|  
|[CPrintDialogEx::PrintRange](#printrange)|Détermine s’il faut imprimer uniquement une plage de pages spécifiée.|  
|[CPrintDialogEx::PrintSelection](#printselection)|Détermine s’il faut imprimer uniquement les éléments actuellement sélectionnés.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPrintDialogEx::m_pdex](#m_pdex)|Une structure utilisée pour personnaliser un `CPrintDialogEx` objet.|  
  
## <a name="remarks"></a>Notes  
 Vous pouvez compter sur l’infrastructure pour gérer de nombreux aspects du processus d’impression de votre application. Pour plus d’informations sur l’utilisation de l’infrastructure pour gérer les tâches d’impression, consultez l’article [d’impression](../../mfc/printing.md).  
  
 Si vous souhaitez que votre application pour gérer l’impression sans l’intervention de l’infrastructure, vous pouvez utiliser la `CPrintDialogEx` de classe avec le constructeur fourni « tel quel », ou vous pouvez dériver votre propre classe de boîte de dialogue de `CPrintDialogEx` et écrire un constructeur pour répondre à vos besoins. Dans les deux cas, ces boîtes de dialogue seront comporte comme les boîtes de dialogue MFC standard, car elles sont dérivées de la classe `CCommonDialog`.  
  
 Pour utiliser un `CPrintDialogEx` d’objet, commencez par créer l’objet en utilisant la `CPrintDialogEx` constructeur. Une fois que la boîte de dialogue a été construite, vous pouvez définir ou modifier des valeurs dans le [m_pdex](#m_pdex) structure pour initialiser les valeurs des contrôles de la boîte de dialogue. Le `m_pdex` structure est de type [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844). Pour plus d’informations sur cette structure, consultez la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Si vous ne fournissez pas vos propres descripteurs dans `m_pdex` pour la **hDevMode** et **hDevNames** membres, veillez à appeler la fonction Windows **GlobalFree** pour ces poignées lorsque vous avez terminé avec la boîte de dialogue.  
  
 Après avoir initialisé les contrôles de boîte de dialogue, appelez le `DoModal` fonction membre pour afficher la boîte de dialogue et permettent aux utilisateurs de sélectionner des options d’impression. Lorsque `DoModal` renvoie, vous pouvez déterminer si l’utilisateur a sélectionné le bouton OK, appliquer ou annuler.  
  
 Si l’utilisateur a cliqué sur OK, vous pouvez utiliser `CPrintDialogEx`de fonctions membres pour récupérer les informations entrées par l’utilisateur.  
  
 Le `CPrintDialogEx::GetDefaults` la fonction membre est utile pour extraire les valeurs par défaut d’imprimante en cours sans afficher une boîte de dialogue. Cette méthode ne requiert aucune interaction utilisateur.  
  
 Vous pouvez utiliser les fenêtres **CommDlgExtendedError** fonction pour déterminer si une erreur s’est produite lors de l’initialisation de la boîte de dialogue et pour en savoir plus sur l’erreur. Pour plus d’informations sur cette fonction, consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations sur l’utilisation de `CPrintDialogEx`, consultez [Classes de](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `IObjectWithSite`  
  
 `IPrintDialogCallback`  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialogEx`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdlgs.h  
  
##  <a name="a-namecprintdialogexa--cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a>CPrintDialogEx::CPrintDialogEx  
 Construit une feuille de propriétés d’impression Windows 2000.  
  
```  
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwFlags`  
 Un ou plusieurs indicateurs que vous pouvez utiliser pour personnaliser les paramètres de la boîte de dialogue, combinées à l’aide de l’opérateur OR. Par exemple, le **PD_ALLPAGES** indicateur définit la plage d’impression par défaut pour toutes les pages du document. Consultez le [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur ces indicateurs.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parente ou propriétaire de la boîte de dialogue.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre construit uniquement l’objet. Utilisez le `DoModal` fonction membre pour afficher la boîte de dialogue.  
  
##  <a name="a-namecreateprinterdca--cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a>CPrintDialogEx::CreatePrinterDC  
 Crée un contexte de périphérique (DC) imprimante à partir de la [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) et [DEVNAMES](../../mfc/reference/devnames-structure.md) structures.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Handle vers le contexte de l’imprimante qui vient d’être créé.  
  
### <a name="remarks"></a>Notes  
 Le contrôleur de domaine renvoyé est également stocké dans le **hDC** membre [m_pdex](#m_pdex).  
  
 Ce contrôleur de domaine est supposé pour être l’imprimante par défaut du contrôleur de domaine, et tout autre obtenu précédemment imprimante que contrôleurs de domaine doivent être supprimées. Cette fonction peut être appelée et le contrôleur de domaine qui en résulte est utilisé, sans jamais afficher la boîte de dialogue d’impression.  
  
##  <a name="a-namedomodala--cprintdialogexdomodal"></a><a name="domodal"></a>CPrintDialogEx::DoModal  
 Appelez cette fonction pour afficher la feuille de propriétés d’impression Windows 2000 courantes et permettent aux utilisateurs de sélectionner différentes options d’impression telles que le nombre de copies, la plage de pages, et si les copies doivent être triées.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le INT_PTR valeur de retour est en fait un HRESULT. Consultez la section valeurs de retour de [PrintDlgEx](http://msdn.microsoft.com/library/windows/desktop/ms646942) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Si vous souhaitez initialiser les diverses options de la boîte de dialogue Imprimer en définissant les membres de la `m_pdex` structure, vous devez le faire avant d’appeler `DoModal`, mais une fois que l’objet de la boîte de dialogue est construit.  
  
 Après avoir appelé `DoModal`, vous pouvez appeler des fonctions à récupérer les paramètres ou les informations saisies par l’utilisateur dans la boîte de dialogue autres membres.  
  
 Si le **PD_RETURNDC** indicateur est utilisé lors de l’appel `DoModal`, une contrôleur de domaine de l’imprimante est retournée dans le **hDC** membre [m_pdex](#m_pdex). Ce contrôleur de domaine doit être libérée avec un appel à [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) par l’appelant de `CPrintDialogEx`.  
  
##  <a name="a-namegetcopiesa--cprintdialogexgetcopies"></a><a name="getcopies"></a>CPrintDialogEx::GetCopies  
 Appelez cette fonction après avoir appelé `DoModal` pour récupérer le nombre de copies demandé.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de copies demandé.  
  
##  <a name="a-namegetdefaultsa--cprintdialogexgetdefaults"></a><a name="getdefaults"></a>CPrintDialogEx::GetDefaults  
 Appelez cette fonction pour récupérer les valeurs par défaut du périphérique de l’imprimante par défaut sans afficher une boîte de dialogue.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** en cas de réussite, sinon **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Crée un contexte de périphérique (DC) imprimante à partir de la [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) et [DEVNAMES](../../mfc/reference/devnames-structure.md) structures.  
  
 `GetDefaults`n’affiche pas la feuille de propriétés d’impression. Au lieu de cela, il définit les **hDevNames** et **hDevMode** membres de [m_pdex](#m_pdex) à des handles pour le [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) et [DEVNAMES](../../mfc/reference/devnames-structure.md) structures qui sont initialisés pour l’imprimante par défaut. Les deux **hDevNames** et **hDevMode** doit être NULL, ou `GetDefaults` échoue.  
  
 Si le **PD_RETURNDC** est défini, cette fonction seulement retournera pas **hDevNames** et **hDevMode** (situé dans **m_pdex.hDevNames** et **m_pdex.hDevMode**) à l’appelant, mais retourne également un DC d’imprimante dans **m_pdex.hDC**. Il incombe à l’appelant de supprimer l’imprimante du contrôleur de domaine et appeler les fenêtres [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) fonction sur les poignées lorsque vous avez terminé avec le `CPrintDialogEx` objet.  
  
##  <a name="a-namegetdevicenamea--cprintdialogexgetdevicename"></a><a name="getdevicename"></a>CPrintDialogEx::GetDeviceName  
 Appelez cette fonction après avoir appelé [DoModal](#domodal) pour récupérer le nom de l’imprimante actuellement sélectionnée, ou après avoir appelé [GetDefaults](#getdefaults) pour récupérer le nom de l’imprimante par défaut.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nom de l’imprimante sélectionnée.  
  
### <a name="remarks"></a>Remarques  
 Utilisez un pointeur vers le `CString` objet retourné par `GetDeviceName` comme valeur de `lpszDeviceName` dans un appel à [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="a-namegetdevmodea--cprintdialogexgetdevmode"></a><a name="getdevmode"></a>CPrintDialogEx::GetDevMode  
 Appelez cette fonction après avoir appelé [DoModal](#domodal) ou [GetDefaults](#getdefaults) pour extraire des informations sur le périphérique d’impression.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) structure de données qui contient des informations sur l’environnement d’un pilote d’impression et de l’initialisation du périphérique. Vous devez déverrouiller la mémoire consommée par cette structure avec Windows [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) (fonction), qui est décrite dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdrivernamea--cprintdialogexgetdrivername"></a><a name="getdrivername"></a>CPrintDialogEx::GetDriverName  
 Appelez cette fonction après avoir appelé [DoModal](#domodal) ou [GetDefaults](#getdefaults) pour récupérer le nom du pilote de périphérique d’imprimante définis par le système.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CString` en spécifiant le nom du pilote définies par le système.  
  
### <a name="remarks"></a>Remarques  
 Utilisez un pointeur vers le `CString` objet retourné par `GetDriverName` comme valeur de `lpszDriverName` dans un appel à [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="a-namegetportnamea--cprintdialogexgetportname"></a><a name="getportname"></a>CPrintDialogEx::GetPortName  
 Appelez cette fonction après avoir appelé [DoModal](#domodal) ou [GetDefaults](#getdefaults) pour récupérer le nom du port imprimante actuellement sélectionnée.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nom du port imprimante actuellement sélectionnée.  
  
##  <a name="a-namegetprinterdca--cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a>CPrintDialogEx::GetPrinterDC  
 Retourne un handle vers le contexte de l’imprimante.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Handle vers le contexte de l’imprimante.  
  
### <a name="remarks"></a>Remarques  
 Vous devez appeler Windows [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) (fonction) pour supprimer le contexte de périphérique lorsque vous avez terminé l’utiliser.  
  
##  <a name="a-namempdexa--cprintdialogexmpdex"></a><a name="m_pdex"></a>CPrintDialogEx::m_pdex  
 Structure PRINTDLGEX dont les membres stockent les caractéristiques de l’objet de la boîte de dialogue.  
  
```  
PRINTDLGEX m_pdex;  
```  
  
### <a name="remarks"></a>Remarques  
 Après avoir construit un `CPrintDialogEx` de l’objet, vous pouvez utiliser `m_pdex` pour définir les divers aspects de la boîte de dialogue avant d’appeler le [DoModal](#domodal) fonction membre. Pour plus d’informations sur la `m_pdex` de la structure, consultez [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Si vous modifiez le `m_pdex` membre de données directement, vous devez remplacer un comportement par défaut.  
  
##  <a name="a-nameprintalla--cprintdialogexprintall"></a><a name="printall"></a>CPrintDialogEx::PrintAll  
 Appelez cette fonction après avoir appelé `DoModal` pour déterminer s’il faut imprimer toutes les pages dans le document.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si toutes les pages dans le document doivent être imprimées ; sinon **FALSE**.  
  
##  <a name="a-nameprintcollatea--cprintdialogexprintcollate"></a><a name="printcollate"></a>CPrintDialogEx::PrintCollate  
 Appelez cette fonction après avoir appelé `DoModal` pour déterminer si l’imprimante doit collate imprimés tous les exemplaires du document.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si l’utilisateur sélectionne la case à cocher dans la boîte de dialogue ; sinon **FALSE**.  
  
##  <a name="a-nameprintcurrentpagea--cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a>CPrintDialogEx::PrintCurrentPage  
 Appelez cette fonction après avoir appelé `DoModal` pour déterminer s’il faut imprimer la page active dans le document.  
  
```  
BOOL PrintCurrentPage() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si **imprimer la Page en cours** est sélectionné dans la boîte de dialogue ; sinon **FALSE**.  
  
##  <a name="a-nameprintrangea--cprintdialogexprintrange"></a><a name="printrange"></a>CPrintDialogEx::PrintRange  
 Appelez cette fonction après avoir appelé `DoModal` pour déterminer s’il faut imprimer uniquement une plage de pages dans le document.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si seulement une plage de pages dans le document doivent être imprimées ; sinon **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Les plages de pages spécifié peuvent être déterminés à partir de [m_pdex](#m_pdex) (voir **nPageRanges**, **nMaxPageRanges**, et **lpPageRanges** dans les [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]).  
  
##  <a name="a-nameprintselectiona--cprintdialogexprintselection"></a><a name="printselection"></a>CPrintDialogEx::PrintSelection  
 Appelez cette fonction après avoir appelé `DoModal` pour déterminer si vous souhaitez imprimer uniquement les éléments actuellement sélectionnés.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si seuls les éléments sélectionnés sont imprimés ; sinon **FALSE**.  
  
## <a name="see-also"></a>Voir aussi  
 [CCommonDialog (classe)](../../mfc/reference/ccommondialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CPrintInfo (Structure)](../../mfc/reference/cprintinfo-structure.md)

