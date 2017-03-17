---
title: Classe de COleCmdUI | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
dev_langs:
- C++
helpviewer_keywords:
- document object server
- COleCmdUI class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
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
ms.openlocfilehash: 38e7019d7636166262028d955455cee675824f8b
ms.lasthandoff: 02/24/2017

---
# <a name="colecmdui-class"></a>COleCmdUI (classe)
Implémente une méthode pour que MFC mette à jour l'état des objets d'interface utilisateur associés aux fonctionnalités pilotées par `IOleCommandTarget`de votre application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleCmdUI::COleCmdUI](#colecmdui)|Construit un objet `COleCmdUI`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleCmdUI::Enable](#enable)|Active ou désactive l’indicateur de commande enable.|  
|[COleCmdUI::SetCheck](#setcheck)|Définit l’état d’un bouton marche/arrêt bascule commande.|  
|[COleCmdUI::SetText](#settext)|Retourne une chaîne de texte Nom ou l’état d’une commande.|  
  
## <a name="remarks"></a>Notes  
 Dans une application qui n’est pas activée pour DocObjects, lorsque l’utilisateur affiche un menu dans l’application, le processus MFC **UPDATE_COMMAND_UI** notifications. Chaque notification reçoit un [CCmdUI](../../mfc/reference/ccmdui-class.md) objet peut être manipulée pour refléter l’état d’une commande particulière. Toutefois, lorsque votre application est activée pour DocObjects, MFC traite **UPDATE_OLE_COMMAND_UI** des notifications et assigne `COleCmdUI` objets.  
  
 `COleCmdUI`autorise DocObject à recevoir des commandes provenant de l’interface utilisateur de son conteneur (par exemple, le fichier-nouveau, ouvrir, imprimer, etc.), et permet à un conteneur de recevoir des commandes qui proviennent de l’interface utilisateur de la DocObject. Bien que `IDispatch` peut être utilisé pour distribuer les mêmes commandes `IOleCommandTarget` offre un moyen plus simple pour interroger et exécuter, car il repose sur un ensemble standard de commandes, généralement sans arguments, et aucune information de type n’est impliquée. `COleCmdUI`peut être utilisé pour activer, de mettre à jour et de définir d’autres propriétés de commandes de l’interface utilisateur DocObject. Lorsque vous souhaitez appeler la commande, appelez [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd).  
  
 Pour plus d’informations sur DocObjects, consultez [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) et [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md). Consultez également [Internet premières étapes : Documents actifs](../../mfc/active-documents-on-the-internet.md) et [Documents actifs](../../mfc/active-documents-on-the-internet.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CCmdUI](../../mfc/reference/ccmdui-class.md)  
  
 `COleCmdUI`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdocobj.h  
  
##  <a name="colecmdui"></a>COleCmdUI::COleCmdUI  
 Construit un `COleCmdUI` objet associé à une commande d’interface utilisateur spécifique.  
  
```  
COleCmdUI(
    OLECMD* rgCmds,  
    ULONG cCmds,  
    const GUID* m_pGroup);
```  
  
### <a name="parameters"></a>Paramètres  
 `rgCmds`  
 Une liste des commandes prises en charge associé au GUID donné. Le **OLECMD** structure associe les commandes avec les indicateurs de commande.  
  
 *cCmds*  
 Le nombre de commandes dans `rgCmds`.  
  
 `pGroup`  
 Pointeur vers un GUID qui identifie un ensemble de commandes.  
  
### <a name="remarks"></a>Notes  
 Le `COleCmdUI` objet fournit une interface de programmation pour la mise à jour des objets d’interface utilisateur de DocObject tels que les éléments de menu ou des boutons de barre de contrôle. Les objets d’interface utilisateur peuvent être activés, désactivés, activés, et/ou désactivées via la `COleCmdUI` objet.  
  
##  <a name="enable"></a>COleCmdUI::Enable  
 Appelez cette fonction pour définir l’indicateur de commande de la `COleCmdUI` objet **OLECOMDF_ENABLED**, ce qui indique la commande à l’interface est disponible et activée, ou pour effacer l’indicateur de commande.  
  
```  
virtual void Enable(BOOL bOn);
```  
  
### <a name="parameters"></a>Paramètres  
 `bOn`  
 Indique si la commande associée à la `COleCmdUI` objet doit être activé ou désactivé. NonZero permet à la commande. 0 désactive la commande.  
  
##  <a name="setcheck"></a>COleCmdUI::SetCheck  
 Appelez cette fonction pour définir l’état d’un bouton marche/arrêt bascule commande.  
  
```  
virtual void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>Paramètres  
 `nCheck`  
 Une valeur qui détermine l’état à définir un bouton marche/arrêt bascule commande. Les valeurs possibles sont :  
  
|Valeur|Description|  
|-----------|-----------------|  
|**1**|Définit la commande à on.|  
|**2**|Définit la commande à indéterminé ; l’état ne peut pas être déterminé, car l’attribut de cette commande est dans à la fois et désactiver les États dans la sélection appropriée.|  
|toute autre valeur|Définit la commande à off.|  
  
##  <a name="settext"></a>COleCmdUI::SetText  
 Appelez cette fonction pour retourner une chaîne de texte Nom ou l’état d’une commande.  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszText`  
 Pointeur vers le texte à utiliser avec la commande.  
  
## <a name="see-also"></a>Voir aussi  
 [CCmdUI (classe)](../../mfc/reference/ccmdui-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




