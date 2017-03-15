---
title: Classe de CConnectionPoint | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- CConnectionPoint class
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
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
ms.openlocfilehash: a511f252bf921433d070059518e6e67b952680eb
ms.lasthandoff: 02/24/2017

---
# <a name="cconnectionpoint-class"></a>Classe de CConnectionPoint
Définit un type particulier d'interface utilisé pour communiquer avec d'autres objets OLE, appelé « point de connexion ».  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CConnectionPoint : public CCmdTarget  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|Construit un objet `CConnectionPoint`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CConnectionPoint::GetConnections](#getconnections)|Récupère tous les points de connexion dans un mappage de connexions.|  
|[CConnectionPoint::GetContainer](#getcontainer)|Récupère le conteneur du contrôle qui possède le mappage de connexions.|  
|[CConnectionPoint::GetIID](#getiid)|Récupère l’ID d’interface d’un point de connexion.|  
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|Récupère le nombre maximal de points de connexion pris en charge par un contrôle.|  
|[CConnectionPoint::GetNextConnection](#getnextconnection)|Récupère un pointeur vers l’élément de connexion à `pos`.|  
|[CConnectionPoint::GetStartPosition](#getstartposition)|Démarre une itération de la carte en retournant un **POSITION** valeur qui peut être passé à un `GetNextConnection` appeler.|  
|[CConnectionPoint::OnAdvise](#onadvise)|Appelé par l’infrastructure lors de l’établissement ou l’arrêt d’une connexion.|  
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|Récupère un pointeur vers l’interface du récepteur demandé.|  
  
## <a name="remarks"></a>Remarques  
 Contrairement aux interfaces OLE normales, qui servent à implémenter et d’exposer les fonctionnalités d’un contrôle OLE, un point de connexion implémente une interface sortante qui est en mesure de lancer des actions sur d’autres objets, tels que le déclenchement d’événements et notifications de modification.  
  
 Une connexion se compose de deux parties : l’objet qui appelle l’interface, appelé la « source » et l’objet qui implémente l’interface, appelé « récepteur ». En exposant un point de connexion, une source permet à des récepteurs d’établir des connexions à elle-même. Via le mécanisme de point de connexion, un objet source Obtient un pointeur vers l’implémentation du récepteur d’un ensemble de fonctions membres. Par exemple, pour déclencher un événement implémenté par le récepteur, la source peut appeler la méthode appropriée de l'implémentation du récepteur.  
  
 Par défaut, un `COleControl`-classe dérivée implémente deux points de connexion : notifications de modification d’un des événements et un pour la propriété. Ces connexions sont utilisées, respectivement, de déclenchement d’événement et pour avertir un récepteur (par exemple, le conteneur du contrôle) lorsqu’une valeur de propriété a changé. Prise en charge est également fournie pour les contrôles OLE implémenter des points de connexion supplémentaires. Pour chaque point de connexion implémenté dans votre classe de contrôle, vous devez déclarer un élément de connexion » » qui implémente le point de connexion. Si vous implémentez un ou plusieurs points de connexion, vous devez également déclarer une seule « mappage de connexions » dans votre classe de contrôle.  
  
 Suivant illustre un mappage de connexions simple et un point de connexion pour le `Sample` contrôle OLE, composé de deux fragments de code : la première partie déclare le mappage de connexions et le point ; le second implémente cette carte et le point. Le premier fragment est inséré dans la déclaration de la classe de contrôle, sous la `protected` section :  
  
 [!code-cpp[NVC_MFCConnectionPoints&#7;](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]  
  
 Le `BEGIN_CONNECTION_PART` et `END_CONNECTION_PART` déclarent une classe incorporée, `XSampleConnPt` (dérivée de `CConnectionPoint`) qui implémente ce point de connexion particulier. Si vous souhaitez remplacer toutes les `CConnectionPoint` les fonctions membres, ou ajouter vos propres fonctions membres, déclarez-les entre ces deux macros. Par exemple, la macro `CONNECTION_IID` remplace la fonction membre `CConnectionPoint::GetIID` lorsqu'elle est placée entre ces deux macros.  
  
 Le deuxième fragment de code est inséré dans le fichier d’implémentation (. (CPP) de votre classe de contrôle. Ce code implémente le mappage de connexions, qui inclut le point de connexion supplémentaires, `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints n °&2;](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]  
  
 Une fois ces fragments de code ont été insérées, le contrôle OLE exemple expose un point de connexion pour le **ISampleSink** interface.  
  
 En règle générale, les points de connexion prennent en charge la « multidiffusion », qui est la possibilité de distribution à plusieurs récepteurs connectés à la même interface. Le fragment de code suivant montre comment accomplir la multidiffusion en parcourant chaque destinataire sur un point de connexion :  
  
 [!code-cpp[NVC_MFCConnectionPoints n °&4;](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
 Cet exemple récupère l'ensemble actuel de connexions sur le point de connexion `SampleConnPt` par un appel à `CConnectionPoint::GetConnections`. Il parcourt ensuite les connexions et appelle `ISampleSink::SinkFunc` sur chaque connexion active.  
  
 Pour plus d’informations sur l’utilisation de `CConnectionPoint`, consultez l’article [Points de connexion](../../mfc/connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdisp.h  
  
##  <a name="a-namecconnectionpointa--cconnectionpointcconnectionpoint"></a><a name="cconnectionpoint"></a>CConnectionPoint::CConnectionPoint  
 Construit un objet `CConnectionPoint`.  
  
```  
CConnectionPoint();
```  
  
##  <a name="a-namegetconnectionsa--cconnectionpointgetconnections"></a><a name="getconnections"></a>CConnectionPoint::GetConnections  
 Appelez cette fonction pour récupérer toutes les connexions actives pour un point de connexion.  
  
```  
const CPtrArray* GetConnections();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un tableau de connexions actives (récepteurs). Certaines des pointeurs dans le tableau peuvent être NULL. Chaque pointeur non NULL dans ce tableau peut être converti en toute sécurité vers un pointeur vers l’interface du récepteur à l’aide d’un opérateur de conversion.  
  
##  <a name="a-namegetcontainera--cconnectionpointgetcontainer"></a><a name="getcontainer"></a>CConnectionPoint::GetContainer  
 Appelé par l’infrastructure pour récupérer le **IConnectionPointContainer** du point de connexion.  
  
```  
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’opération réussit, un pointeur vers le conteneur ; dans le cas contraire **NULL**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est généralement implémentée par le `BEGIN_CONNECTION_PART` (macro).  
  
##  <a name="a-namegetiida--cconnectionpointgetiid"></a><a name="getiid"></a>CConnectionPoint::GetIID  
 Appelée par l’infrastructure pour extraire l’ID d’interface d’un point de connexion.  
  
```  
virtual REFIID GetIID() = 0;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à l’ID d’interface. du point de connexion  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction pour retourner l’ID de ce point de connexion.  
  
##  <a name="a-namegetmaxconnectionsa--cconnectionpointgetmaxconnections"></a><a name="getmaxconnections"></a>CConnectionPoint::GetMaxConnections  
 Appelé par l’infrastructure pour récupérer le nombre maximal de connexions prises en charge par le point de connexion.  
  
```  
virtual int GetMaxConnections();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre maximal de connexions prises en charge par le contrôle, ou -1 si aucune limite.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut retourne -1, n’indiquant aucune limite.  
  
 Remplacez cette fonction si vous souhaitez limiter le nombre de récepteurs qui peuvent se connecter à votre contrôle.  
  
##  <a name="a-namegetnextconnectiona--cconnectionpointgetnextconnection"></a><a name="getnextconnection"></a>CConnectionPoint::GetNextConnection  
 Récupère un pointeur vers l’élément de connexion à `pos`.  
  
```  
LPUNKNOWN GetNextConnection(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pos`  
 Spécifie une référence à un **POSITION** valeur retournée par une précédente `GetNextConnection` ou [GetStartPosition](#getstartposition) appeler.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément de connexion spécifié par `pos`, ou NULL.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est particulièrement utile pour l’itération sur tous les éléments dans le mappage de connexions. Lors d’une itération, ignorer toutes les valeurs NULL retournées par cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCConnectionPoints n °&4;](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
##  <a name="a-namegetstartpositiona--cconnectionpointgetstartposition"></a><a name="getstartposition"></a>CConnectionPoint::GetStartPosition  
 Démarre une itération de la carte en retournant un **POSITION** valeur qui peut être passé à un [GetNextConnection](#getnextconnection) appeler.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **POSITION** valeur qui indique la position de départ pour l’itération de la carte ; ou **NULL** si le mappage est vide.  
  
### <a name="remarks"></a>Remarques  
 La séquence d’itération n’est pas prévisible ; Par conséquent, le « premier élément de la carte » n’a aucune signification spéciale.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CConnectionPoint::GetNextConnection](#getnextconnection).  
  
##  <a name="a-nameonadvisea--cconnectionpointonadvise"></a><a name="onadvise"></a>CConnectionPoint::OnAdvise  
 Appelé par l’infrastructure lorsqu’une connexion est établie ou interrompue.  
  
```  
virtual void OnAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>Paramètres  
 `bAdvise`  
 **TRUE**, si une connexion est établie ; sinon **FALSE**.  
  
### <a name="remarks"></a>Notes  
 L'implémentation par défaut n'exécute aucune opération.  
  
 Remplacez cette fonction si vous souhaitez une notification lorsque les récepteurs de connecter ou déconnecter votre point de connexion.  
  
##  <a name="a-namequerysinkinterfacea--cconnectionpointquerysinkinterface"></a><a name="querysinkinterface"></a>CConnectionPoint::QuerySinkInterface  
 Récupère un pointeur vers l’interface du récepteur demandé.  
  
```  
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,  
    void** ppInterface);
```  
  
### <a name="parameters"></a>Paramètres  
 `pUnkSink`  
 Identificateur de l’interface du récepteur demandé.  
  
 `ppInterface`  
 Un pointeur vers le pointeur d’interface identifié par `pUnkSink`. Si l’objet ne prend pas en charge cette interface, \* `ppInterface` a **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
## <a name="see-also"></a>Voir aussi  
 [CCmdTarget (classe)](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)


