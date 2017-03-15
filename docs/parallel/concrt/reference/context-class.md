---
title: Classe du contexte | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::Context
dev_langs:
- C++
helpviewer_keywords:
- Context class
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 11d8252afdfe9c02869b14f976f8f348513c46b8
ms.lasthandoff: 02/24/2017

---
# <a name="context-class"></a>Context, classe
Représente une abstraction pour un contexte d'exécution.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class Context;
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[~ Context, destructeur](#dtor)||  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Block (méthode)](#block)|Bloque le contexte actuel.|  
|[CurrentContext (méthode)](#currentcontext)|Retourne un pointeur vers le contexte actuel.|  
|[GetId (méthode)](#getid)|Retourne un identificateur pour le contexte qui est unique dans le planificateur auquel le contexte appartient.|  
|[GetScheduleGroupId (méthode)](#getschedulegroupid)|Retourne un identificateur pour le groupe de planification qui le contexte fonctionne actuellement.|  
|[GetVirtualProcessorId (méthode)](#getvirtualprocessorid)|Retourne un identificateur pour le processeur virtuel sur lequel le contexte s’exécute actuellement.|  
|[ID (méthode)](#id)|Retourne un identificateur pour le contexte actuel qui est unique dans le planificateur auquel le contexte actuel appartient.|  
|[IsCurrentTaskCollectionCanceling (méthode)](#iscurrenttaskcollectioncanceling)|Retourne une indication précisant si la collection de tâches qui s’exécute actuellement inline sur le contexte actuel est en cours d’annulation (ou sera bientôt).|  
|[IsSynchronouslyBlocked (méthode)](#issynchronouslyblocked)|Détermine si le contexte est bloqué de façon synchrone. Un contexte est considéré pour être bloqué de façon synchrone s’il a exécuté explicitement une action qui a mené au blocage.|  
|[Oversubscribe (méthode)](#oversubscribe)|Injecte un processeur virtuel supplémentaire dans un planificateur pour la durée d’un bloc de code lorsqu’elle est appelée sur un contexte s’exécutant sur un des processeurs virtuels dans ce planificateur.|  
|[ScheduleGroupId (méthode)](#schedulegroupid)|Retourne un identificateur pour le groupe de planification qui fonctionne sur le contexte actuel.|  
|[Unblock (méthode)](#unblock)|Débloque le contexte et le rend exécutable.|  
|[VirtualProcessorId (méthode)](#virtualprocessorid)|Retourne un identificateur pour le processeur virtuel sur lequel le contexte actuel s’exécute.|  
|[Yield (méthode)](#yield)|Produit l'exécution pour qu'un autre contexte puisse s'exécuter. Si aucun autre contexte n'est disponible pour la production, le planificateur peut produire dans un autre thread du système d'exploitation.|  
  
## <a name="remarks"></a>Remarques  
 Le Planificateur de Runtime d’accès concurrentiel (voir [planificateur](scheduler-class.md)) utilise des contextes d’exécution pour exécuter le travail en file d’attente à celle-ci par votre application. Un thread Win32 est un exemple d’un contexte d’exécution sur un système d’exploitation.  
  
 À tout moment, le niveau d’accès concurrentiel d’un planificateur est égal au nombre de processeurs virtuels lui accordée par le Gestionnaire de ressources. Un processeur virtuel est une abstraction pour une ressource de traitement et est mappé à un thread matériel sur le système sous-jacent. Seulement un contexte de planificateur unique peut s’exécuter sur un processeur virtuel à un moment donné.  
  
 Le planificateur est coopératif par nature et un contexte d’exécution peut conduire son processeur virtuel dans un contexte différent à tout moment s’il souhaite entrer dans un état d’attente. Lors de l’issue de l’attente, il ne peut pas reprendre jusqu'à ce qu’un processeur virtuel disponible dans le planificateur commence son exécution.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `Context`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameblocka-block"></a><a name="block"></a>Bloc 

 Bloque le contexte actuel.  
  
```
static void __cdecl Block();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode entraîne la création du planificateur par défaut du processus et/ou son attachement au contexte d'appel s'il n'existe aucun planificateur actuellement associé au contexte d'appel.  
  
 Si le contexte d’appel s’exécute sur un processeur virtuel, le processeur virtuel trouve un autre contexte exécutable à exécuter ou peut potentiellement créer un nouveau.  
  
 Après le `Block` méthode a été appelée ou sera appelée, vous devez la coupler avec un appel à la [Unblock](#unblock) méthode à partir d’un autre contexte d’exécution pour qu’il puisse exécuter à nouveau. N’oubliez pas qu’il existe une période critique entre le moment où votre code publie son contexte d’un autre thread pouvoir appeler le `Unblock` (méthode) et le point où la méthode réelle appel à `Block` est effectuée. Pendant cette période, vous ne devez appeler une méthode qui peut bloquer et débloquer pour des raisons de son propre (par exemple, d’acquérir un verrou). Les appels à la `Block` et `Unblock` méthode ne suivent pas la raison du blocage et déblocage. Un seul objet doit être propriétaire d’un `Block` -  `Unblock` paire.  
  
 Cette méthode peut lever diverses exceptions, notamment [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md).  
  
##  <a name="a-namedtora-context"></a><a name="dtor"></a>~ Contexte 

```
virtual ~Context();
```  
  
##  <a name="a-namecurrentcontexta-currentcontext"></a><a name="currentcontext"></a>CurrentContext 

 Retourne un pointeur vers le contexte actuel.  
  
```
static Context* __cdecl CurrentContext();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le contexte actuel.  
  
### <a name="remarks"></a>Notes  
 Cette méthode entraîne la création du planificateur par défaut du processus et/ou son attachement au contexte d'appel s'il n'existe aucun planificateur actuellement associé au contexte d'appel.  
  
##  <a name="a-namegetida-getid"></a><a name="getid"></a>GetId 

 Retourne un identificateur pour le contexte qui est unique dans le planificateur auquel le contexte appartient.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Identificateur du contexte qui est unique dans le planificateur auquel le contexte appartient.  
  
##  <a name="a-namegetschedulegroupida-getschedulegroupid"></a><a name="getschedulegroupid"></a>GetScheduleGroupId 

 Retourne un identificateur pour le groupe de planification qui le contexte fonctionne actuellement.  
  
```
virtual unsigned int GetScheduleGroupId() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un identificateur pour le contexte travaille actuellement sur le groupe de planification.  
  
### <a name="remarks"></a>Remarques  
 La valeur de retour de cette méthode est un échantillonnage instantané du groupe de planification qui le contexte s’exécute. Si cette méthode est appelée sur un contexte autre que le contexte actuel, la valeur peut être obsolète au moment où elle est retournée et ne peut pas être fiables. En règle générale, cette méthode est utilisée pour le débogage ou uniquement à des fins de suivi.  
  
##  <a name="a-namegetvirtualprocessorida-getvirtualprocessorid"></a><a name="getvirtualprocessorid"></a>GetVirtualProcessorId 

 Retourne un identificateur pour le processeur virtuel sur lequel le contexte s’exécute actuellement.  
  
```
virtual unsigned int GetVirtualProcessorId() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si le contexte est en cours d’exécution sur un processeur virtuel, un identificateur pour le processeur virtuel sur lequel le contexte s’exécute actuellement. dans le cas contraire, la valeur `-1`.  
  
### <a name="remarks"></a>Remarques  
 La valeur de retour de cette méthode est un échantillonnage instantané du processeur virtuel sur lequel le contexte s’exécute. Cette valeur peut être obsolète au moment où elle est retournée et ne peut pas être fiables. En règle générale, cette méthode est utilisée pour le débogage ou uniquement à des fins de suivi.  
  
##  <a name="a-nameida-id"></a><a name="id"></a>ID 

 Retourne un identificateur pour le contexte actuel qui est unique dans le planificateur auquel le contexte actuel appartient.  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si le contexte actuel est associé à un planificateur, un identificateur pour le contexte actuel qui est unique dans le planificateur auquel le contexte actuel appartient ; dans le cas contraire, la valeur `-1`.  
  
##  <a name="a-nameiscurrenttaskcollectioncancelinga-iscurrenttaskcollectioncanceling"></a><a name="iscurrenttaskcollectioncanceling"></a>IsCurrentTaskCollectionCanceling 

 Retourne une indication précisant si la collection de tâches qui s’exécute actuellement inline sur le contexte actuel est en cours d’annulation (ou sera bientôt).  
  
```
static bool __cdecl IsCurrentTaskCollectionCanceling();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si un planificateur est associé au contexte d’appel et un groupe de tâches exécute une tâche inline sur ce contexte, une indication précisant si ce groupe de tâches est en cours d’annulation (ou sera bientôt) ; dans le cas contraire, la valeur `false`.  
  
##  <a name="a-nameissynchronouslyblockeda-issynchronouslyblocked"></a><a name="issynchronouslyblocked"></a>IsSynchronouslyBlocked 

 Détermine si le contexte est bloqué de façon synchrone. Un contexte est considéré pour être bloqué de façon synchrone s’il a exécuté explicitement une action qui a mené au blocage.  
  
```
virtual bool IsSynchronouslyBlocked() const = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si le contexte est bloqué de façon synchrone.  
  
### <a name="remarks"></a>Notes  
 Un contexte est considéré pour être bloqué de façon synchrone s’il a exécuté explicitement une action qui a mené au blocage. Dans le Planificateur de thread, cela indique un appel direct à la `Context::Block` méthode ou un objet de synchronisation qui a été créé à l’aide de la `Context::Block` méthode.  
  
 La valeur de retour de cette méthode est un échantillonnage instantané montrant si le contexte est bloqué de façon synchrone. Cette valeur peut être périmée au moment où elle est retournée et peut uniquement être utilisé dans des circonstances très spécifiques.  
  
##  <a name="a-nameoperatordeletea-operator-delete"></a><a name="operator_delete"></a>opérateur delete 

 Un `Context` est détruit en interne par le runtime. Il ne peut pas être explicitement supprimé.  
  
```
void operator delete(void* _PObject);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PObject`  
 Pointeur vers l’objet à supprimer.  
  
##  <a name="a-nameoversubscribea-oversubscribe"></a><a name="oversubscribe"></a>Oversubscribe) 

 Injecte un processeur virtuel supplémentaire dans un planificateur pour la durée d’un bloc de code lorsqu’elle est appelée sur un contexte s’exécutant sur un des processeurs virtuels dans ce planificateur.  
  
```
static void __cdecl Oversubscribe(bool _BeginOversubscription);
```  
  
### <a name="parameters"></a>Paramètres  
 `_BeginOversubscription`  
 Si `true`, une indication qu’un processeur virtuel supplémentaire doit être ajouté pour la durée du surabonnement. Si `false`, indique que le surabonnement doit se terminer et que le processeur virtuel ajouté précédemment doit être supprimé.  
  
##  <a name="a-nameschedulegroupida-schedulegroupid"></a><a name="schedulegroupid"></a>ScheduleGroupId 

 Retourne un identificateur pour le groupe de planification qui fonctionne sur le contexte actuel.  
  
```
static unsigned int __cdecl ScheduleGroupId();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si le contexte actuel est associé à un planificateur et travaillez sur un groupe de planification, un identificateur pour le Planificateur de groupe qui le contexte actuel fonctionne ; dans le cas contraire, la valeur `-1`.  
  
##  <a name="a-nameunblocka-unblock"></a><a name="unblock"></a>Débloquer 

 Débloque le contexte et le rend exécutable.  
  
```
virtual void Unblock() = 0;
```  
  
### <a name="remarks"></a>Notes  
 Il est parfaitement légal pour un appel à la `Unblock` méthode précèdent un appel correspondant à la [bloc](#block) méthode. Tant que les appels à la `Block` et `Unblock` méthodes sont appariés correctement, le runtime gère correctement le naturel des deux ordres. Un `Unblock` appel avant une `Block` appel annule simplement l’effet de la `Block` appeler.  
  
 Il existe plusieurs exceptions peuvent être levées par cette méthode. Si un contexte essaie d’appeler le `Unblock` méthode sur lui-même, un [context_self_unblock](context-self-unblock-class.md) exception sera levée. Si les appels à `Block` et `Unblock` ne sont pas correctement associés (par exemple, deux appels à `Unblock` sont effectuées pour un contexte qui est en cours d’exécution), un [context_unblock_unbalanced](context-unblock-unbalanced-class.md) exception sera levée.  
  
 N’oubliez pas qu’il existe une période critique entre le moment où votre code publie son contexte d’un autre thread pouvoir appeler le `Unblock` (méthode) et le point où la méthode réelle appel à `Block` est effectuée. Pendant cette période, vous ne devez appeler une méthode qui peut bloquer et débloquer pour des raisons de son propre (par exemple, d’acquérir un verrou). Les appels à la `Block` et `Unblock` méthode ne suivent pas la raison du blocage et déblocage. Un seul objet doit être propriétaire d’un `Block` et `Unblock` paire.  
  
##  <a name="a-namevirtualprocessorida-virtualprocessorid"></a><a name="virtualprocessorid"></a>VirtualProcessorId 

 Retourne un identificateur pour le processeur virtuel sur lequel le contexte actuel s’exécute.  
  
```
static unsigned int __cdecl VirtualProcessorId();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si le contexte actuel est associé à un planificateur, un identificateur pour le processeur virtuel sur lequel le contexte actuel s’exécute ; dans le cas contraire, la valeur `-1`.  
  
### <a name="remarks"></a>Remarques  
 La valeur de retour de cette méthode est un échantillonnage instantané du processeur virtuel sur lequel le contexte actuel s’exécute. Cette valeur peut être obsolète au moment où elle est retournée et ne peut pas être fiables. En règle générale, cette méthode est utilisée pour le débogage ou uniquement à des fins de suivi.  
  
##  <a name="a-nameyielda-yield"></a><a name="yield"></a>Rendement 

 Produit l'exécution pour qu'un autre contexte puisse s'exécuter. Si aucun autre contexte n'est disponible pour la production, le planificateur peut produire dans un autre thread du système d'exploitation.  
  
```
static void __cdecl Yield();
```  
  
### <a name="remarks"></a>Remarques  
 Cette méthode entraîne la création du planificateur par défaut du processus et/ou son attachement au contexte d'appel s'il n'existe aucun planificateur actuellement associé au contexte d'appel.  
  
##  <a name="a-nameyieldexecutiona-yieldexecution"></a><a name="yieldexecution"></a>YieldExecution 

 Produit l'exécution pour qu'un autre contexte puisse s'exécuter. Si aucun autre contexte n'est disponible pour la production, le planificateur peut produire dans un autre thread du système d'exploitation.  
  
```
static void __cdecl YieldExecution();
```  
  
### <a name="remarks"></a>Remarques  
 Cette méthode entraîne la création du planificateur par défaut du processus et/ou son attachement au contexte d'appel s'il n'existe aucun planificateur actuellement associé au contexte d'appel.  
  
 Cette fonction est une nouveauté de [!INCLUDE[vs_dev14](../../../ide/includes/vs_dev14_md.md)] et est identique à la [Yield](#yield) de fonctionner mais n’est pas en conflit avec la macro Yield de Windows.h.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [Scheduler (classe)](scheduler-class.md)   
 [Planificateur de tâches](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




