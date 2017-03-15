---
title: "Contrôle d’application | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- application control
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
caps.latest.revision: 12
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 81eb0bcdd8c9d154f62635e7f306cefcf7a15c1b
ms.lasthandoff: 02/24/2017

---
# <a name="application-control"></a>Contrôle d'application
OLE requiert un contrôle important sur les applications et leurs objets. Les DLL système OLE doivent être en mesure de lancer et de distribuer automatiquement des applications, coordonner leur production et la modification d’objets, et ainsi de suite. Les fonctions dans cette rubrique satisfaire ces besoins. Outre appelée par les DLL système OLE, ces fonctions doivent parfois être appelées par les applications.  
  
### <a name="application-control"></a>Contrôle d'application  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|Indique si l’application peut s’arrêter.|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Récupère le filtre de messages en cours de l’application.|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Récupère l’indicateur de contrôle de l’utilisateur actuel.|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Active ou désactive l’indicateur de contrôle utilisateur.|  
|[AfxOleLockApp](#afxolelockapp)|Incrémente le nombre global de l’infrastructure du nombre d’objets actifs dans une application.|  
|[AfxOleUnlockApp](#afxoleunlockapp)|Décrémente décompte de l’infrastructure du nombre d’objets actifs dans une application.|  
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Inscrit un serveur dans le Registre du système OLE.|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|Implémente l’interface utilisateur pour le *typename* commande de l’objet.|  
  
##  <a name="a-nameafxolecanexitappa--afxolecanexitapp"></a><a name="afxolecanexitapp"></a>AfxOleCanExitApp  
 Indique si l’application peut s’arrêter.  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’application peut s’arrêter ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Une application ne doit pas s’arrêter s’il existe des références en suspens à ses objets. Les fonctions globales `AfxOleLockApp` et `AfxOleUnlockApp` incrémenter ou décrémenter, respectivement, un compteur de références aux objets de l’application. L’application ne doit pas s’arrêter quand ce compteur est différent de zéro. Si le compteur est différente de zéro, fenêtre principale de l’application est masquée (pas détruite) lorsque l’utilisateur sélectionne Fermer dans le menu système ou quitter dans le menu fichier. L’infrastructure appelle cette fonction **CFrameWnd::OnClose**.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCAutomation n °&2;](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>Spécifications  
 **En-tête**: afxdisp.h 

##  <a name="a-nameafxolegetmessagefiltera--afxolegetmessagefilter"></a><a name="afxolegetmessagefilter"></a>AfxOleGetMessageFilter  
 Récupère le filtre de messages en cours de l’application.  
  
```   
COleMessageFilter* AFXAPI  AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le filtre de messages en cours.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour accéder à l’actuel `COleMessageFilter`-objet, dérivé comme vous appelleriez `AfxGetApp` pour accéder à l’objet d’application actuel.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCAutomation n °&3;](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation n °&4;](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête**: afxwin.h 

##  <a name="a-nameafxolegetuserctrla--afxolegetuserctrl"></a><a name="afxolegetuserctrl"></a>AfxOleGetUserCtrl  
 Récupère l’indicateur de contrôle de l’utilisateur actuel.  
  
```   
BOOL  AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’utilisateur est dans le contrôle de l’application ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 L’utilisateur est dans le contrôle de l’application lorsque l’utilisateur a explicitement ouvert ou créé un nouveau document. L’utilisateur est également dans le contrôle si l’application n’a pas démarrée par les DLL système OLE, en d’autres termes, si l’utilisateur a lancé l’application avec le shell du système.  

### <a name="requirements"></a>Spécifications  
 **En-tête**: afxdisp.h

##  <a name="a-nameafxolesetuserctrla--afxolesetuserctrl"></a><a name="afxolesetuserctrl"></a>AfxOleSetUserCtrl  
 Active ou désactive l’indicateur de contrôle utilisateur, qui est expliquée dans la référence pour `AfxOleGetUserCtrl`.  
  
```  
void  AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>Paramètres  
 *bUserCtrl*  
 Spécifie si l’indicateur de contrôle utilisateur doit être configurée ou désactivée.  
  
### <a name="remarks"></a>Notes  
 L’infrastructure appelle cette fonction lorsque l’utilisateur crée ou charge un document, mais pas lorsqu’un document est chargé ou créé via une action indirecte, telle que le chargement d’un objet incorporé à partir d’une application conteneur.  
  
 Appelez cette fonction si d’autres actions dans votre application doivent placer l’utilisateur dans le contrôle de l’application.  

### <a name="requirements"></a>Spécifications  
 **En-tête**: afxdisp.h

##  <a name="a-nameafxolelockappa--afxolelockapp"></a><a name="afxolelockapp"></a>AfxOleLockApp  
 Incrémente le nombre global de l’infrastructure du nombre d’objets actifs dans l’application.  
  
```   
void  AFXAPI  AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>Remarques  
 Le framework conserve un décompte du nombre d’objets actifs dans une application. Le `AfxOleLockApp` et `AfxOleUnlockApp` fonctions, respectivement, incrémenter ou décrémenter ce nombre.  
  
 Lorsque l’utilisateur tente de fermer une application qui a des objets actifs : une application pour laquelle le nombre d’objets actifs est différente de zéro, le framework masque l’application à partir de la vue de l’utilisateur au lieu de l’arrêter complètement. Le `AfxOleCanExitApp` fonction indique si l’application peut s’arrêter.  
  
 Appelez `AfxOleLockApp` à partir de n’importe quel objet qui expose les interfaces OLE, si elle serait pas souhaitable pour cet objet d’être détruites lors toujours utilisé par une application cliente. Appeler également `AfxOleUnlockApp` dans le destructeur de tout objet qui appelle `AfxOleLockApp` dans le constructeur. Par défaut, `COleDocument` (et les classes dérivées) automatiquement verrouiller et déverrouiller l’application.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCAutomation n °&5;](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête**: afxdisp.h

##  <a name="a-nameafxoleunlockappa--afxoleunlockapp"></a><a name="afxoleunlockapp"></a>AfxOleUnlockApp  
 Décrémente compte de l’infrastructure des objets actifs dans l’application.  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>Notes  
 Consultez `AfxOleLockApp` pour plus d’informations.  
  
 Lorsque le nombre d’objets actifs atteint zéro, **AfxOleOnReleaseAllObjects** est appelée.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [AfxOleLockApp](#afxolelockapp).  

### <a name="requirements"></a>Spécifications  
 **En-tête**: afxdisp.h  

##  <a name="a-nameafxoleregisterserverclassa--afxoleregisterserverclass"></a><a name="afxoleregisterserverclass"></a>AfxOleRegisterServerClass  
 Cette fonction permet d’enregistrer votre serveur dans le Registre du système OLE.  
  
```   
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszShortTypeName,  
    LPCTSTR lpszLongTypeName,  
    OLE_APPTYPE nAppType = OAT_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL); 
```  
  
### <a name="parameters"></a>Paramètres  
 `clsid`  
 Référence à l’ID de classe du serveur OLE  
  
 `lpszClassName`  
 Pointeur vers une chaîne contenant le nom de classe des objets du serveur.  
  
 *lpszShortTypeName*  
 Pointeur vers une chaîne contenant le nom court du type d’objet du serveur, tels que « Graphique ».  
  
 *lpszLongTypeName*  
 Pointeur vers une chaîne contenant le nom long du type d’objet du serveur, tels que « Graphique de Microsoft Excel 5.0 ».  
  
 `nAppType`  
 Une valeur extraite de la **OLE_APPTYPE** énumération qui spécifie le type d’application OLE. Les valeurs possibles sont les suivants :  
  
- `OAT_INPLACE_SERVER`Serveur a interface utilisateur complète du serveur.  
  
- `OAT_SERVER`Prend en charge uniquement l’incorporation.  
  
- `OAT_CONTAINER`Conteneur prend en charge les liaisons aux incorporations.  
  
- `OAT_DISPATCH_OBJECT``IDispatch`-objet compatible.  
  
 `rglpszRegister`  
 Tableau de pointeurs vers des chaînes représentant les clés et valeurs à ajouter si aucune valeur existante pour les clés ne se trouvent dans le Registre du système OLE.  
  
 `rglpszOverwrite`  
 Tableau de pointeurs vers des chaînes représentant les clés et valeurs à ajouter au Registre système OLE si le Registre contient des valeurs existantes pour les clés donnés.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la classe de serveur est inscrit avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 La plupart des applications peuvent utiliser **COleTemplateServer::Register** pour inscrire des types de documents de l’application. Si le format du Registre du système de votre application ne tient pas le modèle par défaut, vous pouvez utiliser `AfxOleRegisterServerClass` pour plus de contrôle.  
  
 Le Registre est constitué d’un ensemble de clés et valeurs. Le `rglpszRegister` et `rglpszOverwrite` arguments sont des tableaux de pointeurs vers des chaînes, composé d’une clé et la valeur séparés par un **NULL** caractère ( `'\0'`). Chacune de ces chaînes peut avoir des paramètres remplaçables dont les emplacements sont marqués par les séquences de caractères `%1` via `%5`.  
  
 Les symboles sont renseignés comme suit :  
  
|Symbole|Valeur|  
|------------|-----------|  
|%1|ID de classe, sous formaté de chaîne|  
|%2|Nom de classe|  
|%3|Chemin d’accès au fichier exécutable|  
|%4|Nom de type court|  
|%5|Nom de type long|  

### <a name="requirements"></a>Spécifications  
 **En-tête**: afxdisp.h

##  <a name="a-nameafxoleseteditmenua--afxoleseteditmenu"></a><a name="afxoleseteditmenu"></a>AfxOleSetEditMenu  
 Implémente l’interface utilisateur pour le *typename* commande de l’objet.  
  
```   
void  AFXAPI  AfxOleSetEditMenu(
    COleClientItem* pClient,  
    CMenu* pMenu,  
    UINT iMenuItem,  
    UINT nIDVerbMin,  
    UINT nIDVerbMax = 0,  
    UINT nIDConvert = 0); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pClient`  
 Pointeur vers l’élément OLE de client.  
  
 `pMenu`  
 Pointeur vers l’objet menu mise à jour.  
  
 *iMenuItem*  
 Index de l’élément de menu à mettre à jour.  
  
 `nIDVerbMin`  
 L’ID de commande qui correspond au verbe principal.  
  
 *nIDVerbMax*  
 L’ID de commande qui correspond au dernier verbe.  
  
 *nIDConvert*  
 ID de l’élément de menu convertir.  
  
### <a name="remarks"></a>Notes  
 Si le serveur reconnaît uniquement un verbe principal, l’élément de menu devienne « verbe *typename* objet » et le `nIDVerbMin` commande est envoyée lorsque l’utilisateur sélectionne la commande. Si le serveur reconnaît plusieurs verbes, alors que l’élément de menu devienne « *typename* objet » et un sous-menu répertoriant tous les verbes s’affiche lorsque l’utilisateur sélectionne la commande. Lorsque l’utilisateur choisit un verbe dans le sous-menu, `nIDVerbMin` est envoyé si la première action est choisie, `nIDVerbMin` + 1 est envoyée si la deuxième action choisie et ainsi de suite. La valeur par défaut `COleDocument` implémentation gère automatiquement cette fonctionnalité.  
  
 Vous devez disposer de l’instruction suivante dans le script de ressources d’application de votre client (. Fichier RC) :  
  
 **#include \<afxolecl.rc >**  

### <a name="requirements"></a>Spécifications  
 **En-tête**: afxole.h 

## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

