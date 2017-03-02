---
title: CDateTimeCtrl (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDateTimeCtrl
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], CDateTimeCtrl class
- date-picking functionality
- CDateTimeCtrl class
- DateTimePicker control [MFC]
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
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
ms.openlocfilehash: e5407934021abdb64dfb625e3dfb2c1841b7a5f0
ms.lasthandoff: 02/24/2017

---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl (classe)
Encapsule les fonctionnalités d'un contrôle de sélecteur de date et d'heure.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|Construit un objet `CDateTimeCtrl`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|Ferme le contrôle de sélecteur de date et d’heure actuels.|  
|[CDateTimeCtrl::Create](#create)|Crée le contrôle de sélecteur de date et d’heure et l’attache à le `CDateTimeCtrl` objet.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|Récupère des informations sur le contrôle de sélecteur de date et d’heure actuelle.|  
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|Retourne la taille idéale du contrôle de sélecteur de date et d’heure qui est nécessaire pour afficher la date ou l’heure.|  
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|Récupère la couleur d’une partie donnée du calendrier du mois dans le contrôle de sélecteur de date et d’heure.|  
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|Récupère le `CMonthCalCtrl` objet associé avec le contrôle de sélecteur de date et d’heure.|  
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|Récupère la police actuellement utilisée par la date et de contrôle de calendrier mensuel enfant du contrôle de sélecteur d’heure.|  
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|Obtient le style du contrôle de sélecteur de date et d’heure actuels.|  
|[CDateTimeCtrl::GetRange](#getrange)|Récupère actuel minimale et maximale autorisée de temps système pour un contrôle de sélecteur de date et d’heure.|  
|[CDateTimeCtrl::GetTime](#gettime)|Récupère l’heure actuellement sélectionnée à partir d’un contrôle de sélecteur de date et d’heure et le place dans une certaine `SYSTEMTIME` structure.|  
|[CDateTimeCtrl::SetFormat](#setformat)|Définit l’affichage d’un contrôle de sélecteur de date et d’heure conformément à une chaîne de format donné.|  
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|Définit la couleur d’une partie donnée du calendrier mois dans un contrôle de sélecteur de date et d’heure.|  
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|Définit la police qui contrôle month calendar de date et heure sélecteur du contrôle enfant utilisera.|  
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|Définit le style du contrôle de sélecteur de date et d’heure actuels.|  
|[CDateTimeCtrl::SetRange](#setrange)|Définit les périodes de configurations système minimale et maximale autorisée pour un contrôle de sélecteur de date et d’heure.|  
|[CDateTimeCtrl::SetTime](#settime)|Définit l’heure dans un contrôle de sélecteur de date et d’heure.|  
  
## <a name="remarks"></a>Remarques  
 Le contrôle de sélecteur de date et d’heure (contrôle DTP) fournit une interface simple pour échanger des informations de date et d’heure avec un utilisateur. Cette interface contient des champs, chacun d'entre eux affiche une partie des informations de date et heure stockées dans le contrôle. L’utilisateur peut modifier les informations stockées dans le contrôle en modifiant le contenu de la chaîne dans un champ donné. L’utilisateur peut passer d’un champ à l’aide de la souris ou du clavier.  
  
 Vous pouvez personnaliser le contrôle de sélecteur de date et d’heure en appliquant des styles à l’objet lors de sa création. Consultez la page [Date et heure des Styles de contrôle de sélecteur de](http://msdn.microsoft.com/library/windows/desktop/bb761728) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur les styles spécifiques pour le contrôle de sélecteur de date et d’heure. Vous pouvez définir le format d’affichage du contrôle DTP à l’aide de styles de formats. Ces styles de format décrits sous « Format Styles » dans la [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)] rubrique [Date et heure des Styles de contrôle de sélecteur de](http://msdn.microsoft.com/library/windows/desktop/bb761728).  
  
 Le contrôle de sélecteur de date et d’heure utilise également des notifications et les rappels, qui sont décrites dans [à l’aide de CDateTimeCtrl](../../mfc/using-cdatetimectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdtctl.h  
  
##  <a name="a-namecdatetimectrla--cdatetimectrlcdatetimectrl"></a><a name="cdatetimectrl"></a>CDateTimeCtrl::CDateTimeCtrl  
 Construit un objet `CDateTimeCtrl`.  
  
```  
CDateTimeCtrl();
```  
  
##  <a name="a-nameclosemonthcala--cdatetimectrlclosemonthcal"></a><a name="closemonthcal"></a>CDateTimeCtrl::CloseMonthCal  
 Ferme le contrôle de sélecteur de date et d’heure actuels.  
  
```  
void CloseMonthCal() const;  
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [DTM_CLOSEMONTHCAL](http://msdn.microsoft.com/library/windows/desktop/bb761753) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_dateTimeCtrl`, qui est utilisé pour accéder par programme le contrôle de sélecteur de date et d’heure. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1 n °&1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple suivant ferme le calendrier déroulant pour le contrôle de sélecteur de date et d’heure actuels.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1 n °&5;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]  
  
##  <a name="a-namecreatea--cdatetimectrlcreate"></a><a name="create"></a>CDateTimeCtrl::Create  
 Crée le contrôle de sélecteur de date et d’heure et l’attache à le `CDateTimeCtrl` objet.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwStyle`  
 Spécifie la combinaison de styles de contrôle date heure. Consultez la page [Date et heure des Styles de contrôle de sélecteur de](http://msdn.microsoft.com/library/windows/desktop/bb761728) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus d’informations sur les styles de sélecteur de date et d’heure.  
  
 `rect`  
 Une référence à un [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure, qui représente la position et la taille du contrôle de sélecteur de date et d’heure.  
  
 `pParentWnd`  
 Un pointeur vers un [CWnd](../../mfc/reference/cwnd-class.md) objet de la fenêtre parente du contrôle de sélecteur de date et d’heure. Il ne doit pas être **NULL**.  
  
 `nID`  
 Spécifie l’ID de contrôle de. la date et l’heure sélecteur du contrôle  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la création a réussi ; sinon 0.  
  
### <a name="remarks"></a>Notes  
  
##### <a name="to-create-a-date-and-time-picker-control"></a>Pour créer un contrôle de sélecteur de date et d’heure  
  
1.  Appelez [CDateTimeCtrl](#cdatetimectrl) pour construire un `CDateTimeCtrl` objet.  
  
2.  Appelez cette fonction membre, ce qui crée le contrôle de sélecteur de date et d’heure de Windows et l’attache à le `CDateTimeCtrl` objet.  
  
 Lorsque vous appelez **créer**, les contrôles communs sont initialisés.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CDateTimeCtrl n °&1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]  
  
##  <a name="a-namegetdatetimepickerinfoa--cdatetimectrlgetdatetimepickerinfo"></a><a name="getdatetimepickerinfo"></a>CDateTimeCtrl::GetDateTimePickerInfo  
 Récupère des informations sur le contrôle de sélecteur de date et d’heure actuelle.  
  
```   
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[out] `pDateTimePickerInfo`|Un pointeur vers un [DATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761729) structure qui reçoit la description du contrôle de sélecteur de date et l’heure actuelle.<br /><br /> L’appelant est chargé d’allouer cette structure. Toutefois, cette méthode initialise le `cbSize` membre de la structure.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si cette méthode a réussi ; dans le cas contraire, `false`.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [DTM_GETDATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761755) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_dateTimeCtrl`, qui est utilisé pour accéder par programme le contrôle de sélecteur de date et d’heure. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1 n °&1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant indique si correctement extrait les informations sur le contrôle de sélecteur de date et d’heure actuelle.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1 n °&4;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]  
  
##  <a name="a-namegetmonthcalcolora--cdatetimectrlgetmonthcalcolor"></a><a name="getmonthcalcolor"></a>CDateTimeCtrl::GetMonthCalColor  
 Récupère la couleur d’une partie donnée du calendrier du mois dans le contrôle de sélecteur de date et d’heure.  
  
```  
COLORREF GetMonthCalColor(int iColor) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `iColor`  
 Un `int` valeur qui spécifie la zone de couleur du calendrier du mois à récupérer. Pour une liste de valeurs, consultez le `iColor` paramètre [SetMonthCalColor](#setmonthcalcolor).  
  
### <a name="return-value"></a>Valeur de retour  
 A **COLORREF** valeur qui représente la couleur pour la partie spécifiée du contrôle month calendar en cas de réussite. La fonction retourne -1 en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [DTM_GETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761759), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CDateTimeCtrl n °&2;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]  
  
##  <a name="a-namegetmonthcalctrla--cdatetimectrlgetmonthcalctrl"></a><a name="getmonthcalctrl"></a>CDateTimeCtrl::GetMonthCalCtrl  
 Récupère le `CMonthCalCtrl` objet associé avec le contrôle de sélecteur de date et d’heure.  
  
```  
CMonthCalCtrl* GetMonthCalCtrl() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) objet, ou **NULL** en cas d’échec ou si la fenêtre n’est pas visible.  
  
### <a name="remarks"></a>Remarques  
 Contrôles date time picker créent un contrôle de calendrier mensuel enfants lorsque l’utilisateur clique sur la flèche déroulante. Lorsque le `CMonthCalCtrl` objet n’est plus nécessaire, il est détruit, donc votre application ne doit pas reposer sur le stockage de l’objet qui représente le calendrier du mois du contrôle date time picker enfants.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CDateTimeCtrl n °&3;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]  
  
##  <a name="a-namegetmonthcalfonta--cdatetimectrlgetmonthcalfont"></a><a name="getmonthcalfont"></a>CDateTimeCtrl::GetMonthCalFont  
 Obtient la police actuellement utilisée par la date et de contrôle de calendrier mensuel du contrôle de sélecteur d’heure.  
  
```  
CFont* GetMonthCalFont() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [CFont](../../mfc/reference/cfont-class.md) objet, ou **NULL** en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Le `CFont` objet désigné par la valeur de retour est un objet temporaire et détruit pendant le temps de traitement inactif suivant.  
  
##  <a name="a-namegetmonthcalstylea--cdatetimectrlgetmonthcalstyle"></a><a name="getmonthcalstyle"></a>CDateTimeCtrl::GetMonthCalStyle  
 Obtient le style du contrôle calendrier mois de la liste déroulante qui est associé avec le contrôle de sélecteur de date et d’heure actuels.  
  
```  
DWORD GetMonthCalStyle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le style du contrôle calendrier du mois de la liste déroulante, qui est une combinaison d’opérations de bits (ou) de date et heure de styles de contrôle de sélecteur. Pour plus d’informations, consultez [Styles de contrôle Month Calendar](http://msdn.microsoft.com/library/windows/desktop/bb760919).  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [DTM_GETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761763) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetrangea--cdatetimectrlgetrange"></a><a name="getrange"></a>CDateTimeCtrl::GetRange  
 Récupère actuel minimale et maximale autorisée de temps système pour un contrôle de sélecteur de date et d’heure.  
  
```  
DWORD GetRange(
    COleDateTime* pMinRange,  
    COleDateTime* pMaxRange) const;  
  
DWORD GetRange(
    CTime* pMinRange,  
    CTime* pMaxRange) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pMinRange`  
 Un pointeur vers un [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) objet ou un [CTime](../../atl-mfc-shared/reference/ctime-class.md) objet contenant la première heure autorisée dans le `CDateTimeCtrl` objet.  
  
 `pMaxRange`  
 Un pointeur vers un `COleDateTime` objet ou un `CTime` objet contenant la dernière heure autorisée dans le `CDateTimeCtrl` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `DWORD` contenant des indicateurs qui indiquent les plages sont définies. If  
  
 `return value & GDTR_MAX` == 0  
  
 le deuxième paramètre est valid. De même, si  
  
 `return value & GDTR_MIN` == 0  
  
 le premier paramètre est valid.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [DTM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761767), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dans l’implémentation par MFC, vous pouvez spécifier `COleDateTime` ou `CTime` utilisations.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CDateTimeCtrl n °&4;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]  
  
##  <a name="a-namegettimea--cdatetimectrlgettime"></a><a name="gettime"></a>CDateTimeCtrl::GetTime  
 Récupère l’heure actuellement sélectionnée à partir d’un contrôle de sélecteur de date et d’heure et le place dans une certaine `SYSTEMTIME` structure.  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;  
DWORD GetTime(CTime& timeDest) const;  
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *timeDest*  
 Dans la première version, une référence à un [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) objet qui recevra les informations système. Dans la deuxième version, une référence à un [CTime](../../atl-mfc-shared/reference/ctime-class.md) objet qui recevra les informations système.  
  
 *pTimeDest*  
 Un pointeur vers le [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) structure pour recevoir les informations système. Ne doit pas être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Dans la première version, différent de zéro si l’heure est correctement écrit dans le `COleDateTime` objet ; sinon 0. Dans les versions des deuxième et troisième, un `DWORD` valeur égale à la **dwFlag** jeu de membres le [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) structure. Consultez le **notes** section ci-dessous pour plus d’informations.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [DTM_GETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761769), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dans l’implémentation MFC de **GetTime**, vous pouvez utiliser `COleDateTime` ou `CTime` classes, ou vous pouvez utiliser un `SYSTEMTIME` structure pour stocker les informations d’heure.  
  
 La valeur de retour `DWORD` dans les versions des deuxième et troisième, ci-dessus, indique si le contrôle de sélecteur de date et d’heure est défini sur l’état « aucune date », comme indiqué dans le [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) membre de la structure `dwFlags`. Si la valeur retournée est égal à **GDT_NONE**, le contrôle est défini pour l’état « aucune date » et utilise le **DTS_SHOWNONE** style. Si la valeur retournée est égal à **GDT_VALID**, l’heure système est correctement stockée dans l’emplacement de destination.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CDateTimeCtrl n °&5;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]  
  
##  <a name="a-namegetidealsizea--cdatetimectrlgetidealsize"></a><a name="getidealsize"></a>CDateTimeCtrl::GetIdealSize  
 Retourne la taille idéale du contrôle de sélecteur de date et d’heure qui est nécessaire pour afficher la date ou l’heure.  
  
```  
BOOL GetIdealSize(LPSIZE psize) const;  
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[out] `psize`|Pointeur vers un [taille](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure qui contient la taille idéale pour le contrôle.|  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de retour est toujours `true`.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [DTM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb761757) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_dateTimeCtrl`, qui est utilisé pour accéder par programme le contrôle de sélecteur de date et d’heure. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1 n °&1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant récupère la taille idéale pour afficher le contrôle de sélecteur de date et d’heure.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1 n °&2;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]  
  
##  <a name="a-namesetformata--cdatetimectrlsetformat"></a><a name="setformat"></a>CDateTimeCtrl::SetFormat  
 Définit l’affichage d’un contrôle de sélecteur de date et d’heure conformément à une chaîne de format donné.  
  
```  
BOOL SetFormat(LPCTSTR pstrFormat);
```  
  
### <a name="parameters"></a>Paramètres  
 *pstrFormat*  
 Pointeur vers une chaîne de format se terminant par zéro qui définit l’affichage de votre choix. Ce paramètre **NULL** réinitialise le contrôle à la chaîne de format par défaut pour le style actuel.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
> [!NOTE]
>  Entrée d’utilisateur ne détermine pas le succès ou l’échec de cet appel.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [DTM_SETFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb761771), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CDateTimeCtrl n °&6;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]  
  
##  <a name="a-namesetmonthcalcolora--cdatetimectrlsetmonthcalcolor"></a><a name="setmonthcalcolor"></a>CDateTimeCtrl::SetMonthCalColor  
 Définit la couleur d’une partie donnée du calendrier mois dans un contrôle de sélecteur de date et d’heure.  
  
```  
COLORREF SetMonthCalColor(
    int iColor,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>Paramètres  
 `iColor`  
 `int`valeur qui spécifie la zone de contrôle month calendar à définir. Cette valeur peut être une des opérations suivantes.  
  
|Valeur|Signification|  
|-----------|-------------|  
|MCSC_BACKGROUND|Définir la couleur d’arrière-plan affichée entre les mois.|  
|MCSC_MONTHBK|Définir la couleur d’arrière-plan affichée dans le mois.|  
|MCSC_TEXT|Définissez la couleur utilisée pour afficher du texte dans un mois.|  
|MCSC_TITLEBK|Définir la couleur d’arrière-plan affichée dans le titre du calendrier.|  
|MCSC_TITLETEXT|Définissez la couleur utilisée pour afficher du texte dans le titre du calendrier.|  
|MCSC_TRAILINGTEXT|Définissez la couleur utilisée pour afficher l’en-tête et le texte des jours de fin. Les jours précédents et sont les jours des mois précédents et suivants qui apparaissent dans le calendrier actuel.|  
  
 `ref`  
 A **COLORREF** valeur représentant la couleur qui est définie pour la zone spécifiée du calendrier du mois.  
  
### <a name="return-value"></a>Valeur de retour  
 A **COLORREF** valeur qui représente le paramètre précédent de la couleur pour la partie spécifiée du contrôle month calendar en cas de réussite. Sinon, le message retourne -1.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [DTM_SETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761773), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor).  
  
##  <a name="a-namesetmonthcalfonta--cdatetimectrlsetmonthcalfont"></a><a name="setmonthcalfont"></a>CDateTimeCtrl::SetMonthCalFont  
 Définit la police qui contrôle month calendar de date et heure sélecteur du contrôle enfant utilisera.  
  
```  
void SetMonthCalFont(
    HFONT hFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `hFont`  
 Handle de la police qui sera définie.  
  
 `bRedraw`  
 Spécifie si le contrôle doit être redessiné immédiatement lors de la définition de la police. Ce paramètre **TRUE** force le contrôle à redessiner.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [DTM_SETMCFONT](http://msdn.microsoft.com/library/windows/desktop/bb761775), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#7;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]  
  
> [!NOTE]
>  Si vous utilisez ce code, que vous souhaitez faire membre de votre `CDialog`-classe appelée dérivée `m_MonthFont` de type **CFont**.  
  
##  <a name="a-namesetmonthcalstylea--cdatetimectrlsetmonthcalstyle"></a><a name="setmonthcalstyle"></a>CDateTimeCtrl::SetMonthCalStyle  
 Définit le style du contrôle calendrier mois de la liste déroulante qui est associé avec le contrôle de sélecteur de date et d’heure actuels.  
  
```  
DWORD SetMonthCalStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|[in] `dwStyle`|Un nouveau mois du calendrier style du contrôle, qui est une combinaison d’opérations de bits (OR) de styles de contrôle month calendar. Pour plus d’informations, consultez [Styles de contrôle Month Calendar](http://msdn.microsoft.com/library/windows/desktop/bb760919).|  
  
### <a name="return-value"></a>Valeur de retour  
 Le style précédent du contrôle calendrier mois de la liste déroulante.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [DTM_SETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761778) message, qui est décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit la variable, `m_dateTimeCtrl`, qui est utilisé pour accéder par programme le contrôle de sélecteur de date et d’heure. Cette variable est utilisée dans l'exemple suivant.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1 n °&1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant définit le contrôle de sélecteur de date et d’heure pour afficher les numéros de semaine, les noms abrégés des jours de la semaine et aucun indicateur aujourd'hui.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1 n °&3;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]  
  
##  <a name="a-namesetrangea--cdatetimectrlsetrange"></a><a name="setrange"></a>CDateTimeCtrl::SetRange  
 Définit les périodes de configurations système minimale et maximale autorisée pour un contrôle de sélecteur de date et d’heure.  
  
```  
BOOL SetRange(
    const COleDateTime* pMinRange,  
    const COleDateTime* pMaxRange);

 
BOOL SetRange(
    const CTime* pMinRange,  
    const CTime* pMaxRange);
```  
  
### <a name="parameters"></a>Paramètres  
 `pMinRange`  
 Un pointeur vers un [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) objet ou un [CTime](../../atl-mfc-shared/reference/ctime-class.md) objet contenant la première heure autorisée dans le `CDateTimeCtrl` objet.  
  
 `pMaxRange`  
 Un pointeur vers un `COleDateTime` objet ou un `CTime` objet contenant la dernière heure autorisée dans le `CDateTimeCtrl` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre implémente le comportement du message Win32 [DTM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761780), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dans l’implémentation par MFC, vous pouvez spécifier `COleDateTime` ou `CTime` utilisations. Si le `COleDateTime` objet a un **NULL** état, la plage sera supprimée. Si le `CTime` pointeur ou `COleDateTime` pointeur est **NULL**, la plage sera supprimée.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CDateTimeCtrl::GetRange](#getrange).  
  
##  <a name="a-namesettimea--cdatetimectrlsettime"></a><a name="settime"></a>CDateTimeCtrl::SetTime  
 Définit l’heure dans un contrôle de sélecteur de date et d’heure.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);  
BOOL SetTime(const CTime* pTimeNew);  
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *transfertnouvelle*  
 Une référence à un [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) objet contenant l’à laquelle le contrôle est fixé.  
  
 *pTimeNew*  
 Dans la deuxième version ci-dessus, un pointeur vers un [CTime](../../atl-mfc-shared/reference/ctime-class.md) objet contenant l’heure défini pour le contrôle. Dans la troisième version ci-dessus, un pointeur vers un [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) structure contenant l’heure défini pour le contrôle.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre implémente le comportement du message Win32 [DTM_SETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761782), comme décrit dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Dans l’implémentation MFC de **SetTime**, vous pouvez utiliser la `COleDateTime` ou `CTime` classes, ou vous pouvez utiliser un `SYSTEMTIME` structure pour définir les informations d’heure.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_CDateTimeCtrl n °&8;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [MFC exemple CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl (classe)](../../mfc/reference/cmonthcalctrl-class.md)

