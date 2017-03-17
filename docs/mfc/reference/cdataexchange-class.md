---
title: CDataExchange (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
dev_langs:
- C++
helpviewer_keywords:
- DDX/DDV, Technical Note 26
- DDX/DDV, CDataExchange class
- DDX (dialog data exchange), direction of exchange
- DDX (dialog data exchange), between dialog and CDialog
- DDX (dialog data exchange), custom DDX routines
- DDV (dialog data validation)
- m_bSaveAndValidate
- CDataExchange class
- exchanging data between dialogs and CDialogs
- DDV (dialog data validation), custom DDV routines
- DDX/DDV
- DDX (dialog data exchange)
- validating data, dialog box data entry
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
caps.latest.revision: 20
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
ms.openlocfilehash: 8f35e87d562a894411401755ccd4fdd54e43b58a
ms.lasthandoff: 02/24/2017

---
# <a name="cdataexchange-class"></a>CDataExchange (classe)
Prend en charge les routines d’échange de données de boîtes de dialogue (DDX) et de validation de données de boîtes de dialogue (DDV) utilisées par les classes MFC (Microsoft Foundation Class).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDataExchange  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDataExchange::CDataExchange](#cdataexchange)|Construit un objet `CDataExchange`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDataExchange::Fail](#fail)|Appelé lorsque la validation échoue. Réinitialise le focus au contrôle précédent et lève une exception.|  
|[CDataExchange::PrepareCtrl](#preparectrl)|Prépare le contrôle spécifié pour l’échange de données ou la validation. Utilisation des contrôles de nonedit.|  
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|Prépare le contrôle d’édition spécifié pour l’échange de données ou la validation.|  
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|Prépare le contrôle OLE spécifié pour l’échange de données ou la validation. Utilisation des contrôles de nonedit.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|Indicateur pour la direction de DDX et DDV.|  
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|La boîte de dialogue ou la fenêtre dans laquelle l’échange de données a lieu.|  
  
## <a name="remarks"></a>Remarques  
 `CDataExchange`n’a pas d’une classe de base.  
  
 Utilisez cette classe si vous écrivez des routines d’échange de données pour les types de données personnalisés ou des contrôles, ou si vous écrivez vos propres routines de validation des données. Pour plus d’informations sur l’écriture de vos propres routines DDX et DDV, consultez [Technical Note 26](../../mfc/tn026-ddx-and-ddv-routines.md). Pour une vue d’ensemble de DDX et DDV, consultez [boîte de dialogue données échange et Validation de](../../mfc/dialog-data-exchange-and-validation.md) et [boîtes de dialogue](../../mfc/dialog-boxes.md).  
  
 Un `CDataExchange` objet fournit les informations de contexte nécessaires pour placent DDX et DDV à prendre. L’indicateur `m_bSaveAndValidate` est **FALSE** lorsque DDX est utilisée pour remplir les valeurs initiales des contrôles de boîte de dialogue à partir de membres de données. L’indicateur `m_bSaveAndValidate` est **TRUE** lorsque DDX est utilisée pour définir les valeurs actuelles des contrôles de boîte de dialogue dans les membres de données et quand les DDV est utilisé pour valider les valeurs de données. Si la validation DDV échoue, la procédure DDV affichera une boîte de message décrivant l’erreur d’entrée. Appelle ensuite la procédure DDV **échec** pour réinitialiser le focus au contrôle incriminé et lever une exception pour arrêter le processus de validation.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CDataExchange`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="cdataexchange"></a>CDataExchange::CDataExchange  
 Appelez cette fonction membre pour construire un `CDataExchange` objet.  
  
```  
CDataExchange(
    CWnd* pDlgWnd,  
    BOOL bSaveAndValidate);
```  
  
### <a name="parameters"></a>Paramètres  
 *pDlgWnd*  
 Pointeur vers la fenêtre parente qui contient le contrôle. Il s’agit généralement un [CDialog](../../mfc/reference/cdialog-class.md)-objet dérivé.  
  
 `bSaveAndValidate`  
 Si **TRUE**, valide les données de cet objet, puis écrit les données des contrôles aux membres. Si **FALSE**, cet objet déplace des données des membres à des contrôles.  
  
### <a name="remarks"></a>Notes  
 Construire un `CDataExchange` objet vous-même pour stocker des informations supplémentaires dans l’objet exchange de données à transmettre à votre fenêtre [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) fonction membre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCControlLadenDialog&#70;](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]  
  
##  <a name="fail"></a>CDataExchange::Fail  
 L’infrastructure appelle cette fonction membre en cas d’échec d’une opération de validation (DDV) de données de boîte de dialogue.  
  
```  
void Fail();
```  
  
### <a name="remarks"></a>Remarques  
 **Échec** restaure le focus et la sélection sur le contrôle dont la validation a échoué (s’il existe un contrôle à restaurer). **Échec** puis lève une exception de type [CUserException](../../mfc/reference/cuserexception-class.md) pour arrêter le processus de validation. L’exception provoque l’erreur à afficher une boîte de message. Après l’échec de la validation de DDV, l’utilisateur peut entrer des données dans le contrôle qui posent problème.  
  
 Les implémenteurs de routines DDV personnalisées peuvent appeler **échec** à partir des procédures en cas d’échec d’une validation.  
  
 Pour plus d’informations sur l’écriture de vos propres routines DDX et DDV, consultez [Technical Note 26](../../mfc/tn026-ddx-and-ddv-routines.md). Pour une vue d’ensemble de DDX et DDV, consultez [boîte de dialogue données échange et Validation de](../../mfc/dialog-data-exchange-and-validation.md) et [rubriques de la boîte de dialogue](../../mfc/dialog-boxes.md).  
  
##  <a name="m_bsaveandvalidate"></a>CDataExchange::m_bSaveAndValidate  
 Cet indicateur indique la direction d’une opération d’échange de données boîte de dialogue.  
  
```  
BOOL m_bSaveAndValidate;  
```  
  
### <a name="remarks"></a>Remarques  
 L’indicateur est différente de zéro si le `CDataExchange` objet est utilisé pour déplacer des données dans les contrôles de boîte de dialogue pour les membres de données de classe de boîte de dialogue une fois que l’utilisateur modifie les contrôles. L’indicateur est égal à zéro si l’objet est utilisé pour initialiser des contrôles de boîte de dialogue à partir de données membres de classe de boîte de dialogue.  
  
 L’indicateur est également différente de zéro pendant la validation de données de boîtes de dialogue (DDV).  
  
 Pour plus d’informations sur l’écriture de vos propres routines DDX et DDV, consultez [Technical Note 26](../../mfc/tn026-ddx-and-ddv-routines.md). Pour une vue d’ensemble de DDX et DDV, consultez [boîte de dialogue données échange et Validation de](../../mfc/dialog-data-exchange-and-validation.md) et [rubriques de la boîte de dialogue](../../mfc/dialog-boxes.md).  
  
##  <a name="m_pdlgwnd"></a>CDataExchange::m_pDlgWnd  
 Contient un pointeur vers le [CWnd](../../mfc/reference/cwnd-class.md) objet de boîte de dialogue d'où l’échange de données (DDX) ou validation (DDV) est en cours.  
  
```  
CWnd* m_pDlgWnd;  
```  
  
### <a name="remarks"></a>Remarques  
 Cet objet est généralement un [CDialog](../../mfc/reference/cdialog-class.md) objet. Les implémenteurs de routines DDX ou DDV personnalisées peuvent utiliser ce pointeur pour accéder à la boîte de dialogue qui contient les contrôles qu’ils fonctionnent sur.  
  
 Pour plus d’informations sur l’écriture de vos propres routines DDX et DDV, consultez [Technical Note 26](../../mfc/tn026-ddx-and-ddv-routines.md). Pour une vue d’ensemble de DDX et DDV, consultez [boîte de dialogue données échange et Validation de](../../mfc/dialog-data-exchange-and-validation.md) et [rubriques de la boîte de dialogue](../../mfc/dialog-boxes.md).  
  
##  <a name="preparectrl"></a>CDataExchange::PrepareCtrl  
 L’infrastructure appelle cette fonction membre pour préparer le contrôle spécifié pour l’échange de données de boîtes de dialogue (DDX) et validation (DDV).  
  
```  
HWND PrepareCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDC`  
 L’ID du contrôle peut être préparé pour DDX ou DDV.  
  
### <a name="return-value"></a>Valeur de retour  
 Le `HWND` du contrôle en cours de préparation pour DDX ou DDV.  
  
### <a name="remarks"></a>Remarques  
 Utilisez [PrepareEditCtrl](#prepareeditctrl) à la place pour les contrôles d’édition ; utilisez cette fonction membre pour tous les autres contrôles.  
  
 Préparation comprend le stockage du contrôle `HWND` dans la `CDataExchange` classe. L’infrastructure utilise ce handle pour restaurer le focus sur le contrôle en cas de défaillance DDX ou DDV précédemment actif.  
  
 Les implémenteurs de routines DDX ou DDV personnalisées doivent appeler `PrepareCtrl` pour tous les contrôles non modifiable pour lequel ils sont échanger des données via DDX ou validation des données via DDV.  
  
 Pour plus d’informations sur l’écriture de vos propres routines DDX et DDV, consultez [Technical Note 26](../../mfc/tn026-ddx-and-ddv-routines.md). Pour une vue d’ensemble de DDX et DDV, consultez [boîte de dialogue données échange et Validation de](../../mfc/dialog-data-exchange-and-validation.md) et [rubriques de la boîte de dialogue](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareeditctrl"></a>CDataExchange::PrepareEditCtrl  
 L’infrastructure appelle cette fonction membre pour préparer le contrôle d’édition spécifié pour l’échange de données de boîtes de dialogue (DDX) et validation (DDV).  
  
```  
HWND PrepareEditCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDC`  
 L’ID du contrôle d’édition peut être préparé pour DDX ou DDV.  
  
### <a name="return-value"></a>Valeur de retour  
 Le `HWND` du contrôle d’édition en cours de préparation pour DDX ou DDV.  
  
### <a name="remarks"></a>Notes  
 Utilisez [PrepareCtrl](#preparectrl) à la place pour tous les autres contrôles.  
  
 Préparation se compose de deux éléments. Tout d’abord, `PrepareEditCtrl` stocke du contrôle `HWND` dans la `CDataExchange` classe. L’infrastructure utilise ce handle pour restaurer le focus sur le contrôle en cas de défaillance DDX ou DDV précédemment actif. Ensuite, `PrepareEditCtrl` définit un indicateur dans la `CDataExchange` classe pour indiquer que le contrôle dont les données sont échangées ou validé sont un contrôle d’édition.  
  
 Les implémenteurs de routines DDX ou DDV personnalisées doivent appeler `PrepareEditCtrl` pour tous les contrôles pour lesquels ils sont échanger des données via DDX ou validation des données via DDV d’édition.  
  
 Pour plus d’informations sur l’écriture de vos propres routines DDX et DDV, consultez [Technical Note 26](../../mfc/tn026-ddx-and-ddv-routines.md). Pour une vue d’ensemble de DDX et DDV, consultez [boîte de dialogue données échange et Validation de](../../mfc/dialog-data-exchange-and-validation.md) et [rubriques de la boîte de dialogue](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareolectrl"></a>CDataExchange::PrepareOleCtrl  
 L’infrastructure appelle cette fonction membre pour préparer le contrôle OLE spécifié pour l’échange de données de boîtes de dialogue (DDX) et validation (DDV).  
  
```  
COleControlSite* PrepareOleCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDC`  
 L’ID du contrôle OLE peut être préparé pour DDX ou DDV.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le site de contrôle OLE.  
  
### <a name="remarks"></a>Remarques  
 Utilisez [PrepareEditCtrl](#prepareeditctrl) à la place pour les contrôles d’édition ou [PrepareCtrl](#preparectrl) pour tous les autres contrôles non OLE.  
  
 Les implémenteurs de routines DDX ou DDV personnalisées doivent appeler `PrepareOleCtrl` pour tous les contrôles OLE pour lequel ils sont échanger des données via DDX ou validation des données via DDV.  
  
 Pour plus d’informations sur l’écriture de vos propres routines DDX et DDV, consultez [Technical Note 26](../../mfc/tn026-ddx-and-ddv-routines.md). Pour une vue d’ensemble de DDX et DDV, consultez [boîte de dialogue données échange et Validation de](../../mfc/dialog-data-exchange-and-validation.md) et [rubriques de la boîte de dialogue](../../mfc/dialog-boxes.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC VIEWEX](../../visual-cpp-samples.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)   
 [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)


