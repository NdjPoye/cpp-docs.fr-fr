---
title: "AsyncBase, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncBase (classe)"
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Implémente la machine à état asynchrone du Windows Runtime.  
  
## Syntaxe  
  
```  
  
template <  
   typename TComplete,  
   typename TProgress = Details::Nil,  
   AsyncResultType resultType = SingleResult  
>  
class AsyncBase : public AsyncBase< TComplete, Details::Nil, resultType >;  
  
template <  
   typename TComplete,  
   AsyncResultType resultType  
>  
class AsyncBase< TComplete, Details::Nil, resultType > : public Microsoft::WRL::Implements< IAsyncInfo >;  
```  
  
#### Paramètres  
 `TComplete`  
 Un gestionnaire d'évènements appelé lorsqu'une opération asynchrone se termine.  
  
 `TProgress`  
 Un gestionnaire d'événements appelé lorsqu'une opération asynchrone en cours d'exécution signale le déroulement actuel de l'exécution.  
  
 `resultType`  
 Une des valeurs de l'énumération [AsyncResultType](../windows/asyncresulttype-enumeration.md).  Par défaut, SingleResult.  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[AsyncBase::AsyncBase, constructeur](../windows/asyncbase-asyncbase-constructor.md)|Initialise une instance de la classe AsyncBase.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[AsyncBase::Cancel, méthode](../windows/asyncbase-cancel-method.md)|Annule une opération asynchrone.|  
|[AsyncBase::Close, méthode](../windows/asyncbase-close-method.md)|Ferme l'opération asynchrone.|  
|[AsyncBase::FireCompletion, méthode](../windows/asyncbase-firecompletion-method.md)|Appelle le gestionnaire d'événements de complétion, ou réinitialise le délégué interne de progression.|  
|[AsyncBase::FireProgress, méthode](../windows/asyncbase-fireprogress-method.md)|Appelle le gestionnaire d'événements de progression actuel.|  
|[AsyncBase::get\_ErrorCode, méthode](../windows/asyncbase-get-errorcode-method.md)|Récupère le code d'erreur pour l'opération asynchrone en cours.|  
|[AsyncBase::get\_Id, méthode](../windows/asyncbase-get-id-method.md)|Récupère le handle de l'opération asynchrone.|  
|[AsyncBase::get\_Status, méthode](../windows/asyncbase-get-status-method.md)|Récupère une valeur indiquant l'état de l'opération asynchrone.|  
|[AsyncBase::GetOnComplete, méthode](../windows/asyncbase-getoncomplete-method.md)|Copie l'adresse du gestionnaire d'événements de complétion actuel vers la variable spécifiée.|  
|[AsyncBase::GetOnProgress, méthode](../windows/asyncbase-getonprogress-method.md)|Copie l'adresse du gestionnaire d'événements de progression actuel vers la variable spécifiée.|  
|[AsyncBase::put\_Id, méthode](../windows/asyncbase-put-id-method.md)|Définit le handle de l'opération asynchrone.|  
|[AsyncBase::PutOnComplete, méthode](../windows/asyncbase-putoncomplete-method.md)|Définit l'adresse du gestionnaire d'événement de complétion à la valeur spécifiée.|  
|[AsyncBase::PutOnProgress, méthode](../windows/asyncbase-putonprogress-method.md)|Définit l'adresse du gestionnaire d'événement de progression à la valeur spécifiée.|  
|[AsyncBase::Start, méthode](../windows/asyncbase-start-method.md)|Démarre l'opération asynchrone.|  
  
### Méthodes protégées  
  
|Name|Description|  
|----------|-----------------|  
|[AsyncBase::CheckValidStateForDelegateCall, méthode](../windows/asyncbase-checkvalidstatefordelegatecall-method.md)|Teste si les propriétés de délégués peuvent être modifiées dans l'état asynchrone en cours.|  
|[AsyncBase::CheckValidStateForResultsCall, méthode](../windows/asyncbase-checkvalidstateforresultscall-method.md)|Teste si les résultats d'une opération asynchrone peuvent être collectés dans l'état asynchrone en cours.|  
|[AsyncBase::ContinueAsyncOperation, méthode](../windows/asyncbase-continueasyncoperation-method.md)|Détermine si l'opération asynchrone doit continuer ou doit s'arrêter.|  
|[AsyncBase::CurrentStatus, méthode](../windows/asyncbase-currentstatus-method.md)|Récupère l'état de l'opération asynchrone actuelle.|  
|[AsyncBase::ErrorCode, méthode](../windows/asyncbase-errorcode-method.md)|Récupère le code d'erreur pour l'opération asynchrone en cours.|  
|[AsyncBase::OnCancel, méthode](../windows/asyncbase-oncancel-method.md)|En cas de substitution dans une classe dérivée, annule une opération asynchrone.|  
|[AsyncBase::OnClose, méthode](../windows/asyncbase-onclose-method.md)|En cas de substitution dans une classe dérivée, annule une opération asynchrone.|  
|[AsyncBase::OnStart, méthode](../windows/asyncbase-onstart-method.md)|En cas de substitution dans une classe dérivée, démarre une opération asynchrone.|  
|[AsyncBase::TryTransitionToCompleted, méthode](../windows/asyncbase-trytransitiontocompleted-method.md)|Indique si l'opération asynchrone en cours est terminée.|  
|[AsyncBase::TryTransitionToError, méthode](../windows/asyncbase-trytransitiontoerror-method.md)|Indique si le code d'erreur spécifié peut modifier l'état d'erreur interne.|  
  
## Hiérarchie d'héritage  
 `AsyncBase`  
  
 `AsyncBase`  
  
## Configuration requise  
 **En\-tête:** async.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)