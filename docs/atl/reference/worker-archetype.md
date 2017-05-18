---
title: "Archétype de travail | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
caps.latest.revision: 16
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
ms.openlocfilehash: 046160644cca3bd23e4293a3c52692d2b4c94cd5
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="worker-archetype"></a>Archétype de travail
Les classes qui se conforment à la *travail* archétype fournissent le code pour traiter des éléments de travail en file d’attente sur un pool de threads.  
  
 **Mise en œuvre**  
  
 Pour implémenter une classe conforme à cette archétype, la classe doit fournir les fonctionnalités suivantes :  
  
|Méthode|Description|  
|------------|-----------------|  
|[Initialiser](#initialize)|Appelée pour initialiser l’objet de travail avant que toutes les demandes sont transmises à [Execute](#execute).|  
|[Exécuter](#execute)|Appelée pour traiter un élément de travail.|  
|[Arrêter](#terminate)|Appelé pour annuler l’initialisation de l’objet de travail une fois que toutes les demandes qui ont été transmis au [Execute](#execute).|  
  
|TypeDef|Description|  
|-------------|-----------------|  
|[RequestType](#requesttype)|Typedef pour le type d’élément de travail qui peut être traité par la classe de travail.|  
  
 Par défaut *travail* classe ressemble à ceci :  
  
 [!code-cpp[NVC_ATL_Utilities&#137;](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **Implémentations existantes**  
  
 Ces classes sont conformes à cette archétype :  
  
|Classe|Description|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Reçoit les demandes du pool de threads et les transmet à un objet de travail qui est créé et détruit pour chaque demande.|  
  
 **Utilisation**  
  
 Ces paramètres de modèle que la classe conforme à cette archétype :  
  
|Nom du paramètre|Utilisé par|  
|--------------------|-------------|  
|*Travail*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*Travail*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** atlutil.h  
  
## <a name="execute"></a>WorkerArchetype::Execute
Appelée pour traiter un élément de travail.  
  
  
  
```  
void Execute(
    RequestType request,  
    void* pvWorkerParam,  
    OVERLAPPED* pOverlapped);
```  
  
#### <a name="parameters"></a>Paramètres  
 `request`  
 L’élément de travail à traiter. L’élément de travail est du même type que `RequestType`.  
  
 `pvWorkerParam`  
 Un paramètre personnalisé compris par la classe de travail. Également transmis à `WorkerArchetype::Initialize` et `Terminate`.  
  
 `pOverlapped`  
 Un pointeur vers le [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) structure utilisée pour créer la file d’attente à laquelle les éléments ont été en file d’attente.  
  
## <a name="initialize"></a>WorkerArchetype::Initialize
Appelée pour initialiser l’objet de travail avant que toutes les demandes sont transmises à `WorkerArchetype::Execute`.  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Paramètres  
 `pvParam`  
 Un paramètre personnalisé compris par la classe de travail. Également transmis à `WorkerArchetype::Terminate` et `WorkerArchetype::Execute`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourner **TRUE** en cas de réussite, **FALSE** en cas d’échec.  
  
## <a name="requesttype"></a>WorkerArchetype::RequestType
Typedef pour le type d’élément de travail qui peut être traité par la classe de travail.  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>Remarques  
 Ce type doit être utilisé comme premier paramètre de `WorkerArchetype::Execute` et doit pouvoir être casté vers et depuis un ULONG_PTR entière.  
  
## <a name="terminate"></a>WorkerArchetype::Terminate
Appelé pour annuler l’initialisation de l’objet de travail une fois que toutes les demandes qui ont été transmis au `WorkerArchetype::Execute`).  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Paramètres  
 `pvParam`  
 Un paramètre personnalisé compris par la classe de travail. Également transmis à `WorkerArchetype::Initialize` et `WorkerArchetype::Execute`.  
  
## <a name="see-also"></a>Voir aussi  
 [Archétypes](../../atl/reference/atl-archetypes.md)   
 [Concepts](../../atl/active-template-library-atl-concepts.md)   
 [Composants COM bureau ATL](../../atl/atl-com-desktop-components.md)




