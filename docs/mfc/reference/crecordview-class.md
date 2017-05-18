---
title: CRecordView (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRecordView
- AFXDB/CRecordView
- AFXDB/CRecordView::CRecordView
- AFXDB/CRecordView::IsOnFirstRecord
- AFXDB/CRecordView::IsOnLastRecord
- AFXDB/CRecordView::OnGetRecordset
- AFXDB/CRecordView::OnMove
- AFXDB/CRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- CRecordView class
- ODBC recordsets, viewing records
- records, viewing ODBC
- views, ODBC
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
caps.latest.revision: 25
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 04ff47900037dcbaa12e2cba2c9a3e84caf54a69
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="crecordview-class"></a>CRecordView (classe)
Vue qui affiche des enregistrements de base de données dans des contrôles.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class AFX_NOVTABLE CRecordView : public CFormView  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CRecordView::CRecordView](#crecordview)|Construit un objet `CRecordView`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CRecordView::IsOnFirstRecord](#isonfirstrecord)|Retourne zéro si l’enregistrement actif est le premier enregistrement dans le jeu d’enregistrements.|  
|[CRecordView::IsOnLastRecord](#isonlastrecord)|Retourne zéro si l’enregistrement actif est le dernier enregistrement dans le jeu d’enregistrements.|  
|[CRecordView::OnGetRecordset](#ongetrecordset)|Retourne un pointeur vers un objet d’une classe dérivée de `CRecordset`. ClassWizard substitue cette fonction pour vous et crée le jeu d’enregistrements si nécessaire.|  
|[CRecordView::OnMove](#onmove)||  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CRecordView::OnMove](#onmove)|Si l’enregistrement en cours a changé, il met à jour sur la source de données, puis passe à l’enregistrement spécifié (suivante, précédente, première ou dernière).|  
  
## <a name="remarks"></a>Notes  
 La vue est une vue de formulaire directement connectée à un `CRecordset` objet. La vue est créée à partir d’une ressource modèle de boîte de dialogue et affiche les champs de le `CRecordset` l’objet dans les contrôles du modèle de boîte de dialogue. Le `CRecordView` objet utilise l’échange de données de boîtes de dialogue (DDX) et l’échange de champs d’enregistrements (RFX) pour automatiser le déplacement des données entre les contrôles sur le formulaire et les champs de l’objet recordset. `CRecordView`fournit également une implémentation par défaut pour le déplacement vers le premier, suivant, précédent ou le dernier enregistrement et une interface de mise à jour de l’enregistrement actuellement affiché.  
  
> [!NOTE]
>  Si vous travaillez avec les classes d’objets d’accès aux données (DAO) plutôt que les classes Open Database Connectivity (ODBC), utilisez la classe [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) à la place. Pour plus d’informations, consultez l’article [vue d’ensemble : programmation de base de données](../../data/data-access-programming-mfc-atl.md).  
  
 La plus courante consiste à créer votre vue de l’enregistrement avec l’Assistant Application. Assistant Création d’applications TGE crée la classe de vue de l’enregistrement et ses classes de recordset associées dans le cadre de votre application squelette starter. Si vous ne créez pas la classe de vue de l’enregistrement avec l’Assistant Application, vous pouvez le créer ultérieurement avec ClassWizard. Si vous devez simplement un formulaire unique, l’approche de l’Assistant Création d’applications est plus facile. ClassWizard vous permet de décider d’utiliser une vue d’enregistrement plus tard dans le processus de développement. Pour créer une vue d’enregistrement et un jeu d’enregistrements séparément et puis de les connecter à l’aide de ClassWizard est l’approche la plus souple car elle vous donne davantage de contrôle dans la classe de recordset et son. H /. Fichier CPP. Cette approche vous permet également de disposer de plusieurs vues des enregistrements sur la même classe de recordset.  
  
 Pour faciliter aux utilisateurs finaux de déplacement entre les enregistrements dans la vue de l’enregistrement, l’Assistant Application crée menu (et éventuellement de barre d’outils) pour déplacer des ressources à la première, suivant, précédent ou le dernier enregistrement. Si vous créez une classe d’affichage de l’enregistrement avec ClassWizard, vous devez créer ces ressources vous-même avec les menus et la bitmap des éditeurs.  
  
 Pour plus d’informations sur l’implémentation par défaut pour le déplacement entre les enregistrements, consultez `IsOnFirstRecord` et `IsOnLastRecord` et l’article [à l’aide d’une vue d’enregistrement](../../data/using-a-record-view-mfc-data-access.md).  
  
 `CRecordView`assure le suivi de la position de l’utilisateur dans le jeu d’enregistrements afin que la vue de l’enregistrement peut mettre à jour l’interface utilisateur. Lorsque l’utilisateur passe à des extrémités de l’objet recordset, la vue d’enregistrement désactive les objets d’interface utilisateur, tels que les éléments de menu ou des boutons de barre d’outils, pour déplacer ultérieurement dans la même direction.  
  
 Pour plus d’informations sur la déclaration et utilisation de votre vue de l’enregistrement et les classes de jeu d’enregistrements, consultez « Conception et création d’une vue enregistrement » dans l’article [vues des enregistrements](../../data/record-views-mfc-data-access.md). Pour plus d’informations sur le travail vues d’enregistrement et de leur utilisation, consultez l’article [à l’aide d’une vue d’enregistrement](../../data/using-a-record-view-mfc-data-access.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CRecordView`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdb.h  
  
##  <a name="crecordview"></a>CRecordView::CRecordView  
 Lorsque vous créez un objet d’un type dérivé de `CRecordView`, appelez des deux formes de constructeur pour initialiser l’objet de vue et d’identifier la ressource de boîte de dialogue sur laquelle repose la vue.  
  
```  
explicit CRecordView(LPCTSTR lpszTemplateName);  
explicit CRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszTemplateName`  
 Contient une chaîne terminée par le caractère null qui correspond au nom d’une ressource modèle de boîte de dialogue.  
  
 `nIDTemplate`  
 Contient le numéro d’ID d’une ressource modèle de boîte de dialogue.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez soit identifier la ressource par son nom (passez une chaîne comme argument au constructeur) ou par son ID (passer un entier non signé comme argument). ID est recommandé d’utiliser une ressource.  
  
> [!NOTE]
>  Votre classe dérivée *doit* fournir son propre constructeur. Dans le constructeur de votre classe dérivée, appelez le constructeur de `CRecordView::CRecordView` avec le nom de la ressource ou l’ID en tant qu’argument, comme illustré dans l’exemple ci-dessous.  
  
 **CRecordView::OnInitialUpdate** appelle `UpdateData`, qui appelle la méthode `DoDataExchange`. Cet appel initial à `DoDataExchange` se connecte `CRecordView` contrôle (indirectement) de `CRecordset` créés par ClassWizard de données membres de champ. Ces membres de données ne peut pas être utilisés tant qu’après l’appel de la classe de base **CFormView::OnInitialUpdate** fonction membre.  
  
> [!NOTE]
>  Si vous utilisez ClassWizard, l’Assistant définit un `enum` valeur `CRecordView::IDD`, il spécifie dans la déclaration de classe et l’utilise dans la liste d’initialisation de membre du constructeur.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDatabase n°&32;](../../mfc/codesnippet/cpp/crecordview-class_1.cpp)]  
  
##  <a name="isonfirstrecord"></a>CRecordView::IsOnFirstRecord  
 Appelez cette fonction membre pour déterminer si l’enregistrement actif est le premier enregistrement de l’objet recordset associé à cette vue de l’enregistrement.  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’enregistrement actif est le premier enregistrement de l’objet recordset. sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est utile pour écrire vos propres implémentations par défaut de gestionnaires de mise à jour de commande écrits par ClassWizard.  
  
 Si l’utilisateur se déplace vers le premier enregistrement, le framework désactive les objets d’interface utilisateur pour atteindre la première ou de l’enregistrement précédent.  
  
##  <a name="isonlastrecord"></a>CRecordView::IsOnLastRecord  
 Appelez cette fonction membre pour déterminer si l’enregistrement actif est le dernier enregistrement de l’objet recordset associé à cette vue de l’enregistrement.  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’enregistrement actif est le dernier enregistrement de l’objet recordset. sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est utile pour écrire vos propres implémentations de la valeur par défaut des gestionnaires de mise à jour de commandes ClassWizard écrit pour prendre en charge une interface utilisateur pour le déplacement entre les enregistrements.  
  
> [!CAUTION]
>  Le résultat de cette fonction est fiable, à ceci près que la vue ne peut pas détecter la fin du jeu d’enregistrements jusqu'à ce que l’utilisateur a déplacé au-delà de celle-ci. L’utilisateur doit déplacer au-delà du dernier enregistrement avant l’affichage de l’enregistrement peut indiquer qu’il doit désactiver les objets d’interface utilisateur pour les déplacer vers l’enregistrement suivant ou le dernier. Si l’utilisateur déplace au-delà du dernier enregistrement, puis revient au dernier enregistrement (ou avant qu’elle), la vue de l’enregistrement peut effectuer le suivi de la position de l’utilisateur dans le jeu d’enregistrements et désactiver les objets d’interface utilisateur correctement. `IsOnLastRecord`est également non fiable après un appel à la fonction de mise en œuvre **OnRecordLast**, qui gère les `ID_RECORD_LAST` commande, ou `CRecordset::MoveLast`.  
  
##  <a name="ongetrecordset"></a>CRecordView::OnGetRecordset  
 Retourne un pointeur vers le `CRecordset`-dérivés d’objet associé à la vue de l’enregistrement.  
  
```  
virtual CRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CRecordset`-objet dérivé si l’objet a été créé ; sinon une **NULL** pointeur.  
  
### <a name="remarks"></a>Remarques  
 Vous devez substituer cette fonction membre pour créer ou obtenir un objet recordset et de retourner un pointeur vers lui. Si vous déclarez votre classe d’affichage de l’enregistrement avec ClassWizard, l’Assistant écrit un remplacement de la valeur par défaut. Implémentation de ClassWizard par défaut retourne le pointeur de jeu d’enregistrements stocké dans la vue de l’enregistrement s’il en existe. Si non, il construit un objet recordset du type que vous avez spécifié avec ClassWizard et appelle son **ouvrir** membre de fonction pour ouvrir la table ou exécuter la requête, puis retourne un pointeur vers l’objet.  
  
 Pour plus d’informations et d’exemples, consultez l’article [vues des enregistrements : utilisation d’une vue d’enregistrement](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="onmove"></a>CRecordView::OnMove  
 Appelez cette fonction membre pour déplacer vers un autre enregistrement dans le jeu d’enregistrements et afficher ses champs dans les contrôles de la vue de l’enregistrement.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDMoveCommand`  
 Une des valeurs d’ID de commande standard suivantes :  
  
- `ID_RECORD_FIRST`Déplacer vers le premier enregistrement du jeu d’enregistrements.  
  
- `ID_RECORD_LAST`Accéder au dernier enregistrement dans le jeu d’enregistrements.  
  
- `ID_RECORD_NEXT`Déplacer vers l’enregistrement suivant dans le jeu d’enregistrements.  
  
- `ID_RECORD_PREV`Déplacer vers l’enregistrement précédent dans le jeu d’enregistrements.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le déplacement a réussi ; Sinon, 0 si la demande de déplacement a été refusée.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut appelle approprié **déplacer** fonction membre de la `CRecordset` objet associé à la vue de l’enregistrement.  
  
 Par défaut, `OnMove` met à jour l’enregistrement en cours dans la source de données si l’utilisateur a été modifié dans la vue de l’enregistrement.  
  
 L’Assistant Application crée une ressource de menu avec des éléments de menu premier, dernier enregistrement, enregistrement suivant et enregistrement précédent. Si vous sélectionnez l’option de barre d’outils ancrable, l’Assistant Application crée également une barre d’outils avec des boutons correspondant à ces commandes.  
  
 Si vous déplacez au-delà du dernier enregistrement du jeu d’enregistrements, la vue de l’enregistrement continue d’afficher le dernier enregistrement. Si vous déplacez vers l’arrière au-delà du premier enregistrement, la vue de l’enregistrement continue à afficher le premier enregistrement.  
  
> [!CAUTION]
>  L’appel `OnMove` lève une exception si l’objet recordset ne comporte aucun enregistrement. Appeler la fonction de gestionnaire de mise à jour interface utilisateur approprié : **OnUpdateRecordFirst**, **OnUpdateRecordLast**, **OnUpdateRecordNext**, ou **OnUpdateRecordPrev** — correspondants avant de déplacer pour déterminer si le jeu d’enregistrements comporte tous les enregistrements.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CFormView](../../mfc/reference/cformview-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CRecordset (classe)](../../mfc/reference/crecordset-class.md)   
 [Classe de CFormView](../../mfc/reference/cformview-class.md)

