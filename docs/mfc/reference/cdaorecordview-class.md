---
title: CDaoRecordView (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoRecordView
dev_langs:
- C++
helpviewer_keywords:
- CDaoRecordView class
- data-bound controls [C++], DAO controls
- data binding [C++], DAO views
- bound controls [C++], displaying database data
- application wizards [C++], creating record views
- controls [MFC], data binding
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
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
ms.openlocfilehash: 11aa318e84e89835ceb710725590f3c3e6387fcd
ms.lasthandoff: 02/24/2017

---
# <a name="cdaorecordview-class"></a>CDaoRecordView (classe)
Vue qui affiche des enregistrements de base de données dans des contrôles.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class AFX_NOVTABLE CDaoRecordView : public CFormView  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CDaoRecordView::CDaoRecordView](#cdaorecordview)|Construit un objet `CDaoRecordView`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDaoRecordView::IsOnFirstRecord](#isonfirstrecord)|Retourne zéro si l’enregistrement actif est le premier enregistrement dans le jeu d’enregistrements.|  
|[CDaoRecordView::IsOnLastRecord](#isonlastrecord)|Retourne zéro si l’enregistrement actif est le dernier enregistrement dans le jeu d’enregistrements.|  
|[CDaoRecordView::OnGetRecordset](#ongetrecordset)|Retourne un pointeur vers un objet d’une classe dérivée de `CDaoRecordset`. ClassWizard substitue cette fonction pour vous et crée le jeu d’enregistrements si nécessaire.|  
|[CDaoRecordView::OnMove](#onmove)|Si l’enregistrement en cours a changé, il met à jour sur la source de données, puis passe à l’enregistrement spécifié (suivante, précédente, première ou dernière).|  
  
## <a name="remarks"></a>Remarques  
 La vue est une vue de formulaire directement connectée à un `CDaoRecordset` objet. La vue est créée à partir d’une ressource modèle de boîte de dialogue et affiche les champs de le `CDaoRecordset` l’objet dans les contrôles du modèle de boîte de dialogue. Le `CDaoRecordView` objet utilise l’échange de données de boîtes de dialogue (DDX) et l’échange de champs d’enregistrements DAO (DFX) pour automatiser le déplacement des données entre les contrôles sur le formulaire et les champs de l’objet recordset. `CDaoRecordView`fournit également une implémentation par défaut pour le déplacement vers le premier, suivant, précédent ou le dernier enregistrement et une interface de l’enregistrement actuellement en mode de mise à jour.  
  
> [!NOTE]
>  Les classes de base de données DAO sont distinctes des classes de base de données MFC basées sur Open Database Connectivity (ODBC). Tous les noms de classe de base de données DAO ont le préfixe « CDao ». Vous pouvez toujours accès aux sources de données ODBC avec les classes DAO ; les classes DAO offrent généralement des fonctionnalités supérieures, car elles utilisent le moteur de base de données Microsoft Jet.  
  
 La plus courante consiste à créer votre vue de l’enregistrement avec l’Assistant Application. L’Assistant Application crée la classe de vue de l’enregistrement et ses classes de recordset associées dans le cadre de votre application squelette starter.  
  
 Si vous devez simplement un formulaire unique, l’approche de l’Assistant Création d’applications est plus facile. ClassWizard vous permet de décider d’utiliser une vue d’enregistrement plus tard dans le processus de développement. Si vous ne créez pas la classe de vue de l’enregistrement avec l’Assistant Application, vous pouvez le créer ultérieurement avec ClassWizard. Pour créer une vue d’enregistrement et un jeu d’enregistrements séparément et puis de les connecter à l’aide de ClassWizard est l’approche la plus souple car elle vous donne davantage de contrôle dans la classe de recordset et son. H /. Fichier CPP. Cette approche vous permet également de disposer de plusieurs vues des enregistrements sur la même classe de recordset.  
  
 Pour faciliter aux utilisateurs finaux de déplacement entre les enregistrements dans la vue de l’enregistrement, l’Assistant Application crée menu (et éventuellement de barre d’outils) pour déplacer des ressources à la première, suivant, précédent ou le dernier enregistrement. Si vous créez une classe d’affichage de l’enregistrement avec ClassWizard, vous devez créer ces ressources vous-même avec les menus et la bitmap des éditeurs.  
  
 Pour plus d’informations sur l’implémentation par défaut pour le déplacement entre les enregistrements, consultez `IsOnFirstRecord` et `IsOnLastRecord` et l’article [à l’aide d’une vue d’enregistrement](../../data/using-a-record-view-mfc-data-access.md), qui s’applique aux deux `CRecordView` et `CDaoRecordView`.  
  
 `CDaoRecordView`assure le suivi de la position de l’utilisateur dans le jeu d’enregistrements afin que la vue de l’enregistrement peut mettre à jour l’interface utilisateur. Lorsque l’utilisateur passe à des extrémités de l’objet recordset, la vue d’enregistrement désactive les objets d’interface utilisateur, tels que les éléments de menu ou des boutons de barre d’outils, pour déplacer ultérieurement dans la même direction.  
  
 Pour plus d’informations sur la déclaration et utilisation de votre vue de l’enregistrement et les classes de jeu d’enregistrements, consultez « Conception et création d’une vue enregistrement » dans l’article [vues des enregistrements](../../data/record-views-mfc-data-access.md). Pour plus d’informations sur le travail vues d’enregistrement et de leur utilisation, consultez l’article [à l’aide d’une vue d’enregistrement](../../data/using-a-record-view-mfc-data-access.md). Tous les articles mentionnés ci-dessus s’appliquent aux deux `CRecordView` et `CDaoRecordView`.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CDaoRecordView`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdao.h  
  
##  <a name="a-namecdaorecordviewa--cdaorecordviewcdaorecordview"></a><a name="cdaorecordview"></a>CDaoRecordView::CDaoRecordView  
 Lorsque vous créez un objet d’un type dérivé de `CDaoRecordView`, appelez des deux formes de constructeur pour initialiser l’objet de vue et d’identifier la ressource de boîte de dialogue sur laquelle repose la vue.  
  
```  
explicit CDaoRecordView(LPCTSTR lpszTemplateName);  
explicit CDaoRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszTemplateName`  
 Contient une chaîne terminée par le caractère null qui correspond au nom d’une ressource modèle de boîte de dialogue.  
  
 `nIDTemplate`  
 Contient le numéro d’ID d’une ressource modèle de boîte de dialogue.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez soit identifier la ressource par son nom (passez une chaîne comme argument au constructeur) ou par son ID (passer un entier non signé comme argument). ID est recommandé d’utiliser une ressource.  
  
> [!NOTE]
>  Votre classe dérivée doit fournir son propre constructeur. Dans le constructeur de votre classe dérivée, appelez le constructeur de `CDaoRecordView::CDaoRecordView` avec le nom de la ressource ou l’ID en tant qu’argument.  
  
 **CDaoRecordView::OnInitialUpdate** appelle `CWnd::UpdateData`, qui appelle la méthode `CWnd::DoDataExchange`. Cet appel initial à `DoDataExchange` se connecte `CDaoRecordView` contrôle (indirectement) de `CDaoRecordset` créés par ClassWizard de données membres de champ. Ces membres de données ne peut pas être utilisés tant qu’après l’appel de la classe de base **CFormView::OnInitialUpdate** fonction membre.  
  
> [!NOTE]
>  Si vous utilisez ClassWizard, l’Assistant définit un `enum` valeur `CDaoRecordView::IDD` dans la déclaration de classe et les utilise dans l’initialisation d’un membre de liste pour le constructeur.  
  
 [!code-cpp[NVC_MFCDatabase&#35;](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]  
  
##  <a name="a-nameisonfirstrecorda--cdaorecordviewisonfirstrecord"></a><a name="isonfirstrecord"></a>CDaoRecordView::IsOnFirstRecord  
 Appelez cette fonction membre pour déterminer si l’enregistrement actif est le premier enregistrement de l’objet recordset associé à cette vue de l’enregistrement.  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’enregistrement actif est le premier enregistrement de l’objet recordset. sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est utile pour écrire des gestionnaires de mise à jour de commande écrits par ClassWizard vos propres implémentations de la valeur par défaut.  
  
 Si l’utilisateur se déplace vers le premier enregistrement, le désactive framework des objets d’interface utilisateur (par exemple, les éléments de menu ou les boutons de barre d’outils) que vous avez pour passer à la première ou de l’enregistrement précédent.  
  
##  <a name="a-nameisonlastrecorda--cdaorecordviewisonlastrecord"></a><a name="isonlastrecord"></a>CDaoRecordView::IsOnLastRecord  
 Appelez cette fonction membre pour déterminer si l’enregistrement actif est le dernier enregistrement de l’objet recordset associé à cette vue de l’enregistrement.  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’enregistrement actif est le dernier enregistrement de l’objet recordset. sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est utile pour écrire vos propres implémentations de la valeur par défaut des gestionnaires de mise à jour de commandes ClassWizard écrit pour prendre en charge une interface utilisateur pour le déplacement entre les enregistrements.  
  
> [!CAUTION]
>  Le résultat de cette fonction est fiable, à ceci près que la vue n’est peut-être pas en mesure de détecter la fin du jeu d’enregistrements jusqu'à ce que l’utilisateur ait dépassé. L’utilisateur peut avoir d’aller au-delà du dernier enregistrement avant l’affichage de l’enregistrement peut indiquer qu’il doit désactiver les objets d’interface utilisateur pour les déplacer vers l’enregistrement suivant ou le dernier. Si l’utilisateur déplace au-delà du dernier enregistrement, puis revient au dernier enregistrement (ou avant qu’elle), la vue de l’enregistrement peut effectuer le suivi de la position de l’utilisateur dans le jeu d’enregistrements et désactiver les objets d’interface utilisateur correctement.  
  
##  <a name="a-nameongetrecordseta--cdaorecordviewongetrecordset"></a><a name="ongetrecordset"></a>CDaoRecordView::OnGetRecordset  
 Retourne un pointeur vers le `CDaoRecordset`-dérivés d’objet associé à la vue de l’enregistrement.  
  
```  
virtual CDaoRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CDaoRecordset`-objet dérivé si l’objet a été créé ; sinon une **NULL** pointeur.  
  
### <a name="remarks"></a>Remarques  
 Vous devez substituer cette fonction membre pour créer ou obtenir un objet recordset et de retourner un pointeur vers lui. Si vous déclarez votre classe d’affichage de l’enregistrement avec ClassWizard, l’Assistant écrit un remplacement de la valeur par défaut. Implémentation de ClassWizard par défaut retourne le pointeur de jeu d’enregistrements stocké dans la vue de l’enregistrement s’il en existe. Si non, il construit un objet recordset du type que vous avez spécifié avec ClassWizard et appelle son **ouvrir** membre de fonction pour ouvrir la table ou exécuter la requête, puis retourne un pointeur vers l’objet.  
  
 Pour plus d’informations et d’exemples, consultez l’article [vues des enregistrements : utilisation d’une vue d’enregistrement](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="a-nameonmovea--cdaorecordviewonmove"></a><a name="onmove"></a>CDaoRecordView::OnMove  
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
 L’implémentation par défaut appelle la fonction de membre de déplacement appropriée de le `CDaoRecordset` objet associé à la vue de l’enregistrement.  
  
 Par défaut, `OnMove` met à jour l’enregistrement en cours dans la source de données si l’utilisateur a été modifié dans la vue de l’enregistrement.  
  
 L’Assistant Application crée une ressource de menu avec des éléments de menu premier, dernier enregistrement, enregistrement suivant et enregistrement précédent. Si vous sélectionnez l’option de barre d’outils initiale, l’Assistant Application crée également une barre d’outils avec des boutons correspondant à ces commandes.  
  
 Si vous déplacez au-delà du dernier enregistrement du jeu d’enregistrements, la vue de l’enregistrement continue d’afficher le dernier enregistrement. Si vous déplacez vers l’arrière au-delà du premier enregistrement, la vue de l’enregistrement continue à afficher le premier enregistrement.  
  
> [!CAUTION]
>  L’appel `OnMove` lève une exception si l’objet recordset ne comporte aucun enregistrement. Appeler la fonction de gestionnaire de mise à jour interface utilisateur approprié : **OnUpdateRecordFirst**, **OnUpdateRecordLast**, **OnUpdateRecordNext**, ou **OnUpdateRecordPrev** — correspondants avant de déplacer pour déterminer si le jeu d’enregistrements comporte tous les enregistrements.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CFormView](../../mfc/reference/cformview-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset (classe)](../../mfc/reference/cdaorecordset-class.md)   
 [Classe d’objet CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef (classe)](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase (classe)](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace (classe)](../../mfc/reference/cdaoworkspace-class.md)   
 [Classe de CFormView](../../mfc/reference/cformview-class.md)

