---
title: COleDBRecordView (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDBRecordView
dev_langs:
- C++
helpviewer_keywords:
- MFC, OLE DB
- COleDBRecordView class
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 89b5cb175900d11854dcad03440a1ef0bfb8cff9
ms.lasthandoff: 02/24/2017

---
# <a name="coledbrecordview-class"></a>COleDBRecordView (classe)
Vue qui affiche des enregistrements de base de données dans des contrôles.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|Construit un objet `COleDBRecordView`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Retourne une norme `HRESULT` valeur.|  
|[COleDBRecordView::OnMove](#onmove)|Met à jour l’enregistrement en cours (si « Dirty ») sur la source de données, puis l’enregistrement spécifié (suivante, précédente, première ou dernière).|  
  
## <a name="remarks"></a>Notes  
 La vue est une vue de formulaire directement connectée à un `CRowset` objet. La vue est créée à partir d’une ressource modèle de boîte de dialogue et affiche les champs de le `CRowset` l’objet dans les contrôles du modèle de boîte de dialogue. Le `COleDBRecordView` objet utilise l’échange de données de boîtes de dialogue (DDX) et les fonctionnalités de navigation intégrées `CRowset`, pour automatiser le déplacement des données entre les contrôles sur le formulaire et les champs de l’ensemble de lignes. `COleDBRecordView`fournit également une implémentation par défaut pour le déplacement vers le premier, suivant, précédent ou le dernier enregistrement et une interface de mise à jour de l’enregistrement actuellement affiché.  
  
 Vous pouvez utiliser des fonctions DDX avec **COleDbRecordView** pour obtenir des données directement à partir du jeu d’enregistrements de base de données et les afficher dans un contrôle de boîte de dialogue. Vous devez utiliser le **DDX_\* ** méthodes (telles que `DDX_Text`), et non le **DDX_Field\* ** fonctions (telles que `DDX_FieldText`) avec **COleDbRecordView**. `DDX_FieldText`ne fonctionne pas avec **COleDbRecordView** car `DDX_FieldText` prend un argument supplémentaire de type **CRecordset\* ** (pour `CRecordView`) ou **CDaoRecordset\* ** (pour `CDaoRecordView`).  
  
> [!NOTE]
>  Si vous travaillez avec les classes d’objets d’accès aux données (DAO) plutôt que les classes de modèles du consommateur OLE DB, utilisez la classe [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) à la place. Pour plus d’informations, consultez l’article [vue d’ensemble : programmation de base de données](../../data/data-access-programming-mfc-atl.md).  
  
 `COleDBRecordView`assure le suivi de la position de l’utilisateur dans l’ensemble de lignes afin que la vue de l’enregistrement peut mettre à jour l’interface utilisateur. Lorsque l’utilisateur passe à des extrémités de l’ensemble de lignes, la vue d’enregistrement désactive utilisateur interface objets â €» tels que les éléments de menu ou de barre d’outils boutons â €» pour le déplacement dans la même direction.  
  
 Pour plus d’informations sur les classes de l’ensemble de lignes, consultez le [à l’aide de OLE DB modèles du consommateur](../../data/oledb/ole-db-consumer-templates-cpp.md) article.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxoledb.h  
  
##  <a name="a-namecoledbrecordviewa--coledbrecordviewcoledbrecordview"></a><a name="coledbrecordview"></a>COleDBRecordView::COleDBRecordView  
 Construit un objet `COleDBRecordView`.  
  
```  
COleDBRecordView(LPCTSTR lpszTemplateName);  
COleDBRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszTemplateName`  
 Contient une chaîne terminée par le caractère null qui correspond au nom d’une ressource modèle de boîte de dialogue.  
  
 `nIDTemplate`  
 Contient le numéro d’ID d’une ressource modèle de boîte de dialogue.  
  
### <a name="remarks"></a>Remarques  
 Lorsque vous créez un objet d’un type dérivé de `COleDBRecordView`, appelez un des constructeurs pour créer l’objet d’affichage et d’identifier la ressource de boîte de dialogue sur laquelle repose la vue. Vous pouvez identifier la ressource par son nom (passez une chaîne comme argument au constructeur) ou par son ID (passer un entier non signé comme argument).  
  
> [!NOTE]
>  Votre classe dérivée *doit* fournir son propre constructeur. Dans le constructeur, appelez le constructeur, `COleDBRecordView::COleDBRecordView`, avec le nom de la ressource ou l’ID en tant qu’argument.  
  
##  <a name="a-nameongetrowseta--coledbrecordviewongetrowset"></a><a name="ongetrowset"></a>COleDBRecordView::OnGetRowset  
 Retourne un handle pour le **CRowset<> </> ** objet associé à la vue de l’enregistrement.  
  
```  
virtual CRowset<>* OnGetRowset(Â) = 0;  
 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Vous devez substituer cette fonction membre pour créer ou obtenir un objet d’ensemble de lignes et de retourner un handle vers lui. Si vous déclarez votre classe d’affichage de l’enregistrement avec ClassWizard, l’Assistant écrit un remplacement de la valeur par défaut. Implémentation de ClassWizard par défaut retourne le handle de l’ensemble de lignes stocké dans la vue de l’enregistrement s’il en existe. Si non, il construit un objet d’ensemble de lignes du type que vous avez spécifié avec ClassWizard et appelle son **ouvrir** membre de fonction pour ouvrir la table ou exécuter la requête, puis retourne un handle vers l’objet.  
  
> [!NOTE]
>  Qui précèdent MFC 7.0, `OnGetRowset` retourné un pointeur vers `CRowset`. Si vous avez un code qui appelle `OnGetRowset`, vous devez modifier le type de retour à la classe version **CRowset<>**.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDatabase&#38;](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]  
  
 Pour plus d’informations et d’exemples, consultez l’article [vues des enregistrements : utilisation d’une vue d’enregistrement](../../data/using-a-record-view-mfc-data-access.md).  
  
##  <a name="a-nameonmovea--coledbrecordviewonmove"></a><a name="onmove"></a>COleDBRecordView::OnMove  
 Permet d’afficher se déplace vers un autre enregistrement dans le jeu de lignes et d’afficher ses champs dans les contrôles de l’enregistrement.  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDMoveCommand`  
 Une des valeurs d’ID de commande standard suivantes :  
  
- `ID_RECORD_FIRST`Â Â Â déplacer vers le premier enregistrement du jeu d’enregistrements.  
  
- `ID_RECORD_LAST`Â Â Â déplacer au dernier enregistrement du jeu d’enregistrements.  
  
- `ID_RECORD_NEXT`Â Â Â atteindre l’enregistrement suivant dans le jeu d’enregistrements.  
  
- `ID_RECORD_PREV`Â Â Â atteindre l’enregistrement précédent dans le jeu d’enregistrements.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le déplacement a réussi ; Sinon, 0 si la demande de déplacement a été refusée.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut appelle approprié **déplacer** fonction membre de la `CRowset` objet associé à la vue de l’enregistrement.  
  
 Par défaut, `OnMove` met à jour l’enregistrement en cours dans la source de données si l’utilisateur a été modifié dans la vue de l’enregistrement.  
  
 L’Assistant Application crée une ressource de menu avec des éléments de menu premier, dernier enregistrement, enregistrement suivant et enregistrement précédent. Si vous sélectionnez l’option de barre d’outils ancrable, l’Assistant Application crée également une barre d’outils avec des boutons correspondant à ces commandes.  
  
 Si vous déplacez au-delà du dernier enregistrement du jeu d’enregistrements, la vue de l’enregistrement continue d’afficher le dernier enregistrement. Si vous déplacez vers l’arrière au-delà du premier enregistrement, la vue de l’enregistrement continue à afficher le premier enregistrement.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




